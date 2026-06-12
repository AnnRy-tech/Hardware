Power supply VDD vs Power supply LCD 
/////////////////////////////////////
1. Power Supply VDD = 3.3V (The "Brain" Power)
***********************************************
This is the logic voltage for the display's internal microchip (the controller/driver).
What it does: 
It powers the internal registers, memory, and communication lines that talk to your microcontroller.
What it means for you: 
Your data signals (Pins like RS, RW, E, or SPI lines) must send 3.3V signals.
If you connect a 5V microcontroller (like an Arduino Uno) directly to these pins, you risk burning out the display's brain.
So my logic signals should be 3.3 V

Power Supply LCD = 5.5V (The "Glass" Power)
*********************************************
This is the analog driving voltage for the actual liquid crystal fluid trapped inside the glass panel. 
It is often labeled as \(V_{LCD}\), V₀, or \(V_{EE}\) in datasheets.
What it does: Liquid crystals require a higher voltage potential to physically twist and block light (which creates the pixels or characters you see). 
3.3V is simply not strong enough to make the crystals move efficiently, resulting in a completely blank or faint screen.

What it means for you:
The display needs a 5.5V electrical source dedicated strictly to biasing the glass matrix so the dark areas look crisp and readable.
