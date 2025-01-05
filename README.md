# LSB_ActionDetection

## Overview
**LSB_ActionDetection** is an advanced Python project that implements computer vision and machine learning techniques for real-time LSB detection in video sequences. The system combines MediaPipe's powerful pose estimation capabilities with deep learning models to achieve accurate action recognition.

## Key Features
- Real-time LSB
- Support for webcam input and video file processing
- Pre-trained model for immediate use
- Custom training pipeline for new actions
- Integration with MediaPipe for robust pose estimation
- Comprehensive logging system for model training analysis

## Repository Structure
```
LSB_ActionDetection/
├── Proyect.ipynb          # Main Jupyter notebook with detection code
├── action.h5              # Trained neural network model
├── MP_Data/               # MediaPipe-related data and training datasets
└── Logs/
    └── train/            # Training logs for performance analysis
```

## Prerequisites
### System Requirements
- Python 3.7 or higher
- CUDA-compatible GPU (recommended for optimal performance)
- Webcam (for real-time detection)

### Required Libraries
```
tensorflow >= 2.4.0
numpy >= 1.19.5
opencv-python >= 4.5.0
mediapipe >= 0.8.0
jupyter >= 1.0.0
```

## Installation Guide

1. Clone the repository:
   ```bash
   git clone https://github.com/joreir/LSB_ActionDetection.git
   cd LSB_ActionDetection
   ```

2. Create and activate a virtual environment (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage Instructions

### Quick Start
1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

2. Open `Proyect.ipynb` and follow the step-by-step instructions.

### Real-time Detection
```python
# Example code snippet for real-time detection
import cv2
from action_detector import ActionDetector

detector = ActionDetector(model_path='action.h5')
detector.start_webcam_detection()
```

## Training Custom Models

### Data Preparation
1. Collect video samples for each action you want to detect
2. Process videos and extract poses using MediaPipe:
   ```python
   from data_processor import process_videos
   process_videos(input_dir='raw_videos/', output_dir='MP_Data/')
   ```

### Training Process
1. Organize your processed data in the `MP_Data` directory
2. Configure training parameters in `Proyect.ipynb`
3. Execute the training cells
4. Monitor progress in `Logs/train/`

## Performance Optimization
- Use GPU acceleration when available
- Adjust model complexity based on your hardware capabilities
- Optimize input resolution for better performance
- Consider batch processing for offline analysis

## Troubleshooting
Common issues and solutions:
- **MediaPipe Installation Errors**: Ensure you have the latest pip version
- **CUDA Compatibility**: Check TensorFlow-CUDA compatibility matrix
- **Memory Issues**: Reduce batch size or input resolution

## Contributing
We welcome contributions! Please follow these steps:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Submit a pull request

### Development Guidelines
- Follow PEP 8 style guide
- Add unit tests for new features
- Update documentation as needed
- Maintain compatibility with Python 3.7+

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Authors
- **joreir** 
- **agus1np** 

## Acknowledgments
- Google MediaPipe team for their excellent pose estimation library
- TensorFlow community for deep learning frameworks
- Contributors and users of this project

## Citation
If you use this project in your research, please cite:
```
@software{LSB_ActionDetection,
  author = {joreir, agus1np},
  title = {LSB_ActionDetection: Real-time Human Action Detection},
  year = {2024},
  url = {https://github.com/joreir/LSB_ActionDetection}
}
```
