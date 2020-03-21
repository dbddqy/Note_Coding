# simplify3d 打印开始结束的gcode

starting:  
```gcode
G28 ; home all axes

G1 Y10.0 F500
G1 X60.0 E9 F500
G1 X100.0 E12 F500
```

ending:  
```gcode
G28 X0
M104 S0 ; turn off extruder
M140 S0 ; turn off bed
M106 S0
M84 ; disable motors
```