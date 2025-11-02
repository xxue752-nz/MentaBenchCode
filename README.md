# Menta: On-Device Mental Health Monitoring System

<div align="center">

![Menta Workflow](images/workflow.jpg)

**Privacy-Preserving Mental Health Assessment Using Small Language Models on Mobile Devices**

</div>

## 📋 Overview

Menta is an innovative on-device mental health monitoring system that leverages Small Language Models (SLMs) to analyze social media content for mental health indicators, including depression, stress, and suicidal ideation. The system operates entirely on-device to ensure user privacy and data security.

### Key Features

- 🔒 **Privacy-First**: All processing happens on-device, no data leaves your device
- 📱 **Mobile-Optimized**: Designed specifically for iOS devices with efficient resource usage
- 🧠 **Multi-Dimensional Analysis**: Evaluates depression, stress, and suicidal thoughts
- ⚡ **Real-Time Monitoring**: Provides immediate in-situ predictions
- 🎯 **High Accuracy**: Fine-tuned SLMs for mental health assessment tasks

## 🗂️ Project Structure

This repository contains two main components:

### 1. [`Menta_deployment/`](./Menta_deployment) - Mobile Application & Model Deployment

This folder contains the iOS application for deploying the mental health monitoring model on mobile devices.

**Contents:**
- **Menta/**: SwiftUI-based iOS application
  - Mental health prediction interface
  - Real-time social media post analysis
  - Privacy-preserving data handling
  - Batch processing capabilities
- **llamacpp-framework/**: llama.cpp framework compiled for iOS
  - Optimized for Apple Silicon and ARM devices
  - XCFramework for multi-platform support (iOS, tvOS, visionOS)
  - Pre-built binaries for quick integration
- **Menta.xcodeproj/**: Xcode project configuration

**Key Features:**
- On-device AI screening
- Lightweight storage with no cloud dependency
- Real-time mental health report generation
- Resource monitoring (CPU, RAM, battery)
- Safety alert system for high-risk cases

### 2. [`Menta_pretraining_code/`](./Menta_pretraining_code) - Model Training & Fine-tuning

This folder contains all the code and datasets for training and fine-tuning the Menta model.

**Contents:**
- **Training Scripts**:
  - `Menta_lora_multitask_weighted_optimized.py`: Multi-task learning with LoRA fine-tuning
  - `Menta_lora_config1_logprob.py`: LoRA configuration with log probability implementation
  - `improved_logprob_implementation.py`: Enhanced log probability calculations
- **Datasets**:
  - Reddit depression dataset
  - Stress analysis dataset (Dreaddit)
  - Suicidal ideation dataset (SDCNL)
  - Multi-user mental health posts
- **Configuration**:
  - `config.yaml`: Training hyperparameters and model settings
  - `requirements.txt`: Python dependencies

**Training Approach:**
- Multi-task learning for depression, stress, and suicidal ideation detection
- LoRA (Low-Rank Adaptation) for efficient fine-tuning
- Weighted loss functions for balanced learning
- Log probability analysis for confidence estimation

## 🚀 Quick Start

### For Model Deployment (iOS)

1. Navigate to the deployment folder:
```bash
cd Menta_deployment
```

2. Open the Xcode project:
```bash
open Menta.xcodeproj
```

3. Build and run on your iOS device or simulator

For detailed deployment instructions, see [`Menta_deployment/SETUP.md`](./Menta_deployment/SETUP.md)

### For Model Training

1. Navigate to the training folder:
```bash
cd Menta_pretraining_code
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Configure training parameters in `config.yaml`

4. Start training:
```bash
python Menta_lora_multitask_weighted_optimized.py
```

For detailed training instructions, see [`Menta_pretraining_code/README.md`](./Menta_pretraining_code/README.md)

## 🔬 How It Works

The Menta system follows a comprehensive workflow:

1. **User Browsing**: Monitors social media interactions where mental health states may manifest
2. **Data Cache**: Stores data locally with lightweight, privacy-preserving storage
3. **Social Media Post Monitoring**: 
   - Applies on-device AI screening
   - Adheres to privacy and data minimization principles
   - Identifies suicidal ideation and other mental health indicators
4. **In-situ Prediction**: Generates multi-dimensional mental health reports including:
   - Risk level assessment
   - Depression indicators
   - Stress levels
   - Suicidal thought detection
   - Confidence scores
5. **Log Saving**: Records metadata, system logs, and resource usage for performance monitoring

## 🛡️ Privacy & Security

- **100% On-Device Processing**: No data transmitted to external servers
- **Data Minimization**: Only essential data is temporarily cached locally
- **No Cloud Storage**: All processing and storage occurs on the user's device
- **Privacy by Design**: Built with privacy as the core principle

## 📊 Performance

The system is optimized for mobile devices with:
- Efficient CPU and RAM usage
- Low battery consumption
- Fast inference times
- Real-time prediction capabilities

## 🔧 Technical Stack

### Deployment
- **Language**: Swift, SwiftUI
- **Platform**: iOS 15.0+
- **ML Framework**: llama.cpp (C++ inference)
- **Model Format**: GGUF (quantized models)

### Training
- **Language**: Python 3.8+
- **Frameworks**: PyTorch, Transformers
- **Techniques**: LoRA fine-tuning, multi-task learning
- **Base Models**: Small Language Models (SLMs)

## 📝 Citation

If you use Menta in your research, please cite:

```bibtex
@software{menta2024,
  title={Menta: On-Device Mental Health Monitoring with Small Language Models},
  author={Your Team},
  year={2024},
  url={https://github.com/xxue752-nz/Menta}
}
```

## 📄 License

This project is licensed under the terms specified in the [LICENSE](./LICENSE) file.

## 🤝 Contributing

Contributions are welcome! Please read our contributing guidelines before submitting pull requests.

## ⚠️ Disclaimer

Menta is a research tool and should not be used as a substitute for professional mental health diagnosis or treatment. If you or someone you know is experiencing mental health issues or suicidal thoughts, please contact a mental health professional or crisis helpline immediately.

**Crisis Resources:**
- National Suicide Prevention Lifeline (US): 1-800-273-8255
- Crisis Text Line (US): Text HOME to 741741
- International Association for Suicide Prevention: https://www.iasp.info/resources/Crisis_Centres/

## 📧 Contact

For questions, issues, or collaborations, please open an issue on GitHub or contact the maintainers.

---

<div align="center">
Made with ❤️ for mental health awareness and privacy-preserving AI
</div>

