This project is an AI-powered adaptive learning system that uses a Brain–Computer Interface (BCI) to improve learning experiences for students, especially those with ADHD, dyslexia, and autism.
Instead of assuming how a student is learning, we measure their attention in real-time using EEG signals and adapt the content accordingly.EEG signals are captured using a wearable headset placed on the student’s head during learning sessions. The headset records brain activity in real time, which is then amplified and sent to the system for processing and attention detection

How It Works (End-to-End Workflow)
1. Signal Acquisition
EEG electrodes are used to capture brain activity from the scalp.
These signals are very weak, so they are amplified using circuits (like AD620/INA114) and sent to a microcontroller (Arduino).


2. Preprocessing:
The raw EEG signals contain noise, so we process them by:
i)Filtering unwanted noise
ii)Extracting important frequency bands:
iii)Alpha waves (8–13 Hz) → relaxation / distraction
iv)Beta waves (13–30 Hz) → focus / attention


3. Attention Detection (ML / Logic)
Using extracted features, the system determines whether the student is:
Focused → high beta, low alpha
Distracted → high alpha, low beta
This can be done using simple heuristics or machine learning models.

4. Adaptive Learning
Based on the detected attention state, the system dynamically changes how content is delivered:
High attention → continue current content
Medium attention → switch to audio-based explanation
Low attention → introduce interactive quizzes or engaging formats
This makes learning more personalized and effective.

5. Feedback & Visualization
The system provides dashboards for both students and teachers:
i)Student Dashboard:
Attention percentage (live gauge)
EEG signal visualization (charts)
Adaptive content section
Session logs (focus/distraction tracking)

ii)Teacher Dashboard:
Class-wise attention overview
Performance insights
Content effectiveness analysis
Exportable reports
Frontend Implementation
The frontend is built using:
React.js → component-based UI
Tailwind CSS → clean and responsive styling
Recharts → real-time data visualization
Framer Motion → smooth animations

Currently, EEG data is simulated using a custom hook (useDemoStream) to demonstrate real-time behavior.

6. Deployment
The frontend is deployed on Netlify, making it accessible through a live URL without local setup.
 Accessibility & Neurodiverse Design
 
This project focuses heavily on accessibility and comfort:
Custom color themes (cream, pastel, low-glare)
Dyslexia-friendly font support
Focus/Reader mode (reduced distractions)
Text-to-speech support
Reduced animations option
Clear, simple UI layout
