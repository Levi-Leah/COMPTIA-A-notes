

// Chapter 1: motherboards, processors, memory
# Understanding motherboard
    
```
> **To know on the exam:**
> * form factors like ATX and ITX
> * connector types like PCI, PCIe, power, SATA, eSATA, M.2, headers
> * compatibillity concerns like AMD/Intel sockets, different MB types (e.g. servers, multisocket, desktop, mobile)
> * BIOS/UEFI boot options, USB permissions, TPM fan configs, secure boot, boot passwds
> * security and encryption w/ TPM and HSM
```
    
- **Motherboard/system board/main board**
    - printed circuit board (PCB)
        - conductive series of pathways laminated to a nonconductive substrate that lines the bottom of the computer
        - often uniform in color
            - green, blue, black, red
    - most important component
        - Connects all other components together
    
## Motherboard form factors
    
- motherboards are classified by **form factors** (design)
    - **ATX**
        - Advanced technology eXtended motherboard
        - developed by Intel in mid 1990s
        - has processor and memory slots at right angles to expansion cards
            -  puts processor and memory in line with fan output of power supply
            - allows processor to run cooler
            - allows full-length expansion cards install
        - ATX and micro-ATX are primary PC motherboard form factors in use today
        - 12”*9.6” or 305mm*244mm
![](assets/17192310295527.jpg)
    - **ITX**
        - Information Technology eXtended motherboard
        - developed by VIA Technologies in early 2000s
        - low power, small form factor (SFF) for specialty use
            - home theater systems, compact desktops, gaming systems, embedded components
        - ITX is not a form factor, it’s a family of form factors
            - Mini-ITX
                - 4 mounting holes, 3 of them line up with ATX and micro-ATX ff
                - rear interfaces are placed in same location as on ATX
                - compatible with ATX cases
                - 6.7′′ × 6.7′′ (170 mm × 170 mm)
            - Nano-ITX
                - 4.7′′ × 4.7′′ (120 mm × 120 mm)
            - Pico-ITX
                - 3.9′′ × 2.8′′ (100 mm × 72 mm)
            - Mobile-ITX
                - 2.4′′ × 2.4′′ (60 mm × 60 mm)
    ![](assets/17192317075115.jpg)
## System board components
### Bus architecture

- data is sent from one component to another via bus
- bus is a collection of signal pathways
- ineptly days PCs used **serial busses**
    - sent one bit at a time
    - very slow
- **parallel busses** came after
    - 8 bits at a time per synchronous separate lines
    - big speed increase
    - loss of circuit length
        - how long circuit could be
    - throughput
        - how much data can be moved at a time
    - signal could only travel short distance
    - the amount of data was limited cause of synchronization needed between separate lines
- **serial busses** are back in play now
    - engineers figured out how to make the transmission faster than with parallel busses
    - the limitation of serial circuits is in the capabilities of the transceivers
    - specification examples:
        - **SATA**
            - Serial Advanced Technology Attachment
        - **USB**
            - Universal Serial Bus
        - **IEEE 1394/FireWire**
        - **PCIe**
            - Peripheral Component Interconnect Express
- several different busses on motherboard
    - expansion slots
    - communication between CPU, RAM, and other components
- busses’ throughput can be rated by the **bus speed**
    - higher bus speed = higher performance
    - sometimes busses must be synchronized
        - e.g. system bus and expansion bus
    - sometimes busses reference each other for speed
        - e.g. internal bus speed of CPU is derived from frontside bus clock

### Chipsets

- collection of chips/circuits that perform interface and peripheral functions for the processor
    - circuitry that provides interface for memory, expansion cards, onboard peripherals
    - dictates how motherboard communicates with installed peripherals
- usually have name and model number given by manufacturer
    - manufacturer and model tell you the chipset’s features
        - supported CPU, RAM, type/brand of onboard video, etc.
- can be made of one or several integrated circuit chips
    - e.g. Intel typically use 2 chips

- can be decided into 2 functional groups:
    - **Northbridge**
        - high speed peripheral communication
            - primary communication with integrated video using e.g. PCIe
            - processor to memory communication
        - PC performance relies on Northbridge and its communication capabilities w/ peripherals it controls
        - NB is directly connected to SB
        - NB controls SB and helps manage communication between SB and the rest of the computer
        - **FSB**
            - front side bus
            - for communication between CPU and memory
            - e.g. set of signal pathways connecting CPU and memory
            - clock signal that drives FSB also used to drive communication for other devices
                - PCIe slots
                    - referred to as *local bus technologies*
                        - cause directly connected to the system bus (FSB in this case) and operate at the same speed as FSB
                            - allows faster data transfer and communication
        - **BSB**
            - back side bus
            - not always present
            - set of signal pathways between CPU and external cache memory
            - uses same cock signal as FSB
            - if no BSB, cache is placed on FSSB with the CPU and main memory
    - **Southbridge**
        - provides support to the slower onboard peripherals
            - USB, SATA, PATA, parallel ports, serial ports, etc.
        - manages their communication w/ the rest of the computer and resources given to them
        - these components don’t need to keep up w/ external clock of the CPU
        - aren’t a bottleneck
        - tl;dr if not CPU, memory, cache, PCIe slots -> SB in charge
        - most motherboards got integrated USB, network, analog/digital audio ports for SB to manage
        - SB also manages communication w/ slower expansion buses
            - PCI and legacy buses 
    - > AMD and Intel integrated both into most of their CPUs

