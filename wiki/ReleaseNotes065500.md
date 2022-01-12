LArSoft v06\_55\_00 Release Notes
======================================================================

-   **Table of contents**
-   [LArSoft v06\_55\_00 Release Notes](#LArSoft-v06_55_00-Release-Notes)
    -   [Purpose](#Purpose)
    -   [New features](#New-features)
    -   [Bug fixes](#Bug-fixes)
    -   [Updated dependencies](#Updated-dependencies)
-   [Change List](#Change-List)
    -   [larsoft v06\_55\_00](#larsoft-v06_55_00)
    -   [lareventdisplay v06\_14\_00](#lareventdisplay-v06_14_00)
    -   [larexamples v06\_07\_06](#larexamples-v06_07_06)
    -   [larpandora v06\_17\_03](#larpandora-v06_17_03)
    -   [larwirecell v06\_08\_01](#larwirecell-v06_08_01)
    -   [larana v06\_11\_00](#larana-v06_11_00)
    -   [larreco v06\_44\_00](#larreco-v06_44_00)
    -   [larsim v06\_33\_00](#larsim-v06_33_00)
    -   [larevt v06\_16\_06](#larevt-v06_16_06)
    -   [lardata v06\_31\_02](#lardata-v06_31_02)
    -   [larcore v06\_15\_03](#larcore-v06_15_03)
    -   [larpandoracontent v03\_08\_01](#larpandoracontent-v03_08_01)
    -   [larsoftobj v1\_29\_01](#larsoftobj-v1_29_01)
    -   [lardataobj v1\_21\_02](#lardataobj-v1_21_02)
    -   [larcorealg v1\_09\_01](#larcorealg-v1_09_01)
    -   [larcoreobj v1\_16\_01](#larcoreobj-v1_16_01)
    -   [larbatch v01\_32\_06](#larbatch-v01_32_06)
    -   [larutils v1\_20\_01](#larutils-v1_20_01)

[list of LArSoft releases](LArSoft_release_list)
Download instructions for [larsoft v06\_55\_00](http://scisoft.fnal.gov/scisoft/bundles/larsoft/v06_55_00/larsoft-v06_55_00.html)
Download instructions for [just larsoftobj v1\_29\_01](http://scisoft.fnal.gov/scisoft/bundles/larsoftobj/v1_29_01/larsoftobj-v1_29_01.html)

Purpose
--------------------

-   changes to develop
-   build with art 2.08.04

New features
------------------------------

Bug fixes
------------------------

-   [\#17898](/redmine/issues/17898 "Bug: Cannot get hit-track association in file produced with v06_26_01_07 using develop branch (Closed)") resolved with art 2.08.04
    -   see [Kyle’s presentation](https://indico.fnal.gov/event/15586/contribution/4/material/slides/0.pdf)
-   [\#17926](/redmine/issues/17926 "Necessary Maintenance: Implement a better name for the track proxy accessor to the unfitted trajectory. (Closed)")
-   [\#18002](/redmine/issues/18002 "Necessary Maintenance: Missing override directives in detinfo::LArPropertiesStandard (Closed)")

Updated dependencies
----------------------------------------------

||
|Product|Version|Qualifiers|Notes|
|canvas|v3\_00\_03|e14:nu|[Release Notes](/redmine/projects/canvas/wiki/Release_Notes)|
|gallery|v1\_05\_03|e14:nu|[Release Notes](/redmine/projects/gallery/wiki/Release_Notes_10503)|
|art|v2\_08\_04|e14:nu|[Release Notes](/redmine/projects/art/wiki/Series_208)|
|ifdh\_art|v2\_03\_05|e14:nu:s56||
|artdaq\_core|v1\_07\_12|e14:nu:s56||
|nusimdata|v1\_08\_04|e14||
|nutools|v2\_16\_06|e14|[Release Notes](/redmine/projects/nutools/wiki/NuTools_Release_Notes#nutools-v2_16_06-10232017)|

Change List
============================

larsoft v06\_55\_00
------------------------------------------

-   2017-10-25 Lynn Garren : larsoft v06\_55\_00 for larsoft v06\_55\_00
-   2017-10-25 Lynn Garren : fix genie and dk2nu
-   2017-10-25 Lynn Garren : update product versions
-   2017-10-25 Lynn Garren : update dependency database
-   2017-10-24 Lynn Garren : ifdh\_art v2\_03\_05

lareventdisplay v06\_14\_00
----------------------------------------------------------

-   2017-10-25 Lynn Garren : lareventdisplay v06\_14\_00 for larsoft v06\_55\_00
-   2017-10-20 Tingjun Yang : Take into account particle generation time. Turn off cosmics in MCTruthVectors2D.
-   2017-10-20 Tingjun Yang : fix color code for track id text.
-   2017-10-20 Tingjun Yang : Display cluster id instead of index so we can see negative id.

larexamples v06\_07\_06
--------------------------------------------------

-   2017-10-25 Lynn Garren : larexamples v06\_07\_06 for larsoft v06\_55\_00

larpandora v06\_17\_03
------------------------------------------------

-   2017-10-25 Lynn Garren : larpandora v06\_17\_03 for larsoft v06\_55\_00

larwirecell v06\_08\_01
--------------------------------------------------

-   2017-10-25 Lynn Garren : larwirecell v06\_08\_01 for larsoft v06\_55\_00

larana v06\_11\_00
----------------------------------------

-   2017-10-25 Lynn Garren : larana v06\_11\_00 for larsoft v06\_55\_00
-   2017-10-20 Nick Grant : Merge branch ‘develop’ of ssh://cdcvs.fnal.gov/cvs/projects/larana into develop
-   2017-10-19 Nick Grant : Update MVAPID\_module.cc, MVAAlg.h and MVAAlg.cxx to get detector dimensions and calculate wire angles from geometry

larreco v06\_44\_00
------------------------------------------

-   2017-10-25 Lynn Garren : larreco v06\_44\_00 for larsoft v06\_55\_00
-   2017-10-24 Lynn Garren : nutools v2\_16\_06
-   2017-10-22 Robert Sulej : remove cout
-   2017-10-22 Robert Sulej : move nu event dumping to dunetpc (specific to dune geo)
-   2017-10-21 Robert Sulej : Merge branch ‘develop’ of ssh://cdcvs.fnal.gov/cvs/projects/larreco into develop
-   2017-10-20 Robert Sulej : align all wire offsets, cleanup code
-   2017-10-20 Robert Sulej : pass output node name as cmd line param

larsim v06\_33\_00
----------------------------------------

-   2017-10-25 Lynn Garren : larsim v06\_33\_00 for larsoft v06\_55\_00
-   2017-10-21 Jason Stock : removing G4ModuleLable from ParticleInventoryService. It isn’t needed outside the service provider.
-   2017-10-20 Jason Stock : Finalizing fhicl validation in ParticleInventoryService and passthrough of a fhicl table to ParticleInventory
-   2017-10-20 Jason Stock : squash renaming a couple items
-   2017-10-20 Jason Stock : Making the ParticleInventoryService fhicl validation ready.
-   2017-10-19 Jason Stock : Bug Fix in the PrepEvent for the ParticleInventory service provider. Missing negation.
-   2017-10-19 Jason Stock : Merge remote-tracking branch ‘origin/develop’ into feature/JStock\_ParticleInventory
-   2017-10-19 Jason Stock : Making the TrackIdToEveTrackId function constant. (for use in BackTracker).
-   2017-10-19 Jason Stock : Adding TrackIdToEveTrackId function to ParticleInventory (Needed for new HitToEveId function in BackTracker).
-   2017-10-18 Jason Stock : Merge remote-tracking branch ‘remotes/origin/develop’ into feature/JStock\_ParticleInventory
-   2017-10-18 Jason Stock : Final touches on some of the template methods. Implimenting last cleanup and data retrieval.
-   2017-10-17 Jason Stock : Adding in useful error handeling.
-   2017-10-17 Jason Stock : Update to ParticleInventory using reccomendations for Gianluca to clean up a couple points and begin adding fhicl validation support.
-   2017-10-13 Jason Stock : Bandaid for the ParticleInventoryService provider type until I can sit down with an expert and do it right.
-   2017-10-13 Jason Stock : Added larprovider type to ParticleInventoryService
-   2017-10-13 Jason Stock : Slight change in naming conventions to make functions which return pointers or vectors of pointers more explicit
-   2017-10-12 Jason Stock : Added header for Message Facility
-   2017-10-12 Jason Stock : Updating ParticleInventory functions to be const and making the cache objects mutable.
-   2017-10-12 Jason Stock : Fixed a bug. The run flag was backwards for realData vs Simulation.
-   2017-10-12 Jason Stock : Changing the use of the PartInv so that a pointer to the instance can be given to BackTracker and PhotonBackTracker.
-   2017-10-12 Jason Stock : removing fhicl support due to errors. I’ll need to talk to someone about the right way to configure ParticleInventory.
-   2017-10-12 Jason Stock : Making Particle Inventory fhcl configurable.
-   2017-10-12 Jason Stock : Reduce dependency on art. (Only art::Handle left).
-   2017-10-11 Jason Stock : Quick squash to clean up commits before sharing. Initial Commit of ParticleInventoryService.

larevt v06\_16\_06
----------------------------------------

-   2017-10-25 Lynn Garren : larevt v06\_16\_06 for larsoft v06\_55\_00

lardata v06\_31\_02
------------------------------------------

-   2017-10-25 Lynn Garren : lardata v06\_31\_02 for larsoft v06\_55\_00
-   2017-10-24 Lynn Garren : nutools v2\_16\_06
-   2017-10-24 Gianluca Petrillo : Track proxy metod name trajectory() (and related) renamed.
-   2017-10-24 Lynn Garren : virtual override for issue 18002

larcore v06\_15\_03
------------------------------------------

-   2017-10-25 Lynn Garren : larcore v06\_15\_03 for larsoft v06\_55\_00
-   2017-10-24 Lynn Garren : art v2\_08\_04

larpandoracontent v03\_08\_01
--------------------------------------------------------------

larsoftobj v1\_29\_01
----------------------------------------------

-   2017-10-25 Lynn Garren : larsoftobj v1\_29\_01 for larsoft v06\_55\_00
-   2017-10-25 Lynn Garren : cmake v3\_9\_2
-   2017-10-25 Lynn Garren : update product versions
-   2017-10-24 Lynn Garren : gallery v1\_05\_03

lardataobj v1\_21\_02
----------------------------------------------

-   2017-10-25 Lynn Garren : lardataobj v1\_21\_02 for larsoft v06\_55\_00
-   2017-10-24 Lynn Garren : nusimdata v1\_08\_04

larcorealg v1\_09\_01
----------------------------------------------

-   2017-10-25 Lynn Garren : larcorealg v1\_09\_01 for larsoft v06\_55\_00

larcoreobj v1\_16\_01
----------------------------------------------

-   2017-10-25 Lynn Garren : larcoreobj v1\_16\_01 for larsoft v06\_55\_00
-   2017-10-24 Lynn Garren : canvas v3\_00\_03

larbatch v01\_32\_06
--------------------------------------------

-   2017-10-25 Lynn Garren : larbatch v01\_32\_06 for larsoft v06\_55\_00
-   2017-10-06 Herbert Greenlee : Get validate-on-worker from stage rather than project in gui app.

larutils v1\_20\_01
------------------------------------------

-   2017-10-25 Lynn Garren : larutils v1\_20\_01 for larsoft v06\_55\_00
-   2017-10-24 Lynn Garren : adding s56 for art v2\_08\_04
-   2017-10-20 Tingjun Yang : Change ncores to 4 for mac builds for lariat.