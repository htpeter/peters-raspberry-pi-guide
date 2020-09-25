# peters-raspberry-pi-guide

hey, I'm peter. when I set up and started using my raspberry pi for fun robotics stuff in 2020-08, I wrote down the steps here for my own reference so I could repeat them in the future. I hope they might help you.

## getting started + installation

0. buy a raspberry pi. make sure you have a power adapter and a micro sd card with your purchase. a battery and fun connectors are nice. if you buy connectors, make sure you've got all the necessary intermediary connectors. sometimes you get fun new widget but you realize you need some intermediary board to connect it. make sure you do some googles!
1. create an SD card with the Raspian operating system. I used the imager software https://www.raspberrypi.org/downloads/ and Raspbian Lite (no desktop).
2. now we will connect to the pi remotely. if you chose raspbian then you can boot up your raspberry pi with an ethernet connection and use user `pi` w/ password `rapsberry` (https://www.raspberrypi.org/documentation/linux/usage/users.md#:~:text=The%20default%20user%20is%20pi,and%20change%20each%20user's%20password.)
first you need to drag out a monitor and keyboard to connect and enable SSH using these instructions https://www.raspberrypi.org/documentation/remote-access/ssh/

To get your ip address, run `ip addr`. the local address is usually the 2nd listing and starts with 192.168.1 followed by a final additional number.

Later on you may boot up your pi and have forgotten the IP address. So I can avoid dragging out another mointor, I usually use this Lan Scan script and try to SSH to each. This method is a bit slow so I go make a cup of tea or adjust the ping commands timeout parameter.
```
for ip in $(seq 1 254); do ping -c 1 192.168.1.$ip>/dev/null;
    [ $? -eq 0 ] && echo "192.168.1.$ip UP" || : ;
done
```
