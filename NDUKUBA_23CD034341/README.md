😃 Emotion Detection Web Application
🧠 Overview

Emotion Detection Web App is a Flask-based machine learning project that identifies human emotions from facial images using a pretrained deep learning model retrained on the FER-2013 dataset.
It combines computer vision, transfer learning, and a simple web interface to perform real-time facial emotion recognition, displaying the detected emotion and confidence level.

The project demonstrates how an AI model can be fine-tuned for emotion classification and integrated into a deployable web application hosted on Render.

🚀 Features

🖼️ Upload or capture images directly through the browser

⚡ Real-time prediction of facial emotions with confidence scores

🧠 Retrained deep learning model (MobileNetV2 fine-tuned on FER-2013)

🌐 Flask backend API with /predict endpoint for easy integration

💻 Minimal responsive interface (HTML, CSS, and JavaScript)

☁️ Deployed via GitHub → Render for public access

🔄 Retrainable model via Google Colab notebook using the FER-2013 dataset

🧩 Tech Stack
Category	Technologies Used
Backend	Flask (Python)
Frontend	HTML, CSS, JavaScript
Machine Learning	TensorFlow / Keras
Dataset	FER-2013 (Facial Expression Recognition Dataset from Kaggle)
Deployment	Render (via GitHub repo)
Training Environment	Google Colab
🗂️ Project Structure
NDUKUBA_23CD034341_EMOTION_APP/
│
├── app.py                     # Flask backend server
├── model.py                   # Script used to retrain the model (in Colab or locally)
├── model/
│   └── emotion_model.h5       # Trained Keras model weights
├── templates/
│   └── index.html             # Minimal web interface
├── static/
│   └── style.css              # Basic CSS styling
├── requirements.txt           # Dependencies
├── README.md
└── web_address.txt            # Deployed Render URL

⚙️ Installation & Setup
1️⃣ Create and Activate a Virtual Environment
python -m venv venv


Activate it:

Windows:

venv\Scripts\activate


macOS/Linux:

source venv/bin/activate

2️⃣ Install Dependencies
pip install -r requirements.txt


Ensure that your Python version is 3.10 or 3.11 (TensorFlow 2.20 compatible).

3️⃣ Run the Application
python app.py


Then open your browser and go to:
👉 http://127.0.0.1:5000

🔍 API Endpoint
POST /predict
Parameter	Type	Description
image	Base64 string	Image data captured or uploaded via frontend

Example Response:

{
  "emotion": "happy",
  "confidence": 0.94
}

☁️ Deployment Guide (GitHub → Render)

Push your entire project folder to GitHub:

git init
git add .
git commit -m "Initial commit - Emotion Detection Web App"
git branch -M main
git remote add origin https://github.com/YOURUSERNAME/NDUKUBA_23CD034341_EMOTION_APP.git
git push -u origin main


Log in to Render.com
 → New → Web Service

Connect your GitHub repository

Choose:

Environment: Python 3

Build command:

pip install -r requirements.txt


Start command:

gunicorn app:app


Deploy — after build completes, Render provides your public web URL.

Copy that URL into a text file named web_address.txt and include it in your zipped submission folder.

📊 Model Information

Base model: Pretrained MobileNetV2 (from Keras Applications)

Dataset used for retraining: FER-2013 Facial Expression Dataset

Classes: angry, disgust, fear, happy, sad, surprise, neutral

Training environment: Google Colab (GPU enabled)

Output model: emotion_model.h5

The retrained model is saved locally and used by Flask for inference.

🔒 Security & Good Practices

❌ Do not commit large .h5 or dataset files to public GitHub repositories

🚫 Avoid uploading real user photos — use sample test images

🔐 Store sensitive keys or config separately if you extend the project

📦 Use Git LFS if your model exceeds 100 MB

🌱 Future Improvements

📸 Add live webcam feed for real-time video predictions

🎛️ Support multiple pretrained model choices (VGG16, ResNet, etc.)

📈 Include confidence graphs or bar charts for visual comparison

🧠 Add emotion intensity scaling (e.g., “slightly happy”, “very angry”)

🐳 Dockerize for easier multi-platform deployment

🧾 License

This project is provided for educational purposes as part of a Machine Learning coursework.
You are free to modify and improve it for learning and research use.

🙌 Credits

Developed by Sharon Ndukuba (23CD034341)
Supervised by Department of Computer & Information Sciences, Covenant University

Based on open-source pretrained CNN models and FER-2013 dataset from Kaggle.
Inspired by modern emotion recognition architectures using transfer learning.