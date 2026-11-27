# Week 9: Technical Proof of Concept & Interaction Shift 

## 1. Initial Prototype: Mouse & Keyboard 
This week, we began setting up the initial technical architecture in TouchDesigner. To start, we used the most basic input devices:
* We used the `Mouse In CHOP` to capture the mouse’s X and Y coordinates to control the position of the beam on the screen.
* We used the `Keyboard In CHOP` to capture keystrokes (such as pressing the number “1”) to control the beam’s zoom level.
![image](https://git.arts.ac.uk/user-attachments/assets/a7446437-f469-4a26-87e0-ec2a932f4946)


## 2. Critical Reflection: The Problem of Anthropocentrism 
While testing the initial prototype, we immediately noticed a disconnect between the project’s concept and its interaction methods. Interacting with the system using a mouse and keyboard felt like operating a machine. This method of interaction conveyed a strong sense of precise, human control, which ran counter to our original principles of Distributed Agency and ecological fragility.

## 3. Technical Pivot: Introducing Computer Vision 
To break away from the mechanical feel of control and make the interaction more physical and organic, we decided to completely overhaul the input logic:
* **Abandoning traditional hardware triggers:** I removed all CHOP nodes related to the mouse and keyboard.
* **Integrating MediaPipe gesture tracking:** I incorporated a camera as a sensor and used MediaPipe to extract spatial keypoints from the user’s hands.
![屏幕截图 2026-03-12 212208](https://git.arts.ac.uk/user-attachments/assets/41add97d-9f64-498c-bbb6-976b88027189)
![屏幕截图 2026-03-12 204509](https://git.arts.ac.uk/user-attachments/assets/5f8dc4c9-ad2b-4c0a-b34c-c873cb3f12df)

**The Significance of the Technical Redesign:**
Through this shift, the audience’s physical presence directly became a variable influencing the ecosystem. More importantly, the introduction of MediaPipe gave us the ability to track the number of hands (Max Hands). This also laid the core technical foundation for our “single-player nurturing vs. multi-player destruction” interaction model.
![屏幕截图 2026-03-12 225028](https://git.arts.ac.uk/user-attachments/assets/f737c54e-419a-4502-8d7b-18b46719749b)
