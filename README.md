# Milestone2.1: stm32knightrider
Group Name: **Lucky Lizard** :lizard:

Group Member: 
1. **Andi Nur Asyikin Binti Andi Zainuddin**
2. **Lim Yong Chuan**
3. **Nur Fatini Binti Isa**

## Ojective
STM32 toolchain checkout
## Equipment
- [x] Board used: **NUCLEO-F411RE**
- [x] Software used: **STM32CubeIDE**
- [x] Breadboard
- [x] LEDs
- [x] Jumper

## Procedure
1. Knight rider lights are row of LEDs which sweep back and forth.
2. 8 LEDs are arranged on the breadboard in a single row.
3. They are connected to ports A of the nucleo board.
4. The first bit of GPIOA pins are connected to the most right led.
5. The output data registers, GPIOA_ODR are used to write output data to output pin.
5. The source code is generated in C language: [stm32knightrider.c](https://github.com/LuckyLizard-MKEL1123/stm32knightrider/blob/main/stm32knightrider.c)
6. 2 for loop are useed to simulate the motion LED being turn on sequentially in 2 direction.

   - The first for loop is to show the movement from right to left. 
   - The first bit set is the most right bit which 1.
   - Since there are a total of 8 bits, the program should loop 8 times with incremental no of bit being set.
   - A delay of 125 ms is set as invertal so that it will 1s for one LEDs motion from right to left.
   
| Loop, i | set bit i of GPIOA | Output |
|---------|--------------------|--------|
| 1 | 0000 0001 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: |
| 2 | 0000 0010 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: |
| 3 | 0000 0100 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: |
| 4 | 0000 1000 | :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: |
| 5 | 0001 0000 | :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 6 | 0010 0000 | :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 7 | 0100 0000 | :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 8 | 1000 0000 | :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |

   - The second for loop is to show the movement from left to right.
   - The most left bit is already on from the previous loop.
   - Thus, the next no of bit to be turn on is the seventh bit.
   - Compared to the first loop condition, the program should loop only 7 times at this stage.
   - A delay of 125 ms is set as invertal so that it will 1s for one LEDs motion from right to left.
   - One full cycle of knight rider light will be 2s.
   
| Loop, i | set bit i of GPIOA | Output |
|---------|--------------------|--------|
| 7 | 0100 0000 | :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 6 | 0010 0000 | :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 5 | 0001 0000 | :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 4 | 0000 1000 | :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: |
| 3 | 0000 0100 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: |
| 2 | 0000 0010 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: |
| 1 | 0000 0001 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: |

## Results
Link for milestone 2.1 demo: [knight_rider](link)
## References
1. https://www.youtube.com/watch?v=KFSpxY_KM5A
