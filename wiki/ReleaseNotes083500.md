LArSoft v08\_35\_00 Release Notes
======================================================================

-   **Table of contents**
-   [LArSoft v08\_35\_00 Release Notes](#LArSoft-v08_35_00-Release-Notes)
    -   [Purpose](#Purpose)
    -   [New features](#New-features)
    -   [Bug fixes](#Bug-fixes)
    -   [Updated dependencies](#Updated-dependencies)
-   [Change List](#Change-List)
    -   [larsoft v08\_35\_00](#larsoft-v08_35_00)
    -   [lareventdisplay v08\_08\_20](#lareventdisplay-v08_08_20)
    -   [larexamples v08\_02\_25](#larexamples-v08_02_25)
    -   [larg4 v08\_05\_02](#larg4-v08_05_02)
    -   [larpandora v08\_07\_24](#larpandora-v08_07_24)
    -   [larwirecell v08\_08\_01](#larwirecell-v08_08_01)
    -   [larana v08\_12\_00](#larana-v08_12_00)
    -   [larreco v08\_22\_00](#larreco-v08_22_00)
    -   [larsim v08\_15\_01](#larsim-v08_15_01)
    -   [larevt v08\_06\_14](#larevt-v08_06_14)
    -   [lardata v08\_09\_02](#lardata-v08_09_02)
    -   [larcore v08\_06\_01](#larcore-v08_06_01)
    -   [larpandoracontent v03\_15\_08](#larpandoracontent-v03_15_08)
    -   [larsoftobj v08\_21\_00](#larsoftobj-v08_21_00)
    -   [lardataobj v08\_06\_02](#lardataobj-v08_06_02)
    -   [lardataalg v08\_08\_10](#lardataalg-v08_08_10)
    -   [larcorealg v08\_16\_00](#larcorealg-v08_16_00)
    -   [larcoreobj v08\_06\_00](#larcoreobj-v08_06_00)
    -   [larbatch v01\_51\_10](#larbatch-v01_51_10)
    -   [larutils v1\_25\_00](#larutils-v1_25_00)

[list of LArSoft releases](LArSoft_release_list)\
Download instructions for [larsoft v08\_35\_00](http://scisoft.fnal.gov/scisoft/bundles/larsoft/v08_35_00/larsoft-v08_35_00.html)\
Download instructions for [just larsoftobj v08\_21\_00](http://scisoft.fnal.gov/scisoft/bundles/larsoftobj/v08_21_00/larsoftobj-v08_21_00.html)

Purpose
--------------------

New features
------------------------------

-   resolve [\#23196](/redmine/issues/23196 "Support: Make GausHitFinder's dependence on RawDigit optional (Resolved)")
    -   larreco feature/usher\_removerawdigits
    -   larana feature/usher\_removeRawDigits
-   larcorealg feature/gp\_SplitWires
    -   additions for ICARUS geometry

Bug fixes
------------------------

Updated dependencies
----------------------------------------------

Change List
============================

larsoft v08\_35\_00
------------------------------------------

-   2019-11-05 Lynn Garren : larsoft v08\_35\_00 for larsoft v08\_35\_00
-   2019-11-05 Lynn Garren : product versions
-   2019-11-05 Lynn Garren : product versions

lareventdisplay v08\_08\_20
----------------------------------------------------------

-   2019-11-05 Lynn Garren : lareventdisplay v08\_08\_20 for larsoft v08\_35\_00

larexamples v08\_02\_25
--------------------------------------------------

-   2019-11-05 Lynn Garren : larexamples v08\_02\_25 for larsoft v08\_35\_00

larg4 v08\_05\_02
--------------------------------------

-   2019-11-05 Lynn Garren : larg4 v08\_05\_02 for larsoft v08\_35\_00

larpandora v08\_07\_24
------------------------------------------------

-   2019-11-05 Lynn Garren : larpandora v08\_07\_24 for larsoft v08\_35\_00

larwirecell v08\_08\_01
--------------------------------------------------

-   2019-11-05 Lynn Garren : larwirecell v08\_08\_01 for larsoft v08\_35\_00

larana v08\_12\_00
----------------------------------------

-   2019-11-05 Lynn Garren : larana v08\_12\_00 for larsoft v08\_35\_00
-   2019-11-05 Tingjun Yang : Do not declare rawdigits.
-   2019-11-04 Usher, Tracy L : Remove references to RawDigits which were intended for hit collection associations.

larreco v08\_22\_00
------------------------------------------

-   2019-11-05 Lynn Garren : larreco v08\_22\_00 for larsoft v08\_35\_00
-   2019-11-01 Usher, Tracy L : Updating fhicl definiton for gaushitfinder to remove reference to RawDigit associations
-   2019-11-01 Usher, Tracy L : Removing the ability to make direct RawDigit\<–\>Hit associations as this is seen as obsolete, particularly since one can recover this through Wire\<–\>Hit associations and Wire\<–\>RawDigit associations. This is particularly a problem for experiments that cannot afford to keep very large RawDigit collections in memory.

larsim v08\_15\_01
----------------------------------------

-   2019-11-05 Lynn Garren : larsim v08\_15\_01 for larsoft v08\_35\_00

larevt v08\_06\_14
----------------------------------------

-   2019-11-05 Lynn Garren : larevt v08\_06\_14 for larsoft v08\_35\_00

lardata v08\_09\_02
------------------------------------------

-   2019-11-05 Lynn Garren : lardata v08\_09\_02 for larsoft v08\_35\_00

larcore v08\_06\_01
------------------------------------------

-   2019-11-05 Lynn Garren : larcore v08\_06\_01 for larsoft v08\_35\_00

larpandoracontent v03\_15\_08
--------------------------------------------------------------

larsoftobj v08\_21\_00
------------------------------------------------

-   2019-11-05 Lynn Garren : larsoftobj v08\_21\_00 for larsoft v08\_35\_00
-   2019-11-05 Lynn Garren : product versions

lardataobj v08\_06\_02
------------------------------------------------

-   2019-11-05 Lynn Garren : lardataobj v08\_06\_02 for larsoft v08\_35\_00

lardataalg v08\_08\_10
------------------------------------------------

-   2019-11-05 Lynn Garren : lardataalg v08\_08\_10 for larsoft v08\_35\_00

larcorealg v08\_16\_00
------------------------------------------------

-   2019-11-05 Lynn Garren : larcorealg v08\_16\_00 for larsoft v08\_35\_00
-   2019-10-27 Gianluca Petrillo : Added iterators for geometry and readout data containers.
-   2019-10-26 Gianluca Petrillo : Unbundled index management from geometry data containers.
-   2019-10-15 Gianluca Petrillo : Added \`resizeAs()\` to geometry and readout data containers.
-   2019-10-15 Gianluca Petrillo : Added default constructors for geometry and readout data collections.
-   2019-10-08 Gianluca Petrillo : Added support for data containers for readout elements in \`geo::GeometryCore\`.
-   2019-10-08 Gianluca Petrillo : Added data containers for readout elements.
-   2019-10-08 Gianluca Petrillo : Updated geometry data container classes.

larcoreobj v08\_06\_00
------------------------------------------------

larbatch v01\_51\_10
--------------------------------------------

-   2019-11-05 Lynn Garren : larbatch v01\_51\_10 for larsoft v08\_35\_00
-   2019-10-25 Herbert Greenlee : Don’t let file names get too long during multiple fcl jobs.

larutils v1\_25\_00
------------------------------------------

-   2019-11-05 Lynn Garren : larutils v1\_25\_00 for larsoft v08\_35\_00
-   2019-11-04 Thomas Junk : build artifacts are in MRB\_BUILDDIR
-   2019-11-01 Thomas Junk : build script with mrb for protoduneana