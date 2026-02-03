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

### 1. Last yr's project

<img width="904" height="542" alt="image" src="https://github.com/user-attachments/assets/daa28588-059f-4333-a42b-d56b9e544387" />

### »» What's working, what isn't, debugging & possible improvements

- In the first module (leftmost), the servo motors that moved the blue-colored boards, which represent water, worked nicely. I liked how springs were used to pull the boards back to their initial position, which eliminated the need for additional servo motors. However, the boat wasn't securely mounted, which led to inconsistent movement and sometimes no movement at all. This could have been fixed by adding a third screw or using nuts to securely hold the screws.
- In the second module, the motor was not working at all. To debug this, a multimeter could be used to assess whether the circuit is complete or incomplete. If complete, then the motor might be damaged, but if the circuit is incomplete, then there might be some faulty wires or connections in the circuit.
- The third module worked mostly fine, with the only uncertainty being with the rotating tree since its rotation was not smooth. It might therefore be hard to know whether it's malfunctioning or perhaps working as intended. Additionally, the motor was hidden away in a way that made it difficult to easily debug where the problem was. This could have been made easier if a hinge or sliding mechanism had been used to close the compartment where the motor was kept, allowing for easy access during assessment and debugging.

- In the fourth module, the only main issue was that the conveyor belt at the back was not functional. This could be due to an error in the code or in the circuit connection.

- The last module (Ferris wheel) worked only when it was pushed slightly inwards. It turned out that the issue was a loose mechanical connection between the Ferris wheel and the driving motor, which could have been fixed by adding extra srews for more strength. 



### 2. Game Choice

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
Instead of using a digital display, the game world is represented physically using a small conveyor belt. Obstacles are attached to the belt and move toward the player, simulating the scrolling motion of a platformer. The player character is represented by a vertically moving platform constrained by guide rails and activated through a spring-based input. The rails restrict the motion to a controlled vertical path, preventing unintended movement while maintaining a physical sense of jumping.
