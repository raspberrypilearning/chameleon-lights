
--- question ---

---
legend: Question 3 of 3
---

Your chameleon lights project used an `if` statement to display an image based on different conditions. 

Which line of code checked if the humidity was low?

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 94
line_highlights: 
---
while True: # Forever

  humidity = sense.get_humidity() # Take a reading 
  if humidity > 75: # If the reading is higher than 75
    humidity_high() # Display image
  elif humidity < 40: # If the reading is less than 40
    humidity_low() # Display image
  else:
    humidity_medium() # Display image
  sleep(1)
--- /code ---

--- choices ---

- ( ) Line 97


  --- feedback ---

Try again. This line of code checks if the `humidity` is high. 

  --- /feedback ---

- (x) Line 99


  --- feedback ---

Excellent! This line of code checks if the `humidity` is low. 

  --- /feedback ---

- ( ) Line 101


  --- feedback ---

Have another go. This line of code is used to say what should happen if the conditions in the statements above have not been met. 

  --- /feedback ---

--- /choices ---

--- /question ---
