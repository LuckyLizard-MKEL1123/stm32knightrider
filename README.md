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
- [x] Resistors

## Procedure
1. STM32CubeIDE is used as development platform throughout this course
2. For this milestone, letters **A, F, Y** is translated into morse code and transmitted through the blink of LED on the nucleo board.
3. The source code is generated in C language: [stm32morse.c](https://github.com/LuckyLizard-MKEL1123/stm32morse/blob/main/stm32morse.c)
   
  - Port A, Pin 5 represent the green LED on the nucleo board
  - An array is declared to determine the sequence of pin toggling
  
| Letter | Morse code | How it's coded ** *() represents delay in ms*|
| ----------- | ----------- | ----------- |
| A | • -| ON(300) OFF(300) ON(900) |
| F | • • - • | ON(300) OFF(300) ON(300) OFF(300) ON(900) OFF(300) ON(300) |
| Y | - • - -| ON(900) OFF(300) ON(300) OFF(300) ON(900) OFF(300) ON(900) |
  - For international Morse code, the length of a dot should be 1 unit which is coded as 300ms delay in this project
  - Meanwhile, a dash is 3 units where 3x300ms= 900ms.
  - The space between parts should be 1 unit and space between letters should be 3 units.
  - Lastly, space between words should be 7 units. So, a delay of 7x300ms=2100ms is introduced after the first cycle of letter A, F, and Y.
  
## Results
Link for milestone 2.1 demo: [knight_rider](link)
## References
