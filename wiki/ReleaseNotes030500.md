LArSoft v03\_05\_00 Release Notes
======================================================================

-   **Table of contents**
-   [LArSoft v03\_05\_00 Release Notes](#LArSoft-v03_05_00-Release-Notes)
    -   [Purpose](#Purpose)
    -   [New features](#New-features)
    -   [Bug fixes](#Bug-fixes)
    -   [Updated dependencies](#Updated-dependencies)
-   [Change List](#Change-List)
    -   [larsoft v03\_05\_00](#larsoft-v03_05_00)
    -   [lareventdisplay v03\_03\_00](#lareventdisplay-v03_03_00)
    -   [larexamples v03\_02\_10](#larexamples-v03_02_10)
    -   [larpandora v03\_04\_03](#larpandora-v03_04_03)
    -   [larana v03\_03\_07](#larana-v03_03_07)
    -   [larreco v03\_04\_02](#larreco-v03_04_02)
    -   [larsim v03\_03\_02](#larsim-v03_03_02)
    -   [larevt v03\_03\_00](#larevt-v03_03_00)
    -   [lardata v03\_05\_00](#lardata-v03_05_00)
    -   [larcore v03\_04\_00](#larcore-v03_04_00)

[list of LArSoft releases](LArSoft_release_list)\
[Download instructions](http://scisoft.fnal.gov/scisoft/bundles/larsoft/v03_05_00/larsoft-v03_05_00.html)

Purpose
--------------------

-   Changes in develop since v03\_04\_06
-   MicroBoone request

New features
------------------------------

-   UniqueRangeSet object in lardata
-   AuxDetGeo trapezoid implimentation change
-   [\#7532](/redmine/issues/7532 "Feature: Make dump_wires.fcl independent of geometry (Closed)"): make DumpWires module independent of geometry

Bug fixes
------------------------

Updated dependencies
----------------------------------------------

  ---------- ------------- ----------- --------------------------------------------------
  Product    Version       Qualifier   Notes
  larbatch   v01\_00\_01               build with cetbuildtools v4\_04\_03
  git        v1\_8\_5\_6               security update
  mrb        v1\_03\_04                improvements for building null flavored products
  ---------- ------------- ----------- --------------------------------------------------

Change List
============================

larsoft v03\_05\_00
------------------------------------------

-   2015-01-05 Lynn Garren : make sure cetbuildtools v4\_04\_03 is available
-   2015-01-05 Lynn Garren : larsoft v03\_05\_00 product list
-   2015-01-05 Lynn Garren : lardata Range.h and UniqueRangeSet.h

lareventdisplay v03\_03\_00
----------------------------------------------------------

-   2015-01-05 Lynn Garren : lareventdisplay v03\_03\_00 for larsoft v03\_05\_00
-   2015-01-02 Tingjun Yang : Display all possible wire segments for each wire. This is only relevant for wrapped wires.
-   2014-12-30 Bruce Baller : Prevent accessing nonsensical color values

larexamples v03\_02\_10
--------------------------------------------------

-   2015-01-05 Lynn Garren : larexamples v03\_02\_10 for larsoft v03\_05\_00

larpandora v03\_04\_03
------------------------------------------------

-   2015-01-05 Lynn Garren : larpandora v03\_04\_03 for larsoft v03\_05\_00

larana v03\_03\_07
----------------------------------------

-   2015-01-05 Lynn Garren : for larsoft v03\_05\_00
-   2014-12-21 Alex Himmel : Add an “instance name” to the parameter list for this module. This is blank in the default setup of the module, but needs to be set to a value in order to read in data products from the LBNE 35ton data.
-   2014-12-18 Lynn Garren : larsoft v03\_04\_06
-   2014-12-16 Sarah Lockwitz : Added error score values for tracks with poorly found end points… just in case

larreco v03\_04\_02
------------------------------------------

-   2015-01-05 Lynn Garren : larreco v03\_04\_02 for larsoft v03\_05\_00
-   2015-01-02 Tingjun Yang : Change SeedFinderAlgorithm to SeedFinder.
-   2015-01-02 Tingjun Yang : Clean up fcl files.
-   2014-12-29 Tingjun Yang : use ConvertTicksToX to get x coordinate for each spacepoint

larsim v03\_03\_02
----------------------------------------

-   2015-01-05 Lynn Garren : larsim v03\_03\_02 for larsoft v03\_05\_00
-   2014-12-30 Lynn Garren : using ROOT\_EGPYTHIA6 which is now properly defined by cetbuildtools v4\_04\_02
-   2014-12-29 Lynn Garren : use the predefined library name
-   2014-12-22 Gianluca Petrillo : Added explicit link to Root Pytia6 library, silently needed by Genie

larevt v03\_03\_00
----------------------------------------

-   2015-01-05 Lynn Garren : larevt v03\_03\_00 for larsoft v03\_05\_00
-   2014-12-18 Lynn Garren : larsoft v03\_04\_06
-   2014-12-17 Gianluca Petrillo : Issue [\#7532](/redmine/issues/7532 "Feature: Make dump_wires.fcl independent of geometry (Closed)"): make DumpWires module independent of geometry

lardata v03\_05\_00
------------------------------------------

-   2015-01-05 Lynn Garren : lardata v03\_05\_00 for larsoft v03\_05\_00
-   2015-01-02 Wesley Ketchum : allow ranges to have same start and end
-   2015-01-01 Wesley Ketchum : add in range tool written by kazu

larcore v03\_04\_00
------------------------------------------

-   2015-01-05 Lynn Garren : larcore v03\_04\_00 for larsoft v03\_05\_00
-   2014-12-24 Tyler Alion : Merge branch ‘feature/AuxDetTrap’ into develop. This generalizes the AuxDetGeo object to handle trapezoids differeing in x dimension but not y (local coordinates). In the case of a box, the two width dimensions are the same and all behaves as before, which has been thoroughly tested in the microboone geometry, which is the only other user. A bug was fixed in Geometry::FindAuxDetAtPosition, so microboone will see a difference in their muon counter simulation; the local coordinates system used to be applied where a world coordinate system should have. Now the input position is transformed to local coordinates. lbne35t jobs should keep using the default v2 geometry until larsim/LArG4/AuxDetReadoutGeometry.cxx can be rewritten to be less limiting – a **necessary** change to be able to use lbne35t4apa\_v3.
-   2014-12-24 Tyler Alion : Change the AuxDetGeo trapezoid implimentation to not assume the smaller width to be at local coordinate +z/2, instead using HalfWidth1 and HalfWidth2.
-   2014-12-19 Tyler Alion : Merge branch ‘develop’ into feature/AuxDetTrap
-   2014-12-19 Tyler Alion : rge branch ‘develop’ of ssh://cdcvs.fnal.gov/cvs/projects/larcore into develop
-   2014-12-17 Gianluca Petrillo : Issue 7531: add a new “standard” geometry
-   2014-12-12 Tyler Alion : add comment to the one new AuxDetGeo data member that facilitates trapezoidal AuxDets
-   2014-12-04 Tyler Alion : Generalize AuxDetGeo and FindAuxDetAtPosition to handle trapezoidal AuxDets. This fixes a bug which before overlooked any rotation the AuxDets have in local coordinates.