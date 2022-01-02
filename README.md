# Enlite-receiver-sniffer
Program for listening  Enlite transmitter and transmitting decoded data to bluetooth terminal on phone.
With this firmware, you can make your Medlink device ([v3](https://github.com/sarunia/Med-Link-v3), [v4](https://github.com/sarunia/Med-Link-v4) or [v5](https://github.com/sarunia/Med-Link-v5)) to sniff data sent by your Enlite Minilink sensor.
It's important to not which frequency your device works, in general countries from Europe work with 868 MHz, and countries from America work with 915 MHz.
For each frequency there are two versions of the firmware, the one with bytes display raw data sent from the sensor, like this:

```
Enlite sensor normal mode
Transmitter ID: XXXXXXX
Transmitter firmware: 1.3
Sequence number: 0x40
ISIG factor value: 17
Transmitter battery: 158
Last BG raw data: 4380
BG raw data -5min: 4422
BG raw data -10min: 4477
BG raw data -15min: 4565
BG raw data -20min: 4648
BG raw data -25min: 4749
BG raw data -30min: 4819
BG raw data -35min: 4923
BG raw data -40min: 5050
Med-Link battery:  54%
Raw data:
0xA8   0xB5   0x5C   0xCA
0xA6   0x99   0x8C   0xE5
0x4D   0xC7   0x2C   0x71
0xD1   0x5C   0x71   0xC6
0xCC   0x71   0xD2   0x65
0x55   0x95   0x99   0x6A
0x64   0xEC   0x71   0x58
0xDC   0x71   0x36   0x5C
0x72   0xC9   0xAC   0x72
0x68   0xDC   0x72   0x36
0x3C   0x63   0x8C   0xBC
0x63   0x2E   0xA5   0x55
0x65   0x6C   0x5A   0xA8
Decoded:
0xAB   0x0F   0x2A   0x89
0x3E   0x0D   0x12   0x11
0x40   0x11   0x1C   0x11
0x46   0x00   0x59   0x5A
0x9E   0x11   0x7D   0x11
0xD5   0x12   0x28   0x12
0x8D   0x12   0xD3   0x13
0x3B   0x13   0xBA   0x00
0x97   0x18   0x00   0x00
Ready
```

Firmwares without bytes display the data without showing the raw data:
```
Enlite sensor normal mode
Transmitter ID: XXXXXXX
Transmitter firmware: 1.3
Sequence number: 0x40
ISIG factor value: 17
Transmitter battery: 158
Last BG raw data: 4380
BG raw data -5min: 4422
BG raw data -10min: 4477
BG raw data -15min: 4565
BG raw data -20min: 4648
BG raw data -25min: 4749
BG raw data -30min: 4819
BG raw data -35min: 4923
BG raw data -40min: 5050
Med-Link battery:  54%
Ready
```

#Transmitter ID 
is your Minilink identifier.
#Transmitter Firmware
displays which version of the firmware is installe at your Minilink.
#Sequence number: 
This number is a sequential id that start from 0x00 and goes up to 0x71, the first number after the x, identifies a new data sent from the Enlite sensor, and the last number is 0 or 1, and it identifies the first (0) or the second (1) sensor data sent, for each step.
#ISIG factor value:
Is a fixed value, that is been registered at the factory
Every step Minilink send the last 40 minutes of sensor data read, this are displayed at **BG raw data**
#Med-Link battery
Display the pilot battery percentage.
