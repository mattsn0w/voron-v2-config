# What the heck is this?

These are my [Klipper](https://www.klipper3d.org/) + [MainSail](https://github.com/mainsail-crew/MainsailOS) configuration files for a [Voron Design](https://vorondesign.com/) [2.4 r2 350mm](https://github.com/VoronDesign/Voron-2) that I assembled from a [Formbot Kit](https://www.formbot3d.com/products/voron-24-r2-pro-corexy-3d-printer-kit-with-m8p-cb1-board-and-canbus-wiring-system?VariantsId=10485) 3D Printer.

## About the kit
This kit does not come with instructions from the vendor, but includes all of the parts and hardware needed to build a Voron v2.4R2 3D with several modifications. 
The communities which gave support and got me through the build by reading and re-reading, then trying, rinse and repeat:
- [The Voron Design Documentation](https://docs.vorondesign.com/) - Well thought out, clear and concise.
- [Klipper Docs](https://www.klipper3d.org/) - Exhaustively thorough and it is mind boggling how many hardware configurations, MCUs, and electronic parts are well supported by this software. 🎩
- [Some fine citizens of the 3D printing world](https://github.com/Zev-se/Formbot-voron-2.4-build-guide) who took it upon themselves to write some supplimental documentation to build these modded kits from Formbot. Formbot links to this GitHub repo with seemingly no affiliation. 

## Status
- 3/4/2025
  - I have been printing a lot of toys for kids and tools for people with limited range of motion. All PLA at this point as the panels still need to be installed.
  - I ordered a Waveshare OV5648 5 MP Camera Module for the [Chri.Kai.in/ANGRY_USB_CAM](https://github.com/VoronDesign/VoronUsers/tree/main/printer_mods/chri.kai.in/Angry_CAM_USB).
  - I finished printing and installing the skirts, electronics box fans, and a 7" BTT HDMI V1.2 touchscreen.
- 2/25/2025
  - Finally got TAP working. The issue is in the documentation and certain assumptions made throughout. The Instructions for TAP assume that you built a stock printer and gotten it to a working state before installing and configuring TAP. I needed to manually insert a `#*# [probe]` line into the bottom of my printer.cfg followed by running `PROBE_CALIBRATE` and manually saving a line in this special `[probe]` section: `#*# z_offset = -1.500` . Now my Z TAP stuff works!
  - Ran input shaping and adjusted accordingly.
  - Ordered a couple extra build plates in a moment of desparation while trying to get TAP working. I scratched up the textured PEI surface pretty badly while trying to calibrate the Z offset and get a reliable `PRINT_START` macro. 😢 🤬
  - Tensioned all belts evenly using one of [these slick tensioners](https://github.com/Diyshift/3D-Printer/tree/main/GT2%20Belt%20Tension%20Meter) that a coworker printed for me.
- 2/16/2025 - More testing and understanding on Z-offset calibration. The TAP docs say to comment out the z_offset setting on the `[probe]` section of the config. However, removing this all together produces a blocking RED status error and will not allow the MCU firmware to load and accept the configuration. Homing, QGL, and heating works fine. Next is to calibrate e-steps. I had to flip the `[extruder] dir_pin` by removing the `!` to get the filement to pull through the hotend.  
- 2/15/2025 - The printer is mostly assembled, sans skirts, screen and coveres. Currently working through [Initial Startup](https://docs.vorondesign.com/build/startup/#tilt--qgl-with-heated-bed-and-chamber-v1-trident-v2).
- 2/10/2025 - Picked up a Raspbarry Pi CM4 with eMMC NAND flash and a few GB RAM locally. This was a big improvement on boot time and made firmware and Klipper service restarts much faster. It also is a much higher quality product than BigTreeTech's CB1/CB2.
- 2/7/2025 - The CB1 with provided SD Card is painfully slow. After realizing this unit did not have the onboard flash that I thought it did, I decided to upgrade the compute Module board. I happened to have a CB2 on hand for a future upgrade project. This was much faster, but after getting all the firmware setup and built, I nudged the wifi antenna nad the darn connector popped off the PCB! Now I cannot connect to the printer. 🤬
- 2/2/2025 - [PR for documentation updates](https://github.com/Zev-se/Formbot-voron-2.4-build-guide/commit/133997a850d8d4709106382f292d58198b98d351).
- 1/30/2025 - Despite not being finished with this build, I purchased a [Voron v0.2](https://github.com/VoronDesign/Voron-0) [Formbot sourced kit](https://www.aliexpress.us/item/3256803199432554.html) to build after this one.
- 1/04/2025 - Started assembling the extruded frame.
- 12/2024 - Printer kit was shipped in one large well padded and packaged box. Printed parts were shipped in a smaller well padded.
- 11/28/2024 - I purchased the 350x350 kit with functional printed parts from Formbot on [AliExpress](https://www.aliexpress.us/item/3256803199034766.html). 

