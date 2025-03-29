# Visual Question Answering (VQA) Project

## Overview
This project implements a **Visual Question Answering (VQA)** system that combines computer vision and natural language processing to answer questions about images. The model integrates:
- **ResNet50** for image feature extraction
- **BERT** for question understanding
- **Late fusion mechanism** for answer prediction

## Project Structure
```
├── models/                  # Saved model checkpoints
├── outputs/                 # Training logs and results
├── test_images/             # Sample images for testing
├── notebooks/               # Jupyter notebooks for exploration
├── Presentations/           # Project presentation materials
└── README.md                # This file
```

## Key Implementation Details
- **Dataset**: Subset of COCO-VQA v2.0 (20% training, 5% validation, 5% test)
- **Model Architecture**:
  - Vision: ResNet50 trained from scratch
  - Text: BERT-base-uncased
  - Fusion: Concatenation + FC layers

## Performance Note
The model achieved **43.73% validation accuracy** under constrained training conditions:
- Used only 20% of training data due to GPU memory limitations
- Batch size limited to 16 (vs. typical 32-64 in literature)
- Trained for 10 epochs (vs. 20+ in full implementations)

> **Important**: These results should be interpreted in context of our computational constraints. State-of-the-art models typically achieve 65-75% accuracy when trained on full datasets with larger batch sizes.



## Future Improvements
- [ ] Implement full dataset training with cloud GPUs
- [ ] Add attention mechanisms for better feature fusion
- [ ] Experiment with larger vision backbones (ViT, EfficientNet)

## Citation
```bibtex
@misc{vqa_project_2024,
  title = {Visual Question Answering with Limited Computational Resources},
  author = {Loubaba Malki L'hlaibi and Bouhafa Taha},
  year = {2024},
  note = {Project developed under GPU constraints}
}
```
