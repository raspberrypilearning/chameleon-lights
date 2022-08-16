
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
c = sense.colour.colour[0:3] # Store the sensed_colour value in the variable called c

  image = [
    b, b, b, b, b, b, b, b, 
    b, c, b, b, b, b, b, b, 
    c, b, c, c, c, c, b, b, 
    c, c, c, c, c, c, c, b, 
    b, b, c, c, c, c, c, b, 
    b, c, b, c, b, b, c, b, 
    b, b, b, b, b, c, b, b, 
    b, b, b, b, c, b, b, b]
    
sense.set_pixels(image)
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
