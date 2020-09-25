# peters-raspberry-pi-guide

hey, I'm peter. when I set up and started using my raspberry pi for fun robotics stuff in 2020-08, I wrote down the steps here for my own reference so I could repeat them in the future. I hope they might help you.

## getting started + installation

0. buy a raspberry pi. make sure you have a power adapter and a micro sd card with your purchase. a battery and fun connectors are nice. if you buy connectors, make sure you've got all the necessary intermediary connectors. sometimes you get fun new widget but you realize you need some intermediary board to connect it. make sure you do some googles!
1. create an SD card with the Raspian operating system. I used the imager software https://www.raspberrypi.org/downloads/ and Raspbian Lite (no desktop).
2. if you chose raspbian then you can boot up your raspberry pi with an ethernet connection and use user `pi` w/ password `rapsberry` (https://www.raspberrypi.org/documentation/linux/usage/users.md#:~:text=The%20default%20user%20is%20pi,and%20change%20each%20user's%20password.)
If you want to connect remotely, either follow the below lan scan step or pull out a monitor and login then run `ip addr`

To find the IP of your pi so you can avoid dragging out another mointor, you can use this Lan Scan script and try to SSH to each. Sorry, but its a bit slow!
```
for ip in $(seq 1 254); do ping -c 1 192.168.1.$ip>/dev/null;
    [ $? -eq 0 ] && echo "192.168.1.$ip UP" || : ;
done
```
