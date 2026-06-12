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


Working of LCD display
************************************
SDA and SCL (The Postal System)These two lines are the data highway. SCL acts as a ticking clock to keep everything perfectly timed, while SDA carries the digital letters and configuration coordinates sent from your microcontroller (WO1602I-TM... p. 8). Together, they deliver the computer messages directly into the screen's brain chip (WO1602I-TM... pp. 8, 13).

The Capacitor (The Voltage Booster)Because your main 3.3V power supply is too weak to run the screen glass (WO1602I-TM... pp. 6, 10), the external capacitor acts like a rapid electrical bucket (WO1602I-TM... pp. 8, 10). It fills up with 3.3V, instantly shifts its position to stack on top of the main power line, and dumps the combined, higher voltage onto Pin 1 (VOUT) (WO1602I-TM... pp. 8, 10). This cycle happens thousands of times a second to maintain a steady 4.5V power pool (WO1602I-TM... p. 6, MTY-HSG160... p. 5).

The Liquid Crystal Voltage (The Window Blinds)The screen's glass is filled with millions of microscopic liquid crystals trapped in a fluid layer (MTY-HSG160... p. 4). When the boosted 4.5V power from the capacitor hits them, it creates an electrical field that physically twists these crystals like tiny window blinds (MTY-HSG160... p. 5). Twisting blocks the background light from passing through, which creates the crisp, dark shapes of the letters you see on the screen (MTY-HSG160... p. 4). If the capacitor slips or weakens, the crystals untwist, and your text instantly dims.
