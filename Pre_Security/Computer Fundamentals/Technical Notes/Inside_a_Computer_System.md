# Inside a Computer System - TryHackMe


## 1. Inside a Computer System

- The motherboard: is like our body's skeleton and nervous system. It holds all the different components in place and connects them.

- The CPU (Central Processing Unit), often called the processor: is comparable to a part of our brain. Just like our brain continuously executes instructions (add numbers, pour milk in a bowl, and so on), a CPU does the same for a computer. Modern CPUs have multiple cores that handle instructions in parallel. The CPU connects to the motherboard via the CPU socket.

- RAM (Random Access Memory): is comparable to our brain's short-term or working memory. When working on a task, we keep relevant information in mind temporarily. RAM does the same - it holds data that the CPU needs quick access to. RAM is volatile: when power is lost, all contents are gone. Modern RAM modules use technologies like DDR5 or DDR6 for increased speed and performance.

- SSDs and HDDs are storage devices, comparable to our long-term memory. Just like fond memories are remembered permanently, data is saved long-term on storage devices. HDDs use older technology with moving parts, limiting performance. SSDs have no moving parts and use memory chips, allowing much faster speeds. HDDs remain popular for their large capacity at low cost. Storage connects via SATA cables or PCI Express slots.

- PSU supplies energy to all system components. The PSU is essential and requires careful consideration - if components need more power than the PSU can provide, the system will fail. The PSU takes power from an outlet and distributes it via various connectors like the main motherboard connector and Molex connectors.

- The graphics card is comparable to the visual cortex of our brain. Our eyes pick up information and the visual cortex processes it into images. Similarly, the graphics card receives information from the operating system and programs, then outputs processed visual data to a monitor. Graphics cards connect to PCI Express slots on the motherboard.

- Network adapter lets computers communicate with other systems. Network adapters come in wireless and wired variants. Often they're embedded in the motherboard, but they can also be added as expansion cards. Network cards typically connect via PCI Express ports.

## 2. What Happens When You Press the Start Button?

- Step 1: Press the Power Button
When we press the power button on our computer system, a signal is sent to the PSU to allow power to flow.

- Step 2: Firmware starts
Continuing our analogy from step 1, once the body has started up, our core components are up and running, but our brain is not yet conscious. Like our bodies, a computer system contains firmware that allows all its components to start up. The central system that manages this is called the Unified Extensible Firmware Interface (UEFI). Note: We will often see the term BIOS mentioned instead of UEFI. BIOS does the same as UEFI, but has mainly been replaced by UEFI

- Step 3: Power-On Self Test
Now that our body is up and running, it is time to test if everything is functioning as it should. If something isn't, there will be some alarm signals. One of the routines that the UEFI loads is the Power-On Self Test, which tests if every required component is present, configured correctly, and functioning.

- Step 4: Select Boot Device
Once our body is up and running, configured correctly and fully functional, our system searches for the location of our bootup routine to start our consciousness. In our computer system the UEFI holds an ordered list which prioritizes on which device to look first for the boot up routine for the Operating System.

- Step 5: Initiate Bootloader
Now that our system knows the part of our brain where our consciousness is located, it initiates the "load routine" to start it. Our computer systems follow a similar process: On the selected boot device, the bootloader is initiated. This bootloader transfers the Operating System from the selected boot device to the Random Access Memory. Once the OS is transferred, the UEFI gives control over the different components to the OS.