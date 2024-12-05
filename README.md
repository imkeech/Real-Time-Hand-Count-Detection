# Hand Count: Real-Time Finger Detection Using Computer Vision

## **Objective**
To develop a system that detects and counts the number of fingers shown by a user in real time using computer vision techniques.

## **Key Components**

### **Libraries Used**
- **cv2 (OpenCV):** For video capture and frame processing.
- **mediapipe:** To detect and track hand landmarks.
- **Other Python Libraries:** Standard utility libraries.

### **Functionality**
- Captures video from a webcam and processes each frame.
- Uses the MediaPipe library to detect hands and identify key landmarks.
- Counts the number of fingers extended based on the relative positions of the finger tips and joints.
- Differentiates between left and right hands for more accurate thumb detection.
- Displays the total count of fingers detected on the screen in real time.

## **Algorithm Highlights**
- For each hand detected, checks if the fingertips are above the corresponding joints to determine if a finger is extended.
- Handles thumb detection differently based on whether the hand is left or right.
- Maintains previous finger counts to display contextual information.

## **Visualization**
- Annotates the video feed with detected hand landmarks and connections.
- Displays the total finger count and a breakdown of previous counts when hands are not detected.

## **Real-Time Interaction**
- The application runs in a loop, continuously updating the video frame until the user stops it (e.g., by pressing Esc).

## **Fallback Feature**
### **When No Hand is Detected**
- **Fallback Behavior**: If there is no hand visible in the frame, the system checks the two most recently recorded finger counts:
  - `previous_count`: The last detected finger count.
  - `previous_previous_count`: The finger count detected before the last one.
- **Summing the Counts**: When a hand is not detected:
  - It adds these two values (`previous_count` + `previous_previous_count`).
  - Displays the result as the "total fingers."

### **Why This Feature?**
- Provides continuity and a creative fallback output when the system loses input (i.e., no hands in the frame).
- Creates a fun and dynamic interaction for users to explore how the system combines counts when hands leave the screen.

### **Example Scenario**
1. User shows **3 fingers**: The program stores `3` as `previous_count`.
2. User then shows **2 fingers**: The program stores `2` as `previous_previous_count` and updates `previous_count` to `3`.
3. User removes their hand from the frame:
   - The system displays **5** (`3 + 2`) as the total finger count.

## **Applications**
- Gesture recognition.
- Human-computer interaction.
- Educational or recreational tools for recognizing and displaying finger-based gestures.


