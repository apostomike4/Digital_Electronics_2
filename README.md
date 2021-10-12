# Digital_Electronics_2
# Lab 1: Mike Apostologiorgakis

https://github.com/apostomike4/Digital_Electronics_2


### Blink example

1. What is the meaning of the following binary operators in C?
   * `|` = OR 
   * `&` = AND
   * `^` = XOR
   * `~` = INVERT
   * `<<` = LEFT SHIFT
   * `>>` = RIGHT SHIFT

2. Complete truth table with operators: `|`, `&`, `^`, `~`

| **b** | **a** |**b or a** | **b and a** | **b xor a** | **not b** |
| :-: | :-: | :-: | :-: | :-: | :-: |
| 0 | 0 | 0 | 0 | 0 | 1 | 
| 0 | 1 | 1 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 | 0 |


### Morse code

    #define LED_GREEN   PB5
    #define DELAY 250
    #define SHORT_DELAY 1000
    #define LONG_DELAY 3000
    #ifndef F_CPU
    
    #define F_CPU 16000000
    #endif
    
    #include <util/delay.h>
    #include <avr/io.h>
    
    
int main(void)
{    
    
    // DDRB = DDRB or 0010 0000
    DDRB = DDRB | (1<<LED_GREEN);

    // Set pin LOW in Data Register (LED off)
    // PORTB = PORTB and 1101 1111
    PORTB = PORTB & ~(1<<LED_GREEN);

    // Infinite loop
    while (1)
    {
        // dot is represented with a short delay
        PORTB = PORTB ^ (1<<LED_GREEN);
        _delay_ms(SHORT_DELAY);
        
        // using a delay when the LED is off so we can actually see that the LED is off 
        PORTB = PORTB ^ (1<<LED_GREEN);
        _delay_ms(DELAY);
        
        // comma is represented with a longer delay
        PORTB = PORTB ^ (1<<LED_GREEN);
        _delay_ms(LONG_DELAY);
        
    
    }

    // Will never reach this
    return 0;
}
```

![Screenshot_1](https://user-images.githubusercontent.com/91612253/137041164-8153d94f-a08e-47c3-a8d2-2048873bec09.png)
