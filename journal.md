Homework 2

Process Overview

I began by loading the Adafruit multitasking servo example and verifying that the servo swept correctly using millis() instead of delay(). I then added a momentary switch to control when the servo sweep was active, ensuring the servo only updated while the button was pressed ([servoSwitchControlled](https://github.com/GreatB1/MachineLab/blob/main/code/homework%202/servoSwitchControlled). After confirming this behavior, I extended the code to include a potentiometer to control the speed of the servo sweep ([servoPotentiometerControlled](https://github.com/GreatB1/MachineLab/blob/main/code/homework%202/servoPotentiometerControlled). At each stage, I tested the circuit and code incrementally and committed working versions to GitHub before moving on to the next modification.

Challenges faced

One issue I encountered was getting the servo sweep to run smoothly without using delay(). At first, I was unsure whether the servo timing logic was working correctly because the movement seemed inconsistent. By reviewing how millis() is used inside the Update() function and comparing time differences instead of pausing execution, I understood how non-blocking timing allows the servo to move while the rest of the program continues running.

Another challenge was working with the momentary switch. At first, my logic was reversed because the button reads LOW when pressed. I verified this using the Serial Monitor and adjusted the condition accordingly.

To debug, I used Serial.println() to monitor button states and tested the code incrementally by isolating sections of logic. This helped me understand how millis()-based timing and conditional task execution work together in a multitasking setup.

Images

<img width="424" height="542" alt="image" src="https://github.com/user-attachments/assets/5058b7ef-2db0-45d1-83b4-0278d5f8dc1c" />



<img width="424" height="542" alt="image" src="https://github.com/user-attachments/assets/bffdc0f9-88bd-4507-be06-2af513b68bbb" />

  
