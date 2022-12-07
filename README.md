# Milestone2.1.1: stm32knightrider
Group Name: **Lucky Lizard** :lizard:

Group Member: 
1. **Andi Nur Asyikin Binti Andi Zainuddin**
2. **Lim Yong Chuan**
3. **Nur Fatini Binti Isa**

## Ojective
Interface simple devices GPIO ports
## Equipment
- [x] Board used: **NUCLEO-F411RE**
- [x] Software used: **STM32CubeIDE**
- [x] Breadboard
- [x] LEDs
- [x] Jumper

## Procedure
1. Knight rider lights are row of LEDs which sweep back and forth.
2. 8 LEDs are arranged on the breadboard in a single row.
3. They are connected to ports[11:4] A of the nucleo board.
4. The first bit of GPIOA pins are connected to the most right led.
5. The output data registers, GPIOA_ODR are used to write output data to output pin.
5. The source code is generated in C language: [stm32knightrider.c](https://github.com/LuckyLizard-MKEL1123/stm32knightrider/blob/main/stm32knightrider.c)
6. 2 for loop are used to simulate the motion LED being turn on sequentially in 2 direction.

   - The first for loop is to show the movement from right to left. 
   - The first bit set is the most right bit which is 4th bit.
   - Since there are a total of 8 bits, the program should loop 8 times with incremental number of bit being set.
   - A delay of 125 ms is set as invterval so that it will 1s for one LEDs motion from right to left.
   
| Loop, i | set bit i of GPIOA[11:4] | Output[11:4] |
|---------|--------------------|--------|
| 4 | 0000 0001 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: |
| 5 | 0000 0010 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: |
| 6 | 0000 0100 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: |
| 7 | 0000 1000 | :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: |
| 8 | 0001 0000 | :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 9 | 0010 0000 | :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 10 | 0100 0000 | :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 11 | 1000 0000 | :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |

   - The second for loop is to show the movement from left to right.
   - The most left bit is already on from the previous loop.
   - Thus, the next number of bit to be set is the 10th bit.
   - Compared to the first loop condition, the program should loop only 6 times at this stage.
   - A delay of 125 ms is set as invertal so that it will 1s for one LEDs motion from right to left.
   - One full cycle of knight rider light will be 2s.
   
| Loop, i | set bit i of GPIOA[11:4] | Output[11:4] |
|---------|--------------------|--------|
| 10 | 0100 0000 | :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 9 | 0010 0000 | :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 8 | 0001 0000 | :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: :white_circle: |
| 7 | 0000 1000 | :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: :white_circle: |
| 6 | 0000 0100 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: :white_circle: |
| 5 | 0000 0010 | :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :white_circle: :green_circle: :white_circle: |

## Results
Link for milestone 2.1.1 demo: [knight_rider](link)
## References
1. https://www.youtube.com/watch?v=KFSpxY_KM5A
