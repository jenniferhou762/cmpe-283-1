# cmpe-283-1

## I finished this homework all by my self.

## How did I complete the assignment
1. I was trying to use google cloud service but unfortunately I can't set it up by following the google's documentation.
2. I reimaged my windows desktop and install a ubuntu 16.0.4 on it.
3. After the linux was installed, I followed with this wiki to setup the build enviroment: https://wiki.ubuntu.com/Kernel/BuildYourOwnKernel
4. I forked the linux kernel code in github and then I found that there is no need to use that fork repo for this assignment. 
5. To make sure what I have done is super clear, I decided to create this repo as empty and download the code from our school system.
6. After the file was successfully built, I failed to insert the module to the kernel(could not insert module ./cmpe283-1.ko: Required key not available.). By checking this page: https://vitux.com/how-to-check-if-your-processor-supports-virtualization-technology/ I noticed that I have to turn off the fastboot in BIOS.
7. After turned off fast boot in BIOS, I still couldn't do insmod. The error was related to can't insert unsigned module, and this was resolved by turning off the security boot in BIOS.
8. The module was finaly inserted into the kernel and we got the first result from the log.
9. Then I added the other MSR and follwed the intel manual to finish the code => https://www.intel.com/content/dam/www/public/us/en/documents/manuals/64-ia-32-architectures-software-developer-vol-3c-part-3-manual.pdf

## output of the program:
[10618.064692] Pinbased Controls MSR: 0x7f00000016
[10618.064692]   External Interrupt Exiting: Can set=Yes, Can clear=Yes
[10618.064693]   NMI Exiting: Can set=Yes, Can clear=Yes
[10618.064693]   Virtual NMIs: Can set=Yes, Can clear=Yes
[10618.064694]   Activate VMX Preemption Timer: Can set=Yes, Can clear=Yes
[10618.064694]   Process Posted Interrupts: Can set=No, Can clear=Yes
[10618.064694] --------------------
[10618.064695] Procbased Controls MSR: 0xfff9fffe0401e172
[10618.064695]   Interrupt-window exiting: Can set=Yes, Can clear=Yes
[10618.064696]   Use TSC offsetting: Can set=Yes, Can clear=Yes
[10618.064696]   HLT exiting: Can set=Yes, Can clear=Yes
[10618.064696]   INVLPG exiting: Can set=Yes, Can clear=Yes
[10618.064697]   MWAIT exiting: Can set=Yes, Can clear=Yes
[10618.064697]   RDPMC exiting: Can set=Yes, Can clear=Yes
[10618.064697]   RDTSC exiting: Can set=Yes, Can clear=Yes
[10618.064698]   CR3-load exiting: Can set=Yes, Can clear=No
[10618.064698]   CR3-store exiting: Can set=Yes, Can clear=No
[10618.064698]   CR8-load exiting: Can set=Yes, Can clear=Yes
[10618.064699]   CR8-store exiting: Can set=Yes, Can clear=Yes
[10618.064699]   Use TPR shadow: Can set=Yes, Can clear=Yes
[10618.064700]   NMI-window exiting: Can set=Yes, Can clear=Yes
[10618.064700]   MOV-DR exiting: Can set=Yes, Can clear=Yes
[10618.064700]   Unconditional I/O exiting: Can set=Yes, Can clear=Yes
[10618.064701]   Use I/O bitmaps: Can set=Yes, Can clear=Yes
[10618.064701]   Monitor trap flag: Can set=Yes, Can clear=Yes
[10618.064701]   Use MSR bitmaps: Can set=Yes, Can clear=Yes
[10618.064702]   MONITOR exiting: Can set=Yes, Can clear=Yes
[10618.064702]   PAUSE exiting: Can set=Yes, Can clear=Yes
[10618.064703]   Activate secondary controls: Can set=Yes, Can clear=Yes
[10618.064703] --------------------
[10618.064703] Procbased Controls 2 MSR: 0x8ff00000000
[10618.064703]   Virtualize APIC accesses: Can set=Yes, Can clear=Yes
[10618.064704]   Enable EPT: Can set=Yes, Can clear=Yes
[10618.064704]   Descriptor-table exiting: Can set=Yes, Can clear=Yes
[10618.064705]   Enable RDTSCP: Can set=Yes, Can clear=Yes
[10618.064705]   Virtualize x2APIC mode: Can set=Yes, Can clear=Yes
[10618.064705]   Enable VPID: Can set=Yes, Can clear=Yes
[10618.064706]   WBINVD exiting: Can set=Yes, Can clear=Yes
[10618.064706]   Unrestricted guest: Can set=Yes, Can clear=Yes
[10618.064706]   APIC-register virtualization: Can set=No, Can clear=Yes
[10618.064707]   Virtual-interrupt delivery: Can set=No, Can clear=Yes
[10618.064707]   PAUSE-loop exiting: Can set=No, Can clear=Yes
[10618.064708]   RDRAND exiting: Can set=Yes, Can clear=Yes
[10618.064708]   Enable INVPCID: Can set=No, Can clear=Yes
[10618.064708]   Enable VM functions: Can set=No, Can clear=Yes
[10618.064709]   VMCS shadowing: Can set=No, Can clear=Yes
[10618.064709]   Enable ENCLS exiting: Can set=No, Can clear=Yes
[10618.064709]   RDSEED exiting: Can set=No, Can clear=Yes
[10618.064710]   Enable PML: Can set=No, Can clear=Yes
[10618.064710]   EPT-violation #VE: Can set=No, Can clear=Yes
[10618.064711]   Conceal VMX nonroot operation from Intel PT: Can set=No, Can clear=Yes
[10618.064711]   Enable XSAVES/XRSTORS: Can set=No, Can clear=Yes
[10618.064711]   Mode-based execute control for EPT: Can set=No, Can clear=Yes
[10618.064712]   Use TSC scaling: Can set=No, Can clear=Yes
[10618.064712] --------------------
[10618.064712] Exit Controls MSR: 0x7fffff00036dff
[10618.064713]   Save debug controls: Can set=Yes, Can clear=No
[10618.064713]   Host address-space size: Can set=Yes, Can clear=Yes
[10618.064713]   load IA32_PERF_GLOBAL_CTRL: Can set=Yes, Can clear=Yes
[10618.064714]   Acknowledge interrupt on ezit: Can set=Yes, Can clear=Yes
[10618.064714]   SAVE IA32_PAT: Can set=Yes, Can clear=Yes
[10618.064714]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[10618.064715]   Save IA32_EFER: Can set=Yes, Can clear=Yes
[10618.064715]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[10618.064716]   Save VMX-preemption timer value: Can set=Yes, Can clear=Yes
[10618.064716]   Clear IA32_BNDCFGS: Can set=No, Can clear=Yes
[10618.064716]   Conceal VM exits from intel PT: Can set=No, Can clear=Yes
[10618.064717] --------------------
[10618.064717] Entry Controls MSR: 0xffff000011ff
[10618.064717]   Load debug controls: Can set=Yes, Can clear=No
[10618.064718]   IA-32e mode guest: Can set=Yes, Can clear=Yes
[10618.064718]   Entry to SMM: Can set=Yes, Can clear=Yes
[10618.064719]   Deactivate dual-monitor treatment: Can set=Yes, Can clear=Yes
[10618.064719]   Load IA32_PERF_GLOBAL_CTRL: Can set=Yes, Can clear=Yes
[10618.064720]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[10618.064720]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[10618.064720]   Load IA32_BNDCFGS: Can set=No, Can clear=Yes
[10618.064721]   Conceal VM entries from Intel PT: Can set=No, Can clear=Yes
