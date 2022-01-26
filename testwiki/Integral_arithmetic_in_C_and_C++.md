# Integral arithmetic in C and C

## Unsigned comparison, and `std::abs()` ambiguity

There are [clear rules in C](http://en.cppreference.com/w/cpp/language/operator_arithmetic), which are not always intuitive, about what type comes out of arithmetic operations between different types. Some are listed in this table:

|                 *op1*                 |                 *op2*                 |             *op1* + *op2*             |
|:-------------------------------------:|:-------------------------------------:|:-------------------------------------:|
|     <code class="cpp">int</code>      |     <code class="cpp">int</code>      |     <code class="cpp">int</code>      |
| <code class="cpp">unsigned int</code> | <code class="cpp">unsigned int</code> | <code class="cpp">unsigned int</code> |
| <code class="cpp">unsigned int</code> |     <code class="cpp">int</code>      | <code class="cpp">unsigned int</code> |

Note that:

-   **all binary arithmetic and comparison operators** act like <code class="cpp">+</code>: <code class="cpp">-</code>, <code class="cpp">\*</code>, etc. (that means <code class="cpp">5U \> –6</code> is also false!)
-   the order of the operands does not matter
-   these rules do not depend on the value of the variables, but only on their type (e.g. <code class="cpp">5U - 6U</code> is the same type as <code class="cpp">5U - 4U</code>, that is <code class="cpp">unsigned int</code>)

I want to know if two wires are neighbouring. I rely on the fact that their ID is in sequence, and the IDs happen to be of type <code class="cpp">unsigned int</code>. Then my code:

    <code class="cpp">if (std::abs(w1 - w2) == 1) // do something if the wires are contiguous -- WRONG!!</code>

is **wrong**: <code class="cpp">w1 - w2</code> is an unsigned value (and therefore always positive: Clang will point out that there is no <code class="cpp">std::abs()</code> for <code class="cpp">unsigned int</code>, as it should). If `w1` is `6U` and `w2` is `5U`, <code class="cpp">w1 - w2</code> evaluates to `1` and everything is good, but if `w1` is `5U` and `w2` is `6U`, that difference is now something like `4294967295`, whose absolute value does not compare equal to `1`. Similarly for

    <code class="cpp">if (std::abs(w1 - w2) <= 2) // do something if the wires are close -- WRONG!!</code>

  
LArSoft provides a small function to perform this difference for values of the same type:

    <code class="cpp">
    #include "larcorealg/CoreUtils/NumericUtils.h"
    // ...
    if (util::absDiff(w1, w2) <= 2) // do something if the wires are close</code>

It will refuse to compile if the types are different though, in which case the best option is to explicitly cast one of the two operands depending on the prior knowledge (that is, cast the signed argument into unsigned if it is known that the value must be non-negative, and cast the unsigned into a signed otherwise).

Now I have a base index in an array, and an offset we subtract. The base index is an unsigned integral type (usually <code class="cpp">std::size_t</code>), and the offset may be a signed or unsigned integral type (commonly just an <code class="cpp">int</code>, but it might be more appropriately a <code class="cpp">std::ptrdiff_t</code>). We don't want to point to before the start of the array, so we write:

    <code class="cpp">if (base - offset >= 0) value = data[base - offset]; // WRONG!!</code>

But <code class="cpp">base - offset</code> is an unsigned value (see table above), so the comparison is always true! The compiler will warn in this specific case, but not for example if you want also to skip the first element:

    <code class="cpp">if (base - offset > 0) previousValue = data[base - offset - 1]; // may be WRONG!!</code>

The solution *may* be to reshape the comparison, **if `offset` is unsigned**:

    <code class="cpp">if (base > offset) previousValue = data[base - offset - 1]; // may still be wrong if offset < 0</code>

Note that if you have a case with signed `offset`, when `offset` is negative the comparison <code class="cpp">base \> offset</code> will be likely <code class="cpp">false</code> (as in <code class="cpp">5U \> –6</code> above).  
While there is no simple general solution, it is often possible to rely on the fact that the actual possible range of the indices is quite small compared to the range of the data types involved. This means that it's effectively safe to check the access to an array with an unsigned base index by:

    <code class="cpp">if (base + offset < N) value = data[base + offset];
    if (base + offset - 1 < N) previousValue = data[base + offset - 1];</code>

in that in all supported architecture a signed negative number is interpreted as a large unsigned number (larger than the available memory if `base` is <code class="cpp">std::size_t</code>). Note that in the last example the test <code class="cpp">base + offset - 1 \< N</code> is not equivalent to <code class="cpp">base + offset \< N + 1</code>, since the latter is <code class="cpp">true</code> for `base + offset` equal to `0`.