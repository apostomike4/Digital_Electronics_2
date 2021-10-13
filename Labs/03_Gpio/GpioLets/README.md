# Lab 3: Mike Apostologiorgakis

Link to your `Digital-electronics-2` GitHub repository:

https://github.com/apostomike4/Digital_Electronics_2

### Data types in C

1. Complete table.

| **Data type** | **Number of bits** | **Range** | **Description** |
| :-: | :-: | :-: | :-- | 
| `uint8_t`  | 8 | 0, 1, ..., 255 | Unsigned 8-bit integer |
| `int8_t`   | 8 | -128, ..., 0, ..., 127 | Signed 8-bit interger |
| `uint16_t` | 16 | 0, ..., 65535 | Unsigned 16-bit interger |
| `int16_t`  | 16 | −32768, ..., 0, ..., 32767 | Signed 16-bit interger |
| `float`    | 32 | -3.4e+38, ..., 3.4e+38 | Single-precision floating-point |
| `void`     | 0 | 0 | Empty data type |


### GPIO library

1. In your words, describe the difference between the declaration and the definition of the function in C.
   * Function declaration is how we tell the compiler the name of the function, its parameters and its return.
   * Function definition is the association of the function body with its name and parameters.

2. Part of the C code listing with syntax highlighting, which toggles LEDs only if push button is pressed. Otherwise, the value of the LEDs does not change. Use function from your GPIO library. Let the push button is connected to port D:

```c
    #define LED PB5
    #define BUTTON PD1
    
    #BLINK_DELAY 20
    
    #ifndef F_CPU
    #define F_CPU 16000000
    #endif
    
    #include <util/delay.h>
    #include <avr/io.h>

    int main(void)
    {
    
    // DDRB = DDRB or 0010 0000
    DDRB = DDRB | (1<<LED);
    // Set pin LOW in Data Register (LED off)
    // PORTB = PORTB and 1101 1111
    PORTB = PORTB & ~(1<<LED);
    
    //DDRD = DDRD and 1111 1101
    DDRD = DDRD & ~ (1<<PD1);
    //PORTD= PORTD or 0000 0010
    PORTD = PORTD | (1<<PD1);

    // Infinite loop
    while (1)
    {
        
        if (PIND.1==0)
        {
        // Pause several milliseconds
        _delay_ms(BLINK_DELAY);
        PORTB = PORTB ^ (1<<LED);
        }

    }
    
    }
```


### Traffic light

1. Scheme of traffic light application with one red/yellow/green light for cars and one red/green light for pedestrians. Connect AVR device, LEDs, resistors, one push button (for pedestrians), and supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values!

   ![Screenshot_2](https://user-images.githubusercontent.com/91612253/137040811-0057a916-7415-4ea9-a771-6eebfe2fa4f3.png)
