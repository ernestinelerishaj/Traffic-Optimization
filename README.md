🚦 Smart Traffic Optimization & Accident Detection System
An AI-powered system that analyzes video input to detect traffic congestion, identify potential road accidents, and trigger emergency alerts via SMS using YOLOv8 and Twilio API. A live interface is powered by Gradio, making it accessible through a simple web app.

📌 Overview
This project combines Computer Vision and Communication APIs to simulate a real-world intelligent traffic system. It performs:

✅ Real-time vehicle detection from videos

📊 Dynamic traffic density analysis

🚨 Accident detection using collision inference from bounding boxes

📩 Emergency SMS alerts using Twilio

🚦 Traffic light signal generation based on vehicle load

Built with Ultralytics YOLOv8, OpenCV, and Gradio, this tool can aid in traffic surveillance, urban management, and emergency response systems.

🎯 Use Case
Ideal for:

Smart City applications

Urban Traffic Management Systems

Emergency Response & Alert Systems

AI-based Surveillance & Monitoring Projects

🖥️ Demo Screenshot

A sample video gets processed, traffic signals change dynamically, and SMS alerts are sent on collision detection.

🧠 Key Features
🚗 YOLOv8-based vehicle detection

🔢 Traffic density estimation with live feedback

🚨 Collision-based accident inference

📱 SMS alerts to registered emergency responders via Twilio

🎨 Traffic signal overlay (Red / Yellow / Green)

🖼️ Video annotation & download support

🛠️ Tech Stack
Layer	Tools Used
Detection	YOLOv8 (Ultralytics)
Video I/O	OpenCV
UI/Interface	Gradio
Messaging	Twilio SMS API
Language	Python 3.8+

📁 Folder Structure
perl
Copy
Edit
📂 traffic-alert-system/
├── app.py                # Main logic: Detection + UI
├── processed_output.mp4  # Output video (auto-generated)
├── README.md             # Project documentation
🚀 How to Run the Project
1. Install Dependencies
bash
Copy
Edit
pip install ultralytics gradio opencv-python twilio torch numpy
2. Set Up Twilio (SMS)
Replace these with your credentials in app.py:

python
Copy
Edit
TWILIO_SID = "your_sid"
TWILIO_AUTH_TOKEN = "your_auth_token"
TWILIO_PHONE_NUMBER = "your_twilio_number"
RECIPIENT_PHONE_NUMBER = "your_verified_phone"
⚠️ Twilio requires a verified number to receive SMS in trial mode.

3. Launch App
bash
Copy
Edit
python app.py
A Gradio interface will appear in your browser, allowing you to upload and analyze a video.

🎯 How It Works
Upload a traffic video (e.g., from a surveillance cam)

YOLOv8 detects vehicles frame by frame

Traffic density is calculated

If two vehicle boxes overlap → potential accident → SMS alert triggered

Frame is annotated with detection + traffic signal light

Downloadable video is generated with full visualization

✨ Sample Output
✅ “No accident detected.”

🚨 “Accident detected! Emergency response sent.” (via SMS)

📬 Alert Example
Twilio sends an SMS like:

Copy
Edit
🚨 Accident detected! Sending emergency response.
💻 Example Gradio Interface
python
Copy
Edit
iface = gr.Interface(
    fn=detect_accident_and_traffic,
    inputs=gr.Video(),
    outputs=[gr.Video(), gr.Textbox(label="Alert Message")],
    title="Accident & Traffic Detection System",
    description="Upload a video to detect accidents, measure traffic density, and control traffic signals."
)
