# Hardware, Software, and Networking

## Basic computing and processing

* **Processor**
  - A chip installed in you computer's hardware. It processes instructions for you. It accepts your input and executes it.
  - **Multicore processors** can run multiple tasks at the same time. For example, if you have a 4 core processor, it can run four tasks or threads at the same time.
    > **Hyper-Threading**: Some processors can provide each physical core with multiple virtual cores, allowing for even more parallelism. In this case, a 4-core processor with hyper-threading might appear as having 8 logical cores.

* **Random access memory (RAM)**
  - The processor loads the app's code into RAM.
  - RAM is finite, there's only so much of it. It can quickly fill up.
  - When RAM becomes full, the info not used right now is moved out of RAM and into a **swap file**.
  - Swap file suppliments RAM and adds extra capacity when needed.
  - RAM is fast, swap files are slow.
  - When the old info is needed again, it's not run directly from the swap file, it's moved back into RAM.
  - RAM is volatile memory. Anything you're working on will be closed if you power down your machine.
  - To combat that, you need to save things to persistent, non-volatile storage, e.g. local hard drive, USB flash drive, or online.

* **Operating System**
  - Controls input interfaces like keyboard, display devices, etc.
  - Coordinates instructions that need to be sent to the processor.
  - Coordinates reading and writing to RAM and swap files.

# Units of measurement and notational systems

## Decimals, binary, hexadecimal

* **Decimal**
 - Numbers 0-9.

* **Binary**
  - Computers process bits.
  - We use binary to represent bits.
  - Using binary, a bit can be 1 or 0.
  - We can build computer programs using 1s and 0s.
  - Each combination of binary 1s and 0s can represent a decimal number.
  - With 8 binary digits we can write any decimal number from 0 to 255.

    **Binary Table**
    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
    |-----|----|----|----|---|---|---|---|
    |  1  |  1 |  1 |  1 | 1 | 1 | 1 | 1 |
  - Conversion:
    - 96 decimal to binary
      - 64+32 is 96
      - 0110 0000 binary
    - 12 decimal to binary
      - 8+4 is 12
      - 0000 1100 binary
    

* **Hexadecimal**
  - Bits ain't human readable.
  - Apps needs to send rows of millions of binary digits to be processed.
  -  HEX uses numbers 0-9 and letters A-F.
  - Each HEX number is 4 bits long.
  - Conversion:
    - 0101 111 binary to hex
    - Split into two 8-digit parts
        - 0000 0101
        - 0000 1111
    - Look up what they mean in decimal
      - 0000 0101 is 5
      - 0000 1111 is F
    - In hex, 0101 1111 is 5F

        | Decimal | Binary             | Octal | Hexadecimal |
        | ------- | ------------------ | ----- | ----------- |
        | 0       | 0000 0000          | 0     | 0           |
        | 1       | 0000 0001          | 1     | 1           |
        | 2       | 0000 0010          | 2     | 2           |
        | 3       | 0000 0011          | 3     | 3           |
        | 4       | 0000 0100          | 4     | 4           |
        | 5       | 0000 0101          | 5     | 5           |
        | 6       | 0000 0110          | 6     | 6           |
        | 7       | 0000 0111          | 7     | 7           |
        | 8       | 0000 1000          | 10    | 8           |
        | 9       | 0000 1001          | 11    | 9           |
        | 10      | 0000 1010          | 12    | A           |
        | 11      | 0000 1011          | 13    | B           |
        | 12      | 0000 1100          | 14    | C           |
        | 13      | 0000 1101          | 15    | D           |
        | 14      | 0000 1110          | 16    | E           |
        | 15      | 0000 1111          | 17    | F           |

## ASCII and Unicode

* **American Standard Code for Information Interchange (ASCII)**
  - Uses numbers to represent letters and other symbols.
  - Example of a character encoding standard.
  - Was the most common till early 2000s
  - Flow:
    - You type a letter A
    - In ASCII that's HEX 41
    - HEX is converted to binary
    - Binary is processed by the computer
  - Each pair of HEX numbers represents a letter or character.
  - Upper and lower case characters are represented differently.
  - Limitation: can only encode 128 characters.
    - Great for English but not other langs.

* **Unicode**
  - Developed in late 1980s to support all characters.
  - Supports over 144k characters.
  - Supports most languages.

## Units of storage, throughout, processing

* **Units of storage**
  - **Bits**
    - Binary digit
    - The smallest unit of information
    - Bit is either 1 or 0
    - Anything can be broken down into bits
    - 8 bits is 1 **byte**
    - 1024 bytes is 1 **kilobyte**
    - 1024 kilobytes is 1 **megabyte**
    - 1024 megabytes is one **gigabyte**

* **Units of throughout**

* **Units of processing**


# Data types