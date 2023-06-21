# Introduction

This repository contains opinionated instructions for how to tune in a AnkerMake M5 3D printer for use with PrusaSlicer 2.6+, as well as some pre-calibrated filament profiles and custom print settings optimized for quality.

## Prerequisites

1. Ensure you have followed all of the Quick Start Guide instructions at <https://support.ankermake.com/s/article/AnkerMake-M5-Quick-Start-Guide>
1. Have the latest version of PrusaSlicer 2.6+ installed on your computer
1. Install the latest version of the AnkerMake Community Edition PrusaSlicer profiles from <https://github.com/Ankermgmt/prusaslicer-ankermake-ce-profiles>
1. Download the latest ZIP release of this tuning guide from [releases](releases) and unzip it.
1. Open PrusaSlicer, go to Help > Show Configuration Folder
1. Copy the contents of the `profiles` folder from the release into the PrusaSlicer configuration folder
  1. This will install a series of custom profiles, which can be identified as coming from this repo by having "(Tuned)" in the name of each one.

## Tuning Steps

1. ~~Review [recommended-tools.md](recommended-tools.md) for any tools you might wish to buy.~~ COMING SOON
1. Follow the instructions at [tuning/new-printer.md](tuning/new-printer.md) if this is a new printer, or if you've never followed this tuning guide before.
1. Follow the instructions at [tuning/new-filament.md](tuning/new-filament.md) for every new combination of brand and material you buy in order to ensure optimum print quality.

## License

All profiles and tuning instructions that are part of this repository are licensed under a [Creative Commons Zero v1.0 Universal](LICENSE) license.

All models are licensed under their author's chosen license, detailed in credits.

All linked instructions are licensed under the their author's chosen license, detailed at the specific link.

## Credits

- Xelinor in the AnkerMake Community Discord for PETG print settings
- The entire community at the Unofficial AnkerMake Wiki for helping to understand general tuning and calibration
- [gaaZolee](https://www.thingiverse.com/thing:2729076) from Thingiverse for temperature tower models and gcode script for printing them easily
  - Models under models/temperature-towers are licensed under the [Creative Commons - Attribution - Share Alike](https://creativecommons.org/licenses/by-sa/3.0/) license
- [thetechnicalace](https://wiki.printed.boats/en/Troubleshooting/hardware-fixes) from the Unofficial AnkerMake Wiki for the Full Bed Test print
  - Model under models/full-bed-test is licensed under the [Creative Commons - Attribution](https://creativecommons.org/licenses/by/4.0/) license.
- [yahbluez](https://www.printables.com/model/251587-stress-free-first-layer-calibration-in-less-than-5) from Printables for the First Layer Calibration print
  - Model under models/first-layer-test is licensed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.html)
- [AndrewEllis93](https://github.com/AndrewEllis93/Print-Tuning-Guide) from GitHub for the extrusion multiplier tuning methodology and labelled cubes
- [myevo8u](https://github.com/myevo8u/Prusa-Slicer-Extrusion-Multiplier-Calibration-Script) from GitHub for the method of using a Python script to post-process gcode for faster extrusion multiplier tuning
