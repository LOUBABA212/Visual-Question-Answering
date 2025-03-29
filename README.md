# Visual Question Answering   
*A multimodal deep learning system for answering questions about images*  

---

## 🔍 Overview  
This project implements a **Visual Question Answering (VQA)** system using:  
- **Vision Model**: ResNet50 (pretrained on ImageNet) for image feature extraction  
- **Text Model**: BERT-base-uncased for question understanding  
- **Fusion**: Late concatenation + fully connected layers for answer prediction  

**Full repository (models, datasets, outputs)** is available on Google Drive:  
👉 [Download Full Project Folder](https://drive.google.com/drive/folders/1F0m-6e1kyNcWky9k-zBfJqGwcM9-Xvz5?usp=drive_link)  

---

## 📂 Project Structure  
```
├── models/                  # Pretrained model weights (.pth/.ckpt)
├── outputs/                 # Training logs, metrics, and visualizations
├── test_images/             # Sample images for inference testing
├── notebooks/               # Jupyter notebooks (EDA, prototyping)
├── Presentations/           # Slide decks (PDF/PPT)
├── Report/                  # LaTeX source for the final report
                   
```

---

## ⚙️ Implementation Notes  
### Dataset Constraints  
Due to computational limitations (GPU memory), we used:  
- **20%** of COCO-VQA v2.0 training data  
- Batch size **16** (vs. typical 32-64)  
- **5 epochs** for vision/text components  

### Results Context  
| Component       | Accuracy (Val) | Notes                          |
|----------------|---------------|-------------------------------|
| ResNet50       | 19.34%        | Image feature extraction       |
| BERT           | 40.48%        | Question processing            |
| **Full VQA**   | **43.73%**    | Late fusion (constrained setup)|

> 🔴 **Note**: State-of-the-art models (ViLBERT, LXMERT) achieve ~70% accuracy with full datasets and hardware. Our results reflect trade-offs for local training.



## 📈 Future Improvements  
- [ ] **Scale training**: Use cloud GPUs (Colab/AWS) for full-dataset runs  
- [ ] **Advanced fusion**: Replace late fusion with co-attention (e.g., [MCAN](https://arxiv.org/abs/1906.10770))  
- [ ] **Deployment**: Build a Gradio/Streamlit demo  

---

## 📜 Citation  
```bibtex
@misc{vqa_project_2024,
  title = {Resource-Constrained VQA with ResNet50+BERT},
  author = {Loubaba Malki L'hlaibi and Bouhafa Taha },
  year = {2024},
  howpublished = {GitHub repository with full data on Google Drive}
}
```

---
