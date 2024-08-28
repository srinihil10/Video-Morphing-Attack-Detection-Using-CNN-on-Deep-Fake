# **Video Morphing Attack Detection Using CNN**

## **Overview**
This project is focused on detecting video morphing attacks using a combination of Convolutional Neural Networks (CNN) and Long Short-Term Memory (LSTM) networks. Leveraging the ResNeXt-50 architecture, the model identifies anomalies in video frames to determine whether the video content is real or fake. The project also includes a web interface built with Flask for uploading videos and visualizing the detection results.

## **Features**
- **Morphing Attack Detection**: Utilizes a pre-trained ResNeXt-50 model coupled with an LSTM for sequence processing to detect morphing attacks in video frames.
- **Web Interface**: A Flask-based application that allows users to upload videos, view frame-by-frame analysis, and see the final prediction (Real or Fake) along with the confidence level.
- **Face Detection**: The project includes face detection within video frames, highlighting the detected faces and overlaying prediction labels.
- **Heatmap Generation**: Generates heatmaps to visualize areas in the video frames that contribute most to the model’s decision.

## **Project Structure**
```plaintext
Video-Morphing-Attack-Detection/
│
├── app.py                        # Flask application and model prediction logic
├── models/
│   └── model_90_acc_60_frames_final_data.pt # Pre-trained model weights
├── static/
│   ├── video/                    # Uploaded videos
│   ├── images/                   # Extracted frames and face images
│   └── model/
│       └── real_vs_fake/         # Dataset for real vs fake images
├── templates/
│   ├── first.html                # Home page template
│   ├── login.html                # Login page template
│   ├── chart.html                # Placeholder for chart visualizations
│   ├── uploader.html             # Video upload page template
│   └── results.html              # Results display page template
├── requirements.txt              # Required Python packages
└── README.md                     # Project documentation
```

## **Installation**
1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/Video-Morphing-Attack-Detection.git
   cd Video-Morphing-Attack-Detection
   ```
2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
3. **Download the pre-trained model**:
   - Place the pre-trained model file `model_90_acc_60_frames_final_data.pt` in the `models/` directory.

## **Usage**
1. **Run the Flask application**:
   ```bash
   python app.py
   ```
2. **Upload a video**:
   - Navigate to `http://127.0.0.1:5000` in your web browser.
   - Upload a video file to analyze its authenticity.
3. **View Results**:
   - The results page will display the prediction (Real or Fake) along with the confidence score.
   - It will also show extracted frames with labeled faces.

## **Dataset**
- The project uses a custom dataset of real and fake videos/images for training and evaluation.
- Ensure the dataset is placed in the `static/model/real_vs_fake/` directory, structured as follows:
  ```plaintext
  real_vs_fake/
  ├── train/
  ├── valid/
  └── test/
  ```

## **Model Details**
- **Architecture**: The model uses a ResNeXt-50 backbone for feature extraction followed by an LSTM for sequential processing.
- **Training**: The model was trained using a dataset of real and fake videos, with augmentation techniques applied to increase robustness.

## **Evaluation**
- **Test Accuracy**: The model achieved an accuracy of 90% on the test dataset.
- **Confusion Matrix**: A confusion matrix is generated to analyze the model’s performance, showcasing the True Positive, True Negative, False Positive, and False Negative rates.

## **Future Work**
- **Enhance Model Robustness**: Continue to improve the model by incorporating more diverse datasets and experimenting with different architectures.
- **Real-time Detection**: Implement real-time video stream processing for immediate detection.
- **Extended Visualization**: Add more detailed visualizations and analytics for deeper insights into the detection process.

## **Contributing**
Contributions are welcome! If you’d like to improve the project, please fork the repository and submit a pull request.

## **License**
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
