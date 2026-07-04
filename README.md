🎓 AI-Powered Facial Recognition Attendance System
A contactless, automated biometric attendance tracking system built with Python, Flask, and OpenCV. This project eliminates manual roll calls and prevents proxy attendance by utilizing real-time deep learning facial encodings. It features an integrated liveness detection module (anti-spoofing) to reject fraudulent check-in attempts using photographs or digital screens.

✨ Key Features
Real-Time Verification:Instantly identifies registered students via a live webcam feed.
Anti-Spoofing Security: Calculates Laplacian variance to detect image sharpness, actively blocking flat 2D images or smartphone screens from tricking the scanner.
High-Performance RAM Caching: Loads facial embedding matrices directly into active memory on server startup, resulting in zero-latency matching.
Duplicate Prevention: Automatically isolates and flags duplicate check-ins for the same day.
Secure Admin Dashboard: A protected portal to register high-res student vectors, manage database profiles, and clear terminal history.
CSV Ledger Export: Download today's attendance logs directly into an Excel-ready CSV sheet.
Responsive UI: A clean, dark-mode terminal interface with interactive loading spinners and smart success-throttling.

🛠️ Tech Stack
Backend: Python, Flask
Database: SQLite (Built-in)
Computer Vision & AI: OpenCV (cv2), face_recognition, NumPy
Frontend: HTML5, CSS3, Vanilla JavaScript

📁 Project Structure
Plaintext
├── app.py                 # Core Flask server and facial logic engine
├── database.db            # SQLite database (auto-generates on first run)
├── static/
│   ├── css/
│   │   └── style.css      # Dark-mode dashboard styling and animations
│   └── profiles/          # Secure directory for downscaled student reference photos
└── templates/
    ├── index.html         # Live camera scanner and dynamic log table
    ├── register.html      # Secure onboarding portal for new biometric vectors
    └── admin_list.html    # Internal directory to view/delete records (generated in app.py)
    
🚀 Installation & Setup
1. Clone the repository:
Bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

3. Install required dependencies:
Make sure you have Python installed. Then, install the required libraries:
Bash
pip install flask opencv-python face-recognition numpy
(Note: face-recognition requires dlib and CMake to be installed on your system).

4. Run the application:
Bash
python app.py

5. Access the Terminal:
Open your web browser and navigate to:
http://localhost:5000

💻 How to Use:
Register a Student: Click "Register Student Profile" on the dashboard. Enter a name, upload a clear portrait photo, and click compile. The server will compress the image and extract the facial vector.
Scan Face: Return to the live dashboard. Look into the webcam. The system will detect your face, verify liveness, log the timestamp, and display a green success badge!
Admin Controls: Click "View Registered Students".
Default Credentials: Username: admin | Password: admin123 (Be sure to change this in app.py for production!)

🔮 Future Enhancements
SMS/Email notifications for daily absentees.
Cloud-based database synchronization.
Detailed graphical analytics for university administration.

Created as an academic mini-project.
