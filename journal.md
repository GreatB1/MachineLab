## [Homework 2](https://github.com/michaelshiloh/MachineLab/blob/master/homework.md#homework-due-thursday-29-january-2026)

### Process Overview

I began by loading the Adafruit multitasking servo example and verifying that the servo swept correctly using millis() instead of delay(). I then added a momentary switch to control when the servo sweep was active, ensuring the servo only updated while the button was pressed ([servoSwitchControlled](https://github.com/GreatB1/MachineLab/blob/main/code/homework%202/servoSwitchControlled)). After confirming this behavior, I extended the code to include a potentiometer to control the speed of the servo sweep ([servoPotentiometerControlled](https://github.com/GreatB1/MachineLab/blob/main/code/homework%202/servoPotentiometerControlled)). At each stage, I tested the circuit and code incrementally and committed working versions to GitHub before moving on to the next modification.

### Challenges faced

One issue I encountered was getting the servo sweep to run smoothly without using delay(). At first, I was unsure whether the servo timing logic was working correctly because the movement seemed inconsistent. By reviewing how millis() is used inside the Update() function and comparing time differences instead of pausing execution, I understood how non-blocking timing allows the servo to move while the rest of the program continues running.

Another challenge was working with the momentary switch. At first, my logic was reversed because the button reads LOW when pressed. I verified this using the Serial Monitor and adjusted the condition accordingly.

To debug, I used Serial.println() to monitor button states and tested the code incrementally by isolating sections of logic. This helped me understand how millis()-based timing and conditional task execution work together in a multitasking setup.

Image 1

<img width="424" height="542" alt="image" src="https://github.com/user-attachments/assets/5058b7ef-2db0-45d1-83b4-0278d5f8dc1c" />


Image 2

<img width="424" height="542" alt="image" src="https://github.com/user-attachments/assets/bffdc0f9-88bd-4507-be06-2af513b68bbb" />


  
## [Homework 3](https://github.com/michaelshiloh/MachineLab/blob/master/homework.md#homework-due-tuesday-3-february-2026) 

### Game Choice

I am thinking of exploring a physical reinterpretation of a 2D platformer video game, such as Mario. The project draws inspiration from classic side-scrolling games that rely on simple mechanics such as jumping, timing, and obstacle avoidance. Rather than presenting the game on a digital screen, the goal is to translate the logic of a platformer into a mechanical system.

The focus is on isolating the jumping and examining how it can be experienced through physical input and motion.

### Mood Board

The mood board would include:

- Visual references from minimalist platformer games and pixel art environments
- Images of conveyor belts, looping motion systems, and continuous movement
- Mechanical components such as springs, rails, and guide systems
- Bright, playful colors combined with exposed mechanical structures


### Sketch Ideas & Features

A small-scale mechanical setup consisting of:
- A continuous conveyor belt that represents the scrolling game world
- Physical obstacles attached to the belt that move toward the player
- A stationary player position centered above or beside the belt, with a spring mechanism to enable the player to jump when a button is pressed
- Vertical rails to support the player and prevent jumping off

<img width="824" height="642" alt="image" src="https://github.com/user-attachments/assets/5c350f6d-4e10-4a0c-9318-97f91b6999bc" />


### Mechanical Activation 
Instead of using a digital display, the game world is represented physically using a small conveyor belt. Obstacles are attached to the belt and move toward the player, simulating the scrolling motion of a platformer. The player character is represented by a vertically moving platform constrained by guide rails and activated through a spring-based input. The rails restrict the motion to a controlled vertical path, preventing lateral movement while maintaining a physical sense of jumping.
