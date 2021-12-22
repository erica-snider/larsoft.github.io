LArG4 Migration Notes
================================================

The old geant4 interface in larsim is being replaced with a new package, larg4, and the associated artg4tk package.\
This page has notes about necessary changes.

**This is a preliminary draft.**
-----------------------------------------------------------------

fcl files
------------------------

The experiment top-level control fhicl files will at least need to replace their “largeant” steps in their fhicl files with the new modules:

-   old way:
    -   simulate: [ “rns”, “largeant” ]
-   new way:
    -   simulate: [ “rns”, “larg4Main”, “elecDrift”, “photonProp” ]
    -   where “larg4Main”, “elecDrift”, and “photonProp” are the new modules that replace “largeant”.

An example of how these modules are configured for testing purposes is:\

    physics:{

     producers: {

       rns: { module_type: "RandomNumberSaver" }

       larg4Main: { module_type: "larg4Main" 
         enableVisualization: false
         macroPath: ".:./macros" 
         visMacro: "vis.mac" 
       }

       elecDrift: { module_type: "SimDriftElectrons" 
         SimulationLabel: "larg4Main:LArG4DetectorServicevolTPCActive" 
         StoreDriftedElectronClusters: true
       }

       photonProp: { module_type: "PhotonLibraryPropagation" 
         DoSlowComponent: false
         RiseTimeFast: 6
         RiseTimeSlow: 1300
         EDepModuleLabels: [ "larg4Main:LArG4DetectorServicevolTPCActive" ]
       }

     }