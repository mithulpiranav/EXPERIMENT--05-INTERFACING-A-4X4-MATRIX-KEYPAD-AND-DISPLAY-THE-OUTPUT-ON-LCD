# EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD

## Aim: 
To Interface a 4X4 matrix keypad and show the output on 16X2 LCD display to ARM controller , and simulate it in Proteus
## Components required: 
STM32 CUBE IDE, Proteus 8 simulator .
## Theory:

![image](https://github.com/vasanthkumarch/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/36288975/2a4a795e-1674-4329-ae07-3f5e8d5073e2)

4×4 Keypad Module Pin Diagram
 
4x4 Keypad module Pin Diagram
4×4 Keypad module Pin Diagram
Pin Number	Pin Name	Description
1	R1	Taken out from 1st  ROW
2	R2	Taken out from 2nd  ROW
3	R3	Taken out from 3rd  ROW
4	R4	Taken out from 4th  ROW
5	C1	Taken out from 1st  COLUMN
6	C2	Taken out from 2nd COLUMN
7	C3	Taken out from 3rd  COLUMN
8	C4	Taken out from 4th  COLUMN
4×4 Matrix Keypad Module Hardware Overview
These Keypad modules are made of thin, flexible membrane material. The 4 x4 keypad module consists of 16 keys, these Keys are organized in a matrix of rows and columns. All these switches are connected to each other with a conductive trace. Normally there is no connection between rows and columns. When we will press a key, then a row and a column make contact.

## Procedure : 
 ## LCD 16X2 
   16×2 LCD is named so because; it has 16 Columns and 2 Rows. There are a lot of combinations available like,
   8×1, 8×2, 10×2, 16×1, etc. But the most used one is the 16*2 LCD, hence we are using it here.

All the above mentioned LCD display will have 16 Pins and the programming approach is also the same and hence the choice is left to you. 
Below is the Pinout and Pin Description of 16x2 LCD Module:

![image](https://user-images.githubusercontent.com/36288975/233858086-7b1a88a2-f941-475c-86c2-b3bae68bdf7e.png)
![image](https://user-images.githubusercontent.com/36288975/233857710-541ac1c2-786c-4dfc-b7b5-e3a4868a9cb6.png)
![image](https://user-images.githubusercontent.com/36288975/233857733-05df5dbf-1a1e-479e-85bb-8014a39ad878.png)

4-bit and 8-bit Mode of LCD:

The LCD can work in two different modes, namely the 4-bit mode and the 8-bit mode. In 4 bit mode we send the data nibble by nibble, first upper nibble and then lower nibble. For those of you who don’t know what a nibble is: a nibble is a group of four bits, so the lower four bits (D0-D3) of a byte form the lower nibble while the upper four bits (D4-D7) of a byte form the higher nibble. This enables us to send 8 bit data.

Whereas in 8 bit mode we can send the 8-bit data directly in one stroke since we use all the 8 data lines.

 8-bit mode is faster and flawless than 4-bit mode. But the major drawback is that it needs 8 data lines connected to the microcontroller. This will make us run out of I/O pins on our MCU, so 4-bit mode is widely used. No control pins are used to set these modes. 
 LCD Commands:

There are some preset commands instructions in LCD, which we need to send to LCD through some microcontroller. Some important command instructions are given below:

Hex Code

Command to LCD Instruction Register

0F

LCD ON, cursor ON

01

Clear display screen

02

Return home

04

Decrement cursor (shift cursor to left)

06

Increment cursor (shift cursor to right)

05

Shift display right

07

Shift display left

0E

Display ON, cursor blinking

80

Force cursor to beginning of first line

C0

Force cursor to beginning of second line

38

2 lines and 5×7 matrix

83

Cursor line 1 position 3

3C

Activate second line

08

Display OFF, cursor OFF

C1

Jump to second line, position 1

OC

Display ON, cursor OFF

C1

Jump to second line, position 1

C2

Jump to second line, position 2
 
## Procedure:
 1. click on STM 32 CUBE IDE, the following screen will appear 
 ![image](https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png)

 2. click on FILE, click on new stm 32 project 
 ![image](https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png)
![image](https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png)
3. select the target to be programmed  as shown below and click on next 

![image](https://user-images.githubusercontent.com/36288975/226189280-ed5dcf1d-dd8d-43ae-815d-491085f4863b.png)

4.select the program name 
![image](https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png)


5. corresponding ioc file will be generated automatically 
![image](https://user-images.githubusercontent.com/36288975/226189378-3abbdee2-0df6-470f-a3cd-79c74e3d3ad8.png)

6.select the appropriate pins as gipo, in or out, USART or required options and configure 
![image](https://user-images.githubusercontent.com/36288975/226189403-f7179f1a-3eae-4637-826b-ab4ec35ba1e1.png)
![image](https://user-images.githubusercontent.com/36288975/226189425-2b2414ce-49b3-4b61-a260-c658cb2e4152.png)


7.click on cntrl+S , automaticall C program will be generated 
![image](https://user-images.githubusercontent.com/36288975/226189443-8b43451d-0b14-47e4-a20b-cc09c6ad8458.png)
![image](https://user-images.githubusercontent.com/36288975/226189450-85ffa969-2ffb-4788-81e5-72d60fdda0f1.png)
8. edit the program and as per required 
![image](https://user-images.githubusercontent.com/36288975/226189461-a573e62f-a109-4631-a250-a20925758fe0.png)

9. Add necessary library files of LCD 16x2 , write the program and use project and build  

![image](https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png)
10. once the project is bulild 
![image](https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png)

11. click on debug option 
![image](https://user-images.githubusercontent.com/36288975/226189625-37daa9a3-62e9-42b5-a5ce-2ac63345905b.png)


12.  Creating Proteus project and running the simulation
We are now at the last part of step by step guide on how to simulate STM32 project in Proteus.

13. Create a new Proteus project and place STM32F40xx i.e. the same MCU for which the project was created in STM32Cube IDE. 
14. After creation of the circuit as per requirement as shown below 

![image](https://user-images.githubusercontent.com/36288975/233856847-32bea88a-565f-4e01-9c7e-4f7ed546ddf6.png)

14. Double click on the the MCU part to open settings. Next to the Program File option, give full path to the Hex file generated using STM32Cube IDE. Then set the external crystal frequency to 8M (i.e. 8 MHz). Click OK to save the changes.
https://engineeringxpert.com/wp-content/uploads/2022/04/26.png

15. click on debug and simulate using simulation as shown below 

![image](https://user-images.githubusercontent.com/36288975/233856904-99eb708a-c907-4595-9025-c9dbd89b8879.png)

## CIRCUIT DIAGRAM 

<img width="1918" height="1142" alt="Screenshot 2026-07-24 110738" src="https://github.com/user-attachments/assets/9b35ea97-ce31-4931-a5ef-260111ef2534" />

## STM 32 CUBE PROGRAM :
```
#include <stdint.h>

// --- Register Memory Map Addresses for STM32F401 ---
#define RCC_BASE        0x40023800
#define GPIOA_BASE      0x40020000
#define GPIOB_BASE      0x40020400
#define GPIOC_BASE      0x40020800

// RCC Register
#define RCC_AHB1ENR     (*(volatile uint32_t *)(RCC_BASE + 0x30))

// GPIO Registers (GPIOA, GPIOB, GPIOC)
#define GPIOA_MODER     (*(volatile uint32_t *)(GPIOA_BASE + 0x00))
#define GPIOA_BSRR      (*(volatile uint32_t *)(GPIOA_BASE + 0x18))

#define GPIOB_MODER     (*(volatile uint32_t *)(GPIOB_BASE + 0x00))
#define GPIOB_BSRR      (*(volatile uint32_t *)(GPIOB_BASE + 0x18))

#define GPIOC_MODER     (*(volatile uint32_t *)(GPIOC_BASE + 0x00))
#define GPIOC_PUPDR     (*(volatile uint32_t *)(GPIOC_BASE + 0x0C))
#define GPIOC_IDR       (*(volatile uint32_t *)(GPIOC_BASE + 0x10))
#define GPIOC_BSRR      (*(volatile uint32_t *)(GPIOC_BASE + 0x18))

// Inline Assembly NOP
#define NOP()           __asm__ volatile ("nop")

// --- Microsecond Delay ---
void delay_us(uint32_t us) {
    uint32_t count = us * 16; // Approx delay loops for 16MHz default clock
    while(count--) {
        NOP();
    }
}

// --- Millisecond Delay ---
void delay_ms(uint32_t ms) {
    while(ms--) {
        delay_us(1000);
    }
}

// --- Configure GPIO Pins for LCD & Keypad ---
void GPIO_Init(void) {
    // 1. Enable Clock for GPIOA (Bit 0), GPIOB (Bit 1), and GPIOC (Bit 2)
    RCC_AHB1ENR |= (1 << 0) | (1 << 1) | (1 << 2);

    // 2. Set PA0, PA1, PA2, PA3 (LCD Data D7-D4) as Outputs (Mode 01)
    GPIOA_MODER &= ~((3 << 0) | (3 << 2) | (3 << 4) | (3 << 6));
    GPIOA_MODER |=  ((1 << 0) | (1 << 2) | (1 << 4) | (1 << 6));

    // 3. Set PB0 (RS), PB1 (E) as Outputs (Mode 01)
    GPIOB_MODER &= ~((3 << 0) | (3 << 2));
    GPIOB_MODER |=  ((1 << 0) | (1 << 2));

    // 4. Set PC0, PC1, PC2, PC3 (Keypad Rows A-D) as Outputs (Mode 01)
    GPIOC_MODER &= ~((3 << 0) | (3 << 2) | (3 << 4) | (3 << 6));
    GPIOC_MODER |=  ((1 << 0) | (1 << 2) | (1 << 4) | (1 << 6));

    // 5. Set PC4, PC5, PC6, PC7 (Keypad Cols 1-4) as Inputs (Mode 00)
    GPIOC_MODER &= ~((3 << 8) | (3 << 10) | (3 << 12) | (3 << 14));

    // 6. Configure Internal Pull-Up Resistors for PC4-PC7 (PUPDR Mode 01)
    GPIOC_PUPDR &= ~((3 << 8) | (3 << 10) | (3 << 12) | (3 << 14));
    GPIOC_PUPDR |=  ((1 << 8) | (1 << 10) | (1 << 12) | (1 << 14));

    // Set all Keypad Rows HIGH initially
    GPIOC_BSRR = (1 << 0) | (1 << 1) | (1 << 2) | (1 << 3);
}

// --- Send Nibble to LCD ---
void LCD_SendNibble(uint8_t nibble) {
    if (nibble & 0x01) GPIOA_BSRR = (1 << 3); // D4 -> PA3
    else               GPIOA_BSRR = (1 << 19);

    if (nibble & 0x02) GPIOA_BSRR = (1 << 2); // D5 -> PA2
    else               GPIOA_BSRR = (1 << 18);

    if (nibble & 0x04) GPIOA_BSRR = (1 << 1); // D6 -> PA1
    else               GPIOA_BSRR = (1 << 17);

    if (nibble & 0x08) GPIOA_BSRR = (1 << 0); // D7 -> PA0
    else               GPIOA_BSRR = (1 << 16);

    GPIOB_BSRR = (1 << 1);   // PB1 (E) HIGH
    delay_us(10);
    GPIOB_BSRR = (1 << 17);  // PB1 (E) LOW
    delay_us(100);
}

// --- Send Command or Data Byte ---
void LCD_SendByte(uint8_t value, uint8_t isData) {
    if (isData) GPIOB_BSRR = (1 << 0);  // PB0 (RS) HIGH
    else        GPIOB_BSRR = (1 << 16); // PB0 (RS) LOW

    LCD_SendNibble(value >> 4);
    LCD_SendNibble(value & 0x0F);

    delay_ms(2);
}

// --- Initialize LCD in 4-Bit Mode ---
void LCD_Init(void) {
    delay_ms(50);

    GPIOB_BSRR = (1 << 16); // RS = 0
    LCD_SendNibble(0x03);
    delay_ms(5);
    LCD_SendNibble(0x03);
    delay_ms(1);
    LCD_SendNibble(0x03);
    delay_ms(1);
    LCD_SendNibble(0x02);
    delay_ms(1);

    LCD_SendByte(0x28, 0); // 4-bit mode, 2 lines, 5x8 font
    LCD_SendByte(0x0C, 0); // Display ON, Cursor OFF
    LCD_SendByte(0x01, 0); // Clear Display
    delay_ms(2);
    LCD_SendByte(0x06, 0); // Entry mode set
}

// --- Send Text String ---
void LCD_SendString(char *str) {
    while (*str) {
        LCD_SendByte(*str++, 1);
    }
}

// --- Keypad Key Map matching the Proteus Calculator Layout ---
const char keypad_map[4][4] = {
    {'7', '8', '9', '/'},
    {'4', '5', '6', 'X'},
    {'1', '2', '3', '-'},
    {'C', '0', '=', '+'}
};

// --- Keypad Scan Function ---
char Keypad_GetKey(void) {
    for (int r = 0; r < 4; r++) {
        // 1. Set all rows (PC0-PC3) HIGH
        GPIOC_BSRR = (1 << 0) | (1 << 1) | (1 << 2) | (1 << 3);

        // 2. Drive the current row LOW
        GPIOC_BSRR = (1 << (r + 16));

        delay_us(10); // Short settling delay

        // 3. Read columns (PC4 to PC7)
        uint32_t cols = (GPIOC_IDR >> 4) & 0x0F;

        // 4. Check if any column is pulled LOW (active keypress)
        if ((cols & 0x01) == 0) { while (((GPIOC_IDR >> 4) & 0x0F) == cols); return keypad_map[r][0]; } // Col 1
        if ((cols & 0x02) == 0) { while (((GPIOC_IDR >> 4) & 0x0F) == cols); return keypad_map[r][1]; } // Col 2
        if ((cols & 0x04) == 0) { while (((GPIOC_IDR >> 4) & 0x0F) == cols); return keypad_map[r][2]; } // Col 3
        if ((cols & 0x08) == 0) { while (((GPIOC_IDR >> 4) & 0x0F) == cols); return keypad_map[r][3]; } // Col 4
    }
    return 0; // Return 0 if no key is pressed
}

int main(void) {
    GPIO_Init();
    LCD_Init();

    LCD_SendString("Key Pressed:");
    LCD_SendByte(0xC0, 0); // Move cursor to Line 2

    char key;
    while (1) {
        key = Keypad_GetKey();
        if (key != 0) {
            if (key == 'C') {
                LCD_SendByte(0x01, 0); // Clear Screen on 'ON/C' button press
                delay_ms(2);
                LCD_SendString("Key Pressed:");
                LCD_SendByte(0xC0, 0);
            } else {
                LCD_SendByte(key, 1); // Display pressed key character
            }
        }
    }
}
```

## Output screen shots of proteus  :
<img width="1918" height="1140" alt="Screenshot 2026-07-24 110724" src="https://github.com/user-attachments/assets/708e9a76-c8aa-404f-b14f-92ea2e342977" />
 
## Result :
Interfacing a 4x4 keypad with ARM microcontroller are simulated in proteus and the results are verified.
