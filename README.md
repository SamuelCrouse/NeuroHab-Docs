# QUICK START GUIDE

## ARDUINO IDE DEPENDENCIES
FED3 by Lex Kravitz : 1.16.3<br>
CapacitiveSensor by Paul Bagder : 0.5.1<br>

# NeuroHab Basic Setup and Use
## NeuroHab_firm
<b>NeuroHab_Lib</b> goes in your arduino library folder. Probably: "C:\Users\username\Documents\Arduino\libraries\PLACE_HERE"

<b>The following go in your sketches folder.</b> <br>

NeuroHab-ESP_Logging <br>
NeuroHab-ESP_Logging_Setclock <br>
NeuroHab-MEGA_Example <br>
NeuroHab-MEGA_basic_lick <br>
NeuroHab-MEGA_flush_lines <br>


## Arduino IDE Board Selection
Files labeled -ESP will use <b>ESP32 Dev Module</b> <br>
Files labeled -MEGA will use <b>Arduino Mega or Mega 2560</b> <br>


## Flashing ESP32 Time Clock
Upload NeuroHab-ESP_Logging_Setclock to the Core to set the clock on the LCD screen. You MUST now reflash with NeuroHab-ESP_Logging.<br>
After selecting upload if the board does not automatically connect you made need to hold the boot button on the board. *The small button to the right of the micro-usb connection cable.<b>


## Flashing Arduino Mega 2560
Select the Arduino Mega 2560 COM6 (or COMX) from the drop down and select upload. 


## Removing Air Bubbles from Lines (flush lines)
To remove air bubbles from your lines you need to flash the Arduino Mega (lower square port) with <b>NeuroHab-MEGA_flush_lines</b>.<br>
By default this program will cycle open and closing each valve individually for 5 seconds. If this does not flush the lines properly, change the following lines of code.<br>

      if (valve == 1) {
          digitalWrite(VALVE_1, HIGH);
      }
      if (valve == 2) {
          digitalWrite(VALVE_2, HIGH);
      }
      if (valve == 3) {
          digitalWrite(VALVE_3, HIGH);
      }

      to

      if (valve == 1) {
          digitalWrite(VALVE_1, HIGH);
      }
      if (valve == 2) {
          digitalWrite(VALVE_1, HIGH);
      }
      if (valve == 3) {
          digitalWrite(VALVE_1, HIGH);
      }

Change VALVE_1 to VALVE_2 or VALVE_3 to flush each line completely. You must flash the Arduino each time you change the valve number.
#### You must reflash the Arduino with your desired code to resume experiment behavior.


# Hardware Installation
## Lickport Installation
Each of 3 lickports comes with the port and magnetic housing. The housing inner diameter is ~21mm and the holes are sized for 3mm screws.<br>
To install I recommend placing the magnetic housing on the wall of your homecage and marking both mounting holes and the center 21mm hole with a sharpie. Then, use a 3.5mm drill bit to drill the mounting holes and a 20mm saw bit or similar to drill the center hole. Use the provided screws to mount the lickport housing on the wall. The lickport itself should now easily fit through the wall and allow liquid delivery into the homecage on activation.
