# How people use computers

- [How people use computers](#how-people-use-computers)
  - [Computer features](#computer-features)
  - [General purpose vs dedicated computing devices](#general-purpose-vs-dedicated-computing-devices)
  - [Operating systems](#operating-systems)
  - [Mobile computing devices](#mobile-computing-devices)
  - [Networks](#networks)
  - [Remotely accessed computer systems](#remotely-accessed-computer-systems)
  - [Cloud computing](#cloud-computing)
  - [Virtualization](#virtualization)
  - [Specialized computer systems](#specialized-computer-systems)

## Computer features

- Internet of Things (IoT)
  - Specialized computer device that can communicate data over the internet, not including computers and phones.
    - Smart cars
    - Security cameras
    - Home appliances
    - Medical devices used for monitoring patients
    - Baby monitors
- Processor
  - Super fast electronic calculator that can execute computations based on the programming
- Programming
  - Instructions telling the computer what to do
    - Operating system (OS)
      - Enables the user to interact with the computer
    - Applications
      - Enable the computer to accomplish specific tasks
- Data Storage
  - Internal
  - External
- Data Assets
  - Values assigned to a computer by individuals or organizations
    - Data
      - Raw numbers (input)
    - Information
      - Computer processed raw data (output)
- Hardware Devices
  - Memory, RAM, CPU, etc.
- OS
- Apps
- Output/Interaction Options

---

## General purpose vs dedicated computing devices

- **Multi-user computers**
  - Mainframes
    - Large multitask machines capable of supporting thousands of user sessions at the same time. Each with its own programs and files
  - Minicomputers
    - Small multitask machines
    - Smaller version of mainframes
  - Supercomputers
    - Focused the power of a mainframe computer on a single task
    - Used for massive number crunching
      - Geothermal data, CGI movie effects, census tallying
- **Dedicated computers**
  : sometimes called microcomputers
  - Desktops
  - Laptops/portable

---

## Operating systems

- Runs the device
- Supports apps
- Defines how users can interact with the machine
- Hardware defines what OS you can run
  - Windows runs on IBM/Intel platform
  - Apple runs on Macintosh platform
- GUI vs CLI
- ~~Skipping Windows, Apple, Linux OSs cause self-explanatory~~
- ChromeOS by Google
  - Linux variant
  - Designed for thin clients
    - Minimal computers designed for internet only
      - Can't run certain apps, so you need to use web-based versions (e.g. Office)
    - Has very little storage, most storage is in the cloud

---

## Mobile computing devices

- Smartphones
  - iOS
    - iPhone and iPad
  - Android OS
  - BlackBerry OS (mostly dead)
    - Distinct feature was it's hardware keyboard
  - Windows Phones (so very dead)
    - Windows RT for tables for a thing for a while but is now discontinued
    - Tablets now use Windows 10 Mobile
- Tablets
  - Mostly you can't call or text from a tabled
    - Exception: phablets
  - iOS
  - Android
- Specialty devices
  - Created for specific task
    - E-readers, scientific calculators, GPS navigators

---

## Networks

- Local area network (**LAN**)
  - Two or more computers connected in a single location (e.g. school, office, home)
    - Wired LANs connect via network cables and **switches**
      - Certain types of switches - **routers** - allow computers to communicate with non local networks
        - Routers can send data via phone line, DSL connection, cable TV lines, network cables, etc.
    - Wireless LANs use radio waves
      - Computers on wireless network connect via a wireless access point (**WAP**)
- Wide area network (**WAN**)
  - Two or more LANs connected together

    ```[ascii]
            [WAN]                          [LAN]


              [PC]                           [PC]
              |                              |
    [PC]----[Switch]----[PC]       [PC]----[Switch]----[PC]
              |
            [Router]
              |
    [PC]----[Switch]----[PC]
              |
              [PC]
    ```

- Servers
  - Machines that fulfill specific roles on computer network
    - e.g. file, app, mail, print server
  - Clients
    : machine that receives services
- Recourse sharing
  - Allows you to share resources instead of having multiple
    - e.g. connect all computers to one printer

---

## Remotely accessed computer systems

- Client access servers
- Mobile apps
  - Most are server connected but can be standalone
- Streaming media
- Web apps

---

## Cloud computing

- Data hosted online
- Subscription software 
  - Often cheaper than buying a full version
  - Automated updates
  - Minimizes the need to download locally
- Many cloud-based services are collaborative
  - Enable multiple people to work on the same data and see each other's changes

---

## Virtualization

- Running a system inside of another system
  - Host OS
  - Guest OS
    - VMs
- Used A LOT in networking
- Can save companies money on hardware and maintenance
- Hypervisors
  : virtualization software
  - Type 1
    - Doesn't require OS
    - Shares recourses among virtual computers
    - Can be more efficient and stable than Type 2
  - Type 2
    - Requires an OS
    - You run it as an app
      - VMware, VirtualBox, QEMU, etc.
      - Can slow down your system cause there's a lot of other stuff running

---

## Specialized computer systems

- Do one specific task
  - Point-of-sale terminals (POS)
    - Contain input, memory, minimal processing power
  - ATMs
    - Uses multi-factor authentication
  - GPS
    - Any location on earth has access to at least 4 satellites at any given time
    - GPS receiver unit registers data from at least 3 satellites
    - It calculates how far it is from ech satellite by determining how long it took for the signal (traveling at the speed of light) to arrive
    - Based on that it calculates 2D position (longitude and latitude)
    - Accurate to within a few feet
  - Voice over IP (VoIP)
    - Teleconference
      - Simulates in-person meeting environment
      - Uses life-size participant displays
      - High-fidelity, spatial audio
      - Specific room setup and equipment required
      - Higher technology and setup costs
      - May have compatibility issues with different providers
    - Teleconferencing
      - Used for various meeting types
      - Shows participants in a standard video window
      - Compatible with computers and phones
      - User-friendly and easy to set up
      - More affordable
      - Better interoperability across platforms
  - Plain old telephone system (POTS)