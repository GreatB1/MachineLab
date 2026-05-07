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

<img width="880" height="642" alt="image" src="https://github.com/user-attachments/assets/5c350f6d-4e10-4a0c-9318-97f91b6999bc" />


### Mechanical Activation 
Instead of using a digital display, the game world is represented physically using a small conveyor belt. Obstacles are attached to the belt and move toward the player, simulating the scrolling motion of a platformer. The player character is represented by a vertically moving platform constrained by guide rails and activated through a spring-based input. The rails restrict the motion to a controlled vertical path, preventing unintended movement while maintaining a physical sense of jumping.

## [Homework 4](https://github.com/michaelshiloh/MachineLab/blob/master/homework.md#homework-due-thursday-5-february-2026) 
Conveyor belt mechanism

<img width="880" height="620" alt="image" src="https://github.com/user-attachments/assets/06332a77-27c8-4f72-8d20-79410707c855" />

Source [Easy HomeMade Projects](https://www.youtube.com/watch?v=qoejrZhn5XI)

<img width="880" height="468" alt="image" src="https://github.com/user-attachments/assets/d4bf1e33-0769-4727-8188-133c5f1c2677" />

Source [thingiverse.com](https://www.thingiverse.com/thing:2838888/comments)


## [Homework 5](https://github.com/michaelshiloh/MachineLab/blob/master/homework.md#homework-due-tuesday-10-february-2026) 

## Part 1
### Objective

The goal of this lab was to complete the DC motor control exercise started in class using an Arduino and an L298N motor driver module. The task required controlling both the **speed** and **direction** of a DC motor. Speed control was achieved using PWM (Pulse Width Modulation), and direction control was managed using the H-Bridge functionality built into the L298N module. We used the HowToMechatronics tutorial as a reference during this activity.

### Overview of the System

The Arduino sends a PWM signal to the ENA pin of the L298N to control motor speed. By adjusting the duty cycle of the PWM signal, the average voltage delivered to the motor changes, which directly affects its speed.

Motor direction is controlled using the IN1 and IN2 pins on the L298N. By setting these pins HIGH or LOW in different combinations, the current flowing through the motor is reversed, which changes the direction of rotation.


### Schematic
<img width="880" height="489" alt="image" src="https://github.com/user-attachments/assets/e3b0c5f3-377f-42d7-ad85-d0638cbdf341" />

### Physical Setup
<img width="880" height="525" alt="image" src="https://github.com/user-attachments/assets/b23652c6-e868-4c1c-94ac-0a0048e46f9c" />

### Code
The Arduino code used can be found [here](https://github.com/GreatB1/MachineLab/blob/main/code/Homework%205.m). 

### Results

After completing the wiring and programming, the motor operated successfully. The potentiometer allowed smooth adjustment of motor speed, and the pushbutton reliably changed the motor’s direction. The system responded consistently to input changes and demonstrated proper PWM-based speed control.


### Issues Encountered and Fixes

One issue I encountered was that the motor did not spin when I first powered the circuit. After checking the wiring, I realized that the ENA pin was not properly connected to a PWM-capable pin on the Arduino. Because PWM is required to control speed, the motor was not receiving the correct control signal. I corrected the wiring by connecting ENA to a proper PWM pin, and the motor began functioning as expected.

Another problem occurred at low speed settings. When the potentiometer was turned down to very low values, the motor would make a buzzing sound but would not rotate. This happened because the PWM signal was too low to provide enough starting torque for the motor. To fix this, I adjusted the minimum PWM value in the program so the motor would always receive enough power to start turning. After this adjustment, the motor ran more reliably across the speed range.

I also experienced inconsistent direction changes when pressing the pushbutton. Sometimes the motor would switch directions multiple times with a single press. This was caused by button bounce, which is a common issue with mechanical switches. To resolve this, I added a small delay in the code to debounce the button input. After implementing this fix, the direction toggled correctly with each press.

Additionally, I initially had a grounding issue where the Arduino and motor driver did not share a common ground. This caused unpredictable behavior in the motor’s response. Once I connected the grounds together, the system stabilized and operated consistently.


### Conclusion

This lab helped reinforce my understanding of PWM and H-Bridge motor control. I successfully implemented speed and direction control of a DC motor using an Arduino and L298N module. Troubleshooting wiring errors, PWM limitations, grounding issues, and button debounce problems improved my debugging skills and strengthened my understanding of practical motor control systems.

## Part 2
### Prototype: Conveyor Belt Mechanism (Motor-Driven)

For this phase of the assignment, the objective was to create a rough prototype that validates whether our motor can successfully animate one of the core features of the project. I chose to prototype the horizontal pipe movement using a conveyor belt mechanism.

The aim was to confirm that the motor could drive a continuous loop system capable of translating objects horizontally, even if the structure itself was temporary and made from simple materials.

### Design Approach

The conveyor system consisted of two rollers (a drive roller and a passive roller), a thin flexible cardboard strip acting as the belt, and a basic cardboard frame to hold everything in alignment. The motor was connected to the drive roller using a hub to ensure torque transfer. When powered, the motor rotated the roller, pulling the cardboard belt along its loop.

<img width="680" height="425" alt="JwxA3df" src="https://github.com/user-attachments/assets/2dd8cb5c-99e2-4ea4-9a0f-ee2731bee780" />

https://github.com/user-attachments/assets/bd44ef19-67e3-4379-ab24-febbf37e7785

Thin flexible cardboard was selected because it is lightweight, easy to bend around rollers, and quick to modify during iteration. Since this was only a validation prototype, speed of construction and adaptability were prioritized over durability.

### Difficulties, Fixes & Observations

One of the main issues encountered was belt slipping. Initially, when the motor rotated, the smooth cardboard belt did not maintain sufficient friction against the roller surface. As a result, torque transfer was inconsistent and the belt occasionally stalled. To solve this, I introduced regular small bends (corrugation-like folds) along the length of the cardboard belt. These bends increased surface friction and created additional grip points against the roller. After implementing this modification, slipping was significantly reduced and motion became more consistent.

Tension control also proved critical. A loose belt caused slipping, while excessive tension increased resistance and motor load. Through trial and adjustment, I found a moderate tension that allowed smooth continuous rotation without overloading the motor.

### What I Learned

This prototype reinforced several key mechanical principles:

- Friction is essential for torque transfer in belt-driven systems.

- Small structural modifications (like surface texturing or bending) can dramatically improve performance.

- Rapid prototyping allows mechanical problems to surface early, when they are easiest to fix.

Overall, this iteration successfully validated the motion concept and provided clear direction for refinement.


## [Homework 6](https://github.com/michaelshiloh/MachineLab/blob/master/homework.md#homework-due-tuesday-17-february-2026) 
### Brainstorming & Core Mechanisms

This week, our group focused on defining the mechanical systems that will drive our Flappy Bird–inspired machine. After discussion, we identified three primary motion requirements:

- Vertical motion – The bird should move up and down.

- Horizontal motion – The pipes should translate across the frame.

- Rotational motion – A servo-driven “GAME OVER” sign will rotate into view at the end of the loop.

Of these, the two critical mechanisms are vertical bird movement and horizontal pipe movement. Without either, the project cannot function as an interactive game. For this week’s prototype, we chose to focus on the vertical motion system, since it directly controls user interaction.

### Prototype: Linear Actuation for Vertical Motion

Our objective was to convert rotational motion from a motor into controlled vertical displacement. We implemented a lead-screw mechanism:

- A DC motor rotates a threaded rod.

- A nut constrained from rotating translates along the rod.

This converts rotational motion into linear vertical movement.

Initially, we attempted to construct the support structure using cardboard and adhesive. However, this failed due to insufficient rigidity. After consulting the professor, we rebuilt the structure using a wooden base and mechanical fasteners (nuts and bolts).
<img width="680" height="425" alt="JwxA3df" src="https://github.com/user-attachments/assets/a9ef0bd8-ea4e-4b68-bd4b-e8e699689cb6" />

 We also used L-brackets to constrain the nut while allowing the threaded rod to rotate freely. 
 This successfully enabled rotational-to-linear motion conversion.
 
 <img width="680" height="425" alt="image" src="https://github.com/user-attachments/assets/acdf5bd9-98ff-4218-801d-1982211c0979" />

 The mechanism functioned as intended; the carriage moved vertically in response to motor rotation.

![P16M3xZ](https://github.com/user-attachments/assets/e7ae7db1-d13b-4895-af41-7b730d4af8ca)


### Difficulties, Fixes & Lessons Learned

One major difficulty we encountered was structural instability. During operation, the mechanism exhibited noticeable wobbling, especially during upward motion. This instability was caused by a lack of lateral guidance and insufficient bracing in the frame. Additionally, the motor’s weight created imbalance and bending stress, increasing structural flex. To address this, we replaced the cardboard supports with a wooden base and secured all joints using bolts instead of glue. We tightened mechanical connections and improved bracket placement to better constrain motion. These changes significantly improved rigidity. While some wobble remains, the motion conversion now works consistently and predictably. From this, we learned that linear systems require strict single-axis constraint, and even minor structural flex can compromise mechanical performance.

Another challenge involved material failure in our initial prototype. The cardboard structure was unable to withstand the torque and vibration generated by the motor. Adhesive joints weakened under dynamic loading, and the structure could not maintain alignment. We resolved this by transitioning to wood and using mechanical fasteners. This reinforced the importance of material selection in mechanical systems — dynamic loads and vibration require rigid materials and secure fastening methods rather than temporary bonding solutions.

We also identified a load distribution issue. Because of how the system was assembled, the mechanism indirectly supported the motor’s weight during motion, increasing strain on the structure. This highlighted an inefficiency in our design. As potential improvements, we discussed using a smaller motor, separating the motor mount from the moving assembly, or incorporating vertical guide rails or pipes to reduce lateral movement. This experience emphasized the importance of isolating driving components from moving components and minimizing unnecessary load paths in mechanical design.

### Reflection

This week marked the transition from conceptual planning to physical testing. Although the prototype is not yet structurally optimized, it successfully demonstrates functional vertical motion and validates our core mechanism concept.

More importantly, the process revealed key engineering insights: motion design must account for force distribution and constraint; rigidity and alignment are essential for smooth linear motion; and early prototyping exposes weaknesses that sketches cannot reveal.

Overall, this iteration provided a strong proof of concept and a clear direction for refinement. Our next step will be improving structural stability and integrating guidance systems to achieve smoother, more controlled vertical movement.

## [Homework due at our second individual meeting (April 9)](https://github.com/michaelshiloh/MachineLab/blob/master/homework.md#homework-due-at-our-second-individual-meeting-april-9-12)
During the individual meeting, we discussed how the project would proceed following the transition to online classes. Given the limitations in access to shared tools, workspace, and materials, the focus was on adapting the project to be feasible for independent work at home.

I decided to continue with the original Flappy Bird–inspired concept, but to scale it down into a smaller and simpler version. Instead of building the full multi-mechanism system, I will focus on a reduced setup that still demonstrates the core motion principles, making it more manageable within current constraints.

We also discussed access to tools and materials. Since I no longer have access to the lab, I plan to source the required components independently, including basic materials from local hardware stores and any specialized parts from online retailers.

### Next Steps:
Finalize the simplified design scope and begin acquiring materials needed to start building the individual prototype.

## [Homework due at our third individual meeting (April 16)](https://github.com/michaelshiloh/MachineLab/blob/master/homework.md#homework-due-at-our-third-individual-meeting-april-13--19)
Following the individual meeting, I proceeded with sourcing the materials required to begin building my simplified version of the Flappy Bird–inspired mechanism. I was able to obtain the key components needed for prototyping, including a DC motor, a 12V power adapter, a hot glue gun, and basic construction materials.

Having access to these components allowed me to move from planning into execution. I reviewed my earlier prototype ideas, particularly the conveyor belt and vertical motion mechanisms, and began considering how to adapt them into a more compact and manageable system that can be built at home.

At this stage, no full mechanism has been assembled yet, but the preparation phase is complete. I now have the necessary tools and materials to begin construction and testing.

### Next Steps:
Start building the first working mechanism (likely the conveyor system or vertical motion prototype) and test basic motor-driven movement.

## Change of project direction
Following my earlier consideration of shifting away from the Flappy Bird–inspired project, I finalized my decision to develop a **mechanical, motor-driven sorting system**. The goal is to create a complete, self-contained machine that demonstrates coordinated motion using multiple mechanisms rather than a single isolated component.

### Project Concept

The project will be a **motorized conveyor system with a timed mechanical sorting mechanism**. Objects placed on the conveyor will move forward continuously and interact with a secondary mechanism that redirects or allows them to pass based on timing.

Unlike sensor-based systems, this design will rely entirely on **mechanical synchronization**. A single motor will drive both the conveyor belt and a cam mechanism, ensuring that motion and interaction are inherently coordinated.

### System Overview

The system consists of three main subsystems:

- **Conveyor Belt System**  
  A continuous loop made from flexible cardboard, driven by a motorized roller. This transports objects horizontally across the frame.

- **Cam Mechanism (Timing Control)**  
  A rotating cam attached to the motor shaft. This converts continuous rotation into periodic motion.

- **Sorting Mechanism (Flap/Lever)**  
  A lever or flap connected to the cam follower. At specific intervals, the cam pushes the lever into the conveyor path, redirecting objects off the belt.

### Implementation Plan

1. Build and refine the conveyor system (based on previous prototype).
2. Design and attach a cam to the motor shaft.
3. Create a follower mechanism to translate cam motion into linear movement.
4. Connect the follower to a flap that interacts with objects on the conveyor.
5. Add output paths (straight vs diverted)

### Key Design Considerations

- **Friction & Grip:** Ensuring sufficient contact between belt and rollers (previously improved using bends in the cardboard).
- **Alignment:** Maintaining parallel rollers to prevent belt drift.
- **Timing:** Synchronizing conveyor speed and cam rotation for consistent interaction.
- **Structural Stability:** Reinforcing the frame to reduce wobbling.

### Why This Direction

This approach allows me to:
- Build a **complete mechanical system** rather than a single mechanism  
- Demonstrate **multiple motion types** (continuous + reciprocating)  
- Explore **cause-and-effect relationships** without relying on electronics  
- Work within the constraints of available materials and tools  

### Next Steps

- Begin constructing the refined conveyor system  
- Prototype and test different cam profiles    

### Media

<img width="227" height="222" alt="image" src="https://github.com/user-attachments/assets/73720676-fae2-4376-ba7d-2ce56ebc6a56" />

Source ([Chegg.com](https://learn.adafruit.com/cam-follower-automaton/build-the-mechanism))

<img width="280" height="180" alt="image" src="https://github.com/user-attachments/assets/018f598a-8f4f-4f41-b226-f08d456fe1b0" />

Source (Chegg.com)

## April 21, 2026 – Conveyor System Build & Iteration

I began constructing the conveyor system as the base of my mechanical sorting project. The goal was to create a stable, motor-driven belt capable of continuous horizontal motion using simple, accessible materials.

### Build Process

The structure was made primarily from cardboard, with two DC motors used to drive the system. For the belt, I initially attempted to use cardboard, but it proved too rigid and did not bend smoothly around the rollers. To solve this, I created a belt using masking tape looped onto itself, forming a flexible, continuous, non-sticky surface. This worked significantly better, allowing smooth motion around the rollers.

For the rollers, I used pens as cylindrical supports. This was an effective low-cost solution, as they provided a smooth surface and consistent shape for the belt to rotate around.


### Challenges & Fixes

One major issue was the lack of flexibility in the initial cardboard belt, which caused poor motion and resistance. Switching to a masking tape belt resolved this by improving flexibility and reducing friction during rotation.

Another issue occurred when using a single motor. The belt would frequently get stuck or move inconsistently, likely due to uneven force distribution and friction along the system. To address this, I added a second motor on the opposite roller. This significantly improved motion, as both ends of the belt were now actively driven, reducing strain and preventing stalling.


### Design Modifications

To improve balance and stability, I positioned the two motors on alternate sides of the structure. This helped distribute weight more evenly and prevented the system from tipping to one side.

The use of pens as rollers was also an effective modification, providing a simple and functional alternative to manufactured components.


### Observations & Learning

This iteration highlighted the importance of material selection in dynamic systems. Flexibility, friction, and alignment all play a critical role in achieving smooth motion. It also demonstrated how distributing force (using two motors) can significantly improve system reliability.

Overall, the conveyor system now runs more consistently and provides a solid foundation for integrating the next stage of the project: the cam-driven sorting mechanism.

## Media
<img width="880" height="489" alt="20260422_175305" src="https://github.com/user-attachments/assets/f1925384-863b-4ce6-9931-41e02019f1f4" />
---

<img width="480" height="489" alt="20260422_193310" src="https://github.com/user-attachments/assets/c1c472d5-3faa-484d-8493-6f2691fa3c8b" />
---

<img width="480" height="489" alt="20260422_190811" src="https://github.com/user-attachments/assets/260ab123-ce02-493c-8227-3c539f1a8049" />

https://github.com/user-attachments/assets/5ffdfbdb-2c62-40de-a0e0-2bb919200b2f

https://github.com/user-attachments/assets/42762657-4d8d-46dd-ba18-a0dde389d785

https://github.com/user-attachments/assets/c2204953-a7e1-4848-960f-fef58c86c8c2


### Next Steps

- Refine belt alignment and tension  
- Begin designing and testing the cam mechanism  
- Integrate a sorting flap into the system  

## April 25, 2026 – Cam Mechanism Build & Integration

I began developing the cam mechanism to introduce timed interaction into the conveyor system. The goal was to convert the motor’s continuous rotational motion into a periodic movement that could push objects off the conveyor belt.

### Build Process

The cam was constructed using cardboard. Instead of adding a bump, I created an **eccentric cam** by cutting a circular disk with an off-center hole and mounting it onto a pen shaft. This offset caused the cam to rotate unevenly, generating a periodic displacement as it turned.

<img width="270" height="489" alt="20260430_200255" src="https://github.com/user-attachments/assets/27a1d86c-4a75-42f3-8fef-169300c7c66d" />

A follower and flap mechanism were then added. The flap was horizontally positioned next to the conveyor so that it could interact with objects as they passed. To ensure the flap returned to its original position after being pushed by the cam, I used a rubber band as a restoring force. This allowed the system to repeatedly cycle without requiring additional components.

<img width="480" height="489" alt="20260506_155050" src="https://github.com/user-attachments/assets/59671aa5-7578-48d3-ae84-4b8301b39fc9" />

--
<img width="480" height="489" alt="20260430_201742" src="https://github.com/user-attachments/assets/fe715c15-a127-4abb-a1ca-381303a5a3f3" />

--
<img width="480" height="489" alt="20260430_204214" src="https://github.com/user-attachments/assets/cc93ebc0-2583-4b63-b274-b260cc75d6d5" />


https://github.com/user-attachments/assets/9c0e6cae-d7ec-4930-bd0d-93abd9c53a8c

### Challenges & Fixes

One of the main challenges was adapting the mechanism to work **sideways**, so that the motion could push objects off the conveyor rather than simply move vertically. Initially, the cam motion did not effectively translate into lateral movement. This was resolved by adjusting the orientation of the follower and flap, ensuring that the cam’s displacement was redirected horizontally into the path of the moving objects.

Another challenge was ensuring the flap returned consistently after each cycle. Without a restoring force, the flap would remain displaced after being pushed. The addition of a rubber band solved this issue by pulling the flap back into its default position, allowing continuous operation.

### Observations & Learning

This stage demonstrated how rotational motion can be effectively converted into directional mechanical interaction using a simple cam system. The use of an eccentric cam provided a compact and reliable way to generate periodic motion without complex geometry.

I also learned that **orientation of motion is critical** — simply generating movement is not sufficient; it must be directed appropriately to achieve the intended interaction. Additionally, introducing a restoring force (rubber band) is essential for cyclic mechanisms to function continuously.

### Current Status

The cam mechanism is now functional and capable of producing timed lateral motion. It can be integrated with the conveyor system to begin testing object interaction and sorting behavior.


### Next Steps

- Integrate cam mechanism with the conveyor system  
- Test timing between conveyor movement and flap actuation  
- Adjust cam offset and flap position for more reliable interaction

## April 30, 2026 – System Integration & Timing Control

I integrated the cam mechanism with the conveyor system to create a fully functional, interactive setup. The objective was to synchronize the motion of the conveyor with the cam-driven flap so that objects could be selectively pushed off the belt.

### Integration Process

The cam mechanism was mounted alongside the conveyor, with the flap positioned at a point where objects pass consistently. Since both the conveyor and cam are motor-driven, the system naturally produces periodic interaction based on rotation.

To improve control over timing, I introduced a **manual switch** to control the cam mechanism independently. This allowed me to activate the cam at specific moments, ensuring that the flap would hit objects more reliably as they moved along the conveyor.

<img width="480" height="489" alt="Screenshot_20260506_164415_Gallery" src="https://github.com/user-attachments/assets/7a13c1cb-178c-4cfb-8e34-9627e1087ad9" />

https://github.com/user-attachments/assets/40f7b0a4-fdbd-4815-aa9f-78330305536b

### Challenges & Fixes

A key challenge during integration was achieving correct timing between the moving objects and the flap motion. When both systems ran continuously without control, the flap would often miss the objects. By adding a switch, I was able to manually control when the cam engages, improving accuracy.

Another issue was positioning. The flap needed to be precisely aligned with the conveyor path to ensure consistent interaction. This required adjusting both the height and horizontal placement of the mechanism.

### Observations & Learning

This stage demonstrated the importance of **timing and control in multi-mechanism systems**. While the cam provides periodic motion, introducing a switch allowed for more precise interaction, effectively bridging mechanical motion with user control.

I also observed that even with a working mechanism, system performance depends heavily on alignment and synchronization between components.

### Current Status

The system is now capable of:
- Moving objects along the conveyor  
- Activating the cam mechanism on demand  
- Successfully pushing objects off the belt  

This represents a complete working prototype of a **mechanical sorting system with controlled interaction**.

### Next Steps

- Refine timing for more consistent sorting  
- Improve structural stability and alignment  
- Document final system with images and video

## May 5, 2026 – Final Presentation & Reflection

### Project Overview

For my final project, I developed a **motor-driven mechanical sorting system** consisting of a conveyor belt and a cam-based interaction mechanism. Objects move along the conveyor and are selectively pushed off using a timed flap driven by an eccentric cam.

This project evolved from an initial Flappy Bird–inspired concept into a more focused **mechanism-based system**, allowing me to work effectively within the constraints of building individually at home.


### Adapting to Constraints

Due to the shift to remote work, I needed to redesign the project to match available tools and materials. Instead of attempting a complex multi-system build, I focused on creating a **compact, functional mechanical system** using:

- Cardboard for structure  
- Masking tape for the belt  
- Pens as rollers  
- DC motors for motion  
- A rubber band for restoring force  

This constraint-driven approach pushed me to prioritize **simplicity, functionality, and adaptability** in my design.


### Key Development Stages

1. **Conveyor Prototype**  
   - Initial cardboard belt failed due to lack of flexibility  
   - Replaced with masking tape loop → improved motion  
   - Added second motor to resolve stalling issues  


2. **Cam Mechanism**  
   - Built eccentric cam using off-center hole
   - Converted rotational motion into periodic movement  
   - Added rubber band to reset flap  

3. **System Integration**  
   - Combined conveyor and cam system  
   - Introduced a switch to manually control timing  
   - Achieved consistent object interaction  

### Challenges & Solutions

- **Belt rigidity** → Switched from cardboard to masking tape  
- **Motor stalling** → Added second motor for balanced drive  
- **Directional motion (sideways pushing)** → Reoriented flap and follower  
- **Lack of reset mechanism** → Introduced rubber band  
- **Timing mismatch** → Added switch for manual control  

Each challenge required either a **design modification** or a **material change**, reinforcing the importance of iteration.


### Lessons Learned

**Technical:**
- Material properties (flexibility, friction) directly affect system performance  
- Alignment and force distribution are critical in moving systems  
- Simple mechanisms (like cams) can replace complex control systems  

**Conceptual:**
- Constraints can guide better design decisions rather than limit them  
- Breaking a complex idea into smaller systems improves feasibility  
- Iteration is essential - initial designs rarely work as intended  

**Practical:**
- Readily available materials can be highly effective when used creatively  
- Mechanical timing can substitute for electronic control in certain systems  

### Final Reflection

This project successfully demonstrates a **complete mechanical system** where multiple components work together to produce controlled motion and interaction. 

What began as a game-inspired idea evolved into a **mechanism-focused design**, emphasizing problem-solving, adaptability, and engineering fundamentals. The process of building, testing, failing, and refining was the most valuable part of the project.
