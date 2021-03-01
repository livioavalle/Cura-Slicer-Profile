# Cura Slicer Profile

<p align="center">
    <img src="./media/cura-256.png" alt="Icon">
</p>

## Cura Plugins
- CuraInventorPlugin
- CuraOpenSCADPlugin
- CustomSupportsCylinder
- CustomSupports
- HTMLCuraSettings
- ImportExportProfiles
- MeshTools
- OctoPrintPlugin
- OrientationPlugin
- PauseBackendPlugin
- SettingsGuide2
- StartOptimiser
- TabAntiWarping
- ThingiBrowser
- ZOffsetPlugin

## Materials
- [3dcolors](materials_data/3dcolors/)
- [Prusament](materials_data/prusament/)

## Printers
## Firmware
## Custom G-Code
### Start G-Code
```
; Ender 3 Custom Start G-code
G92 E0 ; Reset Extruder
G28 ; Home all axes
G29 ; Auto Bed Levelling
G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
G1 X0.1 Y20 Z0.3 F5000.0 ; Move to start position
G1 X0.1 Y200.0 Z0.3 F1500.0 E15 ; Draw the first line
G1 X0.4 Y200.0 Z0.3 F5000.0 ; Move to side a little
G1 X0.4 Y20 Z0.3 F1500.0 E30 ; Draw the second line
G92 E0 ; Reset Extruder
G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
G1 X5 Y20 Z0.3 F5000.0 ; Move over to prevent blob squish
```
### End G-Code
```
G91 ;Relative positioning
G1 E-2 F2700 ;Retract a bit
G1 E-2 Z0.2 F2400 ;Retract and raise Z
G1 X5 Y5 F3000 ;Wipe out
G1 Z10 ;Raise Z more
G90 ;Absolute positionning

G1 X0 Y{machine_depth} ;Present print
M106 S0 ;Turn-off fan
M104 S0 ;Turn-off hotend
M140 S0 ;Turn-off bed

M84 X Y E ;Disable all steppers but Z

```
