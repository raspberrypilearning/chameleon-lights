
--- question ---

---
legend: Question 2 of 3
---

A Code Club creator has written some code to detect the colour using the SenseHAT's colour sensor. They have run their code and there are no syntax errors but the colour displayed doesn't seem to match the colour being sensed. 

Which line of code do they need to change?

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 10
line_highlights: 
---
  sleep(2 * sense.colour.integration_time) # Sense the colour
  red, green, blue, clear = sense.colour.colour # Store the sensor readings
  sensed_colour = (blue, green, red) # Store the RGB values for the sensed colour
  sense.clear(sensed_colour) # Fill the LED matrix with the sensed colour
--- /code ---

--- choices ---

- ( ) Line 10

  --- feedback ---

Try again, this line of code senses the colour. 

  --- /feedback ---

- ( ) Line 11

  --- feedback ---

Have another go. This line of code stores the sensor readings. 

  --- /feedback ---

- (x) Line 12

  --- feedback ---

Correct! The RGB colour values have been stored in the wrong order which will produce the wrong colour on the LED matrix.

  --- /feedback ---

- ( ) 13

  --- feedback ---

Try again. This line of code fills the whole LED matrix using the RGB values that have been stored in line 3.

  --- /feedback ---

--- /choices ---

--- /question ---
