# Speech Emotion Recognition
This project explores the use of deep neural network architectures to recognize emotions from speech, using the RAVDESS dataset. The main focus is on comparing the performance of CNN, LSTM, and pre-trained VGG16 models, along with analyzing the effect of data augmentation techniques.

## 🗂️ Dataset

**RAVDESS** – Ryerson Audio-Visual Database of Emotional Speech and Song  
- 8 emotions: neutral, happy, sad, angry, fearful, disgust, surprised, calm  
- 24 actors (12 male, 12 female)  
- 1,440 audio files of spoken phrases

## 🔍 Feature Extraction

From each audio file, the following features were extracted:

- **Mel spectrogram**  
- **MFCC (Mel-Frequency Cepstral Coefficients)**  
- **RMS (Root Mean Square Energy)**  
- **ZCR (Zero Crossing Rate)**

## 🎛️ Data Augmentation Techniques

Applied only to the training data:

- Speed and pitch modification  
- Noise addition (background sounds)  
- Time-stretching (length change without pitch shift)

## 🧠 Implemented Models

### 📌 CNN (Convolutional Neural Network)
- 1D convolution with 64/128 filters  
- MaxPooling and Dropout layers  
- Dense layers with ReLU/Sigmoid activations  
- **Accuracy: up to 65% (with MFCC and augmentation)**
### 📌 LSTM (Long Short-Term Memory)
- 3 LSTM layers with 256, 128, and 32 units  
- Dropout, recurrent dropout, and kernel regularization  
- Final Softmax output for 8 emotion classes  
- **Accuracy: ~68%**
### 📌 VGG16 (Transfer Learning)
- Pretrained on ImageNet  
- Base model frozen; custom Dense layers added  
- Input: mel spectrogram images  
- **Highest accuracy: 70%**
