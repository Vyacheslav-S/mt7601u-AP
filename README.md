# Orange Pi - MT7601U Access Point and Station Mode support. 
Tested on Armbian 23.02.2 (kernel 5.15.93)


Build module:
$ make -C /lib/modules/$(uname -r)/build M=$(pwd) modules
    # Remove device
$ sudo rmmod mt7601u
$ sudo insmod ./mt7601u.ko
    # Insert device

Check there are no errors in dmesg and interface appeared in ip link, check connection stability.
To make change persistent till next kernel upgrade: 
backup original module and replace with compiled.
To find out where is original module run modinfo mt7601u
(view string filename: /lib/modules/KERNEL_VERSION/kernel/drivers/net/wireless/mediatek/mt7601u/mt7601u.ko).

$ sudo iw list
..............
  Supported interface modes:
      * managed
      * AP
      * AP/VLAN
      * monitor
.................      


