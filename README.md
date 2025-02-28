# amdctl
Set P-State voltages and clock speeds on recent AMD CPUs on Linux.

### Disclaimer:

This software can damage your hardware, use at your own risk.

## Description:

Tool for changing voltages and clock speeds for AMD processors with control over every power state and CPU core.

### Usage:

Make the binary executable `chmod +x amdctl`.

Run the program for a list of options, you can type `./amdctl` to run it.

### Compilation:

You can compile with the program `make`.

### Supported CPU Families:

AMD CPU family's 10h(K10), 11h(Turion), 12h(Fusion), 15h(Bulldozer), 16h(Jaguar), 17h(Zen - Untested).

Note that Zen/17h has not been tested, I only modified the program based on the AMD programming reference, use with caution.

This would be most AMD CPU's between 2007 and 2018.

You can find your CPU family by typing `cat /proc/cpuinfo` in a terminal, the values there are in decimal.  
10h is equivalent to 16, 16h 22 for example.

The program will check if your CPU is supported when run.

### Unsupported CPU Families:

AMD CPU family 9h(K9) and earlier.

AMD 13h, I could not find any info on this, so I assume this CPU family does not exist.

AMD 14h(Bobcat) family, these have a different way of calculating clock speed, without a CPU to test I won't attempt to support them.

Anything newer than 17h (for now).

### Requirements:

Root access.

Msr kernel module.

To manually load the msr module: `sudo modprobe msr`

To automatically load the msr module see the [arch wiki](https://wiki.archlinux.org/index.php/Kernel_modules#Automatic_module_handling).

### References:

https://developer.amd.com/resources/developer-guides-manuals/
https://wiki.archlinux.org/index.php/K10ctl  
http://sourceforge.net/projects/k10ctl/  
https://web.archive.org/web/20090914081440/http://www.ztex.de/misc/k10ctl.e.html  
https://01.org/msr-tools  
https://en.wikipedia.org/wiki/List_of_AMD_CPU_microarchitectures  
http://users.atw.hu/instlatx64/  