![](assets/17193133309031.jpg)

![](assets/17193133953466.jpg)

### Expansion slots

- small plastic slots 1-6” long, 0.5” wide
    - video, network, sound, disk interface cards, etc.
- **PCI expansion slots**
    - peripheral component interconnect slot
    - considered old tech but many motherboards still got it
    - typically 3” long and white
    - operate at 33 MHz or 66 MHz (version 2.1) over 32-bit (4-byte) channel
    - data rates of 133 MBps or 266 MBps
        - 133 most common, excluding server architectures
    - PCI is shared-bus topology
        - if 33 MHz and 66 MHz adapters are mixed, all adapters are slowed to 33 MHz
    - older servers might have 64-bit PCI slots
        - double the 32-bit data rates
    - PCI slots are manufactured in **3.3V** and **5V** versions
        - voltage
![](assets/17193150225323.gif)
- **PCIe expansion slots**
![](assets/17193157263410.jpg)
    - most common slot architecture
    - designed to replace PCI and AGP
        - accelerated graphics port
            - graphics card only interface
    - faster than AGP w/ flexibility of PCI
    - no plug compatibility w/ AGP or PCI
    - some modern PCIe motherboards have regular PCI slots for backwards compatibility
        - AGP slots not included for many years
    - PCIe often referred to as bus architecture to compare it to other bus technologies
        - true expansion busses share total bandwidth among all slots
        - PCIe uses a switch component w/ point to point connection to slots
            - each component has full use of corresponding bandwidth
            - more of a star topology vs bus
    - serial technology
        - strips data packets across multiple serial paths
            - higher data rates
    - PCIe uses lanes
        - lanes are pairs of wires for data transmission between components
        - each link between devices consists of 1 or more lanes
        - link widths:
            - x1, x2, x4, x8, x12, x16, x32
                - increased the number of lane data can travel through
            - common are x1, x4, x16
                - x8 used but a bit less common
        - slots for different links vary in size, which corresponds to number of lanes
    - 4 major PCIe versions on the market
        - 1.x, 2.x, 3.0, 4.0
            - these version made the speed of data throughput faster
        - 5.0 also exist and is cross compatible with/ 4.0
            - performance will vary
![](assets/17193700348195.jpg)
    - you can use shorter cards in longer open ended slots
        - up-plugging
        - the other way around is also possible, but not all lower lane slots can accept higher lane cards, assuming it’s an open ended slot
![](assets/17193705607775.jpg)
![](assets/17193705608094.jpg)

> **Riser cards** type of expansion card that provides more expansion slots that other expansion cards can be plugged into. Motherboard needs to accept riser cards and the case should be built for it too
> 
![](assets/17193162337724.jpg)

> **real life example**: cause of high data rate, PCIe is great for gaming. Technologies like NVIDIA’s Scalable Link Interface (SLI) allows users to combine graphics adapters in spaced PCIe x16 slots w/ hardware bridge (provides non-chipset communication between adapters). This forms a single virtual graphics adapter. SLI=ready motherboards allow multiple PCIe graphics adapters to pool GPUs and memory to feed graphics output to a single monitor. Results in increased performance.

### Memory slots and cache

- **RAM**
![](assets/17193712360284.jpg)
    - slots designed for memory chips that comprise primary memory
        - used to store currently used data and CPU instructions
    - PCs nowadays mostly use memory chips arranged n a small circuit board 
        - e.g. **DIMM**
            - dual inline memory module
                - common are 168, 184, 240, 288-pin configurations
        - smaller form factors
            - **SODIMM**
                - small outline DIMM
            - **MicroDIMM**
        - slot nowadays are often color coded
    - sometimes primary memory installed is not enough to service launched apps > out of memory error > apps fail to launch
        - solution 1
            - hard drive can be used as additional RAM
            - this space of hard drive is **swap file** or **paging file**
                - PAGEFILE.SYS in Microsoft OS
                - c:\pagefile.sys
                - optimized space that can deliver info to RAM if requested by memory controller
                    - **memory controller** is a chip that manages access to RAM and adapters w/ memory addresses reserved for communication w/ CPU
                - faster than if it came from general storage pool of the drive
            - the technology is known as **virtual memory/RAM**
            - **virtual memory** allows the system to use hard drive space as additional RAM
            - **paging** virtual memory memory system divides memory into small bocks - **pages** used by RAM and hard drive
            - **paging in/out** when more RAM needed than physically available, hard drive is used to temporarily store access data
                - **paging in** when data in virtual memory memory is needed the system loads/pages in data into RAM
                    - copying from hard drive to RAM
                - **paging out** to make room for new data system identifies the least recently used data/oldest content in RAM and moves it to hard drive/pages out
            - relying on virtual memory slows down the system    
        - solution 2
            - add physical memory to system is cheaper and more effective

