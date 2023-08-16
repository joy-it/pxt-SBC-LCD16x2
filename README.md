# MakeCode Package for the Joy-IT SBC-LCD16x2
This library provides a Microsoft Makecode package for the Joy-IT SBC-LCD16x2 16x2 I2C display module. See https://www.joy-it.net/products/SBC-LCD16x2 for more details.

The 16x2 display can output texts on a total of 16 characters and over 2 lines. It is ideally suited for the quick output of status information or measurement results.

**The 16x2 lcd display is connected via I2C on address 0x21.**

### Initialization

Because the display is an I2C-device, an initial initialization is required before use:

```typescript
SBCLCD16x2.lcd16x2Init()
```

### Power functions

The display supports various power functions. These include power on, power off, backlight power on and backlight power off.

```typescript
// Turn LCD on
SBCLCD16x2.lcd16x2TurnOn()
// Turn LCD off
SBCLCD16x2.lcd16x2TurnOff()
// Turn backlight on
SBCLCD16x2.lcd16x2BacklightOn()
// Turn backlight off
SBCLCD16x2.lcd16x2BacklightOff()
```

### Output text

Text can be send to the display by using the **SBCLCD16x2.LCD16x2_showText(text, x, y)** function. The string to be displayed is passed with **text** and the position on the display is passed with **x** and **y**. The entire display output can be deleted with **SBCLCD16x2.LCD16x2_clear()**.

```typescript
// Show text at position 0 on line 0
SBCLCD16x2.lcd16x2ShowText('Hello World', 0, 0)
// Show text at position 2 on line 1
SBCLCD16x2.lcd16x2ShowText('Hello World', 2, 1)
// Clear output
SBCLCD16x2.lcd16x2Clear()
```

### Shift text

The whole output can be shifted to the left and right and can thus be moved over the display.

```typescript
// Shift text to the left
SBCLCD16x2.lcd16x2ShiftLeft()
// Shift text to the right
SBCLCD16x2.lcd16x2ShiftRight()
```

### Cursor functions

The display also offers the possibility to switch on the current cursor position. You can choose between a permanent and a blinking cursor. Of course, the cursor can also be switched off and moved back to the start position.

```typescript
// Show permanent cursor
SBCLCD16x2.lcd16x2ShowCursor()
// Show blinking cursor
SBCLCD16x2.lcd16x2BlinkingCursor()
// Move cursor to starting position
SBCLCD16x2.lcd16x2ReturnHome()
// Hide cursor
SBCLCD16x2.lcd16x2HideCursor()
```