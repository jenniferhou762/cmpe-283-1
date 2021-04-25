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

[436228.273056] CMPE 283 Assignment 1 Module Start
[436228.273059] Pinbased Controls MSR: 0x7f00000016
[436228.273061]   External Interrupt Exiting: Can set=Yes, Can clear=Yes
[436228.273062]   NMI Exiting: Can set=Yes, Can clear=Yes
[436228.273063]   Virtual NMIs: Can set=Yes, Can clear=Yes
[436228.273064]   Activate VMX Preemption Timer: Can set=Yes, Can clear=Yes
[436228.273065]   Process Posted Interrupts: Can set=No, Can clear=Yes
[436228.273066] --------------------
[436228.273067] Procbased Controls MSR: 0xfff9fffe0401e172
[436228.273068]   Interrupt-window exiting: Can set=Yes, Can clear=Yes
[436228.273069]   Use TSC offsetting: Can set=Yes, Can clear=Yes
[436228.273070]   HLT exiting: Can set=Yes, Can clear=Yes
[436228.273071]   INVLPG exiting: Can set=Yes, Can clear=Yes
[436228.273072]   MWAIT exiting: Can set=Yes, Can clear=Yes
[436228.273073]   RDPMC exiting: Can set=Yes, Can clear=Yes
[436228.273074]   RDTSC exiting: Can set=Yes, Can clear=Yes
[436228.273075]   CR3-load exiting: Can set=Yes, Can clear=No
[436228.273076]   CR3-store exiting: Can set=Yes, Can clear=No
[436228.273077]   CR8-load exiting: Can set=Yes, Can clear=Yes
[436228.273078]   CR8-store exiting: Can set=Yes, Can clear=Yes
[436228.273078]   Use TPR shadow: Can set=Yes, Can clear=Yes
[436228.273079]   NMI-window exiting: Can set=Yes, Can clear=Yes
[436228.273080]   MOV-DR exiting: Can set=Yes, Can clear=Yes
[436228.273081]   Unconditional I/O exiting: Can set=Yes, Can clear=Yes
[436228.273082]   Use I/O bitmaps: Can set=Yes, Can clear=Yes
[436228.273083]   Monitor trap flag: Can set=Yes, Can clear=Yes
[436228.273084]   Use MSR bitmaps: Can set=Yes, Can clear=Yes
[436228.273085]   MONITOR exiting: Can set=Yes, Can clear=Yes
[436228.273086]   PAUSE exiting: Can set=Yes, Can clear=Yes
[436228.273087]   Activate secondary controls: Can set=Yes, Can clear=Yes
[436228.273087] --------------------
[436228.273088] Procbased Controls 2 MSR: 0x8ff00000000
[436228.273089]   Virtualize APIC accesses: Can set=Yes, Can clear=Yes
[436228.273090]   Enable EPT: Can set=Yes, Can clear=Yes
[436228.273091]   Descriptor-table exiting: Can set=Yes, Can clear=Yes
[436228.273092]   Enable RDTSCP: Can set=Yes, Can clear=Yes
[436228.273093]   Virtualize x2APIC mode: Can set=Yes, Can clear=Yes
[436228.273094]   Enable VPID: Can set=Yes, Can clear=Yes
[436228.273095]   WBINVD exiting: Can set=Yes, Can clear=Yes
[436228.273096]   Unrestricted guest: Can set=Yes, Can clear=Yes
[436228.273097]   APIC-register virtualization: Can set=No, Can clear=Yes
[436228.273098]   Virtual-interrupt delivery: Can set=No, Can clear=Yes
[436228.273099]   PAUSE-loop exiting: Can set=No, Can clear=Yes
[436228.273100]   RDRAND exiting: Can set=Yes, Can clear=Yes
[436228.273101]   Enable INVPCID: Can set=No, Can clear=Yes
[436228.273102]   Enable VM functions: Can set=No, Can clear=Yes
[436228.273103]   VMCS shadowing: Can set=No, Can clear=Yes
[436228.273104]   Enable ENCLS exiting: Can set=No, Can clear=Yes
[436228.273105]   RDSEED exiting: Can set=No, Can clear=Yes
[436228.273106]   Enable PML: Can set=No, Can clear=Yes
[436228.273106]   EPT-violation #VE: Can set=No, Can clear=Yes
[436228.273108]   Conceal VMX nonroot operation from Intel PT: Can set=No, Can clear=Yes
[436228.273108]   Enable XSAVES/XRSTORS: Can set=No, Can clear=Yes
[436228.273110]   Mode-based execute control for EPT: Can set=No, Can clear=Yes
[436228.273111]   Sub-page write permissions for EPT: Can set=No, Can clear=Yes
[436228.273112]   Intel PT uses guest physical address: Can set=No, Can clear=Yes
[436228.273113]   Use TSC scaling: Can set=No, Can clear=Yes
[436228.273114]   Enable user wait and pause: Can set=No, Can clear=Yes
[436228.273114]   Enable ENCLV exiting: Can set=No, Can clear=Yes
[436228.273115] --------------------
[436228.273116] Exit Controls MSR: 0x7fffff00036dff
[436228.273117]   Save debug controls: Can set=Yes, Can clear=No
[436228.273118]   Host address-space size: Can set=Yes, Can clear=Yes
[436228.273119]   load IA32_PERF_GLOBAL_CTRL: Can set=Yes, Can clear=Yes
[436228.273120]   Acknowledge interrupt on ezit: Can set=Yes, Can clear=Yes
[436228.273121]   SAVE IA32_PAT: Can set=Yes, Can clear=Yes
[436228.273122]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[436228.273123]   Save IA32_EFER: Can set=Yes, Can clear=Yes
[436228.273124]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[436228.273125]   Save VMX-preemption timer value: Can set=Yes, Can clear=Yes
[436228.273125]   Clear IA32_BNDCFGS: Can set=No, Can clear=Yes
[436228.273126]   Conceal VM exits from intel PT: Can set=No, Can clear=Yes
[436228.273127] --------------------
[436228.273128] Entry Controls MSR: 0xffff000011ff
[436228.273129]   Load debug controls: Can set=Yes, Can clear=No
[436228.273130]   IA-32e mode guest: Can set=Yes, Can clear=Yes
[436228.273131]   Entry to SMM: Can set=Yes, Can clear=Yes
[436228.273132]   Deactivate dual-monitor treatment: Can set=Yes, Can clear=Yes
[436228.273133]   Load IA32_PERF_GLOBAL_CTRL: Can set=Yes, Can clear=Yes
[436228.273134]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[436228.273134]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[436228.273135]   Load IA32_BNDCFGS: Can set=No, Can clear=Yes
[436228.273136]   Conceal VM entries from Intel PT: Can set=No, Can clear=Yes