- **cache**
    - small, very fast
    - sits between CPU and RAM
    - improves system performance
        - predicts what CPU will need nexts and pre-fetches it
            - this allows cache to be smaller than RAM
    - only contains the most recent data or data that’s expected to be used
    - **L1 cache**
        - smallest and fastest
        - located literally on CPU/on-die
        > **L2 and L3 cache** used to be on motherboard but nowadays are on-die
    - **L2 cache**
        - large and a little slower than L1
        > in multicore processors each processor generally has it’s own L1 and L2
        > some processors share L2 among cores
    - **L3 cache**
        - larger and slower than L1 and L2
        - usually shares among processors

        
- increasing order of capacity and distance from CPU
- normally comes with/ decrease in speed too
    - L1
        - 80kb
            - 32kb for instructions
            - 48kb for data
    - L2
        - 512kb
    - L3
        - 8-16mb
    - RAM
        - 16-256gb
    - HDD/SSD
        - 100s of gbs to several tbs

> you can use programs like CPU-Z to check
> 
![](assets/17193737093028.jpg)
### Central processing units and processor sockets

- sockets have fan, heat sink, or both attached to it
    - otherwise will fry itself in a matter of minutes
    - 2 heat sinks, one with fan
![](assets/17194843666757.jpg)
- CPU sockets vary depending on the CPU they hold
![](assets/17194845940186.jpg)
- AM4 socket
    - for AMD processors
        - e.g. Ryzen
    - has **pin grid array (PGA)**
        - holes to receive pins on CPU
    - for PGA-based CPUs **zero insertion force (ZIF)** sockets are popular
        - uses lever on one of the edges to lock/release the mechanism securing the CPU
- LGA 1200 socket
    - has **land grid array (LGA)**
        - spring loaded pins on the socket
        - grid of lands on CPU
        - new technology that places pins on cheaper motherboard, rather than on expensive CPU
            - these pins are a bit more sturdy too
            - device with pins has to be replaced if damaged off
    - LGA-based sockets have a lid that closes over the CPU and is locked in place
- don’t need to apply that much strength to install the CPU anymore
- excessive pressure can damage the CPU or the motherboard

- sockets are made for either Intel or AMD, never both
    - > legacy sockets like Socket5 and Socket7 support both but they’re like 25 yo now
- motherboards and CPUs must be compatible, even within the same Intel/AMD family
- servers and laptops got different sockets altogether
    - some CPU sockets support CPUs designed for desktops/servers

### Multisocket and server motherboards

![](assets/17194864952978.jpg)
- for motherboard compatibility keep in mind
    - CPU type
    - case type
- figure 1.12 got a multisocket motherboard w/ 2 sockets
    - each socket got 8 dedicated memory slots
    - 2 or 4 socket motherboard are common for servers
        - they can make do with a normal single CPU motherboard ofc
    - many server motherboards are ATX-sized
        - many server manufacturers create custom boards tho
- multisocket and server MBs generally use the same sockets as other MBs

### Mobile motherboards

- some manufacturers use standard small-factor MBs
- most manufacturers create custom MBs
![](assets/17194869068241.jpg)
- most laptops got CPUs soldered on MBs
    - no need to worry abt socket compatibility
    - if CPU dies > replace MB
### Power connectors

- MB also got a connector that allows MB to be connected to the power supply
![](assets/17194873822262.jpg)

### Onboard non-volatile storage connectors

- hard drives
    - store data even when powered off, hence non-volatile
    - different types exist, ofc
- hard drives need to be connected to MB
    - **integrated drive electronics (IDE)/parallel ATA**
        - IDE used to be the most common type of hard drive
        - IDE was more than hard drive interface tho
        - was popular for other drive types
            - e.g. optical drives, tape drives
        - today it’s called IDE PATA and considered legacy tech
        - industry favors SATA
![](assets/17194902379520.jpg)
    - **Serial ATA (SATA)**
        - enhancement to ATA/IDE/PATA
            - all refer to same thing
        - transmitting data in order in a single file path is superior to transmitting bits of data in parallel and trying to sync the transmission
        - if you build faster transceivers, serial transmissions is simpler and faster
        - first version was **SATA 1.5** Gbps
            - also known as STA I/SATA 150
            - used 8b/10b encoding scheme
                - every 8 bits of data are converted into 10-bit code
                - helps w/ data integrity
                - 2 non-data overhead bits meant that the rated bandwidth was loosing 20%
        - **SATA 3** Gbps/SATA II/ SATA 300 and **SATA 6** GBPs/SATA III/SATA 600 had similar math behind it
            - each subsequent version doubled the throughput
        - **eSATA**
            - external SATA
            - many MBs have eSATA connectors built in
                - if not you can use an expansion card w/ eSATA ports and plugs into SATA connector
            - SATA is compatible w/ eSATA
            - unlike USB, SATA/eSATA don’t provide power
                - separate power connection is required in addition to data cable
