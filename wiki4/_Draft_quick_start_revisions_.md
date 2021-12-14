Draft quick start revisions \
———————————-[¶](#Draft-quick-start-revisions-)
==============================================


Quick-start guide to using and developing LArSoft code at Fermilab[¶](#Quick-start-guide-to-using-and-developing-LArSoft-code-at-Fermilab)
==========================================================================================================================================

-   **Table of contents**
-   [Draft quick start revisions ———————————-](#Draft-quick-start-revisions-)
-   [Quick-start guide to using and developing LArSoft code at Fermilab](#Quick-start-guide-to-using-and-developing-LArSoft-code-at-Fermilab)
    -   [Before you start](#Before-you-start)
-   [The ultra-quick-start guide:](#The-ultra-quick-start-guide)
    -   [I. To run an installed version LArSoft and experiment code](#I-To-run-an-installed-version-LArSoft-and-experiment-code)
        -   [I.(a) Initial setup.](#Ia-Initial-setup)
        -   [I.(b) Set up experiment code and larsoft.](#Ib-Set-up-experiment-code-and-larsoft)
        -   [I.(c) Run larsoft](#Ic-Run-larsoft)
    -   [II. To check out and build experiment code](#II-To-check-out-and-build-experiment-code)
        -   [II.(a) Initial setup](#IIa-Initial-setup)
        -   [II.(b) Case 1: Create a new working area and check out code](#IIb-Case-1-Create-a-new-working-area-and-check-out-code)
        -   [II.(c) Case 2: Return to an existing work area after starting a new login session](#IIc-Case-2-Return-to-an-existing-work-area-after-starting-a-new-login-session)
        -   [II.(d) Check out and build the code for the first time in this working area](#IId-Check-out-and-build-the-code-for-the-first-time-in-this-working-area)
        -   [II.(e) Building the code in the same login session in the same working area after changing the code](#IIe-Building-the-code-in-the-same-login-session-in-the-same-working-area-after-changing-the-code)
        -   [II.(f) Set up and run the code you just built](#IIf-Set-up-and-run-the-code-you-just-built)
        -   [II.(g) To add another repository to your working area](#IIg-To-add-another-repository-to-your-working-area)
        -   [II.(h) To remove a repository from your working area](#IIh-To-remove-a-repository-from-your-working-area)
    -   [III. Check out, modify and build experiment or LArSoft code](#III-Check-out-modify-and-build-experiment-or-LArSoft-code)
        -   [III.(a) Initial setup](#IIIa-Initial-setup)
        -   [III.(b) Case 1: create a new working area](#IIIb-Case-1-create-a-new-working-area)

These instructions are for working with larsoft release v0\_01\_01 and later, and mrb v0\_04\_02 and later. The instructions assume that LArSoft is installed locally using the download and installation instructions linked from the download page. Changes needed for off-site installations will be noted. This documentation is evolving as we receive feedback. Please open an issue ticket if you have suggestions or complaints.

Please note that all Fermilab redmine repository names are lower case. See the [LArSoft product list](_LArSoft_repositories_packages_and_dependencies_).

See [The developer environment](_The_developer_environment_) page for important information about the git branching model that should be used when developing LArSoft code.


Before you start[¶](#Before-you-start)
--------------------------------------

-   To see list the available versions of a product, including all available qualifiers

> -   set up ups as described below
> -   use **ups list -aK+ \<productname\>** or **ups list -aK+ \<productname\> \<version\>**
> -   alternatively, look at the [LArSoft release list](LArSoft_release_list) page.

-   To verify that all dependencies are available (useful for checking a new installation), use ups depend:

> -   **ups depend \<productname\> \<version\> -q \<qualifiers\>**

-   Each LArSoft “package” below corresponds to a git repository and a ups product which have the same name.

-   You need modern versions of git and gitflow

> -   git must be version 1.8 or newer
> -   git 1.8.0.1 is available in /grid/fermiapp/larsoft/products
> -   gitflow 0.4.1 is available in /grid/fermiapp/larsoft/products


The ultra-quick-start guide:[¶](#The-ultra-quick-start-guide)
=============================================================

Three primary cases are described below:

-   How to run an installed version of LArSoft and experiment code
-   How to check out and build experiment code
-   How to modify, commit and build LArSoft or experiment software

More detailed explanations of what is happening during each of these can be found in the annotated portion of this guide below.


I. To run an installed version LArSoft and experiment code[¶](#I-To-run-an-installed-version-LArSoft-and-experiment-code)
-------------------------------------------------------------------------------------------------------------------------


### I.(a) Initial setup.[¶](#Ia-Initial-setup)

Run experiment-specific setup script. This will set up ups for the experiment, as well as mrb, git and git flow:\

    source /grid/fermiapp/uboone/software/setup_uboone.sh   # or setup_uboone.csh

\
or\

    source /grid/fermiapp/lbne/softare/setup_lbne.sh        # or setup_lbne.csh

-   If off-site, the appropriate script should be modified to reflect the locations of local product installations.


### I.(b) Set up experiment code and larsoft.[¶](#Ib-Set-up-experiment-code-and-larsoft)

Setting up experiment code will set up the appropriate version of larsoft.\

    setup lbnecode v1_00_01 -q e4:prof

\
or\

    setup uboonecode v1_00_01 -q e4:prof

\
For all other experiments, just set up larsoft:\

    setup larsoft v1_00_01 -q e4:prof

\
To see other version and qualifier options, do:\

    ups list -aK+ <product name>


### I.(c) Run larsoft[¶](#Ic-Run-larsoft)

    lar [option list] -c <fcl file>


II. To check out and build experiment code[¶](#II-To-check-out-and-build-experiment-code)
-----------------------------------------------------------------------------------------

There are two cases here: create a new working area and check out code, or return to an existing working area after logging out and starting a new login session.


### II.(a) Initial setup[¶](#IIa-Initial-setup)

Start with the same experiment-specific setup as above.\

    source /grid/fermiapp/uboone/software/setup_uboone.sh   # or setup_uboone.csh

\
or\

    source /grid/fermiapp/lbne/softare/setup_lbne.sh        # or setup_lbne.csh


### II.(b) Case 1: Create a new working area and check out code[¶](#IIb-Case-1-Create-a-new-working-area-and-check-out-code)

    mkdir <work_dir>
    cd <work_dir>
    mrb newDev -v <version> -q <qualifiers>

\
Alternatively:\

    mkdir <work_dir>
    cd <work_dir>
    setup larsoft <version> -q <qualifiers>
    mrb newDev 

\
where \<version\> and \<qualifiers\> refer to the version of larsoft against which to build the code. Perform the local mrb setup for the working area. \

    source localProducts_<long string>/setup

\
where \<long string\> identifies the version and qualifiers used in the creation of this area.

-   This must be performed every time you start working in this or any working area. If you change areas, you must perform this setup for that area. Note that this only configures mrb. It does not set up larsoft or any other product.


### II.(c) Case 2: Return to an existing work area after starting a new login session[¶](#IIc-Case-2-Return-to-an-existing-work-area-after-starting-a-new-login-session)

Perform the local mrb setup for the working area.\

    cd <work_dir>
    source localProducts_<long string>/setup


### II.(d) Check out and build the code for the first time in this working area[¶](#IId-Check-out-and-build-the-code-for-the-first-time-in-this-working-area)

First check out the code:\

    cd srcs
    mrb gitCheckout <repository> [tag_name]       # abbreviate to 'mrb g'
    # 
    # For LBNE code, <repository> = lbnecode
    # For uBooNE code, <repository> = uboonecode 
    #
    # <repository> can also be the name of any redmine repository (i.e. all of larsoft and experiment repositories)
    # or a url or directory path to an arbitrary repository
    #
    # If using an svn repository, use 'mrb svnCheckout <repository> [tag_name]
    #

\
Now build and install the code you have just checked out. The install step will package and install the code as a re-locatable ups product in the localProducts\_xxx directory. From there you can set it up and run it from anywhere.\

    cd ../build
    source mrb setEnv      # abbreviate to 'source mrb s'
    mrb install            # abbreviate to 'mrb i'
    #
    # You can also build and install in two separate steps:
    #   mrb build (abbreviate to mrb b)
    #   mrb install
    # All products in the srcs directory will be built by this procedure, provided that the top-level 
    # CMakeLists.txt file has an "add_subdirectory" line for the product 


### II.(e) Building the code in the same login session in the same working area after changing the code[¶](#IIe-Building-the-code-in-the-same-login-session-in-the-same-working-area-after-changing-the-code)

If within the current login session, you have:

-   already performed all the initialization steps for this working area, including “source mrb setEnv”;
-   have not performed any setup or setEnv for another working area since that initialization;
-   have only modified existing files in your srcs area;\
    then you can just run “make” in the build directory rather “mrb b” or “mrb i” again:\

        cd build
        make          # just performs the build
        make test     # does something if there is a unit test for the product (there are none yet)
        make install  # performs the build and install

    \
    This can be used, for instance, after fixing a compilation error, and is *considerably* faster than using “mrb b” or “mrb i”.

Exceptions:

-   If you add or delete a file, then you will need to run “mrb b” or “mrb i” again.
-   If you add or remove a product from the srcs area, then you will need to follow the procedure outline below.


### II.(f) Set up and run the code you just built[¶](#IIf-Set-up-and-run-the-code-you-just-built)

To run the code you just build, you need to use ups to set it up. Starting with no products set up:\

    setup <lbnecode | uboonecode> <version> -q <qualifier>

\
This step will also set up any larsoft products you have built at the same time.

-   For locally built products, the \<version\> and \<qualifier\> is set in the associated srcs/\<product\>/ups/product\_deps file.
-   The build procedure will un-setup any products that are being built, so if any were set up prior to the build, then those will need to be set up again.
-   To set up all the products in the localProducts\_xxx directory, use “source mrb slp”. If any larsoft sub-products were included in the build (e.g, larcore, lardata, etc.) and larsoft is already set up. then you can use this command to re-set up those products. Alternatively, you can “unsetup uboonecode” or “unsetup lbnecode”, followed by “setup uboonecode”, etc.

Now run the code:\

    lar [options] -c <fcl file>


### II.(g) To add another repository to your working area[¶](#IIg-To-add-another-repository-to-your-working-area)

This assumes that the initial setup and localProducts setup has been performed.

    cd <work_dir>/srcs
    mrb g <new repository> [tag_name]

\
Now build as before.\

    cd ../build
    source mrb setEnv   # This must be run every time the configuration of your working area changes
    mrb i


### II.(h) To remove a repository from your working area[¶](#IIh-To-remove-a-repository-from-your-working-area)

This assumes that the initial setup and localProducts setup has been performed.

    cd <work_dir>/srcs/
    rm -rf <repository>
    #
    # Now you need to remake the top-level CMakeLists.txt file so that it no longer references
    # the repository you just removed
    #
    mrb uc


III. Check out, modify and build experiment or LArSoft code[¶](#III-Check-out-modify-and-build-experiment-or-LArSoft-code)
--------------------------------------------------------------------------------------------------------------------------

There are two cases here: create a new working area, or return to an existing working area in a new login session.


### III.(a) Initial setup[¶](#IIIa-Initial-setup)

Run experiment-specific setup as above:\

    source /grid/fermiapp/uboone/software/setup_uboone.sh   # or setup_uboone.csh

\
or\

    source /grid/fermiapp/lbne/softare/setup_lbne.sh        # or setup_lbne.csh


### III.(b) Case 1: create a new working area[¶](#IIIb-Case-1-create-a-new-working-area)

    mkdir <work_dir>
    cd <work_dir>
    mrb newDev -v <version> -q <qualifier>
    #
    # set up mrb for the local area
    #
    source localProducts_<long string>/setup

    h3. III.(c) Case 2: return to an existing working area

    <pre>
    cd <work_dir>
    source localProducts_<long string>/setup

    h3. III.(d) Check out LArSoft or experiment code

    <pre>
    cd srcs
    mrb g <repository1> [tag_name]
    #
    # This should be repeated to include as many product repositories as needed.
    # To check out all larsoft repositories, use <repository> = "larsoft_suite".
    # For experiment repositories, use <repository> = "lbnecode" or "uboonecode" 
    #
    </pre>
    Now modify the code as needed. Every repository checked out using mrb will be on the develop branch. In order to protect the integrity of the develop branch, all code modifications should be made in a "feature branch". You can use the "git flow" product to assist with this. The general workflow is the following:
    * Create a feature branch and make your modifications
    * Check your changes into your feature branch
    * Pull from the main repository, then rebase (or merge) develop into your feature branch. This will pick up any changes made to the repository since you checked out the code, and allow you to test your change as if you had checked it into develop.
    * Test your change
    * Merge your changes into develop
    * Push the develop branch to the main repository

    The following example uses git flow to create and merge the feature branch (using uboonecode as an example):
    <pre>
    cd uboonecode
    git flow feature start <my_username>_featureName
    [...make changes to the code...]
    git pull origin develop
    git rebase develop
    [...any merge conflicts need to be resolved at this point...]
    [...build and test the changes. When ok, then...]
    git flow feature finish <my_username>_featureName
    #
    # The feature finish step merges the feature branch into develop and deletes 
    # the feature branch
    #
    git push origin develop
    </pre>

    It is also possible to use bare git to perform the branch manipulations:
    <pre>
    cd <work_dir>
    git checkout -b <my_username>_featureName
    [...make changes...]
    git pull origin develop
    git rebase develop
    [...resolve conflicts if any...]
    [...build and test the changes. When ok, then...]
    git merge develop
    git push origin develop
    </pre>

    #
    # where <repository

    Run experiment-specific setup to set up ups for the experiment, plus mrb, git and git flow.
    <pre>
    source /grid/fermiapp/uboone/software/setup_uboone.sh
    </pre>
    or
    <pre>
    source /grid/fermiapp/lbne/softare/setup_lbne.sh
    </pre>
    * *.csh versions available for csh/tcsh users
    * If off-site, the appropriate script should be modified to reflect the locations of local product installations.

    h3. Creating a new working area from a fresh login

    h3. Starting from a fresh login and creating a new working area
    h3. Set up experiment code and larsoft 

    h3. Initial setup of the working environment (starting from a fresh login):

    Run experiment-specific setup script:
    <pre>
    source /grid/fermiapp/uboone/software/setup_uboone.sh
    </pre>
    or
    <pre>
    source /grid/fermiapp/lbne/softare/setup_lbne.sh
    </pre>
    (*.csh versions are also available for csh/tcsh users)

    If off-site, the appropriate script should be modified to reflect the locations of local product installations.

    * Perform the next step *only* if you want to run code in a frozen LArSoft release *and* are interested in running jobs specific to experiments other than LBNE and uBooNE. All other users should skip to the "Create a working area" step.

    h3. Run non-LBNE or non-uBoonE jobs using only a frozen LArSoft release

    <pre>
    setup larsoft <version> -q debug:e4    # (or -q e4:prof)
    lar -c <job fcl file> ...
    </pre>

    > That's it. You're done.

    h2. To build experiment-specific code for LBNE or uBooNE against an existing LArSoft release

    h3. Build uboonecode or lbnecode

    * Note that you may also use an experiment-specific setup script for the intial setup (not including the setup of larsoft).

    > <pre>
    source /grid/fermiapp/products/larsoft/setup
    setup git
    setup gitflow
    setup mrb
    export MRB_PROJECT=<larsoft>
    setup larsoft vx_yy_zz -q e4:prof    # (or -q debug:e4)
    #
    mkdir <working_dir>
    cd <working_dir>
    mrb newDev 
    source ./localProducts_XXX/setup
    #
    cd srcs
    mrb g <uboonecode|lbnecode>
    #
    <work on code...>
    cd ../build
    source mrb s
    mrb i -j4     # (if the machine has enough cores)
    </pre>

    > "<xxx|yyy>" is intended to denote selecting one or the other of xxx or yyy.
    > To work with an existing work area, omit @mkdir@ and @mrb newDev@ steps above.

    h3. Run the software you just built 

    * <pre>setup <uboonecode | lbnecode> <version> -q <qualifiers> </pre> 

    * Note for the brave: "source mrb slp" will setup ALL products in your working localProducts directory.
    * If you've been following these directions, then uboonecode or lbnecode will be the ONLY product in your localProducts directory.

    * Now run
    <pre>lar -c xxx.fcl ...</pre>

    > * Note that the build procedure will un-setup any products that are being built, so those
    > need to be set-up again before they can be used.
    > * The version of @uboonecode@ and @lbnecode@ is set in the associated @ups/product_deps@ file. See
    > the list of releases for the most current version, or use @ups list -aK+ <lbnecode | uboonecode>

    h2. To build and work with larsoft itself

    h3. Create a working area 

    >After you have performed the initial setup:
    > <pre>
    mkdir <working_dir>
    cd <working_dir>
    mrb newDev -v vx_yy_zz -q e4:prof    # (or -q debug:e4)
    </pre>
    > * where 'vx_yy_zz' is the base version for the release you are working with. 
    > * Select from the [[LArSoftWiki#releases|list of releases]], or use 'ups list -aK+ larsoft' to get a complete list of available releases. 
    > * Current beta is v0_02_01 (See [[LArSoftWiki]] for most recent release)
    > * Alternatively, you can 'setup larsoft <version> -q <debug:e4|e4:prof>' before running 'mrb newDev', in which case you can omit the '-v' and '-q' from the 'mrb' command.

    * If you only want to run using the base LArSoft release and uBooNE or LBNE code, then skip ahead to the "To build experiment-specific code for LBNE or uBooNE against an existing LArSoft release" step 

    h3. Check out, develop and build LArSoft code

    > After performing the initial setup and creating the working area, from @<working_dir>@:
    > <pre>
    source ./localProducts_XXX/setup
    cd srcs
    #
    # This next command checks out everything. You can also use single repository
    # names as the last argument if that is all you need. 
    # Abbreviates to mrb g <repo>
    mrb gitCheckout larsoft_suite    
    <work on code...use git flow branching scheme if introducing changes to LArSoft code>
    cd ../build
    source mrb setEnv  # Abbreviated:  source mrb s. This and next step must be done in bash shell!!
    mrb install -j4    # -jN => N parallel processes for the build (if the machine has enough cores)
    </pre>
    > * @mrb install@ (abbreviates to @mrb i@) will build then install results in localProducts_XXX. This
    >   is the preferred command if you need to run what you are building.
    > * You can also use @mrb build@ (or @mrb b@) if you just want the build with no install. Be aware, however, that you cannot run using the resulting build products.

    > The list of repositories and their contents [[ LArSoft repositories packages and dependencies |can be found on this page ]].

    h3. Run the software you just built 

    > Starting from the build directory immediately after running @mrb build@:
    > <pre>
    mrb install  # if this was not run previously
    cd ..        # should now be in the top-level directory of working area
    #
    # The next line is needed if 
    # a) larsoft was set up prior to the build, and
    # b) any larsoft sub-products were built, and
    # c) you are going directly from having built to wanting to run in the same login session
    unsetup larsoft
    #
    # The next line is needed if any experiment code was built or if in a new login
    # session where it has not already been set up.
    # It will set up larsoft, so no need to do that up explicitly. 
    setup <uboonecode | lbnecode> <version> -q <qualifiers>  

    # If no experiment code was built, then comment out the line above and 
    # run this one instead:
    # setup larsoft <version> -q <qualifiers>

    # Now run
    lar -c xxx.fcl ...
    </pre>

    > * Note that the build procedure will un-setup any products that are being built, so those
    > need to be set-up again before they can be used.
    > * The version of @uboonecode@ and @lbnecode@ is set in the associated @ups/product_deps@ file. See
    > the list of releases for the most current version, or use @ups list -aK+ <lbnecode | uboonecode>

    h1. Annotated quick-start guide

    h2.  Initial setup

    The first time you start a mrb project, you'll need to define various things. (The setup for an existing working area are slightly different, as described under 

    * We imagine that these steps will be part of an experiment-specific script to setup the working environment. The generic setup steps are:
    > * setup ups 
    > * set the $PRODUCTS path if necessary
    > * setup git
    > * setup gitflow
    > * define MRB_PROJECT
    > * setup mrb
    > * setup <project> <version>
    > * define MRB_PROJECT
    > > * MRB_PROJECT is meant to define your project. @mrb newDev@ will *require* that MRB_PROJECT be the name of a ups product. 
    > > * Eventually, you will be able to use the experiment name for the project.
    > > * For now, just use "larsoft" in all cases. 

    * This fragment works on uboonegpvm01 and other gpvm machines:
    <pre>
    source /grid/fermiapp/products/larsoft/setup
    setup git
    setup gitflow
    setup mrb
    setup larsoft <version> -q <qualifiers>
    export MRB_PROJECT=larsoft
    </pre>

    > Sample experiment-specific setup scripts that perform the above can be found here:
    > <pre>
    /grid/fermiapp/lbne/software/setup_lbne.sh
    /grid/fermiapp/lbne/software/setup_lbne.csh
    </pre>
    > AND:
    > <pre>
    /grid/fermiapp/uboone/software/setup_uboone.sh
    /grid/fermiapp/uboone/software/setup_uboone.csh
    </pre>

    You are now ready to create a working area.

    h2. Create a working area

    h3. Everything (source code, <localProdDir>, and build directory) in one directory tree

    Case 1: you have setup <MRB_PROJECT> <version> (the recommended procedure)
    <pre>
    mkdir <working_dir>
    cd  <working_dir>
    mrb newDev 
    </pre>
    > * this creates <working_dir>/build, <working_dir>/srcs, and <working_dir>/localProducts_<MRB_PROJECT>_<version>_<qualifiers>
    > * We refer to <working_dir>/localProducts... as <localProdDir>
    * source <localProdDir>/setup

    Case 2: you did not setup <MRB_PROJECT> <version>
    <pre>
    mkdir <working_dir>
    cd  <working_dir>
    mrb newDev -v <version> -q <qualifiers>
    </pre>
    > * this creates <working_dir>/build, <working_dir>/srcs, and <working_dir>/localProducts_<MRB_PROJECT>_<version>_<qualifiers>
    > * We refer to <working_dir>/localProducts... as <localProdDir>
    * source <localProdDir>/setup

    h3. Source code under your home directory
    <pre>
    mkdir <working_dir>
    mkdir <source_dir>
    mrb newDev -T <working_dir> -S <source_dir>
    </pre>
    > * this creates <working_dir>/build and <working_dir>/localProducts_<MRB_PROJECT>_<version>_<qualifiers>
    > * We refer to <working_dir>/localProducts... as <localProdDir>
    > * Note that you may also need to specify -v <version> and -q <qualifiers> as above
    * source <localProdDir>/setup

    h2. Setup work environment for an existing working area from a fresh login

    To set up the working environment for an existing working area, you need to source the setup script in the local products area that created in the previous step. The local setup defines environment variables needed by mrb, and adds the local products area to the $PRODUCTS path so that ups can find local versions of products (created during the build/install step). The generic steps are the following:
    * perform the initial setup above
    > * set up ups 
    > * set the $PRODUCTS path
    > * make sure you have gitflow and git 1.8 or newer
    * source <localProdDir>/setup
    On uboonegpvm0X and lbnegpvm0X:
    <pre>
    source /grid/fermiapp/products/larsoft/setup
    setup git
    setup gitflow
    setup mrb
    export MRB_PROJECT=larsoft
    cd <working_dir>
    source ./localProducts_XXX/setup
    setup larsoft <version> -q <qualifiers>   # optional
    </pre>
    * Note that the larsoft setup needs to come after the setup in localProducts_XXX.

    h2. Developing a package

    * After setting up the working environment:
    <pre>
    cd $MRB_SOURCE
    mrb gitCheckout <package_1>
    mrb g <package_2>
    </pre>
    Or to check out the entire larsoft suite, replace the separate @mrb g ...@ with:
    <pre>
    mrb g larsoft_suite 
    </pre>
    * Please note that all Fermilab redmine repository names are lower case. 
    * mrb presumes your package is in Fermilab redmine unless you specify the full repository name.
    * You may supply either a package name or a repository name
    > * if there is only a package name, presume this is a Fermilab redmine project
    > * if there is a full repository name, use the repository name

    h2. Build code in your working area

    * After setting up the working environment:
    <pre>
    cd $MRB_BUILDDIR
    source mrb setEnv          # Must be done in bash shell!! 
    mrb b [-jN]                # Must be done in the same bash shell
    </pre>
    > * where N is the number of parallel build streams to use
    > * mrb b (build) calls buildtool, which is very powerful
    <pre>
    mrb install                # Abbrev mrb i. Must be done in the same bash shell
    </pre>
    > * optional 
    > * The mrb install command will make a ups product in your <localProdDir> for the package you are building. 
    > * You can also just type "make install [-jN]" 

    * To get rid of what you just built (or tried to build) and start over:
    <pre>
    cd $MRB_BUILDDIR
    rm -rf *
    </pre>
    > Then start from the top of this section.

    h2. Running with the modifications made in your working area

    The build/install procedure performs an @unsetup@ of every product it builds. It does this to ensure that the build environment points only to the local code being built. It also ensures that if you run @setup <product>...@ after the build and within the same login session, you get the locally installed version rather than the one you were pointing to at the beginning of the build/install procedure. (The setup command does nothing if the product is already set up.) After building _and installing_, you will therefore need to run @setup@ for all the products that you just built.

    This behavior results in the following curious complication. If you build only _some_ of the larsoft sub-products, but not the "larsoft" product proper, then running @setup larsoft...@ after the build is completed _will not_ set up the sub-products that you just built. The solution is either to run @setup <sub-product>...@ by hand for each product that was build, or to first run @unsetup larsoft@ so that a subsequent @setup larsoft...@ causes everything to be set up again. 

    Since all this seems complicated, we have introduced the @mrb setup_local_products@ command (abbreviated to @mrb slp@) that will perform the proper setup oA third more simple 
    This example uses the second technique.

    So, assuming that the basic setup has been completed and the local products setup has been sourced, then starting from the build directory:
    <pre>
    cd ..
    unsetup larsoft   
    #
    # The next line is needed if any experiment code was built. It will
    # set up larsoft, so no need to set that up explicitly
    setup <uboonecode | lbnecode> <version> -q <qualifiers>  

    # If no experiment code was build, then comment out the line above and 
    # run this one instead:
    # setup larsoft <version> -q <qualifiers>

    # Now run
    lar -c ...
    </pre>

    You will also need to manually set up any other products that are installed in the local products area that are not already dependencies of either larsoft or the experiment-specific products.

    Since all this seemed complicated, we have introduced the @mrb setup_local_products@ command (abbreviated to @mrb slp@) that will perform the proper setup of all products in the local products directory, regardless of whether they are part of LArSoft. To use this command in the above example (where we am assuming that you had set up @uboonecode@, @lbnecode@, or @larsoft@ going into the build):
    <pre>
    cd ..
    source mrb slp           # Must be done in bash shell!!

    # Now run
    lar -c ...
    </pre>
    (Note that if this command is used, then you must run programs in the same bash shell) 

    If starting from a fresh login, then the usual setup procedure (@setup <lbnecode | uboonecode | larsoft>@ is all that it needed.

    h2. Performing a clean build

    <pre>
    cd $MRB_BUILDDIR
    mrb zapBuild
    source mrb setEnv       # bash shell only from here!!
    mrb install
    </pre>
    OR:
    <pre>
    cd $MRB_BUILDDIR
    rm -rf *
    source mrb setEnv       # bash shell only from here!!
    mrb install
    </pre>

    You should perform a clean build whenever a product is added or removed. Cmake errors during the build may require that you start with a clean build.

    h2. Removing a package from a work area

    <pre>
    cd $MRB_SOURCE
    rm -rf <repo-name>
    mrb uc
    </pre>

    The @mrb uc@ command will update the top-level @CMakeLists.txt@ file to take into account the newly removed package.

    h2. Creating an entirely new product within an existing work area

    Assume that there is an existing repository with the same name that you want to attach to the newly created product.

    <pre>
    cd $MRB_SOURCE
    mrb newProduct <new-prod-name>
    cd <new-prod-name>
    git remote add <alias> <new-prod-repo-url>
    git pull <alias> <branch>
    </pre>

    The new product template has two files that are important to know about and that you will almost certainly need to modify in order to create a new product (the only exception being the case that you are attaching to a repository that already has a working product in it):  @<new-prod-name>/CMakeLists.txt@, and @<new-prod-name>/ups/product_deps@. In general, the @CMakeLists.txt@ files control the build-time configuration and the items that get built, and specify what files in the product get installed where during the install phase. (See the [[cet-is-public:Cetbuildtools cmake modules]] and [[cet-is-public:Art cmake modules]] pages for information on writing CMakelists.txt files within our build system.) The @product_deps@ file controls the run-time configuration via a ups "table" file (@<new-prod-name>/ups/<new-prod-name>.table@) that gets generated during the build and installation procedure. (See the [[cet-is-public:Defining products in the CET build environment]] page for details on the content of product_deps file.) More information on the build system can be found on the [[LArSoftWiki]] page.

    Set the product version number in the @<new-prod-name>/ups/product_deps@ file.

    Then build as usual.

    h1. Comparison of mrb and SRT commands

    The following table compares SRT commands with their approximate mrb analogs. 
    The equivalency is based entirely upon approximate parallel functionality within their respective frameworks.
    HOWEVER, please see the instructions above since there is not a one-to-one translation and behaviors differ.

    | *Legacy / SRT command* | *Analogous mrb command* |
    | setup_larsoft_fnal.sh | The setup procedure above |
    | newrel -t <release> <name> | mkdir <name>; cd <name>; mrb newDev |
    | addpkg_svn -h <package> <tag> | mrb gitCheckout <package> |
    | newpkg <name> | mrb newProduct <name> |
    | srt_setup -a | mrb setEnv |
    | gmake all | mrb install |
    | rmpkg <name> | rm -r <name> ; mrb uc |

    h1. Using prebuilt releases

    The new larsoft ups product and all its dependencies are installed in the /grid/fermiapp/products/larsoft product directory.
    This directory is mounted on the relevant gpvm machines and Fermilab grid worker nodes.
    In addition, a mirror of this directory will be (but is not yet) available on the oasis cvmfs. Once access via cvmfs is in production, we encourage users to install and use a cvmfs client instead of installing the binary distribution wherever possible.

    Binary distributions are available under http://oink.fnal.gov/distro/larsoft/

    If you need to pull everything (LArSoft plus all external packates) in order to create a new installation of the software (for instance, for an off-site installation to support a local analysis group), we recommend using the download script available in that directory.
    <pre>
    wget (or curl -O)  http://oink.fnal.gov/distro/larsoft/downloadLArSoft-<version>.sh
    chmod +x downloadLArSoft-<version>.sh
    ./downloadLArSoft-<version>.sh <product_dir> <main_qualifier> <debug|prof>
    </pre>
    > * This will pull the relocatable ups products and install them in <product_dir> where you should specify the full path to the product directory.
    > * The prof distribution requires about 20G
    You can find detailed instructions for downloading and installing binary and source distributions [[ Download instructions | on the download page ]].

    h1. Building the larsoft "suite" 

    In rare cases, you may need to build from scratch.

    h1.  General Information about git and art 

    * [[cet-is-public:AboutQualifiers|About Qualifiers]]
    * [[cet-is-public:cetbuildtools user guide]]

    * [[cet-is-public:git flow quick start]] (edited 2/4/2013).
    * [[cet-is-public:Marc's suggested git workflow]]
    * [[cet-is-public:GitTipsAndTricks|Git Tips and Tricks]]

    * [[cet-is-public:Building your own code with cmake]]
    * [[cet-is-public:Defining products in the CET build environment]]
    * [[cet-is-public:AddingProductDependencies|Adding Product Dependencies]]
    * [[cet-is-public:CodeTips|Various helpful tips for coding in the CET C++ environment]]

    ----------------------------------------

    h1.  Things that need a home on this page...

    Specification of the [[mrb:First mrb alpha release|basic mrb funtionality]]

    Adding a sub-directory to a product
    Examples for everything