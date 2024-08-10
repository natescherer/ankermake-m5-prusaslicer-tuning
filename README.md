# Introduction

This repository contains opinionated instructions for how to tune in a AnkerMake M5 3D printer for use with PrusaSlicer 2.6+, as well as some pre-calibrated filament profiles and custom print settings optimized for quality.

## Prerequisites

1. Ensure you have followed all of the Quick Start Guide instructions at <https://support.ankermake.com/s/article/AnkerMake-M5-Quick-Start-Guide>
1. Have the latest version of PrusaSlicer installed on your computer
1. Install the latest version of the AnkerMake Community Edition PrusaSlicer profiles from <https://github.com/Ankermgmt/prusaslicer-ankermake-ce-profiles> using their provided instructions.
1. Download the latest ZIP release of this tuning guide from [releases](https://github.com/natescherer/ankermake-m5-prusaslicer-tuning/releases/latest) and unzip it.
1. Open PrusaSlicer, go to Help > Show Configuration Folder
1. Copy the contents of the `profiles` folder from the release into the PrusaSlicer configuration folder
    1. This will install a series of custom profiles, which can be identified as coming from this repo by ending with  "@M5-TUNED" in the name of each one.

## Tuning Steps

1. Follow the instructions at [docs/tuning-new-printer.md](docs/tuning-new-printer.md) if this is a new printer, or if you've never followed this tuning guide before.
1. Follow the instructions at [docs/tuning-new-filament.md](docs/tuning-new-filament.md) for every new combination of brand and material you buy in order to ensure optimum print quality.

## License

All profiles and instructions that are part of this repository are licensed under a [Creative Commons Zero v1.0 Universal](LICENSE) license, except as noted below:

* [Calibration - Temperature Tower](<profiles/printer/Calibration - Temperature Tower.ini>) is adapted from [Smart compact temperature calibration tower](https://www.thingiverse.com/thing:2729076) by [Zolee Gaa](https://www.thingiverse.com/gaazolee/designs), used under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/). "Calibration - Temperature Tower" is licensed under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) by [Nate Scherer](https://github.com/natescherer)
* Any models or scripts redistributed as part of this repository are provided in their own folder along with a copy of their respective license, with attribution in the credits below.

## Credits

* The entire community at the [Unofficial AnkerMake Wiki](https://wiki.printed.boats/en/home) for helping to understand general tuning and calibration
* [gaaZolee](https://www.thingiverse.com/thing:2729076) from Thingiverse for temperature tower models and gcode script for printing them easily
* [thetechnicalace](https://wiki.printed.boats/en/Troubleshooting/m5_hardware-fixes) from the Unofficial AnkerMake Wiki for the Full Bed Test print
* [yahbluez](https://www.printables.com/model/251587-stress-free-first-layer-calibration-in-less-than-5) from Printables for the First Layer Calibration print
* [AndrewEllis93](https://github.com/AndrewEllis93/Print-Tuning-Guide) from GitHub for the extrusion multiplier tuning methodology and labelled cubes
* [myevo8u](https://github.com/myevo8u/Prusa-Slicer-Extrusion-Multiplier-Calibration-Script) from GitHub for the method of using a Python script to post-process gcode for faster extrusion multiplier tuning
* [Creative Tools](https://www.creativetools.se/) for the all-time classic #3DBenchy model
* [s3sebastian](https://www.thingiverse.com/thing:2219103) from Thingiverse for retraction test tower calibratio model
