# Visual Question Answering (VQA) Project

## Overview
This project implements a **Visual Question Answering (VQA)** system that combines **computer vision** and **natural language processing** to answer questions about images. The model integrates a **ResNet-based vision model** for image feature extraction and a **BERT-based text model** for question understanding, using a **late fusion mechanism** to predict answers.

## Key Features
- **Multimodal Learning**: Combines CNNs (ResNet) and Transformers (BERT) for joint image-text understanding.
- **Late Fusion Architecture**: Independently processes image and text features before fusion.
- **COCO-VQA Dataset**: Trained on a subset of the COCO-VQA v2.0 dataset (250K+ images, 1M+ questions).
- **Modular Design**: Easy to experiment with different vision/text backbones.

## Results
| Model Component       | Validation Accuracy |
|-----------------------|---------------------|
| ResNet34 (Vision)     | 20.41%             |
| ResNet50 (Vision)     | 19.34%             |
| BERT (Text)           | 40.48%             |
| **Full VQA Model**    | **43.73%**         |

Test Accuracy: **43.46%**

## Repository Structure
```
├── data/                    # Preprocessed datasets
├── models/                  # Saved model checkpoints
├── notebooks/               # Jupyter notebooks for exploration
├── src/
│   ├── data_processing.py   # Dataset loading and preprocessing
│   ├── vision_model.py      # ResNet implementations
│   ├── text_model.py        # BERT question processing
│   ├── vqa_model.py         # Multimodal fusion architecture
│   └── train.py             # Training pipeline
├── reports/                 # Generated reports/figures
├── README.md                # This file
└── requirements.txt         # Python dependencies
```

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/visual-question-answering.git
   cd visual-question-answering
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. **Training**:
   ```bash
   python src/train.py --model vqa --epochs 10 --batch_size 16
   ```

2. **Inference** (example):
   ```python
   from src.vqa_model import VQAModel
   model = VQAModel.load_from_checkpoint("models/best_vqa.ckpt")
   answer = model.predict(image="sample.jpg", question="What color is the car?")
   ```

## Dataset
The model uses the **COCO-VQA v2.0** dataset. Due to size constraints, this implementation works with a 20% subset. To use the full dataset:

1. Download from [Visual QA](https://visualqa.org/download.html)
2. Place in `data/raw/`
3. Run preprocessing:
   ```bash
   python src/data_processing.py --full_dataset
   ```

## Future Improvements
- Implement attention mechanisms for better feature fusion
- Experiment with larger vision backbones (ViT, EfficientNet)
- Incorporate answer generation (beyond classification)
- Deploy as a web service with Gradio/Streamlit

## Citation
If you use this work, please cite:
```
@misc{vqa_project_2024,
  author = {Bouhafa Taha and Loubaba Malki L'hlaibi},
  title = {Visual Question Answering with Multimodal Late Fusion},
  year = {2024},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/yourusername/visual-question-answering}}
```

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
