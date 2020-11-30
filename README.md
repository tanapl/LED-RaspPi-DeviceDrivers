# Driver for LED control

## About / Synopsis

* This project is for turning on LEDs in Linux platform using C programming language.
* Project status: finished

Youtube video: [link](https://youtu.be/J-4yFp5CeLo)

## Table of contents

* [Title](#driver-for-led-control)
  * [About / Synopsis](#about--synopsis)
  * [Code](#code)
    * [Requirements](#requirements)
    * [Circuit](#circuit)
    * [Build](#build)
    * [Run](#run)
  * [About the Project](#about-the-project)
  * [Preference](#preference)
  * [License](#license)
  
## Code

* Code: [link](https://github.com/TanapolHongsuwan/LED-with-Raspberri-Pi/blob/main/myled.c)
* Makefile: [link](https://github.com/TanapolHongsuwan/LED-with-Raspberri-Pi/blob/main/Makefile)

### Requirements

The code will works with the requirements below.

  * Ubuntu
  * Raspberri Pi 3 above
  * LED x 3
  * 300Ω of resistor x 3
  * Female to male jumper wire x 4
  * Breadboard
  
### Circuit

The Figure below is representing how to setup the circuit for this project.

<img src="https://user-images.githubusercontent.com/67133469/100526038-c3bcf580-3208-11eb-82ca-1e15431e50fa.jpg" width = "500">

* Red jumper for GPIO_17.
* Green jumper for GPIO_24.
* Yellow jumper for GPIO_25.
* Orange jumper for ground.

### Build

1. First of all, clone this repository with the following command.

       $ git clone https://github.com/TanapolHongsuwan/LED-RaspPi-DeviceDrivers.git
       
       $ cd LED-RaspPi-DeviceDrivers
       
  
2. In the folder, type "make" and if there is no target mentioned at the beginning (or old), the process of that target will run.

       $ make
       
     #### WARNING: When you clone and 'make' the repository, there might be an error like the following. 
     
       Makefile:4: *** missing separator (did you mean TAB instead of 8 spaces?).  Stop.
       
   This is an error after you clone the Makefile's code.
   
   * In this case, you should check Makefile and change all spaces in to TAB.
  
3. Install the modules.

       $ sudo insmod myled.ko
  
   * In this case, to erase the old module and kernel module in order to make (compile) the new one.
    
         $ sudo rmmod myled
       
         $ make clean
  
4. Change the permissions on the resulting  /dev/myled0

       $ sudo chmod 666 /dev/myled0
  
### Run

There are 4 patterns for running LED in this program.

1. Only red LED

       $ echo 1 > /dev/myled0
  
2. Only green LED

       $ echo 2 > /dev/myled0
  
3. Only white LED

       $ echo 3 > /dev/myled0
  
4. LEDs' show

       $ echo 4 > /dev/myled0
  
5. To turn off all the LEDs.

       $ echo 0 > /dev/myled0
  
## About the Project

This is my first project with Raspberry Pi based on Prof. Ryuichi Ueda's template code, learning about device driver by Raspberry Pi and LED on Ubuntu. I've written this in English because I wish I could use this repository to share knowledge with not only Japanese, but all programmers around the world somedays in the future.

## Preference

[Prof. Ryuichi Ueda/robosys_device_drivers](https://github.com/ryuichiueda/robosys_device_drivers)

## License

[GNU General Public License v3.0](https://github.com/TanapolHongsuwan/LED-with-Raspberri-Pi/blob/main/LICENSE/)
