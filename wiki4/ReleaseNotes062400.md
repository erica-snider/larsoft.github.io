LArSoft v06\_24\_00 Release Notes[¶](#LArSoft-v06_24_00-Release-Notes)
======================================================================

-   **Table of contents**
-   [LArSoft v06\_24\_00 Release Notes](#LArSoft-v06_24_00-Release-Notes)
    -   [Purpose](#Purpose)
    -   [New features](#New-features)
    -   [Bug fixes](#Bug-fixes)
    -   [Updated dependencies](#Updated-dependencies)
-   [Change List](#Change-List)
    -   [larsoft v06\_24\_00](#larsoft-v06_24_00)
    -   [lareventdisplay v06\_02\_12](#lareventdisplay-v06_02_12)
    -   [larexamples v06\_01\_13](#larexamples-v06_01_13)
    -   [larpandora v06\_06\_01](#larpandora-v06_06_01)
    -   [larwirecell v06\_00\_10](#larwirecell-v06_00_10)
    -   [larana v06\_03\_16](#larana-v06_03_16)
    -   [larreco v06\_18\_01](#larreco-v06_18_01)
    -   [larsim v06\_12\_00](#larsim-v06_12_00)
    -   [larevt v06\_07\_07](#larevt-v06_07_07)
    -   [lardata v06\_14\_02](#lardata-v06_14_02)
    -   [larcore v06\_05\_02](#larcore-v06_05_02)
    -   [larpandoracontent v03\_02\_00](#larpandoracontent-v03_02_00)
    -   [larsoftobj v1\_10\_01](#larsoftobj-v1_10_01)
    -   [lardataobj v1\_10\_01](#lardataobj-v1_10_01)
    -   [larcoreobj v1\_06\_02](#larcoreobj-v1_06_02)
    -   [larbatch v01\_26\_05](#larbatch-v01_26_05)
    -   [larutils v1\_11\_00](#larutils-v1_11_00)

[list of LArSoft releases](LArSoft_release_list)\
Download instructions for [larsoft v06\_24\_00](http://scisoft.fnal.gov/scisoft/bundles/larsoft/v06_24_00/larsoft-v06_24_00.html)\
Download instructions for [just larsoftobj v1\_10\_01](http://scisoft.fnal.gov/scisoft/bundles/larsoftobj/v1_10_01/larsoftobj-v1_10_01.html)


Purpose[¶](#Purpose)
--------------------

-   changes to develop
-   approved features


New features[¶](#New-features)
------------------------------

-   larsim, uboonecode feature/zennamo\_FunctionalFormFlux
    -   [slides](https://indico.fnal.gov/getFile.py/access?contribId=3&resId=0&materialId=slides&confId=13730)


Bug fixes[¶](#Bug-fixes)
------------------------

-   Changed deprecation warning to be less intrusive (see issue [\#14281](/redmine/issues/14281 "Task: Provide an interface for access of reconstructed track information (Accepted)") )


Updated dependencies[¶](#Updated-dependencies)
----------------------------------------------

  --------------- ------------ ------------ --------------------------------------------------------------------------------------------------
  Product         Version      Qualifiers   Notes
  nutools         v2\_10\_00   e10          [NuTools\_Release\_Notes](/redmine/projects/nutools/wiki/NuTools_Release_Notes#nutools-v2_10_00)
  cetbuildtools   v5\_06\_06                recognize \*.tcc headers
  --------------- ------------ ------------ --------------------------------------------------------------------------------------------------


Change List[¶](#Change-List)
============================


larsoft v06\_24\_00[¶](#larsoft-v06_24_00)
------------------------------------------

-   2017-02-07 Lynn Garren : larsoft v06\_24\_00 for larsoft v06\_24\_00
-   2017-02-07 Lynn Garren : no more special handling of lardata
-   2017-02-07 Lynn Garren : update product versions
-   2017-02-02 Lynn Garren : using correct syntax


lareventdisplay v06\_02\_12[¶](#lareventdisplay-v06_02_12)
----------------------------------------------------------

-   2017-02-07 Lynn Garren : lareventdisplay v06\_02\_12 for larsoft v06\_24\_00


larexamples v06\_01\_13[¶](#larexamples-v06_01_13)
--------------------------------------------------

-   2017-02-07 Lynn Garren : larexamples v06\_01\_13 for larsoft v06\_24\_00


larpandora v06\_06\_01[¶](#larpandora-v06_06_01)
------------------------------------------------

-   2017-02-07 Lynn Garren : larpandora v06\_06\_01 for larsoft v06\_24\_00


larwirecell v06\_00\_10[¶](#larwirecell-v06_00_10)
--------------------------------------------------

-   2017-02-07 Lynn Garren : larwirecell v06\_00\_10 for larsoft v06\_24\_00


larana v06\_03\_16[¶](#larana-v06_03_16)
----------------------------------------

-   2017-02-07 Lynn Garren : larana v06\_03\_16 for larsoft v06\_24\_00
-   2017-02-03 Gianluca Petrillo : Fixed recob::Track deprecation warnings.


larreco v06\_18\_01[¶](#larreco-v06_18_01)
------------------------------------------

-   2017-02-07 Lynn Garren : larreco v06\_18\_01 for larsoft v06\_24\_00
-   2017-02-03 Gianluca Petrillo : Fixed recob::Track deprecation warnings.


larsim v06\_12\_00[¶](#larsim-v06_12_00)
----------------------------------------

-   2017-02-07 Lynn Garren : larsim v06\_12\_00 for larsoft v06\_24\_00
-   2017-02-07 Lynn Garren : Merge branch ‘feature/zennamo\_FunctionalFormFlux’ into release/v06\_24\_00
-   2017-02-06 Gianluca Petrillo : MCReco module: release some memory after use.
-   2017-02-03 Joseph Zennamo : Merge branch ‘develop’ into feature/zennamo\_FunctionalFormFlux
-   2017-02-02 Lynn Garren : larsoft v06\_23\_00
-   2017-02-02 Gianluca Petrillo : Random number engines update in CORSIKAGen module.
-   2017-01-31 Joseph Zennamo : Adding an explicit fcl parameter for the binning of the functional flux
-   2017-01-24 Joseph Zennamo : modified fcl parameters to work with a new nutools feature-branch (with same name) that allows users to define a functional form for the neutrino flux and generate events within a user defined energy range


larevt v06\_07\_07[¶](#larevt-v06_07_07)
----------------------------------------

-   2017-02-07 Lynn Garren : larevt v06\_07\_07 for larsoft v06\_24\_00


lardata v06\_14\_02[¶](#lardata-v06_14_02)
------------------------------------------

-   2017-02-07 Lynn Garren : lardata v06\_14\_02 for larsoft v06\_24\_00


larcore v06\_05\_02[¶](#larcore-v06_05_02)
------------------------------------------


larpandoracontent v03\_02\_00[¶](#larpandoracontent-v03_02_00)
--------------------------------------------------------------

-   2017-02-07 Lynn Garren : larpandoracontent v03\_02\_00 for larsoft v06\_24\_00
-   2017-02-07 Lynn Garren : larpandoracontent v03\_02\_00
-   2017-02-02 John Marshall : Merge branch ‘feature/LArShowerPfo’ into develop
-   2017-02-02 John Marshall : Remove unused LArShowerPfo variable.
-   2017-02-02 John Marshall : Deactivate existing, placeholder ShowerParticleBuilding algorithm for now.
-   2017-02-02 John Marshall : Add LArShowerPfo properties, to hold shower additional/derived shower properties whilst in Pandora.
-   2017-01-23 Lynn Garren : fix typo


larsoftobj v1\_10\_01[¶](#larsoftobj-v1_10_01)
----------------------------------------------

-   2017-02-07 Lynn Garren : larsoftobj v1\_10\_01 for larsoft v06\_24\_00


lardataobj v1\_10\_01[¶](#lardataobj-v1_10_01)
----------------------------------------------

-   2017-02-07 Lynn Garren : lardataobj v1\_10\_01 for larsoft v06\_24\_00
-   2017-02-07 Lynn Garren : lardataobj v1\_10\_01 for larsoft v06\_24\_00
-   2017-02-06 Gianluca Petrillo : Exceptionally ignore warnings in unit tests testing deprecated methods.
-   2017-02-03 Gianluca Petrillo : Changed deprecation warning to be less intrusive (see issue [\#14281](/redmine/issues/14281 "Task: Provide an interface for access of reconstructed track information (Accepted)") )


larcoreobj v1\_06\_02[¶](#larcoreobj-v1_06_02)
----------------------------------------------


larbatch v01\_26\_05[¶](#larbatch-v01_26_05)
--------------------------------------------

-   2017-02-07 Lynn Garren : larbatch v01\_26\_05 for larsoft v06\_24\_00
-   2017-02-06 Tingjun Yang : Improve deleting tempdir.


larutils v1\_11\_00[¶](#larutils-v1_11_00)
------------------------------------------