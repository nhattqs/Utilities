# CONKY widget - The CPU Linux Monitoring Tool
Ref: 
* https://www.youtube.com/watch?v=s5csaCSyfoo
* Original config file - https://neoncipher.net/v/conky/
* Customize one - [conky.conf](./conky.conf)

## Install Conky widget:
```
sudo apt-get install conky-all
```
* Start the widget:
```
conky
```
* Mark it running in startup by adding one new process pointed to `conky` command in `Startup Application References`.

## Customizing the widget theme
* Change the configuration path
```
conky -C > ~/Documents/conky.conf
```
* Download the template `conky.conf` and update the default one.
```
mkdir ~/.config/conky
cp -v ~/path/to/download/conky.conf ~/.config/conky/
```
=> Whenver we make the file change, we need to `cp` the file to the `~/.config/conky` path to take affect.
* Get the name of network device which we will monitor by running command:
```
sudo ifconfig
or
ip link show
```
Then update the `[network_device_name]` in NETWORK section with the name retrieved from the command above.
* To get number of processors, run
```
nproc
```
With each processor, we need add 2 config lines
```
Freq: ${freq 1}MHz
Core2 ${cpu cpu2}% ${cpubar cpu2}
```
* We need to figure out what kind of sensor our device supports
```
+ ls /sys/class/hwmon
then loop through all items to check name by
+ ls /sys/class/hwmon/hwmon0/name
```
For instance, we need to monitor temperature of `cputemp` (TEMPERATURES section), we will replace the configuration with `hwmon` number corresponding to the sensor.