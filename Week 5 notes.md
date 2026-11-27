## Week #5


## Integration Task: The Hardware-Software Bottleneck

### 1. Game Logic Validation via Keyboard Mock-up
Before attempting the final Arduino-Unity integration, we implemented a keyboard-based fallback system (using A / D keys) in Unity to simulate the left/right gesture inputs. This step was crucial for playtesting to validate the smoothness of the block movement and tuning the game logic independently of the hardware. 

### 2. Integration Challenges: The Arduino-Unity Bridge

https://git.arts.ac.uk/user-attachments/assets/4d0f37f9-bff4-4da7-87b8-5c00c1d66e99

###### Video 2: Initial integration attempts resulted in hardware noise but no digital response in Unity.

With the Arduino functioning perfectly on its own, we attempted to bridge the hardware to our Unity engine. The goal was to replace the A/D keyboard inputs with the live `"L"` and `"R"` serial data.

However, we encountered a significant bottleneck. While Unity successfully detected the connected Arduino board (e.g., the COM port initialized without crashing), it failed to reliably parse the incoming gesture data. 
![a5f96c148c4aa6d9c0072d9a9bb27b5](https://git.arts.ac.uk/user-attachments/assets/b347a834-8e64-4941-8ab7-73451aa3d5b7)


We observed that the `TX` LED on the Arduino board flashed during gestures, indicating data was leaving the board, but the Tetris blocks in Unity remained completely unresponsive.
![image](https://git.arts.ac.uk/user-attachments/assets/8a371b59-bb78-4869-97bb-7d7913bc8847)

### 3. Identifying the Issues
We encountered a classic serial port contention and parsing issue. The data stream was either lost in the buffer or rejected due to parsing mismatches (e.g., newline character issues or Windows COM port exclusive-access conflicts). Despite multiple attempts to adjust baud rates and basic reading logic (`ReadLine` vs `ReadExisting`), the physical gestures did not trigger digital movement.
![32fe5adf5ed7d073cb694c5cdc150f2](https://git.arts.ac.uk/user-attachments/assets/c0e8192d-b97e-40c1-a0d2-fa857e315a50)


### 4. Current Solution & Next Steps
Due to time constraints and the requirement to present a playable prototype for this week's review, we utilized our keyboard mock-up as a temporary fallback mechanism. 

This challenge beautifully highlights the technical gap between isolated hardware prototyping and real-time engine integration. In the upcoming Sprint 1, our primary engineering objective is to deeply debug this serial communication pipeline—specifically looking into native USB behaviors (`DtrEnable` configurations) and buffer data extraction—so that the tangible gesture input can fully replace the keyboard constraints.
