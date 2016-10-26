# NILinux

Documentations related to NI Linux Real-Time.

### [Under the hood of NI linux Real-Time](http://www.ni.com/white-paper/14626/en/)
Outline:
 1. WebDAV support for file transfer
 2. LabVIEW stuffs - System Call VI (LabVIEW's shell command execution stuffs) and Call Library Function Node (A wrapper for C/C++ ABI/API access)
 3. ** `opkg` built-in package manager ** - NI provides a source for opkg in NILinux at http://download.ni.com/ni-linux-rt .
 4. NI utilies Eclipse for C/C++, [build guide](http://www.ni.com/tutorial/52578/en/).
 5. Real-Time: Linux 2.6 Kernel Completely Fair Scheduler (CFS) NI Remark: Their CFS has improved performance for low-priority task scheduling.
 6. CFS Introduction: [Inside the Linux 2.6 Completely Fair Scheduler.](http://www.ibm.com/developerworks/library/l-completely-fair-scheduler/)
 7. Multicore support: Do not over-preempt: Read the following blockquote for details.
> With respect to multicore support, it’s especially important to follow programming best practices and avoid running a time critical loop on a processor core at 100 percent core utilization. This is because each core in multicore NI Linux Real-Time systems needs some amount of time for OS maintenance/overhead functions, without which system performance can be severely affected. To avoid this performance degradation, ensure that time critical loops allow for the CPU to sleep on the order of 10 milliseconds per 10 seconds of operation to allow for overhead processing.
 8. Serial tasks should be executed on the same core.
 9. LabVIEW stuffs - blackbox their system library calls to get more utilities?

