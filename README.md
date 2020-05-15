[Drive link](https://drive.google.com/open?id=1bKhigrruck6pl0mA11rRQiQc2liFzoFC) for all files,
# Arduino_custom_board
 
The boards.txt file contains various parameters for various menu options for different Arduino supported microcontrollers. These options for the board are some of the parameters which are only specific for some board or they are shown only when the microcontroller is selected. The boards.txt file is situated in the directory **./Arduino15/packages/arduino/hardware/avr/1.8.2/boards.txt.** As these are hidden in the home directory for linux we have to press ctrl+H thus to show hidden files.

There are other files as shown in the below column along with directories, 

Name          | Description   | Type
------------- | ------------- | -------------
boards.txt    | Contains the build instructions and configurations for each board  | Files
platform.txt  | Contains the compiler instructions used for building programs for the board and we have to change only the version and type of the board  | File
bootloaders    | Contains bootloader for each board and bootloader is important and custom for each board  | direcotry
varients    | Contains the board layout and pin configuration for each board in the package. This is where we will change most of the configuration for our custom board  | Directory

These are the various files situated in the 1.8.2 folder, for now we have to edit boards.txt file,

```ruby
uno.name=e-Yantra eYFi_Mega  
uno.vid.0=0x2341
uno.pid.0=0x0043
uno.vid.1=0x2341
uno.pid.1=0x0001
uno.vid.2=0x2A03
uno.pid.2=0x0043
uno.vid.3=0x2341
uno.pid.3=0x0243
uno.upload.tool=avrdude
uno.upload.protocol=arduino
uno.upload.maximum_size=32256
uno.upload.maximum_data_size=2048
uno.upload.speed=115200
uno.bootloader.tool=avrdude
uno.bootloader.low_fuses=0xFF
uno.bootloader.high_fuses=0xDE
uno.bootloader.extended_fuses=0xFD
uno.bootloader.unlock_bits=0x3
uno.bootloader.lock_bits=0x0F
uno.bootloader.file=optiboot/optiboot_atmega328.hex
uno.build.mcu=atmega328p
uno.build.f_cpu=16000000L
uno.build.board=AVR_UNO
uno.build.core=arduino
uno.build.variant = standard
```

Here we have added the name as **e-Yantra eYFi_Mega**

as our board name so we have to just change the name now whenever you will be plugging the uno in the pc there you will see this name instead of Arduino/Genuine Uno.

Installing Arduino CLI:
- MacOS/Linux:
```
	brew update
	brew install arduino-cli
```
- Windows:
	- Link : [Windows 64 bit](https://downloads.arduino.cc/arduino-cli/arduino-cli_latest_Windows_64bit.zip)
	- Link : [Windows 32 bit](https://downloads.arduino.cc/arduino-cli/arduino-cli_latest_Windows_32bit.zip)

Commands:
1. arduino-cli is a container of commands and each command has its own dedicated help text that can be shown with the help command like this:
```
$ arduino-cli help core
```
2. Arduino CLI doesn't strictly require a configuration file to work because the command line interface provides any possible functionality. However, having one can spare you a lot of typing when issuing a command, so let's go ahead and create it with:
```
$ arduino-cli config init
```
3. To create a new sketch named MyFirstSketch in the current directory, run the following command:
```
$ arduino-cli sketch new MyFirstSketch
```
This file will be saved in the /home/username/ directory
4. The first thing to do upon a fresh install is to update the local cache of available platforms and libraries by running:
```
$ arduino-cli core update-index
```
