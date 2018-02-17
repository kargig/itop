itop
====

Interrupts 'top-like' utility for Linux

initial idea: http://et.redhat.com/~jmh/tools/xen/itop

Forked it to make it support more CPUs (up to 24 tested)

Modified by [Mitch Williams](mailto:mitch.a.williams@intel.com) to enable filtering,
user-specified timing interval, and to print the full interrupt name (instead
of the interrupt type and a tiny bit of the name).

Usage
-----

```
itop [-a|-t|-f <string>|-i <interval>]

 -a : force display ALL CPUs (caution if you have many CPUs and a narrow screen) + TOTAL
 -t : DON'T display ALL CPUs, just the TOTAL
```

Default: display ALL CPUs + TOTAL (unless CPUs > 8, then just display the TOTAL)

```
-f <string>: only show interrupts that match on the specified string
```

Default: display all interrupts

```
-i <interval>: sample every <interval> seconds. Can be fractional.
```

Default: sample and display every second.
Note: specifying very short intervals without filters may cause display flickering.

Examples
--------

* Display all interrupts, updating once per second:
```
$ itop
```
* Only display interrupts related to eth0, once per second:
```
$ itop -f eth0
```
* Only display interrupts owned by the ahci driver, every five seconds:
```
$ itop -f ahci -n 5
```
* Only display interrups owned by the ixgbe driver, ten times per second:
```
$ itop -f ixgbe -n 0.1
```
