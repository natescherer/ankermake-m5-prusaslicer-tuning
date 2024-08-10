# New Filament Tuning

There are three categories of tuning steps:
    - Basic/Must-Do, indicated with ✅
        - These require no special tools and are critical to getting good prints.
    - Intermediate, indicated with ⭐
        - These require special tools and will improve your print quality by a moderate amount.
    - Expert, indicated with 🤓
        - These require a significant amount of work, but will ensure you are producing the highest quality prints you can.

You can choose to any/all of these steps, but you should do the steps you choose in the order listed.

## Before You Begin

Before you begin, make sure you have a 0.4mm nozzle installed, as test prints used in calibration are designed for an 0.4mm nozzle with a 0.2mm layer height.

## ✅ Cleaning Nozzle & Hotend

This is mandatory if you are changing the type of material you are printing (i.e. PETG to PLA or vice versa). If you are just changing from one color of the same material to another, this is unnecessary.

1. On the printer, tap the wrench icon and then Nozzle Cleaning > Start, and advance until the nozzle preheats
1. Take your wire brush and thoroughly clean the nozzle (you can disassemble the hotend to clean if you wish as the instructions indicate, but I think this is unnecessary)
    1. Note, if you are using plastic repellent paint, do NOT use a wire brush to clean, as it will remove this coating. Instead pick off any pieces of plastic with tweezers.
1. Cancel out of the cleaning process, then load your cleaning filament
1. Go to Control > Extrude, set the temperature to the last temperature you printed at, and extrude until you see the cleaning filament come out clear
    1. Using the last print temperature is very important to make sure all of the previous filament is cleaned out of the hotend/nozzle
1. Load your new filament, then do a series of 20mm extrusions at an appropriate temperature for it until you see all the cleaning filament removed from the nozzle
1. Clean the nozzle with the wire brush/tweezers again, if necessary

## ⭐ Dry Filament

If you are reasonably sure you've got fresh filament (like you bought Inland brand from a Microcenter that's busy), you can consider skipping this step. However, there's really no way for you to know how long the filament you just bought was sitting around; that silica gel packet in there could be fully saturated, which means there is also at least some moisture in the filament.

I strongly recommend using a filament drier for your filament rather than your home oven; it's hard to get a standard oven to a low enough temperature, and do you really want non-food-safe plastic in your oven? Every filament drier varies; follow your manufacturer's instructions.

## 🤓 Measuring Empty Spool Weight

Taking this step will let you make sure that prints toward the end of the spool have enough filament left to complete!

NOTE: Some brands, like Overture, list an approximate empty spool weight on the packaging, letting you skip this step entirely if you wish.

