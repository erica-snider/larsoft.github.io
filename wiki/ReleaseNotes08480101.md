LArSoft v08\_48\_01\_01 Release Notes
=============================================================================

-   **Table of contents**
-   [LArSoft v08\_48\_01\_01 Release Notes](#LArSoft-v08_48_01_01-Release-Notes)
    -   [Purpose](#Purpose)
    -   [Caveats](#Caveats)
    -   [Updated dependencies](#Updated-dependencies)
-   [Change List](#Change-List)
    -   [larsoft v08\_48\_01\_01](#larsoft-v08_48_01_01)
    -   [lareventdisplay v08\_12\_09\_01](#lareventdisplay-v08_12_09_01)
    -   [larexamples v08\_06\_09\_01](#larexamples-v08_06_09_01)
    -   [larg4 v08\_12\_07\_01](#larg4-v08_12_07_01)
    -   [larpandora v08\_12\_01\_01](#larpandora-v08_12_01_01)
    -   [larrecodnn v08\_01\_02\_01](#larrecodnn-v08_01_02_01)
    -   [larwirecell v08\_12\_08\_01](#larwirecell-v08_12_08_01)
    -   [larana v08\_17\_01\_01](#larana-v08_17_01_01)
    -   [larreco v08\_30\_01\_01](#larreco-v08_30_01_01)
    -   [larsim v08\_22\_01\_01](#larsim-v08_22_01_01)
    -   [larevt v08\_11\_01\_01](#larevt-v08_11_01_01)
    -   [lardata v08\_15\_01](#lardata-v08_15_01)
    -   [larcore v08\_11\_02](#larcore-v08_11_02)
    -   [larpandoracontent v03\_15\_16](#larpandoracontent-v03_15_16)
    -   [larsoftobj v08\_27\_04](#larsoftobj-v08_27_04)
    -   [lardataobj v08\_10\_05](#lardataobj-v08_10_05)
    -   [lardataalg v08\_13\_07](#lardataalg-v08_13_07)
    -   [larcorealg v08\_21\_02](#larcorealg-v08_21_02)
    -   [larcoreobj v08\_10\_04](#larcoreobj-v08_10_04)
    -   [larbatch v01\_52\_02](#larbatch-v01_52_02)
    -   [larutils v1\_25\_09](#larutils-v1_25_09)

[list of LArSoft releases](LArSoft_release_list)\
Download instructions for [larsoft v08\_48\_01\_01](http://scisoft.fnal.gov/scisoft/bundles/larsoft/v08_48_01_01/larsoft-v08_48_01_01.html)\
Download instructions for [just larsoftobj v08\_27\_04](http://scisoft.fnal.gov/scisoft/bundles/larsoftobj/v08_27_04/larsoftobj-v08_27_04.html)

Purpose
--------------------

-   **This is a test release**
-   build with geant4 v4\_10\_6\_p01
-   additionally pick up libwda v2\_28\_0 and related updates

Caveats
--------------------

-   This is a test release. The experiments will need to test and provide their own feature branches.
-   The larsoft code is on the v08\_48\_01\_g4\_test\_br branch.
-   PhysicsList was removed from larsim LegacyLArG4
    -   see [https://geant4-forum.web.cern.ch/t/missing-header-in-application/1622](https://geant4-forum.web.cern.ch/t/missing-header-in-application/1622)
-   The build of larsim GDMLUtils was disabled. It will need modification to build with geant4 v4\_10\_6\_p01.
-   There is no matching release of geant4reweight
    -   geant4reweight v01\_01\_00 is now available, but is not part of the v08\_48\_01\_01 distribution.
-   see [\#24284](/redmine/issues/24284 "Support: geant4reweight for geant4 v4_10_6_p01 (Closed)") and [\#24283](/redmine/issues/24283 "Support: review larsim for geant4 v4_10_6_p01 (Closed)")

Updated dependencies
----------------------------------------------

-   geant4 v4\_10\_6\_p01
-   nug4 v1\_05\_00
-   nutools v3\_07\_00
-   artg4tk v10\_00\_01
-   updated packages for libwda
    -   libwda v2\_28\_0
    -   ifdh\_art v2\_10\_04
    -   nuevdb v1\_02\_04
    -   nugen v1\_10\_04
    -   nusystematics v00\_10\_01

Change List
============================

larsoft v08\_48\_01\_01
-------------------------------------------------

-   2020-04-06 Lynn Garren : larsoft v08\_48\_01\_01 for larsoft v08\_48\_01\_01
-   2020-04-06 Lynn Garren : product versions

lareventdisplay v08\_12\_09\_01
-----------------------------------------------------------------

-   2020-04-06 Lynn Garren : lareventdisplay v08\_12\_09\_01 for larsoft v08\_48\_01\_01

larexamples v08\_06\_09\_01
---------------------------------------------------------

-   2020-04-06 Lynn Garren : larexamples v08\_06\_09\_01 for larsoft v08\_48\_01\_01

larg4 v08\_12\_07\_01
---------------------------------------------

-   2020-04-06 Lynn Garren : larg4 v08\_12\_07\_01 for larsoft v08\_48\_01\_01

larpandora v08\_12\_01\_01
-------------------------------------------------------

-   2020-04-06 Lynn Garren : larpandora v08\_12\_01\_01 for larsoft v08\_48\_01\_01

larrecodnn v08\_01\_02\_01
-------------------------------------------------------

-   2020-04-06 Lynn Garren : larrecodnn v08\_01\_02\_01 for larsoft v08\_48\_01\_01

larwirecell v08\_12\_08\_01
---------------------------------------------------------

-   2020-04-06 Lynn Garren : larwirecell v08\_12\_08\_01 for larsoft v08\_48\_01\_01

larana v08\_17\_01\_01
-----------------------------------------------

-   2020-04-06 Lynn Garren : larana v08\_17\_01\_01 for larsoft v08\_48\_01\_01

larreco v08\_30\_01\_01
-------------------------------------------------

-   2020-04-06 Lynn Garren : larreco v08\_30\_01\_01 for larsoft v08\_48\_01\_01

larsim v08\_22\_01\_01
-----------------------------------------------

-   2020-04-06 Lynn Garren : larsim v08\_22\_01\_01 for larsoft v08\_48\_01\_01
-   2020-04-06 Lynn Garren : build without ConfigurablePhysicsList, PhysicsList, and GDMLUtils

larevt v08\_11\_01\_01
-----------------------------------------------

-   2020-04-06 Lynn Garren : larevt v08\_11\_01\_01 for larsoft v08\_48\_01\_01

lardata v08\_15\_01
------------------------------------------

larcore v08\_11\_02
------------------------------------------

larpandoracontent v03\_15\_16
--------------------------------------------------------------

larsoftobj v08\_27\_04
------------------------------------------------

lardataobj v08\_10\_05
------------------------------------------------

lardataalg v08\_13\_07
------------------------------------------------

larcorealg v08\_21\_02
------------------------------------------------

larcoreobj v08\_10\_04
------------------------------------------------

larbatch v01\_52\_02
--------------------------------------------

larutils v1\_25\_09
------------------------------------------