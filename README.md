# pro380_modbus2HA
Useful bits and pieces to integrate PRO380MOD meters via modbus into Home Assistant

This is a collection of things you may need to successfully integrate your PRO380MOD electricity meters via RS485 and modbus2TCP into Home Assistant.

1. Hardware
- two SolarLog PRO380MOD meters
- configured as slave 1 (addr 001) and slave 2 (addr 002)
- baudrate 9600, parity even
- daisychain RS485 wiring, 120ohm termination on last PRO380MOD
- PUSR USR DR134 modbus2TCP DIN rail adapter ("Lipstick")

2. Prep
- as the PRO380MOD is labelled and distributed under various brands, several manuals can be found on the web (i.e. Inepro, KDK Dornscheidt, SolarLog etc.)
- the attached xsls contains all known registers with their corresponding decimal values, a friendly name for your HA sensors in English and German, the register type as values for the input_type of your sensors - and a preselected set of registers you may want to bring to HA as sensors
- I had AI chat write me my sensor code based on the attached Excel-file; minor adjustments I had to make, mainly for cosmetical reasons (decimals, unit, friendly names) - although working in my setting, better QA my code for fit in your environment

3. Integration
- use the sensor code in modbus_pro380mod_tcp.yam_ or just use the file (renamed to .yaml, of course) to integrate my sensors.
- pay attention to use your correct modbus2TCP parameters at the top of the file. 
