
# Wave! 

An AI-powered web platform for learning American Sign Language (ASL), with instant feedback on your signing through your webcam.


https://github.com/user-attachments/assets/471fa2e7-34dc-4d91-9500-1e6ea1e35113




## Lesson Experience
https://github.com/user-attachments/assets/f057e0d4-b13e-4fbd-a780-7a0cb945e5b9

Each lesson follows a structured sequence to guide you through learning and practicing a sign:

1. **Video Tutorial** – The lesson begins with a video demonstration of the target ASL sign.
3. **Practice Setup** – After watching, click the **Practice Now** button.
4. **Camera Activation** – MediaPipe activates and begins tracking your landmarks.
5. **Recording**
   - Click **Record**.
   - A 3-second countdown appears.
   - When the countdown ends, perform the sign.
   - The system records your landmark data.
6. **Feedback** – The recorded sign is classified by the AI model, and you see whether it was **correct** or **incorrect**.

## The Models

ASL signs vary in complexity, so recognition is split into two models:

- **Static model** – For signs with no motion, like letters and numbers. It takes the 21 hand landmarks from MediaPipe Hands in a single frame and classifies them with a lightweight feedforward neural network.
<img width="684" height="374" alt="image" src="https://github.com/user-attachments/assets/8c2b836a-dd3c-4162-9bfe-98a1f66d096d" />

- **Dynamic model** – For signs that involve movement, facial expressions, or body posture. It takes 30-frame sequences of pose, face, and hand landmarks from MediaPipe Holistic and classifies them with an LSTM network.
<img width="1054" height="466" alt="image" src="https://github.com/user-attachments/assets/811ed404-ee6f-4e83-99da-1c9d15e5da14" />


**Both models were built in TensorFlow and exported to ONNX for deployment.**

## Tech Stack

- **Frontend:** React, Vite, React Router, Axios, MediaPipe (Hands & Holistic)
- **Backend:** Node.js, Express.js, cookie-based authentication
- **Database:** MongoDB Atlas
- **AI:** TensorFlow, ONNX models served via REST API
- **Tools:** GitHub, ESLint
