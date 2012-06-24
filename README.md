itop
====

Interrupts 'top-like' utility for Linux

initial idea: http://et.redhat.com/~jmh/tools/xen/itop

Forked it to make it support more CPUs (up to 24 tested)

== Usage
itop [-a|-t]
 -a : force display ALL CPUs (caution if you have many CPUs and a narrow screen) + TOTAL
 -t : DON'T display ALL CPUs, just the TOTAL

Default: display ALL CPUs + TOTAL (unless CPUs > 8, then just display the TOTAL)
