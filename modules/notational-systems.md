# Notational systems

- [Notational systems](#notational-systems)
  - [Decimal](#decimal)
  - [Binary](#binary)
  - [Hexadecimal](#hexadecimal)

## Decimal

- base 10
  - ... 10<sup>2</sup>, 10<sup>1</sup>, 10<sup>0</sup>,10<sup>-1</sup>, 10<sup>-2</sup> ...
  - Can go in both directions forever
  
      ```[ascii]
      326.47

        3     2     6  .  4     7
        ---   ---   ---   ---   ---  = (3*100)+(2*10)+(6*1)+(4*⅒)+(7*¹⁄₁₀₀)
        100s  10s    1s   ⅒   ¹⁄₁₀₀
      ```

- Numbers from 0 to 9
  
## Binary

- base 2
  - ... 2<sup>5</sup>, 2<sup>4</sup>, 2<sup>3</sup>,2<sup>2</sup>, 2<sup>1</sup>,  2<sup>0</sup>
- Numbers 0 and 1

    ```[ascii]
    11001 in binary to decimal

          0s are ignored
               / \
              /   \
      1   1   0   0   1
      --- --- --- --- --- = 16 + 8 + 1 = 25
      16s  8s  4s  2s  1s
    <-------doubling--------
    ```

    ```[ascii]
    45 decimal to binary

      --- --- --- --- --- ---
      32s 16s  8s  4s  2s  1s

    1. 45-32=13
    2. 13-8=5
    3. 5-4=1
    4. 1-1=0

    101101
    ```

Yana: another way to transform decimal to binary is division by 2

<img src="images/decimal-to-binary-conversion.png" width="500"/>

## Hexadecimal

- base 16
- Numbers 0 to 9; Letters A to F
  - A = 10
  - B = 11
  - C = 12
  - D = 13
  - E = 14
  - F = 15

    ```[ascii]
    7E2 hex to decimal

            14
            |
        7   E   2
        --- --- --- = 7*256+14*16+2*1 = 2018
        16² 16¹ 16⁰
        |    |   |
    256  16   1
    ```

    ```[ascii]
    3000 decimal to hex

        ---  --- --- ---
        16³  16² 16¹ 16⁰
        |    |    |   |
        4096 256  16   1

    1. 3000:256~11->B
    2. 3000-256*11=184
    3. 184:16~11->B
    4. 184-16*11=8

    BB8
    ```
