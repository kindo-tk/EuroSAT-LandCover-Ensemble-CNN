# **An Efficient Light-Weight Ensemble of CNN For EuroSAT Land Cover Classification**

###  Remote Sensing •  Deep Learning •  Land Cover Mapping

---

##  Overview

This project proposes a **Light-Weight Ensemble CNN** for accurate and computationally efficient **land cover classification** using the **EuroSAT Sentinel-2 dataset**.  
The ensemble integrates **ShuffleNet V2, MobileNet V2, and EfficientNet-B1**, each adapted for **4-channel RGB+NIR input**.

- **98.00% accuracy**  
- **90% reduction** in model size compared to VGG16  
- Suitable for **edge devices** (drones, mobile/embedded systems)  
- Uses **transfer learning**, **feature fusion**, and **meta-classification**

All experiments were performed in **Kaggle Notebooks**.

---

##  Dataset Summary

The project uses the **EuroSAT Land Use and Land Cover Classification Dataset** based on **Sentinel-2 multispectral imagery**.

| Property | Value |
|---------|-------|
| Total images | 27,000 |
| Image Size | 64×64 pixels |
| Channels | 13 (we use **RGB + NIR = 4 channels**) |
| Classes | 10 |

### **10 EuroSAT Land Cover Classes**
Annual Crop, Forest, Herbaceous Vegetation, Highway, Industrial, Pasture, Permanent Crop, Residential, River, SeaLake

---

##  Methodology
- Z-score normalization  
- Clipping to [-5, 5]  
- Resizing to 224×224  
- Augmentations: flips, rotations, jitter  
- 5-Fold Cross Validation  
- Hyperparameter tuning (20 trials × 6 epochs)

---

##  Model Architecture

Backbones (4‑channel modified):
- ShuffleNet V2  
- MobileNet V2  
- EfficientNet-B1  

Feature Fusion → 3584 dims  
Meta-classifier:  
`3584 → 256 → Dropout → 128 → Dropout → 10`

---

##  Results

| Metric | Score |
|--------|--------|
| **Accuracy** | **98.00%** |
| Precision (Macro Avg) | 97.90% |
| Recall (Macro Avg) | 98.00% |
| F1-Score (Macro Avg) | 97.94% |
| AUC-ROC (OvR) | 0.9990 |

---

##  Repository Structure

```
notebooks/
results/
paper/
data/
```

---

##  Run on Kaggle
1. Upload notebooks  
2. Add the EuroSAT dataset  
3. Run all cells  

---

## Contributors

This work was carried out in collaboration with:

- **Tufan Kundu**  
- **[Mahajan Hemant Pandharinath](https://github.com/hemant-pm)**  
- **[Harsh Pandey](https://github.com/harshp1801)**

We thank all contributors for their support throughout the project.

