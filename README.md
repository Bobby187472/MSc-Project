# AI-Driven Precision Agriculture
### Early Disease Detection and Sustainable Crop Protection

## Overview
This project presents a **two-stage AI pipeline** for plant disease detection using the **PlantWild dataset** (18,542 in-the-wild images across 89 classes).

- **Stage 1**: Binary classification (healthy vs diseased).  
- **Stage 2**: Fine-grained classification (59 disease categories).  
- **Key Features**:  
  - Class weighting for imbalance.  
  - Interpretability with **Grad-CAM** visualizations.  
  - Deployment via **Flask + Pyngrok** for real-time testing.  

This work was completed as part of my MSc Data Science dissertation at *University of Roehampton* (2025).  

---

## Objectives
- Develop a **field-ready, interpretable** plant disease detection system.  
- Compare optimizers (Adam, SGD, RMSprop) for robust training.  
- Validate using **bootstrap CIs, cross-validation, and statistical tests**.  
- Deploy lightweight system for farmer accessibility.  

---

## Dataset
- **Dataset**: [PlantWild](https://plant.id/plantwild) (18,542 images, 89 classes).  
- **Why PlantWild?**  
  - Realistic, in-field images (lighting, occlusion, clutter).  
  - Broad coverage (33 crops, 59 diseased, 30 healthy).  
  - Public, well-documented, multimodal annotations.  

---

## Methodology
1. **Stage 1 (Binary Classifier)**  
   - Backbone: MobileNetV2 + fine-tuned head.  
   - Optimizer study: Adam, RMSprop, SGD.  
   - Achieved **~90% accuracy (RMSprop best performer)**.  

2. **Stage 2 (Multiclass Classifier)**  
   - MobileNetV2 + AdamW (two-phase training).  
   - Class weighting for imbalance.  
   - Achieved:  
     - **73% Top-1 accuracy**  
     - **92% Top-3 accuracy**  
     - **95% Top-5 accuracy**  

3. **Explainability**  
   - Grad-CAM heatmaps confirm focus on lesion areas.  

4. **Deployment**  
   - Flask API + lightweight frontend.  
   - Accessible externally via Pyngrok tunnel.

---

## Results
- **Binary Classifier (Stage 1)**:  
  - RMSprop: Accuracy 89.6%, F1-score 0.876, AUC 0.958.  
  - Robust under bootstrap & cross-validation.  

- **Multiclass Classifier (Stage 2)**:  
  - Top-1 Accuracy: 73%  
  - Top-3 Accuracy: 92%  
  - Top-5 Accuracy: 95%  
  - Grad-CAM confirms lesion-based decision making.  

---

## Limitations
- Restricted to image-based inputs (no IoT/sensor integration).  
- Performance may degrade on unseen crop-disease combinations.  
- Deployment limited to demo-level Flask app.  

---

## Future Work
- Incorporate **sensor/multimodal data** (e.g., weather, soil).  
- Extend to mobile apps for real-world farmers.  
- Explore lightweight **Vision Transformers** for improved generalization.  

---

## References
- [PlantWild Dataset](https://plant.id/plantwild)  
- Related works cited in dissertation.  
- Frameworks: TensorFlow, Keras, Flask, Pyngrok, OpenCV.  

---

## Acknowledgements
Thanks to **Mr. Karim Bouzoubaa** (supervisor), family, and colleagues for their guidance and support.  
