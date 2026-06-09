# Alien_vs_Predator_Image-Classifier
A deep learning project that classifies images as Alien or Predator using Transfer Learning with ResNet50 and TensorFlow/Keras.
Built as a beginner deep learning project to learn Transfer Learning, data augmentation, and model inference.


🚀 Tech Stack
Python
TensorFlow 
Keras 
ResNet50 
OpenCV 
NumPy 
Matplotlib

🧠 Model Architecture
Pretrained ResNet50 (frozen) is used as a feature extractor, with a custom classification head on top:
Input Image (224×224×3)
        ↓
ResNet50 — pretrained on ImageNet (layers frozen)
        ↓
GlobalAveragePooling2D
        ↓
Dense(2, softmax)
        ↓
  alien | predator

📊 Dataset

Source: Alien vs Predator Images — Kaggle
Classes: alien, predator
Split: train/ and validation/ folders
https://www.kaggle.com/datasets/pmigdal/alien-vs-predator-images

⚙️ Training Details
ComponentDetailBase ModelResNet50 (ImageNet weights, frozen)OptimizerAdam (lr=0.001)LossCategorical CrossentropyInput Size224 × 224 × 3Epochs10AugmentationShear, Zoom, Horizontal Flip
Callbacks used during training:
ModelCheckpoint — saves best model by val_accuracy
EarlyStopping — stops if no improvement for 30 epochs
ReduceLROnPlateau — reduces LR by 10x on plateau


🖥️ How to Run
bash# 1. Clone the repo
git clone https://github.com/yourusername/alien-vs-predator-classifier.git
cd alien-vs-predator-classifier

# 2. Install dependencies
pip install -r requirements.txt

# 3. Open notebook
jupyter notebook alien_vs_predator_classifier.ipynb

📈 Results
MetricValueBest Val Accuracy(add your value)Epochs Trained10Model Format.keras

📁 Project Structure
alien-vs-predator-classifier/
├── alien_vs_predator_classifier.ipynb   # Main notebook
├── requirements.txt                      # Dependencies
└── README.md
