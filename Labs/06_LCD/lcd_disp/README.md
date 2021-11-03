# Lab 6: MIKE APOSTOLOGIORGAKIS

Link to this file in your GitHub repository:

https://github.com/apostomike4/Digital_Electronics_2

### LCD display module

1. In your words, describe what ASCII table is.
   * ASCII table: This table is used as a way to match the human language with the machine language and it consists by letters, numbers, control characters, and other symbols.

2. (Hand-drawn) picture of time signals between ATmega328P and LCD keypad shield (HD44780 driver) when transmitting three character data `De2`.

![1635890940089](https://user-images.githubusercontent.com/91612253/139958938-0e921ec2-ef19-4562-9006-5865a79118d6.jpg)



### Stopwatch

1. Flowchart figure for `TIMER2_OVF_vect` interrupt service routine which overflows every 16&nbsp;ms but it updates the stopwatch LCD approximately every 100&nbsp;ms (6 x 16&nbsp;ms = 100&nbsp;ms). Display tenths of a second and seconds `00:seconds.tenths`. Let the stopwatch counts from `00:00.0` to `00:59.9` and then starts again. The image can be drawn on a computer or by hand. Use clear descriptions of the individual steps of the algorithms.

![1635892507527](https://user-images.githubusercontent.com/91612253/139961164-68241fd4-6b5d-4d6e-8697-b51197c11f46.jpg)


### Custom characters

1. Code listing of two custom character definition. Always use syntax highlighting and meaningful comments:

```c
/* Variables ---------------------------------------------------------*/
// Custom character definition
uint8_t customChar[16] = {
    0b01010,
	  0b01010,
	  0b00100,
	  0b01010,
	  0b00000,
	  0b00000,
	  0b00000,
	  0b00000,
    0b10001,
	  0b11111,
	  0b10001,
	  0b10101,
	  0b10101,
	  0b10001,
	  0b11111,
	  0b10001
};
```


### Kitchen alarm

Consider a kitchen alarm with an LCD, one LED and three push buttons: start, +1 minute, -1 minute. Use the +1/-1 minute buttons to increment/decrement the timer value. After pressing the Start button, the countdown starts. The countdown value is shown on the display in the form of mm.ss (minutes.seconds). At the end of the countdown, the LED will start blinking.

1. Scheme of kitchen alarm; do not forget the supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values.

![Screenshot_5](https://user-images.githubusercontent.com/91612253/139961807-6f01db65-2056-47b2-bb3a-c4d60d38759b.png)

