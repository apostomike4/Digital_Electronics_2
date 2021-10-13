# Lab 4: APOSTOLOGIORGAKIS MIKE

Link to your `Digital-electronics-2` GitHub repository:

https://github.com/apostomike4/Digital_Electronics_2

### Overflow times

1. Complete table with overflow times.

| **Module** | **Number of bits** | **1** | **8** | **32** | **64** | **128** | **256** | **1024** |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| Timer/Counter0 | 8  | 16u | 128u | -- | 1m | -- | 4m | 16m |
| Timer/Counter1 | 16 |  4m   |   33m   | -- | 262m | -- | 1 | 4 |
| Timer/Counter2 | 8  |  16u   |   128u   |  512u  | 1m |  2m  | 4m | 16m |


### Timer library

1. In your words, describe the difference between common C function and interrupt service routine.
   * Function is a construct by the programmer that can be called upon and do whatever we may like.
   * Interrupt service routine is invoked by an interupt request from a hardware device and we can programm it to do whatever we like.![Screenshot_4](https://user-images.githubusercontent.com/91612253/137202873-34e47200-d8ce-4178-a9ff-ccc19d63531e.png)


All in all, the main difference in a function and an ISR, is that the ISR is called from some hardware settings but the function is called whenever we like in main.

2. Part of the header file listing with syntax highlighting, which defines settings for Timer/Counter0:

```c
/**
 * @name  Definitions of Timer/Counter0
 * @note  F_CPU = 16 MHz
 */
// WRITE YOUR CODE HERE
```

3. Flowchart figure for function `main()` and interrupt service routine `ISR(TIMER1_OVF_vect)` of application that ensures the flashing of one LED in the timer interruption. When the button is pressed, the blinking is faster, when the button is released, it is slower. Use only a timer overflow and not a delay library.

![Screenshot_3](https://user-images.githubusercontent.com/91612253/137200305-9fcbbc6b-2057-474b-8346-a15540f7cea1.png)


### Knight Rider

1. Scheme of Knight Rider application with four LEDs and a push button, connected according to Multi-function shield. Connect AVR device, LEDs, resistors, push button, and supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values!

![Screenshot_4](https://user-images.githubusercontent.com/91612253/137202914-f96638c7-0086-4d63-9361-3e6f816dfb68.png)
