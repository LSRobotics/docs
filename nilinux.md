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

### [Introduction to FPGA Interface C API](http://www.ni.com/product-documentation/9036/en/)
Outline:

NI provides library for FPGA access using C. However, FPGA is programmed using LabVIEW.
![NIGraph1](http://www.ni.com/cms/images/devzone/tut/c_fpga_interface_diagram_dz.png)

NI maintains their proprietary C IDE with full access to their system libraries: [LabWindows /CVI](http://www.ni.com/lwcvi/). GCC is also supported. No knowledge about clang :(

![NIGraph2](http://www.ni.com/cms/images/devzone/tut/Introduction_to_FPGA_Interface_C_API_Software_Options.png)

Note that NI might not provide real-time functionalities for C/C++.

 - GCC-neabi for x64 Linux: [oecore-x86_64-x86_64-toolchain-2.0.sh](http://lumen.ni.com/nicif/US/GB_NIDU/content.xhtml?du=http://www.ni.com/download/labview-real-time-module-2014/4959/en/)
 - http://www.ni.com/tutorial/14625/en/ provides build flags for gcc cross-compiling.
 - 