1. As soon as you pull it out of the vacuum bag, drop the whole spool of filament on a scale and weigh it in grams.
1. Subtract the listed weight of the filament (most often 1000g/1kg) from that value, and write that value as "Spool Weight" on the spool itself.
    1. If you wish, you can also record the spool weight in PrusaSlicer under Filament Settings. Spool weight *should* be approximately the same between spools (as long as your filament manufacturer hasn't changed spool design).

Now, when you are getting close to the end of the spool and want to be sure you can print the model you want, disconnect the spool (if connected), weigh it, then subtract the spool weight to get the weigh of remaining filament. Then slice your model and compare the remaining filament weight against the "Used Filament" value in the bottom-right of PrusaSlicer.

## ✅ Calibrating Z-Offset

Recommend doing this step for each combo of brand and material. Z-Offset tends to vary mostly by type of plastic, but because exact formulas can and do vary by brand.

1. On the printer itself, go to Control > Z-Offset and set your starting value:
    1. If you have determined Z-Offset values for other filaments, choose the one from the filament that is most like the new filament you are calibrating. (I.E. if you know your Z-Offset for PLA is 0.02 and you are trying out Silk PLA, use that value to start)
    1. If you are calculting Z-Offset for the first time, just start at 0.00
1. Download the STL file from [../models/first-layer-test](../models/first-layer-test)
1. In PrusaSlicer:
    1. Print Settings: `Calibration - Z-Offset`
    1. Filament Settings: Whatever preset seems closest to your filament.
    1. Printer Settings: `AnkerMake M5 (0.4mm nozzle) -AMCE`
1. Slice and print the gcode file
1. Once printed, peel the test print off the bed and hold it up to a light to inspect. There are pictures that can help posted on the original author's page <https://www.printables.com/model/251587-stress-free-first-layer-calibration-in-less-than-5> but, essentially, you are looking for one contiguous piece with clear lines and no wrinkling or tearing.
    1. If you have lines that aren't joined together, you need to lower your Z-Offset. Subtract 0.01mm from your offset and print again.
    1. If you have wrinkles/tearing, you need to raise your Z-Offset. Add 0.01mm to your offset and print again.
1. Repeat the process of printing and adjusting the Z-Offset until you have a first layer test you are satisfied with and matches photos from the Printables page.
1. Record the Z-Offset somehow, noting the brand, type and color of the filament. (I like to note it on the filament box and put it in a text file I have saved.)
1. As you continue to print this material, make sure that the Z-Offset value stays set. Some actions like performing Auto Bed Leveling or a firmware update can cause the printer to lose the current value.

## ✅ Calibrating Temperature

Unlike Z-Offset, the proper printing temperature *will* vary significantly by manufacturer within the same material type. (It can even vary between similar types of filament within the same brand, like regular PLA and PLA+.)

Temperature calibration is done via printing what is called a "temperature tower"; a print that is designed to stack a series of difficult to print elements vertically, each set printed at a different temperature. Comparing each temperature layer will let you find the best temp for your filament.

NOTE: If there is already a Filament Settings profile from this repo for your brand and type of filament (or another repo where you're sure the settings were made for an M5), you can skip this step and just use it.

1. Download an STL from [../models/temperature-towers](../models/temperature-towers) that will cover the entire listed temperature range for your filament. Don't worry if it also includes temperatures outside the range.

1. In PrusaSlicer:
    1. Print Settings: `0.20mm NORMAL @AMCE`
    1. Filament Settings:
        1. Whatever preset seems closest to your filament.
        1. Set the filament temperature (both `First layer` and `Other Layers`) to the highest listed temperature in the model name.
    1. Set the Printer Settings profile to `Calibration - Temperature Tower @M5-TUNED`
        1. This profile contains pre-loaded custom gcode to adjust the temperature as the model prints
1. Once the temperature tower is done, inspect each layer for finish, layer adhesion, floppy bridges, stringing around the cone, etc. Use the temperature of the layer that looks best as your `Other Layers` temperature for this filament, and a temperature 5C hotter than that as your `First layer` temperature.
1. Save your new Filament Settings profile with a name indicating the brand and type of filament.
1. MAKE SURE TO CHANGE THE PRINTER SETTINGS PROFILE BACK TO NORMAL! Otherwise your next print will have its temperature drop as it gets taller.

## ✅ Calibrating Extrusion Multiplier

Extrusion multiplier calibration helps ensure you have the proper flow rate for the type of filament you are using. The proper flow rate can and will vary across material type and manufacturer. I recommend you do this calibration for every unique combination of manufacturer and material (color shouldn't change EM significantly).

This method was pioneered by Ellis3dp from <https://ellis3dp.com/Print-Tuning-Guide/articles/extrusion_multiplier.html>, and features some tweaks to make the calibration process overall faster. In general, you'll be printing a bunch of short cubes, each with a slightly different EM, and then performing visual/tactile comparisons to find the best one.

The extrusion calibration method used requires running a Python script to modify the gcode PrusaSlicer emits, which means you will need to have Python installed on your machine. Here are brief instructions for each platform:

### Installing Python

Don't have Python installed? (Or, for some reason, you would like to read a very opinionated doc on what I think is the best way to install and update Python?) [See here!](installing_python.md)

### Generating Calibration Gcode

1. Go to <https://github.com/AndrewEllis93/Print-Tuning-Guide>, select Code, then Download ZIP
1. Extract this file, and copy out the directory test_prints/extrusion_multiplier_cubes/labeled
1. In PrusaSlicer
    1. Start a new project with the following settings:
        1. Print Settings: `Calibration - Extrusion Multiplier`
        1. Filament Settings: Whatever you created in the temparatue calibration above
            1. Ensure extrusion multiplier is set to whatever the highest EM value you wish to test is (I recommend 1.00 to start)
        1. Printer Settings: `AnkerMake M5 (0.4mm nozzle) -AMCE`
    1. Drag in as many EM cubes from the extracted zip file as you wish to print, each one is labeled with a different value (and the object names will be used by the Python script to actually adjust the value for each object)
        1. I usually test the range from 0.905 to 1.00 in 0.05 increments, but you can do more or less depending on how much plastic you want to burn and exactly how much you want EM to be dialed in
        1. Just be 100% sure that the highest value EM cube you choose is also what you have set for the extrusion multiplier under Filament Settings, otherwise the test will be broken.
        1. Also, highly recommend that the way you lay the objects out on the print bed goes in sequential order.
    1. Export and save the gcode, but do NOT send it to the printer yet. It needs to be post-processed so each cube prints with a different EM.
1. Download [scripts/Calibrate-Flow-Labeled-Cubes.py](scripts/Calibrate-Flow-Labeled-Cubes.py) to your computer, then execute it by running `python Calibrate-Flow-Labeled-Cubes.py` in the terminal app for your platform.
    1. The script will prompt you to press Enter, which will open a file selection dialog. Choose the gcode file you saved from PrusaSlicer.
    1. The script will modify and save the file on top of itself. Review the output to make sure there weren't any errors.
1. Print the newly modified gcode file.

### Examining Test Prints

If you didn't watch while it was printing, note that each cube has the EM value it was printed with printed into its base. You're going to compare the cubes against each other. I highly recommend you refer the Ellis3dp's original guide for this method to learn how to choose the best value: <https://ellis3dp.com/Print-Tuning-Guide/articles/extrusion_multiplier.html#examples>

Once you have chosen the best value, save that as the EM value for the filament profile in PrusaSlicer.

## ⭐Calibrating Retraction

This is a significantly less scientific process than the other tuning methods, and I'm not happy about it. I've brute forced retraction settings for the `@M5-TUNED` profiles provided in this repository (this is the only major difference between my profiles and the `@AMCE` profiles), so you can consider just taking those. If you want to tune it in for yourself, however, here's my methodology:

## (Optional) Final Validation

If you want to verify you fully have your filament tuned in, there are two prints I recommend using.

### Full-Bed Test

First, I recommend printing a full-bed first layer test using [m5_fullbedtest_bytta.stl](../models/full-bed-test/m5_fullbedtest_bytta.stl). Use the `0.20mm NORMAL @AMCE` profile with the following modifications:

* Skirt and brim
  * `Skirt: distance from brim/object`: 1mm

Ideally, this should come out as one smooth, contiguous layer. If you don't get this, here's a list of steps to try, in order:

1. Perform an Auto Bed Level
1. Re-tune the Z-Offset using instructions from earlier in this guide
1. Consult <https://wiki.printed.boats/en/Troubleshooting/m5_hardware-fixes>

### #3DBenchy

The #3DBenchy model is an absolute classic in the 3D printing space for a reason, as it is an absolute torture test for just about every aspect fo printer and filament tuning. It's included at [3DBenchy.stl](../models/3dbenchy/3DBenchy.stl) for your convenience. <https://www.3dbenchy.com/> is your best resource for learning how to use this model as a test of print quality, there are also plenty of solid YouTube videos out there.

## Contributing

Since you just did all the work of tuning in a new type of filament, perhaps you'd care to share that work with others? If so, please see [../contributing.md](../CONTRIBUTING.md)!