![](assets/17194911862043.jpg)


- **M.2 connector**
    - most recent
    - primary used for hard drives
        - wifi, Bluetooth, gps, NFC adapters are built for M.2 as well
    - M.2 form factor is not a bus standard
    - supports SATA/USB/PCIe busses
        - if you hook SATA to M.2 slot w/ connector, the device speed will be regulated by SATA standards
![](assets/17194915329330.jpg)
### Motherboard headers

- buttons and LEDs plug into the MB through **headers**
    - series of pins
- this includes power buttons, power light, reset button, drive activity light, audio jack, USB ports
- headers for different connections are spread out on MB
    - certain types of headers are grouped together tho
- header purpose is printed on MB
![](assets/17194921535248.jpg)
- figure 1.19 left to right
    - USB, system fan, hard drive, reset button, chassis instructions detector, power light

- **power button and light**
    - soft power feature
        - power button controls power state flexibly, rather than being an on/off switch
        - depending on how long the button is pressed, multiple effects available
        - the effects can be changed through BIOS or OS
        - the LEED light usually signifies the job is done

- **reset button**
    - reboots PC from a cold startup point
        - as if it was turned on from a completely off state but w/o physically cutting off and restoring power to their components
    - keeping PC powered may prolong the life of the electronics affected by power cycling
    - it also can get around software lockups cause connection to MB restarts the system from hardware level
    - certain circuits might need time to drain the charge for the reboot to be successful tho, which is a down side
        - effect.g. Memory chips

- **drive activity light**
    - back in the day HDD had its own LED indicator controlled by said HDD
    - later, MBs had drive headers
        - LED no longer controlled by HDD
        - made it easy to add pins to control drive activity light 
    - nowadays MBs come with/ built-in header for connecting HDD activity light
    - on the up side, you got one light representing all drives
    - on the down side, you can’t tell which drive is active
        - minor concern cause you normally know which drive you’re accessing 
    - removable drives come w/ their own activity light

- **audio jacks**
    - early gen optical drives had a cable attached to the drive which was then connected to the sound card, the speakers would have been attached to the sound card
    - sound from apps running from CD-ROM could travel through the same path as general data
    - 3.5mm jack on the drive’s faceplate was an enhancement to that
    - audio that ran through the cable was rerouted to the front jack when smth was plugged in
    - many modern MBs have 10-position pin header for connecting standardized front-panel audio moduleS
        - some modules got legacy AC’97 analogue ports
        - others have HD audio connections
        - MBs that work for both got a BIOS setting that enables you to choose which header to activate
            - HD is usually the default
![](assets/17196464660099.jpg)

- **USB ports**
    - many devices got USB connectivity
    - for many years MBs had one or more 10-position headers for internal connectivity of the front panel USB ports
        - for many connectors only 9 positions stick out
        - 10th position acts as a key to discourage connecting the wrong device
![](assets/17196467713143.jpg)

### BIOS/UEFI/POST routine

- **firmware**
    - any software encoded in hardware
    - usually ROM chip
        - read-only memory
    - can be run w/o extra instructions from the OS
    - most PCs, large printers, devices w/o OS use firmware
    - expansion cards e.g. SCSI card, graphics adapter use firmware for setting up peripherals
    - 
#### BIOS
- basic input/output
- burned into a chip
- also known as ROM BIOS chip
- one of the most important on MB
- contains BIOS system software that boots the system
- allows OS to interact w/ certain hardware instead of a more complex device drier
- if brand name
    - chip often has manufacturer’s brand name on it and the word BIOS
- if clone
    - chip has sicker or printing from a major BIOS manufacturer
        - AMI, Phoenix, Award, Winbond, etc.
- on later MBs BIOS might be difficult to identify **or be integrated into Southbridge**
![](assets/17196471469974.jpg)
- > 1998 copyright actually refers to the oldest code present on the chip
- > the blue thing at the bottom left is CMOS jumper used to clear CMOS memory. E.g. when an unknown passwd is keeping you out of BIOS/UEFI config

#### UEFI
- unified extensible firmware interface
- one of the features is UEFI access to system resources to store additional modules
- those modules can be added at any time
- this results in support of many systems and platforms
- > **secure boot** won’t be possible w/o BIOS but UEFI makes this tech feasible
- at basic level BIOS/UEFI controls system boot options
- e.g. sequence of drives in which it looks for OS boot files
![](assets/17196480558911.jpg)
- other config options include disabling integrated ports/video card/USB ports
    - usb ports are often disabled on corporate computers
- most BIOS/UEFI offer diagnostic routines
    - e.g. to analyze quality of the components
    - those components are inspected during boot up too but you can do the diagnostic on a much deeper level
        - e.g. rotational speed of MB fans if the computer makes noises and overheats
            - if fans loose speed the cooling capacity ofc decreases
    - you can also access live readings of CPU temperature and ambient temp of the system unit
        - you can set temp at which BIOS/UEFI gives a warning tone or shuts down the system
    - you can monitor fan speed/bus speed/CPU voltage levels and other things
    - you can also achieve **overclocking**
        - setting system clock higher than the CPU is rated for
    - or **undervolting**
        - lowering CPU and RAM voltage to reduce heat and power consumption

