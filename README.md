# 🌊 Diving into Underwater — SAM-Guided Underwater Instance Segmentation

> A deep learning project leveraging **Segment Anything Model (SAM)**  
> to enhance **underwater salient instance segmentation (USIS)**,  
> conducted as part of *AI Project 1* in the **Erasmus Mundus MIR Programme** at Université de Toulon (2025).

---

## 🎯 Objective

The aim of this project was to apply the **Segment Anything Model (SAM)**  
to underwater image segmentation and benchmark its performance against state-of-the-art models such as **YOLOv11**.  
To improve underwater segmentation accuracy, the project reproduced and fine-tuned the **USIS-SAM** model,  
which integrates **Underwater Adaptive ViT (UA-ViT)** and a **Salient Feature Prompt Generator (SFPG)**.

---

## 📂 Repository Structure

| Path | Description |
|------|--------------|
| **DeepLearning.pdf** | Team presentation slides summarizing architecture and results |
| **3581_Diving_into_Underwater_Se.pdf** | Reference paper (USIS-SAM, ICML 2024) |
| **README.md** | Project overview and documentation (this file) |

---

## ⚙️ Methodology

- **Model:** USIS-SAM (Segment Anything Model for Underwater SIS)  
- **Enhancements:**  
  - **UA-ViT** – integrates underwater-specific visual prompts via adapters  
  - **SFPG** – generates salient prompts automatically (no user-provided boxes/points)  
- **Training Setup:**  
  - 24 epochs on A100 (20 GPUs)  
  - Optimizer: AdamW (lr = 1e-4, weight decay = 1e-3)  
  - Dataset: **USIS10K** (10,632 labeled underwater images, 7 categories)

---

## 📊 Results

| Model | Epochs | mAP | mAP50 | mAP75 |
|--------|--------:|------:|------:|------:|
| **USIS-SAM** | 24 | **43.1** | **59.0** | 48.5 |
| YOLOv11-Nano | 50 | 57.9 | 45.6 | — |
| YOLOv11-X | 50 | 58.1 | 57.8 | — |

🟦 **Finding:** USIS-SAM achieved more consistent object boundaries  
and better **salient region accuracy** than YOLO in challenging underwater scenes.

---

## 💡 Key Insights

- SAM requires adaptation to underwater domain knowledge; **UA-ViT adapters** bridge this gap.  
- **SFPG** improves attention on small, overlapping marine objects.  
- **YOLOv11** excelled in general object detection but struggled with underwater distortions.  
- Demonstrated potential of **foundation models (SAM)** for **marine perception tasks**.

---

## 🧩 Tools & Frameworks

- **PyTorch · MMDetection · SAM (Meta AI)**  
- **USIS10K Dataset** (fish, coral, diver, robot, seafloor, ruins, plants)  
- **t-SNE Visualization**, **mAP Metrics**, **AdamW Optimizer**

---

## 👩‍💻 Authors

**Muhammad Pramudya · Hyejoo Kwon · Mateus Pedrosa · Youssief Morsy**  
📍 Erasmus Mundus Master’s in *Marine & Maritime Intelligent Robotics (MIR)*  
📅 Submitted: May 2025  

🔗 [GitHub Repository](https://github.com/S1194789/AI_project_1_Image_Segmentation)
