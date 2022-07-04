# Ender 3 to-do

- <input type="checkbox"> recompile the FW and get latest Marlin FW: https://all3dp.com/2/ender-3-pro-firmware-update-marlin/
- <input type="checkbox"> questions about FW:
  - why are there #error statements that crash the compile? I commented them out. (lines 23-24 of configurations.h)
  - Process: Why did I copy marlin and config to another directory in https://all3dp.com/2/ender-3-v2-firmware-update/ Step 2?
- <input type="checkbox"> Compare the following:
  https://3dprintscape.com/marlin-firmware-on-creality-board-complete-guide/ vs https://all3dp.com/2/ender-3-v2-firmware-update/
  YouTube videos:
  https://www.youtube.com/watch?v=J9vxJT5Tgh4 /_ Teaching Tech _/
  melzi @ 6:55 & 11:38 in configuration.h
  further explanation in https://youtu.be/eq_ygvHF29I https://www.youtube.com/watch?v=pQ7WZST8sqk /_ 3Dprintscape _/
  default env in platformio.ini @ 5:45
  configuration changes start @ 8:00
  https://www.youtube.com/watch?v=oZVTYpHnpIw /_ Thomas Sanladerer _/
  Why was PIDTEMPBED already uncommented? (~line 730 of configurations.h)
  What is the correct value of 'default_envs = mega2560' in the platformio.ini file?
  Terminal says, "Error: Build environment 'mega2560' is incompatible with BOARD_CREALITY_V4. Use one of these: STM32F103RE_creality, STM32F103RE_creality_xfer, STM32F103RC_creality, STM32F103RC_creality_xfer, STM32F103RE_creality_maple"
  Does vscode come with its own c compiler or do i need to install one?
  Enabling EEPROM with https://github.com/jyers/marlin/releases/
  [] Go through guides at https://teachingtechyt.github.io/
  [] m500 and PIDTEMPBED don't work yet
  [] New FW-https://www.th3dstudio.com/hc/downloads/unified-2-firmware/creality/creality-boards-creality/creality-ender-3-3-pro-ender-5-5-pro-firmware-v4-2-x-board/
  Already downloaded and unzipped to C:\Program Files (x86)\Creality-Ender3Pro\FW update
  [] PID BED TEMPERATURE control in Configuration.h

[] Update default Kp parameters:

> > > M303 E-1 S65 U1
> > > SENDING:M303 E-1 S65 U1
> > > bias: 126 d: 126 min: 195.91 max: 204.44
> > > bias: 125 d: 125 min: 196.36 max: 204.44
> > > bias: 124 d: 124 min: 196.36 max: 204.37 Ku: 39.41 Tu: 24.05
> > > Classic PID
> > > Kp: 23.65 Ki: 1.97 Kd: 71.08
> > > bias: 123 d: 123 min: 196.36 max: 204.44 Ku: 38.76 Tu: 24.37
> > > Classic PID
> > > Kp: 23.26 Ki: 1.91 Kd: 70.84
> > > bias: 123 d: 123 min: 196.14 max: 204.44 Ku: 37.70 Tu: 24.85
> > > Classic PID
> > > Kp: 22.62 Ki: 1.82 Kd: 70.26
> > > PID Autotune finished! Put the last Kp, Ki and Kd constants from below into Configuration.h
> > > #define DEFAULT_Kp 22.62
> > > #define DEFAULT_Ki 1.82
> > > #define DEFAULT_Kd 70.26

[] If I can recompile the FW, the above is possible. If not, see note at bottom of https://teachingtechyt.github.io/calibration.html#pid

[] Cura slicer default preamble change to support extruder and bed PIDs.
