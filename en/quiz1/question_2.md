
--- question ---

---
legend: Question 2 of 3
---

A programmer has written some code to detect the colour using the SenseHAT's colour sensor. They have run their code but the colour is only detected once. What should they add to make their code detect the colour in a loop **forever**.  

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 10
line_highlights: 
---
red, green, blue = sense.colour.colour[0:3] # Store the readings
sensed_colour = (red, green, blue) # Store the RGB values
sense.clear(sensed_colour) # Fill the matrix with the sensed colour
--- /code ---

--- choices ---

- ( ) for i in range(10):

  --- feedback ---

Try again, this will only sense the colour 10 times and then stop. It won't repeat forever. 

  --- /feedback ---

- (x) while True:

  --- feedback ---

Correct! `while` is used to loop forever.

  --- /feedback ---

--- /choices ---

--- /question ---
