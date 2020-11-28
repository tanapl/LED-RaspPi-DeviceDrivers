# Driver for LED control

## About / Synopsis

* This project is for turning on an LED in Linux platform using C programming language.
* Project status: finished

Youtube video: [link](https://)

## Table of contents

* [Title / Respository Name](#title--repository-name)
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

Code: [link](https://)
Makefile: [link](https://)

### Requirements

The code will works with the requirements below.

  * Ubuntu native/Ubuntu on WSL
  * Raspberri Pi 3 above
  * LED x 3
  * 300Ω of resistor x 3
  * Female to male jumper wire x 4
  * Breadboard
  
### Circuit

The Figure below is representing how to setup the circuit for this project.


### Build

1. Open a Raspberry Pi on Ubuntu native (or WSL) and  Makefile in the folder that you want to save by using vim (optional).

  $ vi Makefile
  
2. Make a new .c file by using vim (optional) and save the code. Based on Makefile, the name of the file is "myled.c"

  $ vi myled.c
  
3. Type "make" and if there is no target mentioned at the beginning (or old), the process of that target will run.

  $ make
  
4. Install the modules.

  $ sudo insmod myled.ko
  
    * In case, to erase the old module and kernel module in order to make (compile) the new one.
    
  $ sudo rmmod myled
  $ make clean
  
5. Change the permissions on the resulting  /dev/myled0

  $ sudo chmod 666 /dev/myled0
  
### Run

There are 4 patterns for running LED in this program.

1. Only red LED

  $ sudo 1 > /dev/myled0
  
2. Only green LED

  $ sudo 2 > /dev/myled0
  
3. Only white LED

  $ sudo 3 > /dev/myled0
  
4. LEDs show

  $ sudo 4 > /dev/myled0
  
5. To turn off all the LEDs.

  $ sudo 0 > /dev/myled0
  
### About the Project

Mainly, ...

### Preference

[link]

### License

[link]