#### BIOS/UEFI security and encryption

- BIOS/UEFI was always part of security
    - responsible for verifying the integrity of hardware and the boot process
- even back in the day it allowed you to set up 2 passwds
    - admin
        - required before entering BIOS/UEFI config
        - always a good idea to have one
    - user/boot
        - required to boot the OS
        - should not be set on public systems that need to boot on their own
            - in case of a power outage
- recently the role of BIOS/UEFI in security increased
    -  security measures are designed to hand over control to the OS once it’s ready to take over
    -  ensures a seamless transition of security responsibilities from the firmware to the OS
-  **TPM**
    -  trusted platform module
    -  security co-processor/cryptoprocessor
    -  BIOS can be configured to boot the system only after auth-ing he boot device
    -  confirms the hardware being booted to is tied to the system that contains BIOS and TPM
        -  process called **sealing**
            -  sealing device to the system prohibits the use of the device if they’re removed from the system
            -  can be combined w/ PIN passwd that unlocks them
            -  or w/ USB flash drive that must be inserted before boot
    - **Microsoft BitLocker** uses TPM to encrypt the entire drive
        - usually only user data is encrypted
        - BitLocker encrypts the OS files, Registry, hibernation file, etc
        - all that in addition to files/folders secured by file-level encryption
        - if anything changes w/in Win installation TPM doesn’t release the keys for decrypt and boot to secure volume
    - configure TPM in Win
        - start > settings > update & security > Windows security > device security
![](assets/17196518037153.jpg)
    - most MBs have TPM chip installed
        - if they don’t you can’t add one
        - you can enable the same functionality via **HMS**
            - hardware security module
            - security device that manages/creates/securely stores encryption keys
            - enables you to encrypt/decrypt data
            - HMS has several forms
                - simplest is USB or PCIe device that plugs into the system
                - there are also HMS-enabled servers that provide crypto services to entire network
- **Secure Boot**
    - at certain UEFI levels the firmware can check digital signatures for each boot file
        - confirms it’s the approved version that wasn’t modified
    - checked boot files include ROMs, boot loader, etc.
    - only after verifying signatures firmware loads and executes software
    - secure boot might be problematic tho
        - some OS might not be supported by the database of known good signatures stored in firmware
            - system manufacturer can supply an extension UEFI can use to support OS
            - this ain’t possible with traditional BIOS-based firmware
![](assets/17196522595992.jpg)
- some BIOS firmware can do intrusion detection
    - monitor the status of contact on MB
    - if enables, sensor on chassis is connected to contact on MB
    - cover remover is logged by BIOS
    - even if occurs when system is off
        - thanks to CMOS battery
    - at next boot BIOS will notify you of intrusion
        - happens only on first boot unless further intrusion detected

> **LoJack** for laptops by Absolute Software. UEFI-based security system. Similar in many ways to UEFI, e.g. drive encryption, but also has features like remotely tracking laptop, ability to lock/delete certain files.

#### POST

- power-on self test
- major BIOS/UEFI function
- series of system checks performed by BIOS/UEFI and other high-end components
    - **option ROM** 
        - SCSI BIOS and video BIOS
- verifies the integrity of BIOS/UEFI itself
- verifies and confirms the size of primary memory
- performs analysis and catalogs other forms of hardware
    - buses, boot devices
- BIOS/UEFI offers user a key sequence to enter config routine as POST begins
- once POST is complete BIOS/UEFI selects boot device highest in configured boot order and executes **MBR**
    - master boot record
    - or similar
- MBR then calls OS’s boot loader to continue booting
- each POST process ends w/ beep code or displayed code
    - indicates discovered issues
- each BIOS/UEFI publisher has own codes
![](assets/17196536858337.jpg)

 #### Flashing system BIOS/UEFI
 
 - flashing is BIOS/UEFI upgrade
 - can be necessary if hardware upgrade is not recognized even after installing proper drivers
 - only some hardware benefits from this
     - CPU, RAM, drives
     - this hardware usually doesn’t have drives you need to install
     - hence why BIOS/UEFI flashing is the way to go if they’re not recognized
- if you loose power during the upgrade you’re fucked
    - you need to replace BIOS/UEFI chip
        - if that’s not possible replace the motherboard
    - most modern systems have a fail-safe or two
        - e.g. portion of BIOS/UEFI that’s not flashed and has enough code to boot the system and access upgrade image
        - could be passive section where upgrade is installed and switched to only if upgrade is successful
        - somethings these are controlled on screen
        - other times there might be a mechanism like a jumper for BIOS/UEFI recovery
- if you need the upgrade, don’t consult BIOS/UEFI manufacturer
- go to MB or system manufacturer instead
    - they got personalized BIOS/UEFI code after licensing it from BIOS/UEFI manufacturers
    - they’ll give ya latest code and flashing utility for it

