## Week #3

## Unity Task: Initial Tetris Prototype

### 1. Project Selection & Core Concept

**Game Choice Rationale:**
We selected *Tetris* as our foundational project for Week 3. We were drawn to its clear, well-defined rule set and its suitability for exploring core game development principles within the Unity engine. 

The game's inherent simplicity allowed us to focus entirely on fundamental programming mechanics—such as object spawning, grid-based movement, spatial collision, and array-based scoring—without being overwhelmed by overly complex gameplay systems. Most importantly, its straightforward directional controls provided a highly modular and robust digital foundation for our ultimate goal: integrating physical/tangible sensor inputs in the upcoming weeks.

### 2. Initial Unity Setup & Scene Construction

**Scene Foundation:**
We initiated a new hybrid 2D/3D Unity project and configured the main scene. A central "Frame" GameObject was created to mathematically and visually define the playfield boundaries. We utilized a series of 3D cube primitives to construct the left, right, and bottom constraints of the grid. 

To ensure clear visual feedback, a directional light was introduced, and the main orthographic camera was meticulously positioned to frame the playfield perfectly, ensuring players have an unobstructed view of the falling blocks.

![Scene Setup 1](https://git.arts.ac.uk/user-attachments/assets/cc711a59-a93f-48ec-81e3-ff80a7f089ce)

![Scene Setup 2](https://git.arts.ac.uk/user-attachments/assets/4029d778-b978-4bc5-8510-b12e1d00b7f5)

### 3. First Code Implementation & Core Mechanics

**Initial Scripting:**
A primary C# script, `Tetris.cs`, was authored and attached to the "Frame" GameObject to serve as the central game state manager. This script was responsible for maintaining the grid array, instantiating block prefabs, and listening for basic keyboard inputs (A/D/S/W) to simulate our intended physical interactions.

<img width="1090" alt="Script Screenshot" src="https://git.arts.ac.uk/user-attachments/assets/993f220d-8f8d-4e14-be25-c860a927188a" />

### 4. Technical Challenges & Iteration Reasoning

**Instability in the Initial Code:**
While the core systems were functional during our first pass, the initial implementation suffered from several critical stability and architectural issues that required immediate iteration:

* **Collision Detection Failures:** The initial grid-based collision logic was not entirely reliable. Blocks would occasionally clip through the boundary walls or overlap with existing locked blocks, particularly during rapid rotation inputs.
* **Performance Bottlenecks:** The initial line-clearing algorithm was unoptimized. It scanned the entire 2D array multiple times per frame, which began to cause noticeable frame drops as the playfield filled up with objects.
* **Early Serial Port Conflicts:** In preparation for our tangible controller, we drafted a proof-of-concept `SerialController` script. However, early tests showed it was not robust. It would frequently lock the Windows COM port, preventing other applications (like the Arduino IDE) from accessing it. Furthermore, the lack of strict data parsing meant that receiving invalid data streams could potentially crash the Unity editor.

### Conclusion

Week 3 was successfully dedicated to establishing our digital *Tetris* prototype in Unity. We solidified our game concept, constructed the initial environmental scene, and implemented the first iteration of our core game logic. Identifying early bugs in collision, performance, and basic serial communication has provided us with a clear technical roadmap as we prepare to transition into hardware sensor integration next week.
