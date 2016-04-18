# Power Saving on Dell XP15 under Arch

Initially, idle power consumption was around 20w. After tweaking, I get somwehere between 7-10w, doubling (theoretically) the battery life. Here's how.

1. Check the [wiki](https://wiki.archlinux.org/index.php/Power_management)
2. Check this [post](https://bbs.archlinux.org/viewtopic.php?id=204739)
3. Use Kernel 4.4.5-1. Kernel 4.5.0-1 has massive power consumption.
4. Install [tlp](https://wiki.archlinux.org/index.php/TLP)
5. Install [powertop](https://wiki.archlinux.org/index.php/Powertop)
6. Install [bumblebee](https://wiki.archlinux.org/index.php/Bumblebee)