#### CMOS and CMOS battery

- computer has to keep certain settings even when powered off and unplugged
    - date, time
        - > back in the day u needed to go to BIOS/UEFI to change that
    - memory
    - hard/optical drive config
    - CPU settings
        - e.g. overlocking
    - integrated ports
        - settings
        - enabled/disabled
    - boot sequence
    - power management
    - virtualization suppor
    - security
        - passwds
        - LoJack
        - TPM settings 
- computers keep these settings in **CMOS memory chip**
    - complimentary metal oxide semiconductor
    - CMOS is actually a manufacturing technology for integrated circuits
        - first common chip manufactured this way was the memory chip for BIOS/UEFI, hence CMOS memory chip
- BIOS/UEFI starts w/ its own default info then reads info from CMOS
    - e.g. which hard drive types are configured for use
    - any overlapping info from CMOS overrides defaults
- CMOS memory usually not upgradable and might be integrated into BIOS/UEFI chip or South bridge
- to keep these settings integrated circuit-based memory must constantly have power
- CMOS chips got very low power requirements
    - even a small power source can prevent data loss
    - makes them vulnerable to ESD
        - electrostatic discharge
- to ensure CMOS always got power MB manufacturers include **CMOS battery**
    - comes in different shapes and sizes
    - mostly look like large watch batteries or small cylindrical ones
    - mostly long-life, non-rechargeable lithium
![](assets/17196557125016.jpg)
> in real life terms BIOS/UEFI and CMOS are used interchangeably

# Understanding processors

```
> **To know on the exam:**
> * understand difference between x64/x86/ARM
> * single vs multicore
> * multithreading
> * virt support
```

>TL;DR
>
>* **x86** architecture developed by Intel in 1970s
>* initially 16bit width but evolved into 32bit
>* used in laptops, desktops, servers
>* **x64** developed by AMD and later adopted by Intel
>* 64bit with
>* used in modern desktops, laptops, servers
>* can run 32 and 64 bit apps
>* **ARM** developed by ARM in 1980s
>* initially 32bit width now 64bit
>* used in mobile devices, embedded systems, IoTs, and personal computers (w/ Apple’s M1/M2 chips)
>* can’t run x86/x64 apps directly and vice versa
>* need emulation or translation

- CPU controls and directs all computer’s activity via internal and external busses
    - aka does math on large strings of binary numbers
- consists of an array of millions of transistors
- Intel and AMD are the biggest PC-compatible CPU manufacturers
    - compatible w/ every PC-based OS and app on the market
        - there are apps that don’t run on AMD chips but it’s rare
- MB and CPU need to be compatible
    - other components plug into MB and are CPU agnostic
- older CPUs are generally square w/ contacts arranged in PGA
    - pin grid array
- prior to 1981 chips were rectangular w/ 2 rows of 20 pins - DIP
    - dual in-line package
    - you can still see DIP form factors in the wild but they’re not used for PC CPUs
![](assets/17197344954434.jpg)

- most modern CPUs are LGA form factor
    - pins placed on MB, unlike PGA
    - grid of metallic pins called **lands** is on MB, hence the L in the name
![](assets/17194845940186.jpg)
- CPU almost always is close to RAM to improve system speed

## CPU architecture

- CPU does math on large scale, how it does it depends on architecture
- commonly used processors fall into 2 categories
- **CISC based**
    - complex instruction set computing
- **RISC based**
    - reduced instruction set computer
- CISC and RISC are ISA examples
    - instruction set architecture
- set of commands that CPU can execute
- both can perform the same tasks, just differently
- programmers develop code for one or the other tho

### x64/x86

- **CISC**
    - instruction set is more complex than RISC
    - can do multiple math task w/ one instruction
    - each instruction can take multiple clock circles
    - is original ISA for microprocessors
    - well known example is x64/x86 platform by Intel
    - AMD does CISC chips too
- there’s a set of lines between CPU and RAM????
- the most common bus is 64 bit wide
    - there are some 32 bit tho
    - back in the day could be 2/8/16 bit
- wider bus = more data can be processed at a time
- internal registers that are 32 bit wide on a 64 bit system can have 2 pipelines that receive info at the same time
- for 64 bit CPUs buses will always be 64 but wide or a multiple of 64
- x64 is designed to work w/ 64 bits of data at a time
    - OS must support that too
- x86 CPUs can handle 32 bits of info at once
- meaning x64 is newer than x86
- x86 and ARM they got closed ISA btw

### Advanced RISC machine

- one instruction per circle
- instruction have fixed space in memory
- doesn’t do any operations directly on memory
- > say you wanna add 1 to 7. You need to fetch 7 from memory, add 1 to it, then write it back to memory. In CISC that can be one instruction, in RISC it’s 3 separate instructions that can be executed one per circle.
- **ARM** CPU is the most known CPU w/ RISC architecture
    - acronym history is fuzzy
    - ARM also stands for Acorn RISC machine :D
