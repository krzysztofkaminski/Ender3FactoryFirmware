# Ender3FactoryFirmware
Factory `Flash, EEPROM and Fuses` copied from my `Ender 3` MCU.


Burn Flash:
```
avrdude -p m1284p -c usbasp -P /dev/ttyUSB0 -b 115200 -U flash:w:flash.intelhex:i
```


Burn EEPROM:
```
avrdude -p m1284p -c usbasp -P /dev/ttyUSB0 -b 115200 -U eeprom:w:eeprom.intelhex:i
```

M115 - Firmware Info:
```
FIRMWARE_NAME:Marlin V1; Sprinter/grbl mashup for gen6 FIRMWARE_URL:http://www.mendel-parts.com PROTOCOL_VERSION:1.0 MACHINE_TYPE:www.creality3d.cn EXTRUDER_COUNT:1 UUID:00000000-0000-0000-0000-000000000000
```


M501 - Settings from EEPROM:
```
Steps per unit:
M92 X80.00 Y80.00 Z400.00 E93.00
Maximum feedrates (mm/s):
M203 X500.00 Y500.00 Z5.00 E25.00
Maximum Acceleration (mm/s2):
M201 X500 Y500 Z100 E5000
Acceleration: S=acceleration, T=retract acceleration
M204 S500.00 T500.00
Advanced variables: S=Min feedrate (mm/s), T=Min travel feedrate (mm/s), B=minimum segment time (ms), X=maximum XY jerk (mm/s),  Z=maximum Z jerk (mm/s),  E=maximum E jerk (mm/s)
M205 S0.00 T0.00 B20000 X20.00 Z0.40 E5.00
Home offset (mm):
M206 X0.00 Y0.00 Z0.00
PID settings:
M301 P21.73 I1.54 D76.55
```


Device signature = 0x1e9705 (m1284p)
```
lfuse reads as D6
hfuse reads as DC
efuse reads as FD
```
