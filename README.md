# Summary

This is a basic RFID libarary for the rc522. This simply lets you pull a single tag data and later lets you confirm it using the function `detectKey(uid,block)`

# Installation

This package requires `RPi.GPIO`, which I installed on arch arm using

    yay -S python-raspberry-gpio
	
But ubuntu or rasbian can use,

    pip install RPi.GPIO

To install pibeep simply install the pip package.

    pip install rc522


# Example
Simple example of usage 

	from rc522 import detect,detectKey
	uid,block detect(rst=31,irq=29)
	#Later you can check that the same raid tag is still there using
	if detectKey(uid,block,rst=31,irq=29):
		print("RFID tag is still there")
	else:
		print("RFID tag is vacant!")
