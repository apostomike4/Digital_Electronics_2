# Lab 5: MIKE APOSTOLOGIORGAKIS

https://github.com/apostomike4/Digital_Electronics_2

### 7-segment library

1. In your words, describe the difference between Common Cathode and Common Anode 7-segment display.
   * CC SSD: Common cathode 7-segment display means that all ports of the 7-segment are connected to the ground and we can control them with high signal( binary 1).
   * CA SSD: Common anode 7-segment display means that all ports of the 7-segment are connected to Vcc and we can control them with low signal( binary 0).
 
2. Code listing with syntax highlighting of two interrupt service routines (`TIMER1_OVF_vect`, `TIMER0_OVF_vect`) from counter application with at least two digits, ie. values from 00 to 59:

```c
/**********************************************************************
 * Function: Timer/Counter1 overflow interrupt
 * Purpose:  Increment counter value from 00 to 59.
 **********************************************************************/
ISR(TIMER1_OVF_vect)
{
  cnt0++;

  if(cnt0>59) cnt0=0;
}
```

```c
/**********************************************************************
 * Function: Timer/Counter0 overflow interrupt
 * Purpose:  Display tens and units of a counter at SSD.
 **********************************************************************/
ISR(TIMER0_OVF_vect)
{
    static uint8_t pos = 0;
    if(i>6){
    i=0;
    cnt0=0;}
    
    else (cnt0>9){
         cnt0=0;
         i++;}

    SEG_update_shift_regs(cnt0, pos);
}
```

3. Flowchart figure for function `SEG_clk_2us()` which generates one clock period on `SEG_CLK` pin with a duration of 2&nbsp;us. The image can be drawn on a computer or by hand. Use clear descriptions of the individual steps of the algorithms.

   ![your figure]()


### Kitchen alarm

Consider a kitchen alarm with a 7-segment display, one LED and three push buttons: start, +1 minute, -1 minute. Use the +1/-1 minute buttons to increment/decrement the timer value. After pressing the Start button, the countdown starts. The countdown value is shown on the display in the form of mm.ss (minutes.seconds). At the end of the countdown, the LED will start blinking.

1. Scheme of kitchen alarm; do not forget the supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values.

![Screenshot_5](https://user-images.githubusercontent.com/91612253/138905826-c31af333-6831-47e7-abc2-8b5cc6dfed00.png)
