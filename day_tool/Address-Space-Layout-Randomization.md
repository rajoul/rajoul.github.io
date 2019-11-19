# Address-Space-Layout-Randomization (ASLR)

The Linux kernel has a defense mechanism named address space layout randomization (ASLR), which make the adress memory of each running 
program random.So the Buffer overflow attack is soo hard for an attacker to be exploited. it is appeared as a patch in 2005 as a solution to prevent stack overflow attack.
#### 1-Sysctl
/usr/sbin/sysctl is a command used to display kernel parameters located in /proc/sys/
in order to enable od disable ASLR, the file /proc/sys/kernel/randomize_va_space contain kernel.randomize_va_space that take:
<br>0 if disabled </br>
<br> 1 id enabled </br>
<br>2 = Full Randomization </br>
