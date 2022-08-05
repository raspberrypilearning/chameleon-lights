## Draw your chameleon

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will create a function to draw your chameleon. The function will allow you to change the colour of your chameleon based on the colour reading in the next step. 
</div>
<div>
![An animation of what will be achieved by the end of this step.](images/step-three-output.gif){:width="300px"}
</div>
</div>

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
<span style="color: #0faeb0">Functions</span> ...
</p>

### Create your chameleon function

--- task ---

Find the `# Chameleon` comment.

Enter the code `def chameleon(sensed_colour):` to define your `chameleon` function. 

**Tip**: `sensed_colour` between the brackets will be used to pass the value of the **sensed colour** into your function. You will use this alongside the colour sensor in the next step.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 19
line_highlights: 21
---
# Chameleon

def chameleon(sensed_colour):
--- /code ---

--- /task ---

--- task ---

Inside your `def chameleon` function. Enter code to create a variable that will store the `sensed_colour` value. 

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 19
line_highlights: 23
---
# Chameleon

def chameleon(sensed_colour):
  
  c = sensed_colour # Store the sensed_colour value in the variable called c
--- /code ---

--- /task ---

--- task ---

Underneath the `c = sensed_colour` line of code, enter code to draw your chameleon. 

**Tip**: The `c` variable will be used to display the colour that has been sensed by the colour sensor.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 19
line_highlights: 25-33
---
# Chameleon

def chameleon(sensed_colour):
  
  c = sensed_colour # Store the sensed_colour value in the variable called c

  chameleon = [ 
    b, b, b, b, b, b, b, b, 
    b, c, b, b, b, b, b, b, 
    c, b, c, c, c, c, b, b, 
    c, c, c, c, c, c, c, b, 
    b, b, c, c, c, c, c, b, 
    b, c, b, c, b, b, c, b, 
    b, b, b, b, b, c, b, b, 
    b, b, b, b, c, b, b, b]
--- /code ---

--- /task ---

--- task ---

Underneath the code to draw your chameleon. Enter code to **return** the chameleon list that will be used to draw the chameleon on the LED matrix.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 19
line_highlights: 35
---
# Chameleon

def chameleon(sensed_colour):
  
  c = sensed_colour # Store the sensed_colour value in the variable called c

  chameleon = [
    b, b, b, b, b, b, b, b, 
    b, c, b, b, b, b, b, b, 
    c, b, c, c, c, c, b, b, 
    c, c, c, c, c, c, c, b, 
    b, b, c, c, c, c, c, b, 
    b, c, b, c, b, b, c, b, 
    b, b, b, b, b, c, b, b, 
    b, b, b, b, c, b, b, b]

  return chameleon
--- /code ---

--- /task ---

--- task ---

Find your `while` loop and add a `sleep(1)` line of code to make sure that the humidity image displays for 1 second.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 73
line_highlights: 84
---
# Display images based on humidity and colour sensor readings

while True: # Forever

  humidity = sense.get_humidity() # Take a reading from the humidity sensor
  if humidity > 75: # If the reading is higher than 75
    sense.set_pixels(humidity_high) # Display the humidity high image
  elif humidity < 40: # If the reading is less than 40
    sense.set_pixels(humidity_low)
  else:
    sense.set_pixels(humidity_medium) # Display the medium humidity image
  sleep(1)
--- /code ---

--- /task ---

--- task ---

Leave a space underneath the `sleep(1)` line of code and enter code that will create a variable for the `sensed_colour` and draw the chameleon on the LED matrix. 

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 73
line_highlights: 85-87
---
# Display images based on humidity and colour sensor readings

while True: # Forever

  humidity = sense.get_humidity() # Take a reading from the humidity sensor
  if humidity > 75: # If the reading is higher than 75
    sense.set_pixels(humidity_high) # Display the humidity high image
  elif humidity < 40: # If the reading is less than 40
    sense.set_pixels(humidity_low)
  else:
    sense.set_pixels(humidity_medium) # Display the medium humidity image
  sleep(1)
  
  sensed_colour = (0, 255, 0)
  sense.set_pixels(chameleon(sensed_colour)) # Draw the chameleon using the sense colour variable
--- /code ---

**Tip**: The values `(0, 255, 0)` have been placed here to allow you to temporarily test your code. This will be replaced with the **actual** sensed colour in the next step.

--- /task ---

--- task ---

Add another `sleep(1)` to the bottom of your `while` loop to allow you to see the chameleon for 1 second.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 86
line_highlights: 88
---
  sensed_colour = (0, 255, 0)
  sense.set_pixels(chameleon(sensed_colour)) # Draw the chameleon using the sense colour variable
  sleep(1)
--- /code ---

--- /task ---

--- task ---

**Test**: Click Run and test your code. You should see your water droplet image, followed by a green chameleon image.

![A short animation showing the water droplet appearing on the LED matrix followed by the green chameleon.](images/step-three-output.gif){:width="300px"}

--- /task ---


--- save ---