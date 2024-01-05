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