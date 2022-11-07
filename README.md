### CMPE 283
#### Assignment 1

**Steps I used to complete the assignment :**   
1. Downloaded and installed VMware Fusion for Mac OS.
2. Downloaded Ubuntu disk image from the internet.
3. From the VMware dashboard, created a VM.
4. Enabled VT-X/EPT in the VM settings.
5. Forked the https://github.com/torvalds/linux repository to my Github account (https://github.com/anesh13/linux).
6. On the VM's SSH shell, ran the *uname -r* command to check the OS version.
7. Ran the *sudo apt install make* and *sudo apt install gcc* commands.
8. Checked if gcc and make were properly installed by running *gcc -v* and *make -v* commands.
9. Ran the *sudo apt install build-essential kernel-package fakeroot libncurses5-dev libssl-dev ccache bison flex libelf-dev qemu qemu-kvm libvirt-bin  bridge-utils  virt-manager* command to install packages needed to build a kernel.
10. Created two directories by running the *mkdir linuxrepo* command and the *mkdir cmpe283* command.
10. Inside the *linuxrepo* directory, initialized git using *git init*.
11. Cloned the forked linux repository. This took a long time to fetch and failed a few times before I could successfully pull the code.
12. Similarly, inside the *cmpe283* directory, cloned the assignment repository (https://github.com/anesh13/assignment283) with the Makefile and .c files from Canvas.
14. Update the .c file to include the other capabilities by referring to the SDM manual. The volume and sections have been mentioned in comments in the code.
15. Inside this directory, ran the *make* command.
16. Ran the *ls* command.
  - Makefile
  - README.nd
  - cmpe283-1.k0
  - cmpe283-1 .mod.c
  - Module.symvers
  - cmpe283-1.c
  - cmpe283-1.mod
  - cmpe283-1.mod.o
  - cmpe283-1.
  - modules.order
17. Ran *sudo insmod ./cmpe283-1.ko* command.
18. Once the module was inserted, ran the *sudo dmesg* to display driver messages.
19. These are the outputs that the code I added generated.
[1039.551327] CMPE 283 Assignment 1 Module Start  
[1039.551330] Pinbased Controls MSR: 0x3f00000016  
[1039.551331] External Interrupt Exiting: Can set=Yes, Can clear=Yes  
[1039.551332] NMI Exiting: Can set=Yes, Can clear=Yes  
[1039.551333] Virtual NMIs: Can set=Yes, Can clear=Yes  
[1039.551333] Activate VMX Preemption Timer: Can set=No, Can clear=Yes  
[1039.551334] Process Posted Interrupts: Can set=No, Can clear=Yes  
[1039.551335] Primary Process-Based Controls MSR: Oxfff9fffe0401e172  
[1039.551336] Interrupt-window exiting: Can set=Yes, Can clear=Yes  
[1039.551336] Use TSC offsetting: Can set=Yes, Can clear=Yes  
[1039.551337] HLT exiting: Can set=Yes, Can clear=Yes  
[1039.551337] INVLPG exiting: Can set=Yes, Can clear=Yes  
[1039.551337] MWAIT exiting: Can set=Yes, Can clear=Yes  
[1039.551338] RDPMC exiting: Can set=Yes, Can clear=Yes  
[1039.551338] RDTSC exiting: Can set=Yes, Can clear=Yes  
[1039.551339] CR3- load exiting: Can set=Yes, Can clear=No  
[1039.551339] CR3-store exiting: Can set=Yes, Can clear=No  
[1039.551340] CR8- load exiting: Can set=Yes, Can clear=Yes  
[1039.551340] CR8-store exiting: Can set=Yes, Can clear=Yes  
[1039.551341] Use TPR shadow: Can set=Yes, Can clear=Yes  
[1039.551341] NMI-window exiting: Can set=Yes, Can clear=Yes  
[1039.551342] MOV-DR exiting: Can set=Yes, Can clear=Yes  
[1039.551342] Unconditional I/0 exiting: Can set=Yes, Can clear=Yes  
[1039.551343] Use I/0 bitmaps: Can set=Yes, Can clear=Yes  
[1039.551343] Monitor trap flag: Can set=Yes, Can clear=Yes  
[1039.551343] Use MSR bitmaps: Can set=Yes, Can clear=Yes  
[1039.551344] MONITOR exiting: Can set=Yes, Can clear=Yes  
[1039.551344] PAUSE exiting: Can set=Yes, Can clear=Yes  
[1039.551345] Activate secondary controls: Can set=Yes, Can clear=Yes  
[1039.551346] Secondary Process-Based Controls MSR: 0x153cfe000000©  
[1039.551347] Virtualize APIC accesses: Can set=No, Can clear=Yes  
[1039.551347] Enable EPT: Can set=Yes, Can clear=Yes  
[1039.551348] Descriptor-table exiting: Can set=Yes, Can clear=Yes  
[1039.551348] Enable RDTSCP: Can set=Yes, Can clear=Yes  
[1039.551348] Virtualize x2APIC mode: Can set=Yes, Can clear=Yes  
[1039.551349] Enable VPID: Can set=Yes, Can clear=Yes  
[1039.551350] WBINVD exiting: Can set=Yes, Can clear=Yes  
[1039.551350] Unrestricted guest: Can set=Yes, Can clear=Yes  
[1039.551351] APIC-register virtualization: Can set=No, Can clear=Yes  
[1039.551351] Virtual-interrupt delivery: Can set=No, Can clear=Yes  
[1039.551351] PAUSE- loop exiting: Can set=Yes, Can clear=Yes  
[1039.551352] RDRAND exiting: Can set=Yes, Can clear=Yes  
[1039.551352] Enable INVPCID: Can set=Yes, Can clear=Yes  
[1039.551353] Enable VM functions: Can set=Yes, Can clear=Yes  
[1039.551353] VMCS shadowin: Can set=No, Can clear=Yes  
[1039.551354] Enable ENCLS exiting: Can set=No, Can cLear=Yes  
[1039.551354] RDSEED exiting: Can set=Yes, Can clear=Yes  
[1039.551355] Enable PML: Can set=No, Can clear=Yes  
[1039.551355] EPT-violation #VE: Can set=Yes, Can clear=Yes  
[1039.551356] Conceal VMX from PT: Can set=No, Can clear=Yes  
[1039.551356] Enable XSAVES/XRSTORS: Can set=Yes, Can clear=Yes  
[1039.551357] Mode-based execute control for EPT: Can set=No, Can clear=Yes  
[1039.551357] Sub-page write permissions for EPT: Can set=No, Can clear=Yes  
[1039.551357] Intel PT uses guest physical addresses: Can set=No, Can clear=Yes  
[1039.551358] Use TSC scaling: Can set=No, Can clear=Yes  
[1039.551358] Enable user wait and pause: Can set=No, Can clear=Yes  
[1039.551359] Enable ENCLV exiting: Can set=No, Can clear=Yes  
[1039.551360] Tertiary Process-Based Controls MSR: 0x3fffff00036dff  
[1039.551360] LOADIWKEY exiting: Can set=Yes, Can clear=No  
[1039.551361] Enable HLAT: Can set=Yes, Can clear=Yes  
[1039.551361] EPT paging-write control: Can set=Yes, Can clear=No  
[1039.551362] Guest-paging Verification: Can set=Yes, Can clear=Yes  
[1039.551363] Exit Controls MSR: 0x3fffff00036dff  
[1039.551363] Save debug controls: Can set=Yes, Can clear=No  
[1039.551364] Host address-space size: Can set=Yes, Can clear=Yes  
[1039.551364] Load IA32 PERF _GLOBAL CTRL: Can set=Yes, Can clear=No  
[1039.551365] Acknowledge interrupt on exit: Can set=Yes, Can clear=Yes  
[1039.551365] Save IA32_PAT: Can set=Yes, Can clear=Yes  
[1039.551366] Load IA32 PAT: Can set=Yes, Can clear=Yes  
[1039.551366] Save IA32_EFER: Can set=Yes, Can clear=Yes  
[1039.551366] Load IA32 EFER: Can set=Yes, Can clear=Yes  
[1039.551367] Save VMX-preemption timer value: Can set=No, Can clear=Yes  
[1039.551367] Clear IA32 BNDCFGS: Can set=No, Can clear=Yes  
[1039.551367] Conceal VMX from PT: Can set=No, Can clear=Yes  
[1039.551368] Clear IA32_RTIT_CT: Can set=No, Can clear=Yes  
[1039.551368] Load CET state: Can set=No, Can clear=Yes  
[1039.551369] Load PKRS: Can set=No, Can clear=Yes  
[1039.551369] Entry Controls MSR: Oxf3ff000011ff  
[1039.551370] Load debug controls: Can set=Yes, Can clear=No  
[1039.551370] IA-32e mode guest: Can set=Yes, Can clear=Yes  
[1039.551371] Entry to SMM: Can set=No, Can clear=Yes  
[1039.551371] Deactivate dual-monitor treatment: Can set=No, Can clear=Yes  
[1039.551371] Load IA32 _PERF_GLOBAL_CTRL: Can set=Yes, Can clear=Yes  
[1039.551372] Load IA32 _PAT: Can set=Yes, Can clear=Yes  
[1039.551372] Load IA32_EFER: Can set=Yes, Can clear=Yes  
[1039.551373] Load IA32 BNDCFGS: Can set=No, Can clear=Yes  
[1039.551373] Conceal VMX from PT: Can set=No, Can clear=Yes  
[1039.551374] Load IA32 _RTIT_CTL: Can set=No, Can clear=Yes  
[1039.551374] Load CET state: Can set=No, Can clear=Yes  
[1039.551375] Load PKRS: Can set=No, Can clear=Yes  
