This repository contains the board files for the NXP MCXN947 protocard (breakout board). 
Pracblink, a directory I created that is a modified version of  blinky program in zephyr docs that only toggled an LED, 
and I modified it so that every time the LED changes state, the program also sends a message (light is blinking!) over the UART serial port. 
Here is a link to the pracblink repo (https://github.com/Blen-E/pracblink.git ). 
Ensure that the pracblink  is in the correct directory (what I named my directory)--> zephyrproject/zephyr/pracblink. 
Ensure that the mcxn_protocard repo is placed in the correct directory → zephyrproject/boards/mcxn947_protocard. 

Zephyr version:  4.2.99

1. Clone this repository and pracblink repository  
2. Enter virtual environment: source ~/zephyrproject/.venv/bin/activate
3. Enter zephyr directory: cd ~/zephyrproject
4. West build
west build -b mcxn947_protocard/mcxn947/cpu0 zephyr/pracblink -- -DBOARD_ROOT=/home/blen-ermias/zephyrproject 
5. West flash
west flash 
6. Enter Picocom 
picocom -b 115200 /dev/ttyACM0 