- competing tech to Intel and AMD x64 CPU
- RISC can be made smaller than CISC CPUs and produce less heat
    - ideal for mobile devices 
    - most smartphones use RISC
        - e.g. Appel’s A15 and Samsung Exynos CPUs
- RISC use more memory than CISC
    - more code to complete tasks
- 64 bit are most current
    - ARM64
    - 32 bit can be spotted in the wild
        - just ARM

> there are also APUs, accelerated processing units. They combine CPU w/ graphics processing

## CPU cores

- old CPUs were single core
    - one instructions pathway through CPU
    - could process one set of tasks at a time
- then multiple cores w/in CPU were developed
    - each core operates as it’s own CPU
        - if apps and OS can support multicore
            - most do
- almost all desktops on the market are multicore

## CPU characteristics

### Speed

- clock frequency
- MHz in older CPUs
- GHz in newer
- MBs got **oscillators**
    - quartz crystal shaved to a specific geometry
    - **system clock (XTL)**
    - vibrates at specific frequency when electric current passes through 
        - piezoelectric effect
    - oscillation frequency is determined by physical properties e.g. shape and size
    - vibrating crystal has consistent and stable frequency called **clock signal**
    - clock signal is used to time operations w/in computer
        - **FSB speed**
            - front side bus speed
            - effective clock rate
            - computed differently for different types of RAM
            - CPU multiplies FSB speed and produces its own clock rate
- there can be discrepancy between FSB frequency and CPU frequency
    - cause CPU can split clock signal from oscillator that drives FSB into multiple regular signals
    - also, you can adjust CPU clock rate in BIOS
    - or you can tweak speed by overclocking
        - running CPU at higher speed than manufacturer rating
        - this requires more voltage and heat
            - can shorten CPU life
            - usually voids warranty
                - some CPUs are sold w/ ability to overclock them
                - CompTIA says don’t do it unless manufacturer says it’s ok
 
### Multithreading and hyper-threading

- **thread**
    - string of instructions that CPU is running
- old CPUs could only run one thread at a time
- new CPUs run multiple threads at once
    - **multithreading**
- **Hyper threading technology (HTT)**
    - Intel
    - form of **SMT**
        - simultaneous multithreading
        - takes advantage of CPU’s superscalar architecture
        - superscalar CPUs can have multiple instructions operating on separate data at the same time
    - HTT CPUs appear as 2 CPUs to the OS
        - OS can schedule 2 processes at a time
        - as seen in Win10 task manager
        - virt CPUs are listed as **logical**
![](assets/17197364676872.jpg)
    -  just like with **Symmetric multiprocessing (SMP)**
        - 2 or more CPUs use system’s resources
    - OS must support SMP to use HTT
    - on Win, to look up what CPU you got:
        - control panel > system 
![](assets/17197366468032.jpg)
        - more details if you run System Information
            - click start and type msinfo32.exe > click system info when it appears as best match
        - there are 3d party apps like CPU-Z too
        - POST screen also shows it

### Virtualization support

- many CPUs support virt in hardware
- this eases burden on the system that software virtualization imposes
- **AMD-V**
    - AMD’s virt
- **VT**
    - Virtualization Technology
    - Intel’s virt
- most but not all CPUs support virt
- virt must be supported by OS and BIOS/UEFI too for it to work 
- you might need to enable it in BIOS/UEFI

# Understanding memory

```
> **To know on the exam:**
> * difference between SODIMM, DIMM, DDR3, DDR4, DDR5, ECC RAM, single, dual, triple, quad-Chanel RAM
> * understand what virt RAM is
```

- adding memory is most popular, easy, inexpensive way to upgrade your computer
- usually the biggest performance increase
    - MBs and OSs have memory limits tho

![](assets/17198248021309.jpg)
## Parity checking and memory banks

