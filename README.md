# fisktankRestAPI

## Description
A Raspberry Pi with a pair of [DS18B20 temperature sensors](https://www.amazon.com/gp/product/B007R9UU5C) wired into the GPIO header with a breadboard.  I put one sensor in the tank, and the other sensor in the room.   That way, I can track the effect of the ambient room temperature on the tank temperature.

NOTE: Most DS18B20 temperature sensors have a metal housing on the end of the probe.  I tried those first, as they're very common.  They only held up for about a month in my saltwater fish tank.   That's when I switched to the full-plastic version (see link above).

## Configuring the Rapberry Pi
1. Add "dtoverlay=w1-gpio" to the bottom of "/boot/config.txt"
1. Add "w1-gpio" and "w1-therm" to /etc/modules
1. You should now see two devices files in /sys/bus/w1/devices

## Setting up the installation
1. apt-get install python-pip
1. pip install virtualenv
1. git clone fishtankRestAPI
1. cd fishtankRestAPI
1. virtualenv flask
1. flask/bin/pip install flask

## Testing the installation
1. ./fishtankRestAPI.py
1.  curl -i http://127.0.0.1:5000/fishtank/temp

