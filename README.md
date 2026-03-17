# Herb-Tower
Herb Tower by Pascal - Solar Addition

Solar-Powered Herb Tower

🖨️ Print Settings & Materials

Main Tower & Solar Components: PETG is highly recommended. Since this will be sitting in direct sunlight and handling water, PETG provides the necessary UV and temperature resistance to prevent warping.

Water Tank Cap: PLA is perfectly fine here, as it doesn't hold structural weight or sit under constant water pressure.

🛠️ Hardware & Design Upgrades

Increased Capacity: The main water reservoir has been extended by 5mm to hold more water between top-offs.

Easy-Fill Spout: Added a dedicated filling spout with a twistable, threaded lid so you no longer have to disassemble the tower to add water.

Custom Solar Mount: Integrated a fitted mount specifically designed for a compact 6V 100mA (90x60mm) Solar Panel.

Dual-Power Switch: Added precisely spaced mounting holes (14.8mm apart) to fit a standard 3-way Mini Micro Slide Switch. This allows you to easily manually toggle the charging input between the Solar Panel and a standard USB wall charger.

⚡ Electronics & Smart Software Features

This build goes far beyond a simple timer. The ESP32 is running custom ESPHome firmware designed for maximum battery efficiency and hardware protection.

Extreme Deep Sleep: The ESP32 is programmed to sleep for 59 minutes, wake up for just 90 seconds to sync time, check schedules, and report battery health to Home Assistant, and then immediately go back to sleep.

Switch: Implemented deep sleep switch to prevent sleeping for maintenance purposes. Added manual pump button and toggle to disable pump when required.

Dual Voltage Monitoring (Custom Dividers):

Solar/USB Input: Uses a 22kΩ / 10kΩ voltage divider to safely step down the 6V solar input, allowing the ESP32 to detect voltage spikes and report exactly when the sun is shining.

Battery Level: Uses a 10kΩ / 10kΩ voltage divider connected to the TP4056 output to give real-time battery voltage and calculate estimated runtimes.

Motor Brownout Protection (Soft-Start): Water pumps pull massive inrush currents that can trip the TP4056's 1.5A safety cutoff. This software uses a PWM "Soft-Start" to gently fade the pump on, mechanically capped at 90% maximum power to keep the current draw perfectly within safe limits.

Battery Protection Cut-off: Hard-coded safety logic completely prevents the water pump from turning on if the battery drops below 3.2V, preventing deep-discharge damage to your LiPo cell.

🛒 Bill of Materials (Base materials and extra needed for this solar addition)

1x ESP32-C3 (or similar low-power microcontroller)

1x TP4056 LiPo Charging Module

1x 3V-5V Mini Submersible Water Pump

1x MX1508 Motor Driver

1x 6V 100mA Solar Panel (90x60mm) - [Available on AliExpress]

1x 3-way Mini Micro Slide Switch (14.8mm hole spacing)

1x USB C Female connector

Resistors: 3x 10kΩ, 1x 22kΩ
