# ESP32-ECU-emulator for OBD2/CAN data printer

OBD2 ECU emulator based on CAN and OBD2 library by sandeepmistry

   https://github.com/sandeepmistry/arduino-CAN
   
   https://github.com/sandeepmistry/arduino-OBD2


   
This program is used to test OBD2( OBD-II ) monitoring ESP32 board with a following program 
before I connect it to my car.

   https://github.com/sandeepmistry/arduino-OBD2/blob/master/examples/OBD2_03_DataPrinter/OBD2_03_DataPrinter.ino

ESP32(ECU emulator)---TJA1050-----CAN bus connector----TJA1050 ---ESP32(OBD2_03_DataPrinter.ino)
  

# hardware

 TJA1050 CAN tranceiver board is connected to ESP32 devkitC board via
```   
   Vcc <- 5V  ESP32
   GND <- GND ESP32
   CTX <--- GPIO_5 ESP32 devkitC board
   CRX ---> 5V/3.3V level converter ---> GPIO_4
```
   I have used 1N5819 shotkey diode and 1kOhm pulled up to 3.3V
   to connect CRX to ESP32. 
   CTX is directly connected to ESP32 GPIO_5
```   
   +3.3V ----1kOhm----+
                      |
       ESP32 GPIO4 <--+----anode IN1589 cathode>|---<-CRX
```

## sample

output by OBD2_03_DataPrinter.ino running on another ESP32 with TJA1050
```
ets Jun  8 2016 00:22:57

rst:0x1 (POWERON_RESET),boot:0x17 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:1
load:0x3fff0018,len:4
load:0x3fff001c,len:1100
load:0x40078000,len:9232
load:0x40080400,len:6400
entry 0x400806a8
OBD2 data printer
Attempting to connect to OBD2 CAN bus ... success

VIN =
ECU Name =

OBD2 data printer start
PIDs supported [01 - 20] = 0xFFFFFFFF
Monitor status since DTCs cleared = 0x81000000
Freeze DTC = 0x1234FB3F
Fuel system status = 0x200
Calculated engine load = 52.94 %
Engine coolant temperature = 113.00 °C
Short term fuel trim ― Bank 1 = 1.56 %
Long term fuel trim ― Bank 1 = 7.03 %
Short term fuel trim ― Bank 2 = -6.25 %
Long term fuel trim ― Bank 2 = 7.03 %
Fuel pressure = 252.00 kPa
Intake manifold absolute pressure = 255.00 kPa
Engine RPM = 4104.00 rpm
Vehicle speed = 151.00 km/h
Timing advance = 8.00 ° before TDC
Intake air temperature = 42.00 °C
MAF air flow rate = 8.00 grams/sec
Throttle position = 37.25 %
Commanded secondary air status = 0x1
Oxygen sensors present (in 2 banks) = 0x3
Oxygen Sensor 1 - Short term fuel trim = 98.44 %
Oxygen Sensor 2 - Short term fuel trim = 98.44 %
Oxygen Sensor 3 - Short term fuel trim = 98.44 %
Oxygen Sensor 4 - Short term fuel trim = 98.44 %
Oxygen Sensor 5 - Short term fuel trim = 98.44 %
Oxygen Sensor 6 - Short term fuel trim = 98.44 %
Oxygen Sensor 7 - Short term fuel trim = 98.44 %
Oxygen Sensor 8 - Short term fuel trim = 98.44 %
OBD standards this vehicle conforms to = 0xA
Oxygen sensors present (in 4 banks) = 0x1
Auxiliary input status = 0x1
Run time since engine start = 31.00 seconds
PIDs supported [21 - 40] = 0xFFFFFFFF
Distance traveled with malfunction indicator lamp (MIL) on = 1000.00 km
Fuel Rail Pressure (relative to manifold vacuum) = 5177.27 kPa
Fuel Rail Gauge Pressure (diesel, or gasoline direct injection) = 655350.00 kPa
Oxygen Sensor 1 - Fuel?Air Equivalence Ratio = 0.06 ratio
Oxygen Sensor 2 - Fuel?Air Equivalence Ratio = 0.06 ratio
Oxygen Sensor 3 - Fuel?Air Equivalence Ratio = 0.06 ratio
Oxygen Sensor 4 - Fuel?Air Equivalence Ratio = 0.06 ratio
Oxygen Sensor 5 - Fuel?Air Equivalence Ratio = 0.06 ratio
Oxygen Sensor 6 - Fuel?Air Equivalence Ratio = 0.06 ratio
Oxygen Sensor 7 - Fuel?Air Equivalence Ratio = 0.06 ratio
Oxygen Sensor 8 - Fuel?Air Equivalence Ratio = 0.06 ratio
Commanded EGR = 1.57 %
EGR Error = 0.00 %
Commanded evaporative purge = 9.80 %
Fuel Tank Level Input = 12.55 %
Warm-ups since codes cleared = 255.00 count
Distance traveled since codes cleared = error
Evap. System Vapor Pressure = 21.25 Pa
Absolute Barometric Pressure = 215.00 kPa
Oxygen Sensor 1 - Fuel?Air Equivalence Ratio = error
Oxygen Sensor 2 - Fuel?Air Equivalence Ratio = error
Oxygen Sensor 3 - Fuel?Air Equivalence Ratio = error
Oxygen Sensor 4 - Fuel?Air Equivalence Ratio = error
Oxygen Sensor 5 - Fuel?Air Equivalence Ratio = error
Oxygen Sensor 6 - Fuel?Air Equivalence Ratio = error
Oxygen Sensor 7 - Fuel?Air Equivalence Ratio = error
Oxygen Sensor 8 - Fuel?Air Equivalence Ratio = error
Catalyst Temperature: Bank 1, Sensor 1 = 48.00 °C
Catalyst Temperature: Bank 2, Sensor 1 = 48.00 °C
Catalyst Temperature: Bank 1, Sensor 2 = 48.00 °C
Catalyst Temperature: Bank 2, Sensor 2 = 48.00 °C
PIDs supported [41 - 60] = 0xFFFFFFFF
Monitor status this drive cycle = 0x0
Control module voltage = 14.24 V
Absolute load value = 19.61 %
Fuel?Air commanded equivalence ratio = error
Relative throttle position = error
Ambient air temperature = 31.00 °C
Absolute throttle position B = error
Absolute throttle position C = error
Absolute throttle position D = error
Absolute throttle position E = error
Absolute throttle position F = error
Commanded throttle actuator = error
Time run with MIL on = error
Time since trouble codes cleared = error
Maximum value for Fuel?Air equivalence ratio, oxygen sensor voltage, oxygen sensor current, and intake manifold absolute pressure = error
Maximum value for air flow rate from mass air flow sensor = error
Fuel Type = 0x1
Ethanol fuel percentage = error
Absolute Evap system Vapor Pressure = error
Evap system vapor pressure = error
Short term secondary oxygen sensor trim = error
Long term secondary oxygen sensor trim = error
Short term secondary oxygen sensor trim = error
Long term secondary oxygen sensor trim = error
Fuel rail absolute pressure = error
Relative accelerator pedal position = error
Hybrid battery pack remaining life = error
Engine oil temperature = error
Fuel injection timing = error
Engine fuel rate = error
Emission requirements to which vehicle is designed = 0x0
```
