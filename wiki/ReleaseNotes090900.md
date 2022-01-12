LArSoft v09\_09\_00 Release Notes
======================================================================

-   **Table of contents**
-   [LArSoft v09\_09\_00 Release Notes](#LArSoft-v09_09_00-Release-Notes)
    -   [Purpose](#Purpose)
    -   [New features](#New-features)
    -   [Bug fixes](#Bug-fixes)
    -   [Updated dependencies](#Updated-dependencies)
-   [Change List](#Change-List)
    -   [larsoft v09\_09\_00](#larsoft-v09_09_00)
    -   [lareventdisplay v09\_00\_11](#lareventdisplay-v09_00_11)
    -   [larexamples v09\_00\_10](#larexamples-v09_00_10)
    -   [larg4 v09\_01\_03](#larg4-v09_01_03)
    -   [larpandora v09\_03\_01](#larpandora-v09_03_01)
    -   [larsimrad v09\_00\_10](#larsimrad-v09_00_10)
    -   [larrecodnn v09\_02\_02](#larrecodnn-v09_02_02)
    -   [larwirecell v09\_01\_05](#larwirecell-v09_01_05)
    -   [larana v09\_00\_11](#larana-v09_00_11)
    -   [larreco v09\_04\_01](#larreco-v09_04_01)
    -   [larsim v09\_06\_00](#larsim-v09_06_00)
    -   [larevt v09\_00\_08](#larevt-v09_00_08)
    -   [lardata v09\_01\_03](#lardata-v09_01_03)
    -   [larcore v09\_00\_01](#larcore-v09_00_01)
    -   [larpandoracontent v03\_22\_01](#larpandoracontent-v03_22_01)
    -   [larsoftobj v09\_03\_00](#larsoftobj-v09_03_00)
    -   [lardataobj v09\_00\_02](#lardataobj-v09_00_02)
    -   [lardataalg v09\_03\_00](#lardataalg-v09_03_00)
    -   [larcorealg v09\_00\_01](#larcorealg-v09_00_01)
    -   [larcoreobj v09\_00\_00](#larcoreobj-v09_00_00)
    -   [webevd v09\_00\_08](#webevd-v09_00_08)
    -   [larbatch v01\_54\_00](#larbatch-v01_54_00)
    -   [larutils v1\_27\_02](#larutils-v1_27_02)

[list of LArSoft releases](LArSoft_release_list)
Download instructions for [larsoft v09\_09\_00](http://scisoft.fnal.gov/scisoft/bundles/larsoft/v09_09_00/larsoft-v09_09_00.html)
Download instructions for [just larsoftobj v09\_03\_00](http://scisoft.fnal.gov/scisoft/bundles/larsoftobj/v09_03_00/larsoftobj-v09_03_00.html)

Purpose
--------------------

-   changes in develop
-   approved PRs

New features
------------------------------

-   Facilitate call to DetectorClocksStandard::DataFor()
    -   lardataalg PR 16
    -   lardata PR 11
    -   **ubana, ubcv require feature/gp\_simplerForData**
    -   The preparation work needed to get a detinfo::DetectorClocksData from a detinfo::DetectorClocksStandard service provider is non-trivial (see the implementation of the old detinfo::DetectorClocksServiceStandard::DataFor(art::Event const&)).
        This preparation is performed for the lucky art user by detinfo::DetectorClocksServiceStandard, all other users need to make it on their own.
    -   I propose delegating that initialisation to a helper function crafted to work in both art and gallery frameworks, and in general in any environment with an object exposing a minimal art::Event-like interface.
    -   This implementation is a proposal for the described feature. The preparation code has been moved from detinfo::DetectorClocksServiceStandard::DataFor() into an helper function, and detinfo::DetectorClocksServiceStandard::DataFor() now delegates to it. The documentation of the helper function show how it can be used to obtain a detinfo::DetectorClocksData record within gallery.
        Other details:
        -   testing: I am satisfactorily using this implementation in my local area for some (gallery) analysis, and this implementation passes all LArSoft unit tests;
        -   the implementation of detinfo::DetectorClocksServiceStandard::DataFor() has moved into the implementation file to reduce the header inclusion bloating;
-   larpandoracontent PR 15
    -   This PR contains a number of updates designed to improve the robustness of the track/shower characterisation feature added in larpandoracontent v03\_20\_00 and patched in larpandoracontent v03\_21\_01.
    -   A minor dunetpc update is associated with this PR (feature/chappell\_pdsp\_ts\_update).
-   larsim PR 46
    -   added option to bypass ifdh copying of corsika shower db files and use a direct file path instead
    -   I’ve added an option to use a direct file path for a corsika database file instead of copying using ifdh, analogous to option in genie. I have been using this approach on Theta (ALCF) to a). minimise the copying required at large scale and b). to allow ifdh to be avoided, due to frequent unexplained segfaults when copying files with ifdh on Theta’s filesystem (possibly a memory issue? the seg faults occur while copying db files or flux files, but sporadically and not always at the same point in the code).
    -   This is controlled by a new fhicl parameter, fShowerCopyType, which can either be “IFDH” (default) or “DIRECT”. As default the standard IFDH copying is used, so unless this parameter is set this change should be invisible.
-   nusimdata v1\_21\_03 for [\#25114](/redmine/issues/25114 "Feature: Merge of 2 branches into Nusimdata (Closed)")
    -   The processes ‘CoulombScat’ and ‘nCapture’ have been added to the list of allowed processes in MCTrajectory. The default margin of 0.1 comes from what’s in MCTrajectory by default (which is 0.1).
    -   This will have an effect on some Geant4 reweighting machinery which is under development.

Bug fixes
------------------------

-   larreco PR 23
    -   Additional 3D reconstruction improvements
    -   The issue is how to reconstruct multiple 2D trajectories (that have a very small variation in X) in 3D. The latest TrajCluster release fixed the major problems but didn’t incorporate the most recent changes that have been made.

Updated dependencies
----------------------------------------------

-   nulite v3\_07\_03
    -   nusimdata v1\_21\_03
    -   nuevdb v1\_02\_07
    -   nug4 v1\_05\_02
    -   nugen v1\_10\_10
    -   nutools v3\_07\_03
    -   geant4reweight v01\_04\_02
-   nusystematics v00\_10\_06

Change List
============================

larsoft v09\_09\_00
------------------------------------------

-   2020-10-28 Lynn Garren : larsoft v09\_09\_00 for larsoft v09\_09\_00
-   2020-10-28 Lynn Garren : product versions

lareventdisplay v09\_00\_11
----------------------------------------------------------

-   2020-10-28 Lynn Garren : lareventdisplay v09\_00\_11 for larsoft v09\_09\_00

larexamples v09\_00\_10
--------------------------------------------------

-   2020-10-28 Lynn Garren : larexamples v09\_00\_10 for larsoft v09\_09\_00

larg4 v09\_01\_03
--------------------------------------

-   2020-10-28 Lynn Garren : larg4 v09\_01\_03 for larsoft v09\_09\_00

larpandora v09\_03\_01
------------------------------------------------

-   2020-10-28 Lynn Garren : larpandora v09\_03\_01 for larsoft v09\_09\_00

larsimrad v09\_00\_10
----------------------------------------------

-   2020-10-28 Lynn Garren : larsimrad v09\_00\_10 for larsoft v09\_09\_00

larrecodnn v09\_02\_02
------------------------------------------------

-   2020-10-28 Lynn Garren : larrecodnn v09\_02\_02 for larsoft v09\_09\_00

larwirecell v09\_01\_05
--------------------------------------------------

-   2020-10-28 Lynn Garren : larwirecell v09\_01\_05 for larsoft v09\_09\_00

larana v09\_00\_11
----------------------------------------

-   2020-10-28 Lynn Garren : larana v09\_00\_11 for larsoft v09\_09\_00

larreco v09\_04\_01
------------------------------------------

-   2020-10-28 Lynn Garren : larreco v09\_04\_01 for larsoft v09\_09\_00
-   2020-10-27 Lynn Garren : Merge pull request \#23 from brballer/feature/bb\_vsafix
-   2020-10-26 Bruce Baller : Merge branch ‘develop’ into feature/bb\_vsafix
-   2020-10-26 Bruce Baller : Cherry-pick more very-small-angle 3D reconstruction code from feature/bb\_kStudy

larsim v09\_06\_00
----------------------------------------

-   2020-10-28 Lynn Garren : larsim v09\_06\_00 for larsoft v09\_09\_00
-   2020-10-27 Lynn Garren : Merge pull request \#46 from pgreen135/feature/pgreen\_corsikaLocalShowerCopy
-   2020-10-26 Patrick Green : added option to bypass ifdh copying of corsika shower db files and use a direct file path instead

larevt v09\_00\_08
----------------------------------------

-   2020-10-28 Lynn Garren : larevt v09\_00\_08 for larsoft v09\_09\_00

lardata v09\_01\_03
------------------------------------------

-   2020-10-28 Lynn Garren : lardata v09\_01\_03 for larsoft v09\_09\_00
-   2020-10-28 Lynn Garren : Merge branch ‘feature/gp\_simplerForData’ into release/v09\_09\_00
-   2020-10-15 Gianluca Petrillo : DetectorClocksServiceStandard uses new ForData() helper

larcore v09\_00\_01
------------------------------------------

larpandoracontent v03\_22\_01
--------------------------------------------------------------

-   2020-10-28 Lynn Garren : larpandoracontent v03\_22\_01 for larsoft v09\_09\_00
-   2020-10-26 Andrew Chappell : Update CMakeLists and ChangeLog
-   2020-10-22 Andrew Chappell : Further cosmetic changes
-   2020-10-22 Andrew Chappell : Minor style adjustments and replace try block
-   2020-10-22 John Marshall : Checks relating to empty input threeDCaloHitList; also checked by calling function.
-   2020-10-22 Andrew Chappell : Minor style adjustments
-   2020-10-22 Andrew Chappell : Add option to apply training without reconstructability checks
-   2020-10-22 Andrew Chappell : Handle empty maps and throw rather than return for missing lists
-   2020-10-21 Andrew Chappell : Edits to Mva training block
-   2020-10-21 John Marshall : Cosmetic, some variables now fine to exist only within try block.
-   2020-10-21 John Marshall : Edits to charge variables calculation.
-   2020-10-21 John Marshall : Refinements identified during collaborative review.
-   2020-10-21 John Marshall : Cosmetics and some efficiency tweaks.
-   2020-10-20 John Marshall : First-pass overhaul of track/shower id features.
-   2020-10-20 John Marshall : Overhauling implementation.
-   2020-10-20 John Marshall : Cosmetics.
-   2020-10-20 John Marshall : Remove left-over tree-writing functionality.
-   2020-10-20 John Marshall : Include overhaul. Some doxygen additions and corrections.
-   2020-10-20 John Marshall : Revoke previous accidentals.

larsoftobj v09\_03\_00
------------------------------------------------

-   2020-10-28 Lynn Garren : larsoftobj v09\_03\_00 for larsoft v09\_09\_00
-   2020-10-28 Lynn Garren : product versions

lardataobj v09\_00\_02
------------------------------------------------

-   2020-10-28 Lynn Garren : lardataobj v09\_00\_02 for larsoft v09\_09\_00

lardataalg v09\_03\_00
------------------------------------------------

-   2020-10-28 Lynn Garren : lardataalg v09\_03\_00 for larsoft v09\_09\_00
-   2020-10-28 Lynn Garren : Merge branch ‘feature/gp\_simplerForData’ into release/v09\_09\_00
-   2020-10-15 Gianluca Petrillo : Enclose DetectorClocksStandard::ForData() initialization

larcorealg v09\_00\_01
------------------------------------------------

larcoreobj v09\_00\_00
------------------------------------------------

webevd v09\_00\_08
----------------------------------------

-   2020-10-28 Lynn Garren : webevd v09\_00\_08 for larsoft v09\_09\_00

larbatch v01\_54\_00
--------------------------------------------

larutils v1\_27\_02
------------------------------------------

-   2020-10-28 Lynn Garren : larutils v1\_27\_02 for larsoft v09\_09\_00
-   2020-10-26 Lynn Garren : Merge pull request \#8 from SBNSoftware/develop
-   2020-10-26 Wesley : get updated build script from sbnbuild repo
-   2020-10-23 Lynn Garren : need to recognize s102, etc.