LArSoft v06\_85\_00 Release Notes
======================================================================

-   **Table of contents**
-   [LArSoft v06\_85\_00 Release Notes](#LArSoft-v06_85_00-Release-Notes)
    -   [Purpose](#Purpose)
    -   [New features](#New-features)
    -   [Known problems](#Known-problems)
    -   [Updated dependencies](#Updated-dependencies)
-   [Change List](#Change-List)
    -   [larsoft v06\_85\_00](#larsoft-v06_85_00)
    -   [lareventdisplay v06\_22\_00](#lareventdisplay-v06_22_00)
    -   [larexamples v06\_14\_06](#larexamples-v06_14_06)
    -   [larpandora v06\_31\_04](#larpandora-v06_31_04)
    -   [larwirecell v06\_14\_06](#larwirecell-v06_14_06)
    -   [larana v06\_21\_01](#larana-v06_21_01)
    -   [larreco v06\_64\_02](#larreco-v06_64_02)
    -   [larsim v06\_53\_00](#larsim-v06_53_00)
    -   [larevt v06\_22\_04](#larevt-v06_22_04)
    -   [lardata v06\_47\_03](#lardata-v06_47_03)
    -   [larcore v06\_21\_02](#larcore-v06_21_02)
    -   [larpandoracontent v03\_13\_02](#larpandoracontent-v03_13_02)
    -   [larsoftobj v1\_50\_00](#larsoftobj-v1_50_00)
    -   [lardataobj v1\_36\_00](#lardataobj-v1_36_00)
    -   [lardataalg v1\_02\_01](#lardataalg-v1_02_01)
    -   [larcorealg v1\_24\_01](#larcorealg-v1_24_01)
    -   [larcoreobj v1\_24\_01](#larcoreobj-v1_24_01)
    -   [larbatch v01\_43\_00](#larbatch-v01_43_00)
    -   [larutils v1\_22\_09](#larutils-v1_22_09)

[list of LArSoft releases](LArSoft_release_list)\
Download instructions for [larsoft v06\_85\_00](http://scisoft.fnal.gov/scisoft/bundles/larsoft/v06_85_00/larsoft-v06_85_00.html)\
Download instructions for [just larsoftobj v1\_50\_00](http://scisoft.fnal.gov/scisoft/bundles/larsoftobj/v1_50_00/larsoftobj-v1_50_00.html)

Purpose
--------------------

-   changes in develop
-   approved feature branches
-   use art v2\_11\_03
-   add e17 support

New features
------------------------------

-   updates to lardataobj and larsim
    -   The standard implementation of photon library (\`phot::PhotonLibrary\`) has been changed to allocate the library memory kind-of-sparsely. This is designed to reduce the memory needed to run the typical photon library creation jobs. The changes have been performed trying to respect the new features introduced most recently.
    -   This does not replace the need to redesign PhotonVisibilityService and PhotonLibrary
    -   lardataobj develop
    -   larsim feature/gp\_PhotonLibrary
-   `feature/gp_ShowOpticalPhotons` of `lareventdisplay`
    -   "A parameter `services.SimulationDrawingOptions.ShowScintillationLight`, by default `false`, if enabled will flood the 3D event display with the full trajectories of the photons from scintillation^[1](#fn1)^ (there is a maximum, but it’s several millions). Note that these are photons simulated one by one by Geant4 when the specific physics list is used: in the normal usage, a lookup table is used (“photon library”), and Geant4 does not simulate any photon (and therefore this option enables nothing).\
        Therefore, one can consider this a photon simulation debugging tool."
-   lardataobj feature/tjyang\_recobslice
    -   new data product recob::Slice that saves the information after 3D clustering and will be the input to the restructured trajcluster.
-   e17 support
    -   At this time caffe and tensorflow are not available for e17.
    -   Problems reported by e17 tend to point to weaknesses in the code. Given this, it is best if the relevant code developers review and fix the experiment code, since appropriate solutions are not always obvious.

^1^ Actually, all particles with PDG ID 22 (γ) and 0 (*Rootino*… seriously!) with energy below 100 eV will be drawn.

Known problems
----------------------------------

-   larsim
    -   sim::TrackIDE is not filled in BackTracker.cc
    -   The fix is in the head of develop, but missed this release.

Updated dependencies
----------------------------------------------

-   art v2\_11\_03
-   nutools v2\_24\_01

Change List
============================

larsoft v06\_85\_00
------------------------------------------

-   2018-07-25 Lynn Garren : larsoft v06\_85\_00 for larsoft v06\_85\_00
-   2018-07-25 Lynn Garren : update versions
-   2018-07-23 Lynn Garren : add e17 qualifier

lareventdisplay v06\_22\_00
----------------------------------------------------------

-   2018-07-25 Lynn Garren : lareventdisplay v06\_22\_00 for larsoft v06\_85\_00
-   2018-07-24 Lynn Garren : Merge branch ‘feature/team\_for\_e17’ into release/v06\_85\_00
-   2018-07-23 Gianluca Petrillo : Added option to visualize scintillation photons in 3D display
-   2018-07-23 Lynn Garren : add e17 qualifier

larexamples v06\_14\_06
--------------------------------------------------

-   2018-07-25 Lynn Garren : larexamples v06\_14\_06 for larsoft v06\_85\_00
-   2018-07-23 Lynn Garren : add e17 qualifier

larpandora v06\_31\_04
------------------------------------------------

-   2018-07-25 Lynn Garren : larpandora v06\_31\_04 for larsoft v06\_85\_00
-   2018-07-23 Lynn Garren : add e17 qualifier

larwirecell v06\_14\_06
--------------------------------------------------

-   2018-07-25 Lynn Garren : larwirecell v06\_14\_06 for larsoft v06\_85\_00
-   2018-07-24 Lynn Garren : Merge branch ‘feature/team\_for\_e17’ into release/v06\_85\_00
-   2018-07-24 Usher, Tracy L : Remove extraneous output statement used when debugging
-   2018-07-24 Usher, Tracy L : Modifications (mostly) as directed by Brett to enable ability to change input source
-   2018-07-23 Lynn Garren : add e17 qualifier

larana v06\_21\_01
----------------------------------------

-   2018-07-25 Lynn Garren : larana v06\_21\_01 for larsoft v06\_85\_00
-   2018-07-24 Lynn Garren : Merge branch ‘feature/team\_for\_e17’ into release/v06\_85\_00
-   2018-07-23 Lynn Garren : add e17 qualifier
-   2018-07-19 Jose Alfonso Soto : Fixed reading the InputModule parameter as a vector

larreco v06\_64\_02
------------------------------------------

-   2018-07-25 Lynn Garren : Merge branch ‘release/v06\_85\_00’
-   2018-07-25 Lynn Garren : explicit cast to unsigned int for e17 debug build
-   2018-07-25 Lynn Garren : larreco v06\_64\_02 for larsoft v06\_85\_00
-   2018-07-25 Lynn Garren : larreco v06\_64\_02 for larsoft v06\_85\_00
-   2018-07-24 Kyle Knoepfel : Adjustments to support e17.
-   2018-07-23 Lynn Garren : add e17 qualifier

larsim v06\_53\_00
----------------------------------------

-   2018-07-25 Lynn Garren : larsim v06\_53\_00 for larsoft v06\_85\_00
-   2018-07-24 Lynn Garren : Merge branch ‘feature/team\_for\_e17’ into release/v06\_85\_00
-   2018-07-23 Lynn Garren : fix the boolean context usage
-   2018-07-23 Lynn Garren : add e17 qualifier
-   2018-07-23 Gianluca Petrillo : Replaced \`mf::LogDebug\` with \`LOG\_DEBUG\` in some lines of \`PhotonVisibilityService\`.
-   2018-07-23 Gianluca Petrillo : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_PhotonLibrary
-   2018-07-22 Gianluca Petrillo : PhotonLibrary now allocates memory lazy.

larevt v06\_22\_04
----------------------------------------

-   2018-07-25 Lynn Garren : larevt v06\_22\_04 for larsoft v06\_85\_00
-   2018-07-23 Lynn Garren : add e17 qualifier

lardata v06\_47\_03
------------------------------------------

-   2018-07-25 Lynn Garren : lardata v06\_47\_03 for larsoft v06\_85\_00
-   2018-07-24 Lynn Garren : Merge branch ‘feature/team\_for\_e17’ of ssh://cdcvs.fnal.gov/cvs/projects/lardata into feature/team\_for\_e17
-   2018-07-24 Kyle Knoepfel : Adjustment for e17.
-   2018-07-23 Lynn Garren : Merge branch ‘develop’ into feature/team\_for\_e17
-   2018-07-23 Gianluca Petrillo : Possible fix to a GCC 7 complaint.
-   2018-07-23 Lynn Garren : add e17 qualifier

larcore v06\_21\_02
------------------------------------------

-   2018-07-25 Lynn Garren : larcore v06\_21\_02 for larsoft v06\_85\_00
-   2018-07-23 Lynn Garren : add e17 qualifier

larpandoracontent v03\_13\_02
--------------------------------------------------------------

-   2018-07-25 Lynn Garren : larpandoracontent v03\_13\_02 for larsoft v06\_85\_00
-   2018-07-25 Lynn Garren : v03\_13\_02 with e17 support
-   2018-07-23 Lynn Garren : add e17 qualifier

larsoftobj v1\_50\_00
----------------------------------------------

-   2018-07-25 Lynn Garren : larsoftobj v1\_50\_00 for larsoft v06\_85\_00
-   2018-07-25 Lynn Garren : update versions
-   2018-07-23 Lynn Garren : add e17 qualifier

lardataobj v1\_36\_00
----------------------------------------------

-   2018-07-25 Lynn Garren : Merge branch ‘develop’ into release/v06\_85\_00
-   2018-07-25 Gianluca Petrillo : Fixed compilation of debug version of LazyVector.
-   2018-07-25 Lynn Garren : lardataobj v1\_36\_00 for larsoft v06\_85\_00
-   2018-07-24 Lynn Garren : Merge branch ‘feature/tjyang\_recobslice’ into release/v06\_85\_00
-   2018-07-24 Lynn Garren : Merge branch ‘feature/team\_for\_e17’ into release/v06\_85\_00
-   2018-07-24 Tingjun Yang : Add recob::Slice to save slice information.
-   2018-07-24 Gianluca Petrillo : \`util::LazyVector\` constructor now takes it easier with default values.
-   2018-07-24 Gianluca Petrillo : Avoid the copy of a class-static constant in \`util::LazyVector\`.
-   2018-07-23 Gianluca Petrillo : Merge branch ‘feature/gp\_LazyVector’ into develop
-   2018-07-23 Lynn Garren : add e17 qualifier
-   2018-07-23 Gianluca Petrillo : Merge remote-tracking branch ‘origin/develop’ into feature/gp\_LazyVector
-   2018-07-22 Jose Soto : edition of SimDriftedElectronCluster
-   2018-07-22 Gianluca Petrillo : Added \`data\_address()\` and \`shrink\_to\_fit()\` to \`util::LazyVector\`.
-   2018-07-20 Gianluca Petrillo : util::LazyVector, single block “sparse” vector.

lardataalg v1\_02\_01
----------------------------------------------

-   2018-07-25 Lynn Garren : lardataalg v1\_02\_01 for larsoft v06\_85\_00
-   2018-07-23 Lynn Garren : add e17 qualifier

larcorealg v1\_24\_01
----------------------------------------------

-   2018-07-25 Lynn Garren : larcorealg v1\_24\_01 for larsoft v06\_85\_00
-   2018-07-23 Lynn Garren : add e17 qualifier

larcoreobj v1\_24\_01
----------------------------------------------

-   2018-07-25 Lynn Garren : larcoreobj v1\_24\_01 for larsoft v06\_85\_00
-   2018-07-23 Lynn Garren : add e17 qualifier

larbatch v01\_43\_00
--------------------------------------------

-   2018-07-25 Lynn Garren : larbatch v01\_43\_00 for larsoft v06\_85\_00
-   2018-07-24 Herbert Greenlee : Make active projects calculation more robust.
-   2018-07-23 Herbert Greenlee : Modify definition of active projects to include recently ended projects.
-   2018-07-23 Herbert Greenlee : Merge branch ‘develop’ of ssh://cdcvs.fnal.gov/cvs/projects/larbatch into develop
-   2018-07-23 Herbert Greenlee : Fix issues with prestarted project dags.
-   2018-07-18 Lynn Garren : larsoft v06\_84\_00
-   2018-07-18 Herbert Greenlee : Make condor\_hadd\_sam.sh more compatible with latest version of condor\_lar.sh.

larutils v1\_22\_09
------------------------------------------

-   2018-07-25 Lynn Garren : larutils v1\_22\_09 for larsoft v06\_85\_00
-   2018-07-25 Lynn Garren : s70 and e17
-   2018-07-24 Thomas Junk : add e17
-   2018-07-19 Herbert Greenlee : Add colon-free workspace.
-   2018-07-19 Herbert Greenlee : Add error checking.