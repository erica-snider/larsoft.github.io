LArSoft v06\_00\_00\_rc5 Release Notes
===============================================================================

-   **Table of contents**
-   [LArSoft v06\_00\_00\_rc5 Release Notes](#LArSoft-v06_00_00_rc5-Release-Notes)
    -   [Purpose](#Purpose)
    -   [New features](#New-features)
    -   [Bug fixes](#Bug-fixes)
    -   [Updated dependencies](#Updated-dependencies)
-   [Change List](#Change-List)
    -   [larsoft v06\_00\_00\_rc5](#larsoft-v06_00_00_rc5)
    -   [lareventdisplay v06\_00\_00\_rc5](#lareventdisplay-v06_00_00_rc5)
    -   [larexamples v06\_00\_00\_rc5](#larexamples-v06_00_00_rc5)
    -   [larpandora v06\_00\_00\_rc5](#larpandora-v06_00_00_rc5)
    -   [larana v06\_00\_00\_rc5](#larana-v06_00_00_rc5)
    -   [larreco v06\_00\_00\_rc5](#larreco-v06_00_00_rc5)
    -   [larsim v06\_00\_00\_rc5](#larsim-v06_00_00_rc5)
    -   [larevt v06\_00\_00\_rc5](#larevt-v06_00_00_rc5)
    -   [lardata v06\_00\_00\_rc5](#lardata-v06_00_00_rc5)
    -   [larcore v06\_00\_00\_rc5](#larcore-v06_00_00_rc5)

[list of LArSoft releases](LArSoft_release_list)\
[Download instructions](http://scisoft.fnal.gov/scisoft/bundles/larsoft/v06_00_00_rc5/larsoft-v06_00_00_rc5.html)

Purpose
--------------------

-   Fix bug reported by MicroBooNE

New features
------------------------------

-   This release tracks larsoft v05\_13\_00

Bug fixes
------------------------

-   memory leak in root 6 [\#12945](/redmine/issues/12945 "Bug: Excessive memory use in ROOT 6 build of uboonecode (Closed)")

Updated dependencies
----------------------------------------------

  --------------- ------------- ------------ -----------------------------------------------------------------------------------------------------
  Product         Version       Qualifiers   Notes
  nutools         v2\_00\_01    e10          
  art             v2\_00\_03    e10:nu       s36
  root            v6\_06\_04b   e10:nu       [\#12945](/redmine/issues/12945 "Bug: Excessive memory use in ROOT 6 build of uboonecode (Closed)")
  larsoft\_data   v1\_01\_00                 
  mrb             v1\_07\_02                 
  --------------- ------------- ------------ -----------------------------------------------------------------------------------------------------

Change List
============================

larsoft v06\_00\_00\_rc5
---------------------------------------------------

-   2016-06-23 Lynn Garren : update dependency database
-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : Merge branch ‘develop’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : with art v2\_00\_03
-   2016-06-15 Lynn Garren : larsoft v05\_13\_00 for larsoft v05\_13\_00
-   2016-06-15 Lynn Garren : update product versions
-   2016-06-15 Lynn Garren : update dependency database
-   2016-06-10 Gianluca Petrillo : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_TestInfrastructure
-   2016-06-08 Lynn Garren : larsoft v05\_12\_01 for larsoft v05\_12\_01
-   2016-06-08 Lynn Garren : update product versions
-   2016-06-08 Lynn Garren : update dependency database
-   2016-05-20 Gianluca Petrillo : Update script for tests using geometry-aware tester environment

lareventdisplay v06\_00\_00\_rc5
-------------------------------------------------------------------

-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : Merge branch ‘develop’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : cetbuildtools v05\_04\_01
-   2016-06-15 Lynn Garren : lareventdisplay v05\_07\_02 for larsoft v05\_13\_00
-   2016-06-08 Lynn Garren : lareventdisplay v05\_07\_01 for larsoft v05\_12\_01

larexamples v06\_00\_00\_rc5
-----------------------------------------------------------

-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : larsoftobj changes
-   2016-06-23 Lynn Garren : Merge branch ‘develop’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : cetbuildtools v05\_04\_01
-   2016-06-16 Lynn Garren : add missing libraries to the link list
-   2016-06-16 Lynn Garren : the proper way to include a local test header
-   2016-06-15 Lynn Garren : larexamples v05\_07\_00 for larsoft v05\_13\_00
-   2016-06-14 Gianluca Petrillo : Minor additions to RemoveIsolatedSpacePoints documentation
-   2016-06-12 Gianluca Petrillo : Fixed bug in isolation algorithm stress test
-   2016-06-10 Gianluca Petrillo : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_ServiceExample
-   2016-06-07 Gianluca Petrillo : Algorithm/module example: RemoveIsolatedPoints
-   2016-06-08 Lynn Garren : larexamples v05\_06\_09 for larsoft v05\_12\_01
-   2016-06-07 Gianluca Petrillo : Changing the include guard style
-   2016-06-07 Gianluca Petrillo : Added reference to art workbook
-   2016-05-27 Gianluca Petrillo : Fixed some editor weirdness
-   2016-05-20 Gianluca Petrillo : ShowerCalibrationGalore example: reviewed documentation, changed details
-   2016-05-11 Gianluca Petrillo : Added new example: ShowerCalibrationGalore
-   2016-05-05 Gianluca Petrillo : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_ServiceExample
-   2016-05-03 Gianluca Petrillo : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_ServiceExample
-   2016-04-21 Hamlet : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_ServiceExample
-   2016-04-21 Hamlet : Removed a temporary editor file that slipped in.
-   2016-04-20 Hamlet : Added “AtomicNumber” service: a simple, single implementation service.
-   2016-04-19 Hamlet : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_ServiceExample
-   2016-04-13 Gianluca Petrillo : Service example stub

larpandora v06\_00\_00\_rc5
---------------------------------------------------------

-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : Merge branch ‘develop’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : cetbuildtools v05\_04\_01
-   2016-06-15 Lynn Garren : larpandora v05\_09\_07 for larsoft v05\_13\_00
-   2016-06-08 Lynn Garren : larpandora v05\_09\_06 for larsoft v05\_12\_01

larana v06\_00\_00\_rc5
-------------------------------------------------

-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : Merge branch ‘develop’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : cetbuildtools v05\_04\_01
-   2016-06-15 Lynn Garren : larana v05\_09\_04 for larsoft v05\_13\_00
-   2016-06-14 Gianluca Petrillo : Update after modification to the unit test infrastructure
-   2016-06-08 Lynn Garren : larana v05\_09\_03 for larsoft v05\_12\_01

larreco v06\_00\_00\_rc5
---------------------------------------------------

-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : Merge branch ‘develop’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : nutools v2\_00\_01
-   2016-06-15 Lynn Garren : larreco v05\_12\_02 for larsoft v05\_13\_00
-   2016-06-12 Tingjun Yang : Move dune cluster configurations to dunetpc.
-   2016-06-08 Lynn Garren : larreco v05\_12\_01 for larsoft v05\_12\_01
-   2016-06-08 Tingjun Yang : Convert range unit to cm.
-   2016-05-31 Dorota Stefan : add margin to isContained check in the track validation.
-   2016-05-27 Bruce Baller : Revert back to develop
-   2016-05-27 Bruce Baller : Revert back to develop version.
-   2016-05-27 Bruce Baller : Delete std::cout
-   2016-05-27 Bruce Baller : Merge branch ‘develop’ into feature/bb\_TrajCluster
-   2016-05-27 Bruce Baller : Clean up wire checking.
-   2016-05-27 Bruce Baller : Deal with special hits (Chi/DOF \< 0). Use fVertex2DIPCut instead of fMaxVertexTrajSep when attaching trajectories to vertices. Add wire number checks in FindJunkTraj. Change criteria for making TPs in MakeJunkTraj. Add call to CheckHiMultEndHits in CheckTraj. Deal with special hits in GetHitMultiplet.
-   2016-05-27 Bruce Baller : Change CheckHiMultEndHits to handle any trajectory
-   2016-05-25 Lynn Garren : larreco v05\_12\_00 for larsoft v05\_12\_00
-   2016-05-25 Robert Sulej : add typedef inside pma for displacement vector 2d and 3d
-   2016-05-25 Robert Sulej : Merge branch ‘develop’ into feature/rnd\_PmaNoTObject
-   2016-05-23 Aaron Higuera Pichardo : Add histograms for PC studies, works with isNeutrinoInt: false, efficiencies for charge pion, muon and charge kaons
-   2016-05-20 Aaron Higuera Pichardo : Include more efficiencies
-   2016-05-19 Bruce Baller : Make histo hits on long signal regions
-   2016-05-18 Bruce Baller : Merge branch ‘develop’ into feature/bb\_TrajCluster
-   2016-05-18 Bruce Baller : Create histo hits instead of crude hits
-   2016-05-18 Bruce Baller : Create histo hits instead of crude hits
-   2016-05-12 Dorota Stefan : CLHEP vectors
-   2016-05-12 Bruce Baller : Check for out of range trajectory point in SignalAtTp
-   2016-05-11 Dorota Stefan : TObject replaced with another vector from ROOT
-   2016-05-11 Lynn Garren : larreco v05\_11\_01 for larsoft v05\_11\_01
-   2016-05-11 Bruce Baller : Check for invalid MC particle.

larsim v06\_00\_00\_rc5
-------------------------------------------------

-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : Merge branch ‘LARSOFT\_SUITE\_v05\_13\_00-branch’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : larsoft\_data v1\_01\_00
-   2016-06-15 Lynn Garren : larsim v05\_13\_00 for larsoft v05\_13\_00
-   2016-06-15 Jeremy H : A couple of updates to GENIE nucleon decay parser module – Jeremy Hewes
-   2016-06-13 Jeremy H : Temporarily restoring previous version of NDKGen\_module.cc pending further merges – Jeremy Hewes
-   2016-06-13 Jeremy H : Bugfix: committing changes which restore previously defunct GENIE parser module NDKGen\_module.cc – J. Hewes
-   2016-06-13 Kevin Wood : Generalized vertex assignment in NDKGen\_module.cc for geometries with any number of TPCs (still assumes single cryostat)
-   2016-06-12 Kevin Wood : Made vertex assignment uniformly distributed
-   2016-06-09 Lynn Garren : use larsimobj v06\_00\_00\_rc4
-   2016-06-08 Lynn Garren : larsim v05\_12\_01 for larsoft v05\_12\_01

larevt v06\_00\_00\_rc5
-------------------------------------------------

-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : Merge branch ‘develop’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : cetbuildtools v05\_04\_01
-   2016-06-15 Lynn Garren : larevt v05\_07\_02 for larsoft v05\_13\_00
-   2016-06-08 Lynn Garren : larevt v05\_07\_01 for larsoft v05\_12\_01

lardata v06\_00\_00\_rc5
---------------------------------------------------

-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : Merge branch ‘develop’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : nutools v2\_00\_01
-   2016-06-15 Lynn Garren : lardata v05\_09\_00 for larsoft v05\_13\_00
-   2016-06-15 Gianluca Petrillo : Fixed capitalization problem
-   2016-06-14 Gianluca Petrillo : Forgot to compile a test executable…
-   2016-06-10 Gianluca Petrillo : Update to LArSoft 5.12.1
-   2016-06-09 Lynn Garren : use lardataobj v06\_00\_00\_rc4
-   2016-06-09 Lynn Garren : Merge branch ‘develop’ into release/v05\_12\_01
-   2016-06-08 Gianluca Petrillo : Merge branch ‘feature/gp\_FixHuffmannCompress’ into develop
-   2016-06-08 Gianluca Petrillo : Fixed a minor bug in Huffman compression algorithm
-   2016-06-08 Gianluca Petrillo : Added another test of compression
-   2016-06-08 Lynn Garren : lardata v05\_08\_03 for larsoft v05\_12\_01
-   2016-05-20 Gianluca Petrillo : Added unit tests for detector info providers.
-   2016-05-06 Gianluca Petrillo : Moved testing utilities to larcore/TestUtils
-   2016-05-05 Gianluca Petrillo : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_TestInfrastructure
-   2016-05-03 Gianluca Petrillo : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_TestInfrastructure
-   2016-04-20 Hamlet : Update after test header move

larcore v06\_00\_00\_rc5
---------------------------------------------------

-   2016-06-23 Lynn Garren : rc5
-   2016-06-23 Lynn Garren : larsoftobj changes again
-   2016-06-23 Lynn Garren : Merge branch ‘LARSOFT\_SUITE\_v05\_13\_00-branch’ into v06\_00\_00\_art2
-   2016-06-23 Lynn Garren : art v2\_00\_03
-   2016-06-15 Lynn Garren : larcore v05\_08\_00 for larsoft v05\_13\_00
-   2016-06-10 Gianluca Petrillo : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_TestInfrastructure
-   2016-06-10 Gianluca Petrillo : Added method to extend BoundedBoxGeo objects
-   2016-04-19 Hamlet : Fixed typo
-   2016-06-09 Lynn Garren : use larcoreobj v06\_00\_00\_rc4
-   2016-05-20 Gianluca Petrillo : Test infrastructure revised.
-   2016-05-05 Gianluca Petrillo : Test infrastructure revamp.
-   2016-04-19 Hamlet : Moved generic unit test infrastructure from test/Geometry into larcore/TestUtils
-   2016-04-19 Hamlet : Fixed typo