# Device ports and peripherals

- [Device ports and peripherals](#device-ports-and-peripherals)
  - [Expansion Cards](#expansion-cards)
  - [Expansion Slot Types](#expansion-slot-types)
  - [Common Ports and Connectors](#common-ports-and-connectors)
    - [USB (Universal Serial Bus)](#usb-universal-serial-bus)
      - [USB Generations and Speeds](#usb-generations-and-speeds)
      - [USB Connector Types](#usb-connector-types)
    - [Other Peripheral Ports and Connectors](#other-peripheral-ports-and-connectors)

## Expansion Cards

- Expansion cards add specific capabilities to a computer system
- They fit into expansion slots on the motherboard
- Expansion cards have a row of metal pins for slot connection
- An edge with a metal backplate fits into an opening in the PC case for port access

- **Video Card (Display Adapter)**
  - Provides ports to connect to an external display
  - Serves as a graphics processor interface
  - Important for high-performance graphics tasks

    <img src="images/video-card.jpg" width="500"/>

- **Audio (Sound) Card**:
  - Provides ports for audio input and output devices
    - Speakers, headphones, and microphones
  - Most sound ports are round 3.5-mm connectors

    <img src="images/audio-card.webp" width="500"/>

- **Network Interface Card (NIC)**:
  - Enables connection to a local area network (LAN)
  - Wired
    - Plugs into an RJ-45 port
  - Wireless
    - Has small antenna and uses 802.11 standard
  - Each NIC has a unique 48-bit hexadecimal Media Access Control (MAC) address
  - > Network adapters, whether built into the motherboard or as expansion cards, are often referred to as NICs. The term NIC refers to the functionality rather than the physical card.

    <img src="images/Network-Interface-Card-NIC.png" width="500"/>

- **Modem Card**:
  - Used for dial-up Internet access via telephone landlines
  - Has two RJ-11 (telephone) ports side by side
  - The term modem is also now used to refer to:
    - High-speed cable
    - DSL Internet connectivity

    <img src="images/RJ-11-PCI-Modem-Card.jpeg" width="500"/>

## Expansion Slot Types

- Motherboards feature different types of expansion slots to accommodate various expansion cards
- PCI Express 3.0 currently the dominant standard in the market
- The term applies to both the slot and the bus that carries data from the slot to the system bus
- Each slot has between 1 and 32 independent lanes that carry data
- Slots have a numeric designation (such as ×1, ×4, ×8, or ×16) to describe how many lanes it has
  - Lower-capacity slots (e.g., ×1):
    - Suitable for expansion cards that don't require high data throughput
    - e.g. network cards
    - Motherboards typically have several ×1 slots

  - Higher-capacity slots (e.g., ×16):
    - Designed for data-intensive expansion cards
    - e.g. video adapters
    - Motherboards typically have one or two ×16 slots
    - Some motherboards may include a PCIe ×16 slot operating at ×8 speed

- **PCI**
  - Peripheral component interconnect
  - Older general purpose slot

- **PCIe**
  - Faster slot for more up to date technology
  - Slots have numeric designations (e.g., ×1, ×4, ×8, ×16)
    - Differ in size and capacity
    - Indicate the number of data lanes
      - Indicate how much information is going through

- **Mini-PCIe**
  - Found in laptops for smaller versions of standard expansion cards
  - Replaced the older mini-PCI slots in newer laptop models

    <img src="images/pcie-slots.webp" width="500"/>

## Common Ports and Connectors

### USB (Universal Serial Bus)

- Industry-standard connector for a wide variety of peripherals
- Carries both data and power
- Used to connect and charge small electronics

#### USB Generations and Speeds

- Interchangeable and backwards compatible

- **USB 2.0**:
  - Regular USB
    - Up to 1.5 Mbps (low speed) or 12 Mbps (full speed)
    - Typically white ports
  - Hi-Speed USB
    - Up to 480 Mbps
    - Sometimes colorcodded black to differentiate from regular USB

- **USB 3.x**:
  - USB 3.0 (SuperSpeed USB)
    - Up to 5 Gbps
    - Usually blue ports
  - USB 3.1 (Gen 1, formerly USB 3.0)
    - Up to 5 Gbps, same speed as USB 3.0
  - USB 3.1 (Gen 2, SuperSpeed)
    - Up to 10 Gbps
  - USB 3.2
    - ApproximUp to 20 Gbps

  <img src="images/USB_ports_by_color.webp" width="500"/>

#### USB Connector Types

- **Type-A**
  - Standard rectangular USB ports on most PCs and USB cables
- **Type-B**
  - Near-square connector
  - Used for large-sized peripherals like printers
- **Mini-B**
  - Smaller connector for devices like smartphones and cameras
  - Less durable and less common now
- **Micro-B**
  - Compact connector for smaller devices
  - Can have 2-part plug or 1-part plug
- **Type-C**
  - Compact, reversible connector
  - Compatible with larger and smaller devices
- **Lightning**
  - Apple's proprietary charging device

    <img src="images/usb-types.webp" width="500"/>

### Other Peripheral Ports and Connectors

>Relative speeds:
>
>Thunderbolt > USB > FireWire > eSATA

<img src="images/connectors.png" width="500"/>

- **Thunderbolt**
  - Primarily used on MACs to connect monitors
  - Supports a variety of peripherals and daisy-chaining up to six devices
  - **Thunderbolt 1**
    - 10 Gbps, uses Mini DisplayPort connector
  - **Thunderbolt 2**
    - 20 Gbps, also uses Mini DisplayPort connector
  - **Thunderbolt 3**
    - 40 Gbps, uses USB 3.1 Type-C connector

- **FireWire (IEEE 1394)**
  - Becoming obsolete
  - Commonly used with digital cameras, media devices, and external hard drives
  - **FireWire 400**
    - 400 Mbps
  - **FireWire 800**
    - 800 Mbps

- **eSATA**
  - Becoming obsolete
  - For external SATA storage devices like external hard drives
  - Not interchangeable with USB or plain SATA
  - Speeds: 1.5, 3, or 6 Gbps

- **RJ-45**
  - Ethernet networking connector
  - Visible metal pins inside
  - Transparent rectangular plastic connector
  - Has a release tab on top

- **RJ-11**
  - Used for traditional modems and landline telephones
  - Smaller version of RJ-45 connector
  - Less common

- **3.5-mm Audio**
  - Commonly used for microphones, headphones, and speakers
  - Similar to a small headphone jack
  - Often color-coded

- **PS/2**
  - Round plugs for older mice and keyboards with a bunch of pins inside
    - Green for mouse, purple for keyboard
  - Largely replaced by USB

- **Legacy Parallel**
  - Obsolete
    - Mostly replaced by USB
  - For old printers
  - 25-pin D-shaped connector

- **Legacy Serial**
  - Obsolete
  - For various old low-speed devices, e.g. monitors
  - 9-pin D-shaped connector
  - Mostly replaced by USB
