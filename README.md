# Garbage Classification Project

A computer vision project that uses deep learning models to classify different types of garbage/waste materials. This project implements both YOLO (You Only Look Once) object detection and Vision Transformer (ViT) classification approaches for real-time garbage classification.

## 🗂️ Project Overview

This project aims to classify waste materials into 6 different categories:

- **BIODEGRADABLE** - Organic waste that can decompose naturally
- **CARDBOARD** - Paper-based packaging materials
- **GLASS** - Glass containers and bottles
- **METAL** - Metal cans and containers
- **PAPER** - Paper waste and documents
- **PLASTIC** - Plastic containers and packaging

## 🚀 Features

- **Dual Model Approach**: Implements both YOLO object detection and Vision Transformer classification
- **Real-time Processing**: Live video classification using webcam feed
- **Multiple Output Formats**: Supports video recording with annotations
- **Pre-trained Models**: Includes fine-tuned models for immediate use
- **Comprehensive Training**: Multiple training trials with detailed metrics and visualizations

## 📁 Project Structure

```
Garbage_classification/
├── demo.ipynb                                    # Main demo notebook for real-time classification
├── Garbage_classification_yolo.ipynb            # YOLO training and evaluation notebook
├── Vit_Timm_Fine_Tuning_with_confusion_matrix_(vit_tiny_patch16_224).ipynb  # ViT training notebook
├── best_yolo.pt                                 # Best trained YOLO model weights
├── best_vit_model.pth                           # Best trained ViT model weights
├── output.avi                                   # Demo output video
├── output_vit.avi                               # ViT classification output video
├── output_yolo.avi                              # YOLO detection output video
├── yolo_resplit/                                # Dataset directory
│   ├── train/                                   # Training data
│   ├── valid/                                   # Validation data
│   ├── test/                                    # Test data
│   └── data.yaml                                # YOLO dataset configuration
├── Yolo_trials/                                 # Training trials and results
│   ├── trial_0/                                 # First training trial
│   ├── trial_1/                                 # Second training trial
│   ├── trial_2/                                 # Third training trial
│   └── trial_3/                                 # Fourth training trial
└── README.md                                    # This file
```

## 🛠️ Installation

### Prerequisites

- Python 3.8+
- CUDA-compatible GPU (recommended for training)
- Webcam (for real-time demo)

### Dependencies

Install the required packages:

```bash
pip install torch torchvision
pip install ultralytics
pip install timm
pip install opencv-python
pip install pillow
pip install numpy
pip install matplotlib
pip install seaborn
```

## 📊 Dataset

The project uses a custom garbage classification dataset with the following characteristics:

- **Source**: Roboflow Universe - Garbage Classification Dataset
- **Classes**: 6 waste categories
- **Format**: YOLO format with bounding box annotations
- **Split**: Train/Validation/Test sets
- **License**: CC BY 4.0

## 🤖 Models

### 1. YOLO Model

- **Architecture**: YOLOv8 (Ultralytics implementation)
- **Purpose**: Object detection with bounding boxes
- **Output**: Bounding box coordinates and class predictions
- **File**: `best_yolo.pt`

### 2. Vision Transformer (ViT)

- **Architecture**: ViT Tiny Patch16 224
- **Purpose**: Image classification
- **Input Size**: 224x224 pixels
- **Output**: Class probabilities
- **File**: `best_vit_model.pth`

## 🎯 Usage

### Real-time Classification Demo

1. **Open the demo notebook**:

   ```bash
   jupyter notebook demo.ipynb
   ```

2. **Choose your model**:

   - Set `mode = 'yolo'` for YOLO object detection
   - Set `mode = 'vit'` for Vision Transformer classification

3. **Run the demo**:
   - The notebook will access your webcam
   - Real-time classification results will be displayed
   - Press 'q' to quit the demo

### Model Training

#### YOLO Training

1. Open `Garbage_classification_yolo.ipynb`
2. Follow the training pipeline
3. Monitor training progress and metrics
4. Save the best model weights

#### ViT Training

1. Open `Vit_Timm_Fine_Tuning_with_confusion_matrix_(vit_tiny_patch16_224).ipynb`
2. Execute the fine-tuning process
3. View confusion matrix and evaluation metrics
4. Save the trained model

## 📈 Training Results

The project includes multiple training trials with comprehensive metrics:

### YOLO Trials

- **4 training trials** with different hyperparameters
- **Metrics tracked**: Precision, Recall, mAP, F1-Score
- **Visualizations**: Confusion matrices, PR curves, training plots
- **Best model**: Saved as `best_yolo.pt`

### ViT Training

- **Architecture**: ViT Tiny Patch16 224
- **Fine-tuning**: Transfer learning from pre-trained weights
- **Evaluation**: Confusion matrix analysis
- **Best model**: Saved as `best_vit_model.pth`

## 🎥 Output Videos

The project generates annotated videos showing classification results:

- `output.avi` - General demo output
- `output_vit.avi` - ViT classification results
- `output_yolo.avi` - YOLO detection results

## 🔧 Configuration

### YOLO Configuration

The YOLO model uses the configuration in `yolo_resplit/data.yaml`:

- Training/validation/test data paths
- Number of classes: 6
- Class names: ['BIODEGRADABLE', 'CARDBOARD', 'GLASS', 'METAL', 'PAPER', 'PLASTIC']

### ViT Configuration

- Input size: 224x224 pixels
- Normalization: Mean=[0.5, 0.5, 0.5], Std=[0.5, 0.5, 0.5]
- Number of classes: 6

## 📝 License

This project uses the Roboflow Garbage Classification dataset which is licensed under CC BY 4.0.

## 🤝 Contributing

Feel free to contribute to this project by:

- Improving model performance
- Adding new waste categories
- Enhancing the user interface
- Optimizing inference speed

## 📞 Contact

For questions or support, please open an issue in the repository.

---

**Note**: This project is designed for educational and research purposes. For production use, additional validation and testing is recommended.
