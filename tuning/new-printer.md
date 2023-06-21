# New Printer Tuning

These are steps that should be taken when you first get your printer (also a good idea to do each of these if you have never done them, even if your printer isn't new)

All steps on this page are considered required and don't need special tools.

## Before you Begin

Before you begin, make sure you have a 0.4mm nozzle installed, as test prints used in calibration are designed for an 0.4mm nozzle with a 0.2mm layer height.

## Update Firmware

First and foremost, make sure you are always running the latest firmware. You'll also want to run an Auto Bed Level after every firmware update, though you don't need to do that now as you'll be doing it in a later step.

## E-Step Calibration

Calibrating your e-steps is critical to making sure you produce accurate prints. This is basically calibrating your extruder motor to ensure that it's actually extruding the same length of filament as is called for.

The guide from the Unofficial AnkerMake Wiki does a fine job explaining it: <https://wiki.printed.boats/en/Tips/extruder-calibration>

The only thing I would add is that, when you put the nozzle back after calibration, make sure to hold the hotend with a pair of sliding pliers to avoid breaking the weak stock screws holding the block in place. (Side note: highly recommend you replace these screws with some M2x16mm 12.9 alloy hardened screws to prevent bending them and ruining a hotend like I did. Here's the screws I used: <https://www.amazon.com/gp/product/B07W5J19Y5>)

If you've never taken the nozzle off or put it back on before, follow the guide here: <https://support.ankermake.com/s/article/How-to-Replace-the-Nozzle>.
A few things to remember:

- The hotend MUST be heated to both remove and replace the nozzle. Don't burn yourself!
- ALWAYS perform an auto-bed level after changing the nozzle, even if you put the same nozzle back in. (And remember to re-set your Z-Offset after ABL!)

## Mechanical Tuning

There is an excellent article from the Unofficial AnkerMake Wiki that details important hardware tuning steps: <https://wiki.printed.boats/en/Troubleshooting/hardware-fixes>

The following adjustments were needed for my printer, and I recommend doing them in this order:

- FIX 4 - Adjusting Eccentric Nuts and/or Wheels
- FIX 3 - Z-Block Tension Adjustment
- FIX 2 - Check X and Y-axis Belts
  - Doing this will also have you do what's included in step 1
  - The best tuner app I found for iOS is called `Tuner T1`
- Perform an Auto Bed Level
- Follow the instructions at [new-filament.md](new-filament.md) to calculate your Z-Offset (even if you've calculated it before, it's extremely likely the tuning you've done in this step has changed that value,)
- Print a full bed test by using the file at [../models/full-bed-test/m5_fullbedtest_bytta.stl](../models/full-bed-test/m5_fullbedtest_bytta.stl)
  - Profiles:
    - Print Settings: `Calibration - Full Bed Test`
    - Filament Settings: Whatever Generic preset is closest to your filament. Prefer a (Tuned) variant if it exists.
    - Printer Settings: `AnkerMake-CE M5 (0.4mm nozzle)`
- Compare the test versus the `Analyzing a Full Bed Test` section of the linked article. You should be passing at this point. If you aren't, it's possible your Z-Offset value is wrong, you need to perform one or more of the hardware tuning steps above again, or you have a hardware problem that you should contact AnkerMake support about.

## Pressure Advance Tuning

Pressure advance (or linear advance) is how much your printer compensates for g-forces at corners and angles to make sure that the flow rate stays consistent. If you aren't getting sharp 90 degree angles like you'd like, this is what you need to tune.

As with E-step calibration, the Wiki already has a great guide for this. Use their provided PLA gcode and you'll be able to quickly calibrate this value: <https://wiki.printed.boats/en/Tips/Pressure-Linear-Advanced-Tuning>
