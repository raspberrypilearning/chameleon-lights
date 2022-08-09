## Sense the colour

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will set up the colour sensor and use it to sense the colour in the environment. This colour will then be used to colour in your chameleon. 
</div>
<div>
![A short animation showing the colour changing on the sensor and the chameleon changing to match the colour.](images/step-four-output.gif){:width="300px"}
</div>
</div>

**Tip**: The values `(0, 255, 0)` have been placed here to allow you to temporarily test your code. This will be replaced with the **actual** sensed colour in the next step.



### Setup the colour sensor

--- task ---

Find the `# Set up the colour sensor` comment.

Enter the code to set up the colour sensor.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 10
line_highlights: 12-13
---
# Set up the colour sensor

sense.color.gain = 60 # Set the sensitivity of the sensor
sense.color.integration_cycles = 64 # The interval at which the reading will be taken
--- /code ---

--- /task ---

### Use the colour sensor to colour in the chameleon

--- task ---

Go back to your `while` loop and above the line of code `sense.set_pixels(chameleon())` line of code, add code to store and use the sensed colour.

**Tip**: Make room for your new line of code by pressing the enter key.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 76
line_highlights: 87-88
---
while True: # Forever

  humidity = sense.get_humidity() # Take a reading from the humidity sensor
  if humidity > 75: # If the reading is higher than 75
    sense.set_pixels(humidity_high) # Display the humidity high image
  elif humidity < 40: # If the reading is less than 40
    sense.set_pixels(humidity_low)
  else:
    sense.set_pixels(humidity_medium) # Display the medium humidity image
  sleep(1)
  
  red, green, blue = sense.colour.colour[0:3] # Store the sensor readings
  sensed_colour = (red, green, blue)
  sense.set_pixels(chameleon()) # Draw the chameleon using the sense colour variable
  sleep(1)
--- /code ---

--- /task ---

--- task ---

Add `sensed_colour` between the brackets of your `sense.set_pixels(chameleon())` code. This will be used to pass the value of the **sensed colour** into your function. 

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 87
line_highlights: 89
---
  red, green, blue = sense.colour.colour[0:3] # Store the sensor readings
  sensed_colour = (red, green, blue)
  sense.set_pixels(chameleon(sensed_colour)) # Draw the chameleon using the sense colour variable
  sleep(1)
--- /code ---

--- /task ---

--- task ---

Find your `chameleon()` function and add `sensed_colour` between the brackets to use it in the function.

Set your `c` variable to `sensed_colour`.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 20
line_highlights: 22, 24
---
# Chameleon

def chameleon(sensed_colour):
  
  c = (sensed_colour) # Store the sensed_colour value in the variable called c

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

**Test**: Click Run and test your code. You should be able to change the colour on the sensor and see your chameleon change. 

**Debug:** Check your code matches the examples above. Make sure you have passed `sensed_colour` into your function. 

![A short animation showing the colour changing on the sensor and the chameleon changing to match the colour.](images/step-four-output.gif){:width="300px"}

<mark>How does this work with the physical sensehat? Do they stick some colour paper in front of it?</mark>

--- /task ---


--- save ---