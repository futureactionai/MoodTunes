# MoodTunes 🎧😊

**MoodTunes** is a real-time facial emotion detection system integrated with music mood mapping. Using a webcam, the system detects the user's face, classifies their emotion with a deep learning model, and maps the emotion into generalized categories that can be used to personalize music selection.

---

## 🚀 Features

- **Real-time face detection** using Haar Cascades (OpenCV)
- **Emotion classification** using a pretrained CNN model (7 emotion classes)
- **Mood mapping** from 7 emotions into 3 general music mood categories
- **Modular design** with AugeLab Studio custom blocks
- **Extensible architecture** for adding music recommendation and playback in future versions

---

## 🎯 Project Goals

- Provide music recommendations tailored to the user's emotional state
- Create a working prototype (MVP) for drivers or general users
- Deliver a fast, real-time solution using a no-code/low-code approach with AugeLab Studio

---

## 📦 Folder Structure
```
MoodTunes/
├── model.pmod                         # AugeLab Studio workflow file
├── emotion_detection_model.h5         # Pretrained emotion classification model
└── README.md
```

**Additional Required File:**
- `haarcascade_frontalface_default.xml` must be placed in:
```
  C:\Users\[YourUsername]\AppData\Roaming\AugeLab Studio\marketplace\custom_blocks\haarcascade_frontalface_default.xml
```

---

## ⚙️ How to Install and Run

### 1. Prerequisites

- **AugeLab Studio** (ensure it's installed on your system)
- Python 3.7+

### 2. Install Required Packages

Open **AugeLab Studio** and install the required package:

1. Go to **Tools** → **Import Package Window**
2. Install `opencv-python`
3. TensorFlow will be installed automatically

---

### 3. Download the Pretrained Model

The emotion detection model can be downloaded from Hugging Face:

🔗 **[Download the model here](https://huggingface.co/Hammad712/Emotion_Detection/blob/585ef74e422260af318c2078c7718d9cd94da229/emotion_detection_model.h5)**

**Manual Download Steps:**
1. Click the link above
2. Click the **download** icon on the Hugging Face page
3. Save the file as `emotion_detection_model.h5`
4. Place it in the same directory as `model.pmod`

Alternatively, you can use `wget` or `curl`:
```bash
wget https://huggingface.co/Hammad712/Emotion_Detection/resolve/585ef74e422260af318c2078c7718d9cd94da229/emotion_detection_model.h5 -O emotion_detection_model.h5
```

---

### 4. Place the Haar Cascade File

Download `haarcascade_frontalface_default.xml` (included with OpenCV) and place it in:
```
C:\Users\[YourUsername]\AppData\Roaming\AugeLab Studio\marketplace\custom_blocks\haarcascade_frontalface_default.xml
```

Replace `[YourUsername]` with your actual Windows username.

---

### 5. Run the System

1. Open **AugeLab Studio**
2. Load the `model.pmod` workflow file
3. Ensure your webcam is connected
4. Run the workflow to start real-time emotion detection

---

## 🔍 Technical Details

### Emotion Detection Model
- **Architecture:** Convolutional Neural Network (CNN)
- **Input:** 48x48 grayscale images
- **Output:** 7 emotion classes
  - `angry`
  - `disgust`
  - `fear`
  - `happy`
  - `sad`
  - `surprise`
  - `neutral`
- **Source:** Model downloaded from [Hugging Face](https://huggingface.co/Hammad712/Emotion_Detection)

### Mood Mapping Logic

The 7 emotions are mapped into 3 generalized mood categories for music selection:

| Detected Emotion | Mood Category | Music Genre Suggestion |
|------------------|---------------|------------------------|
| `happy`, `surprise` | **Happy** | Upbeat, Pop, Dance |
| `neutral` | **Neutral** | Ambient, Chill, Acoustic |
| `angry`, `disgust`, `fear`, `sad` | **Stressed/Sad** | Calm, Classical, Relaxing |

---

## 📊 System Workflow
```
Camera Feed → Face Detection (Haar Cascade)
                    ↓
            Face Cropping (48x48)
                    ↓
        Emotion Classification (CNN Model)
                    ↓
            Mood Category Mapping
                    ↓
        Music Recommendation (Future Feature)
```

---

## ⚠️ Limitations & Notes

- The model is **pretrained** and downloaded from Hugging Face (not custom-trained for this specific use case)
- Emotion classification accuracy may vary based on:
  - Lighting conditions
  - Face angle and position
  - Camera quality
- **Music playback and recommendation system** is not yet implemented (planned for future versions)
- The system is designed as a proof-of-concept (MVP) and may require optimization for production use

---

## 🛠️ Future Enhancements

- [ ] Integrate Spotify/YouTube API for automatic music playback
- [ ] Add user preference learning for personalized recommendations
- [ ] Improve model accuracy with fine-tuning on diverse datasets
- [ ] Support for multiple face detection simultaneously
- [ ] Mobile app version

---

## 📄 License

This project is open-source and available under the MIT License.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an Issue for bugs and feature requests.

---

## 📧 Contact

For questions or suggestions, please reach out via [futureactionai@gmail.com] or open an issue on GitHub.

---

**Enjoy MoodTunes! 🎵😊**