> TL;DR
> Sometimes due to noise the transmitted data is not the same as received data. To detect these errors additional bits are sent together w/ data bits. The value of additional bits depends on the data bits. Many ways to detect the error, e.g. checksum, but the easiest way is to add parity bit w/ data.
> 
> 2 types of parity:
> * odd parity
>   * total # of 1s in code, including parity, is odd
>   * e.g. if 4 ones > parity is 1, if 5 ones > parity is 0
> * even parity
>   * total # of 1s in code is even
> 
> This way the error can be detected but you’ll still have no idea where the error is. If there’s more than one (even) amount of errors in code they can’[t be detected w/ parity.
> 
> 1 error is a bit error. More errors are burst error
> generally error detection is done by the receiver
> extra bits are called redundant bits

- parity checking is an error-checking scheme
- usually works on byte level
    - 8 bits of data + 1 bit parity added at transmission and removed at receiver’s end
    - if the receiver doesn’t agree w/ parity the error occurs
- 4 common parity types:
    - odd
    - even
    - mark
    - space
- even and odd are used in systems that compute parity
- mark and space are used in systems that don’t compute parity but expect to see a fixed bit value in parity location
    - mark is digital pulse or 1 bit
        - parity is always 1
    - space is lack of pulse or 0 bit
        - parity is always 0
    - mark and space parity offer even less error detection than even and odd parity cause only changes in parity bit can be detected

- even tho parity ain’t best error detection tool it can lock up the system w/ parity error
- if you get enough of these error you need to replace memory
- parity checking is an effective indicator of large scale memory and data transmission failure
- not so good at detecting random errors
- in early days almost all memory was parity-based
- nowadays parity checking in RAM ain’t common

- **non-parity memory**
    - systems that support/reserve location for parity

- **memory bank**
    >TL; DR
    > collection of memory modules grouped together to form a large storage capacity
    > typically used in parallel to improve performance and increase # of data processed at a time

    - most basic memory implementation
        - 8 chips form a set
        - each chip has billions of bits of info
        - for every byte in memory one bit is stored in each of 8 chips
        - 9th chip is added for parity
        - on or more of these sets form a memory bank

## Error checking and correction

> TL;DR
> 
> error correction can be done in 2 ways:
> * receiver can make the sender retransmit the data
> * receiver can use error correcting code that automatically corrects certain errors

- **Error correction code (ECC)**
- if memory supports ECC check bits are generated and stored w/ data
- can detect single and double bit errors
- can correct single nit errors

## Single and double sided memory

- single sided have chips on one side
- double sided has chips on both sides
- double sided memory is treated as 2 separate memory modules
- MB that supports double sided memory has memory controllers that switch between 2 sides
- can access 1 side at a time
- double sided memory allows more memory to be inserted w/ half the physical space
![](assets/17198315165300.webP)

## Single, dual, triple, quad-channel memory

- memory controllers that support dual-channel and up were developed to eliminate the bottle neck between CPU and RAM

- **multichannel memory implementation**
    > it’s implemented by MB, not memory
    - dual-channel memory
        - memory controller coordinates 2 memory banks to work as synchronized set when communicating w/ CPU
        - this doubles specified system bus width as far as memory is concerned
    - triple-channel memory
        - coordinates 3 memory modules at a time
    - quad-channel memory
        - four memory modules at a time

    - single, dual, and quad are common, triple isn’t

    - on most computers you need to install 2-4 memory modules to implement multicore
    - almost always multichannel implementation supports single channel 9installation tho
    - multichannel MBs often got different color slots
    - to use single channel populate slots of same color
    - skip neighboring slots
    - for dual channel fill neighboring slots
    
    - be careful when installing
    - worst case, computer won’t function w/ different modules of different speeds, capabilities, # of sides all bundled together in slots of the same channel
    - installing modules from different manufacturers can be problematic
        - or if the manufacturer is unsupported
    - that said, it’s not memory make-up that ensures multichannel support but the tech MB is based on
        - manufacturers still often sell multiple memory sticks as a bundle to give ya peace of mind
    
    - read manufacturer docs before installing memory
    - most require slower memory be installed in lower number slots
        - cause system adapts to first module it sees, looking at lower number slots first
    - other times it might be required you install higher capacity memory in lower number slots

    - sometimes when you buy memory of highest capacity it won’t work with MB out of the box 
        - may be cause it wasn’t around when the chip was created and a BIOS flash will fix it
        - other times it just won’t work at all
    
    - another common problem occurs when you install 4 modules and they aren’t recognized, even tho 2 or 3 worked just fine
        - may be smth like ur MB support 4 modules
        - you installed 3
        - and the 4th is double sided
        - this means you’re trying to force 5 modules when MB excepts 4

## Types of memory

- all synchronous types of DRAM are most in use
    - SDRAM
    - SDR SDRAM
    - DDR SDRAM
    - DDR2 SDRAM
    - DDR3
    - DDR4
    - DDR5

### DRAM

- dynamic random access memory
- cheaper type of memory used to expand computer memory
- DRAM chips are cheaper to manufacture cause less complex
- **dynamic** means it need constant update signal to keep info written to it
    - **refresh signal**
    - if the signal isn’t received every so often info will bleed out
- most popular is synchronous DRAM like DDR3 and DDR4
    - won’t see DDR2 as often
    - DDR5 is new and not as widely adopted yet

#### Asynchronous DRAM (ADRAM)

- legacy memory type
- independent from CPU external clock
- bit numeric codes on it related to memory **access time**
    - usually 1/10 of value
    - access time is the difference between when info is requested from memory till data is returned
        - often 40-120-nanoseconds
        - lower access time is off better

- not synchronized to front-side bus
    - you often had to add wait states through BIOS for faster CPU to be able to use same memory as slower CPU
    - CPU essentially did nothing waiting for memory to become ready for access

#### Synchronous DRAM (SDRAM)

- only type of RAM installed in mainstream computers
- shares a clock signal with system bus clock
    - provides signal to all local bus components
- ties SDRAM to FSB speed, hence CPU
    - no need to configure CPU to wait

##### SDR SDRAM

- single data SDRAM
- legacy RAM tech
- every time system clock ticks 1 bit of data is transmitted per data pin
- this limits bit rate per pin to corresponding value of clock frequency
- you can double throughput w/ dual channel memory







# Understanding cooling systems




















