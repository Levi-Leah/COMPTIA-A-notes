# Device ports and peripherals

- [Device ports and peripherals](#device-ports-and-peripherals)
  - [Expansion Cards](#expansion-cards)
  - [Expansion Slot Types](#expansion-slot-types)
    - [Other Slot Types](#other-slot-types)

## Expansion Cards

- Expansion cards add specific capabilities to a computer system
- They fit into expansion slots on the motherboard
- Expansion cards have a row of metal pins for slot connection
- An edge with a metal backplate fits into an opening in the PC case for port access

- Types of Expansion Cards
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
  - Mostly used in laptops

<img src="images/pcie-slots.webp" width="500"/>

### Other Slot Types

- **Peripheral Component Interconnect (PCI)**:
  - An older general-purpose slot type still present on many motherboards.
  - Used for a variety of expansion cards.

- **Mini-PCIe Slots**:
  - Found in laptops for smaller versions of standard expansion cards.
  - Replaced the older mini-PCI slots in newer laptop models.