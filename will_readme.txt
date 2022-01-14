cd git
source qmk_venv/bin/activate
cd qmk_firmware
cd keyboards/converter/usb_usb/
cd pro_micro/
nano rules.mk 
	use 8mhz
qmk compile
avrdude -v -p m32u4 -c avr109 -P /dev/ttyACM0 -b 57600 -D -U flash:w:/home/will/git/qmk_firmware/converter_usb_usb_pro_micro_default.hex:i
	tap reset button twice then upload
