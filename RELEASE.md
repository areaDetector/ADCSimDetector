ADCSimDetector Releases
======================

The latest untagged master branch can be obtained at
https://github.com/areaDetector/ADCSimDetector.

Prior to R2-3 the files in this repository were contained in the ADExample
repository.  ADCSimDetector was split into its own repository on Nov. 22, 2016
and the first release of the new repository was called R2-3 to continue the
release numbering from ADExample.

Tagged source code releases from R2-3 onward can be obtained at 
https://github.com/areaDetector/ADCSimDetector/releases.

Tagged source code releases for R2-2 can be obtained at 
https://github.com/areaDetector/ADExample/releases.

Tagged prebuilt binaries from R2-3 onward can be obtained at
https://cars.uchicago.edu/software/pub/ADCSimDetector.

Tagged prebuilt binaries for R2-2 can be obtained at
https://cars.uchicago.edu/software/pub/ADExample.

The versions of EPICS base, asyn, and other synApps modules used for each release can be obtained from 
the EXAMPLE_RELEASE_PATHS.local, EXAMPLE_RELEASE_LIBS.local, and EXAMPLE_RELEASE_PRODS.local
files respectively, in the configure/ directory of the appropriate release of the 
[top-level areaDetector](https://github.com/areaDetector/areaDetector) repository.


Release Notes
=============

R2-5 (July 4, 2017)
========================
* Update constructor for compatibility with ADCore R3-0. 
* Fix medm screen layout for ADCore R3-0.


R2-4 (February 19, 2017)
========================
* Add support for new parameter NDDriverVersion. Minor change to driver and medm screen.


R2-3 (November 22, 2016)
========================
* ADCSimDetector was split into its own repository from ADExample.  The release numbering
  starts where ADExample left off.


R2-2 (October 28, 2016)
========================
* Created a new driver in ADExample/exampleApp/ADCSimDetectorSrc.
  This driver generates times-series data for 8 signals as a 2-D array [8, NumTimePoints].
  The signals are common waveforms (sine, cosine, square wave, sawtooth, random noise, etc.)
  
  The driver was written in part to test the new NDPluginTimeSeries and NDPluginFFT plugins 
  in ADCore R2-5. But it can also serve as a starting point for writing drivers that are used 
  to collect time-series data like ADCs, waveform digitizers, etc.  

  There is a new iocs/iocADCSimDetector directory that creates an application for testing
  the driver.
* Added a new sine-wave simulation mode to simDetector.  This simulation mode constructs images
  as the sum or products of two sine waves in the X and Y directions.  It was designed in part
  to test the new NDPluginFFT plugin in ADCore R2-5.
* Added new iocPvaDriver example IOC.  It implements the new pvaDriver from ADCore R2-5 which
  receives EPICS V4 NTNDArrays over EPICS V4 PVAccess, converts them to NDArrays and calls
  areaDetector plugins.

