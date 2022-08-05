
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
  red, green, blue = sense.colour.colour[0:3] # Store the readings
  sensed_colour = (blue, green, red) # Store the RGB values
  sense.clear(sensed_colour) # Block the colour on the matrix
--- /code ---

--- choices ---

- ( ) Line 10

  --- feedback ---

Try again, this line of code stores the colour readings from the sensor. 

  --- /feedback ---

- (x) Line 11

  --- feedback ---

Correct! The RGB colour values have been stored in the wrong order which will produce the wrong colour on the LED matrix.

  --- /feedback ---

- ( ) Line 12

  --- feedback ---

Try again. This line of code fills the whole LED matrix using the RGB values that have been stored in line 3.

  --- /feedback ---

--- /choices ---

--- /question ---
