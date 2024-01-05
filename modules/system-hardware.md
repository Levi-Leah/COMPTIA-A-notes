# System hardware

- [System hardware](#system-hardware)
  - [Hardware categories](#hardware-categories)
  - [Central processing unit (CPU)](#central-processing-unit-cpu)
    - [CPU speed](#cpu-speed)
      - [64-bit vs 32-bit CPU](#64-bit-vs-32-bit-cpu)
      - [Multicore CPUs](#multicore-cpus)
      - [Program handling](#program-handling)
      - [Cache](#cache)
  - [Cooling](#cooling)
  - [RAM](#ram)
  - [Motherboards](#motherboards)

## Hardware categories

- Input
  - Instructions the user sends to a computer, usually via keyboard or mouse
- Processing
  - Operation performed by a computer according to the input
- Output
  - Result of the operation delivered to the recipient (user or app)
- Storage

---

## Central processing unit (CPU)

- Handle most of the math processing in the computer and determines how fast the computer is
- **Intel** and **AMD** make most of the CPUs
  - Intel has the biggest market share
- **ARM Holdings** designs the vast majority of CPUs fpr mobile devises
  - Licenses it's designs to manufacturers
- Intel vs AMD vs ARM[^1]
  - Desktops can have any chip
  - Laptops mostly have Core Duo CPUs
  - Tablets mostly use Atom CPU (Intel)
  - Mobile computers use ARM
  - 32-bit servers use Opteron CPU (AMD)
  - 64-bit servers EM64T (Intel)
- CPU works with the motherboard to achieve proper speed
  - Motherboard runs at specific bus speed (clock speed)
  - CPUs run at some multiple of the bus speed
    - If motherboard runs at 100MHz and the CPU has 25x multiplier, the CPU runs at 2500MHz (2.5 GHz)
  - Make sure they don't cancel each other out

[^1]: Advanced risk machine

---

### CPU speed

- Speed is measured in cycles per second
- How many operations it can do in 1 second
  - 1 hertz = 1 cycle
  - 1 megahertz = 1 million cycles
  - 1 gigahertz = 1 billion cycles
- Modern CPUs are typically measured ib GHz
  - ~1.5-4 GHz
  - CPU clock speeds hit a wall at 4GHz
    - To increase processing power other improvements are needed
      - 64-bit systems
      - Multicore CPUs
      - Program handling
      - Cache

---

#### 64-bit vs 32-bit CPU

| Feature                   | 32-bit Computing                               | 64-bit Computing                                               |
|---------------------------|------------------------------------------------|----------------------------------------------------------------|
| Data Handling             | Handles data up to 32 bits in complexity       | Handles data up to 64 bits in complexity                       |
| Maximum Number Handling   | Can handle numbers up to ~4 billion            | Can handle numbers up to ~18.4 quintillion (8,446,744,073,709,551,615) |
| Application Compatibility | Can run 32-bit applications                    | Can run both 32-bit and 64-bit applications                    |
| Application Limitation    | -                                              | 64-bit applications may not utilize full potential on 32-bit systems |
| Addressable Memory        | Limited, less than 4 GB typically              | Significantly higher, theoretically up to 16 exabytes          |

---

#### Multicore CPUs

- Introduction of dual-core CPUs combined two CPUs into a single chip
- Increased processing capability and efficiency
- Evolved from single-core to 2, 4, 6, and 8-core architectures
- Multicore processors collectively improve performance
- vCPU
  : CPU assigned to a virtual system
  - The number of vCPUs impacts cloud-based virtual machine deployment and software licensing costs
    - Some SW licenses are based on the number of physical or virtual CPUs

---

#### Program handling

- CPUs operate based on a codebook or instruction set
- Programs are written in various languages and translated into the CPU's instruction set
- Different CPUs with the same clock speed may perform tasks at different efficiencies
- Processor efficiency and features can outweigh raw clock speed

---

#### Cache

- Applications are loaded into PC's memory for operation
- The CPU fetches data from RAM, subject to physical limitations of the motherboard's system bus
- CPUs use cache, a type of fast RAM embedded in the chip, to speed up performance
- CPUs have multiple levels of cache (L1, L2, L3) with varying speeds and sizes
  - L1 is smallest and fastest
  - Each subsequent level is larger and slower
- Multicore CPU designs may have shared or separate caches for each core, affecting cost and performance

---

## Cooling

- Faster CPUs require more electricity
- More electricity leads to greater heat, which can slow down the computer and damage components
- Overheating can cause component malfunction or reduce chip's lifespan
- Designs from portable computer processors have influenced modern CPU efficiency
  - Miniaturizing CPU components reduces electricity needs while maintaining performance
  - Refining CPU instruction processing increases efficiency
- Even low-powered CPUs can generate harmful heat

---

- **Passive cooling**
  - Does not use power or mechanical parts
  - Less effective for very hot components
  - **Heat Sinks**:
    - Made of heat-conductive metal like aluminum
    - Uses thermal paste to attach to the chip
    - Designed with spikes or baffles to increase surface area
    - Heat moves from chip to heat sink, then dissipates into air
    - Case fans assist in removing hot air from the case
- **Active cooling**
  - Involves electrically powered components and mechanical parts
  - **Fan cooling**
    - **CPU Cooling**:
      - Fan attached to CPU's heat sink
      - Aims to circulate air and reduce CPU heat
    - **Case Fans**:
      - Cools the entire interior of the computer
      - Additional fans may be placed strategically in the case
  - **Liquid cooling**
    - Efficient but risky due to liquid's electrical conductivity
    - **Components**:
      - Heat sinks (water blocks) attached to hot chips (CPU, GPU)
      - Sealed tubing for liquid flow
      - Pump circulates liquid, transferring heat to a reservoir
      - Reservoir may have a fan-cooled radiator

---

## RAM

- Random access memory
  - RAM is temporary memory vs hard drive is permanent memory
  - Every time you turn the computer off it flushes the memory
  - RAM vs ROM (Read-Only Memory)
    - ROM is nonvolatile and retains information when powered off
- System RAM refers to memory serving the computer as a whole
- RAM allows data to be read from any section, not sequentially
- The table keeps track of what's stored where

- Many different types of RAM
  - **Dynamic RAM (DRAM)**
    : Used for system RAM
    - Needs constant refreshing
    - Data is lost when power is off

- Types of RAM in a computer
  - **DIMMs**
    :Dual Inline Memory Modules
  - **SODIMMs**
    - Laptops use Small Outline DIMMs
  - DIMMs and SODIMMs have metal tabs called pins
    - Different types of RAM have different number of pins so they fit in particular slots
    - Different physically and in how they operate
- **RAM Capacity**
  - Motherboard determines the capacity of RAM it can handle
  - DIMM capacities range from 1 GB to 16 GB in typical desktops
  - RAM should not be mixed
    - e.g. don't mix up 8GB with 16GB

- **RAM Technologies and Speeds**
  - **Single Data Rate (SDR) RAM**:
    - Mostly obsolete
    - Synchronized with the motherboard
      - Performs one operation per system timer tick
        - Millions of ticks per second
    - 168 pins on a DIMM

  - **Double Data Rate (DDR) RAM**:
    - Sends or receives data twice per clock tick on the motherboard
    - Apart from capacity, RAM has sped rating:
      - DDR, DDR2, DDR3, DDR4
      - Each version is faster and more efficient than the last
      - DDR has 184 pins, DDR2 and DDR3 have 240 pins (different notches though), DDR4 has 288 pins
      - Generations are not interchangeable due to different pin arrangements and slots

  - DDR RAM and DDR SDRAM are synonymous.
    - "SDRAM" implies synchronous operation, and all DDR RAM is synchronous

- **Virtual Machines**
  - RAM amount can be specified in virtual machines.
  - CPU and RAM together are known as compute power.
  - Adjusting virtual machine compute power is called vertical scaling, scaling up, or scaling down.

---

## Motherboards

- Essential for the computing process
- Connects all computer components
- Provides pathways (buses) between memory slots, CPU socket, input/output ports, and built-in devices (network and sound adapters)
- Has an intelligent controller (the chipset) to manage traffic and bus speeds

---

- **Motherboard Form Factors**

  - Motherboards come in various sizes and shapes, known as form factors
  - Fit into different kinds of cases for mobile devices, desktops, or servers
  - Common form factors
    - ATX
      - Full-size motherboard for larger desktops
    - microATX
      - For smaller systems
    - Mini-ITX
      - For even smaller or specialty systems
  - Motherboards have different form factors for connectivity

- **Motherboard Features**

  - **CPUs Supported**:
    - Support a specific range of CPUs based on chip attributes (e.g., pin number)
      - e.g. compatible with either Intel or AMD, not interchangeable
  - **RAM Supported**:
    - Support specific types of RAM (e.g., DDR3, DDR4) with defined min and max capacity limits
  - **Built-in Components**:
    - May include on-board audio, video, and network support
    - Built-in components save the need for separate expansion cards
  - **Expansion Slots**:
    - Slots for adding expansion cards
    - Different technologies for slots
      - Most common is PCI Express (PCIe) technology
  - **Firmware**:
    - Set of programs stored on a chip (not CPU) to update the motherboard
      - Modern systems come with Unified extensible firmware interface (UEFI)
      - Older systems use Basic input output system (BIOS)
  - **Special Features**:
    - High-quality boards might include special storage controllers, extra security, and virtualization support
