# AI FOR THREAT DETECTION IN DEFENSE
This project focuses on leveraging **Artificial Intelligence (AI)** for **real-time threat detection** from defense surveillance footage.  
Using the **YOLOv8 object detection framework**, the system classifies vehicles into *civilian*, *safe (friendly)*, or *threat (hostile)* categories to enhance security and support rapid decision-making in defense operations.

---

## Objective
> How can AI be utilized to accurately classify vehicles in real-time from surveillance footage, specifically distinguishing between civilian and potentially hostile vehicles?
The goal is to build a **robust, real-time classification system** that can detect, recognize, and categorize vehicles seen in defense surveillance feeds with high accuracy and minimal latency.

---
## Concept Overview
The model enhances **situational awareness** by automating the identification of:
- **Civilian Vehicles** (low risk)
- **Safe Vehicles** (friendly or allied)
- **Threat Vehicles** (potential enemy units)
This system aims to assist defense personnel in **early threat detection**, **mission planning**, and **risk assessment** using live video feeds.

---

## 📂 Dataset Preparation
Since no ready dataset existed for this specific use case, we **built a custom dataset from scratch**.

### **Data Collection**
- Scraped open-source image repositories and defense archives  
- Curated vehicle images from **surveillance and military datasets**  
- Uploaded all data to **Roboflow** for annotation and preprocessing

### **Dataset Stats**
- **Total Images:** ~1,000 (before augmentation)  
- **Classes:** 11 categories  
- **Categories:**
  - 🟡 **Civilian:** Tempo, Auto, Tractor, Bus, Truck  
  - 🔴 **Threat:** Enemy Truck, Tank, Armored Vehicle *(mostly from China & Pakistan)*  
  - 🟢 **Safe:** Indian Army Truck, Tank, Armored Vehicle

---

## 🧰 Tools & Technologies

| Category | Tools |
|-----------|-------|
| **Model** | YOLOv8 (Ultralytics) |
| **Dataset Platform** | Roboflow |
| **Programming Language** | Python |
| **Frameworks/Libraries** | PyTorch, OpenCV, ultralytics |
| **Environment** | Google Colab |
| **Visualization** | Matplotlib, Roboflow dashboard |

---

##  Methodology
1. **Dataset Creation & Annotation**  
   Images were annotated in Roboflow with bounding boxes and class labels.

2. **Model Training (YOLOv8)**  
   - YOLOv8 was trained using our custom dataset  
   - Automatic dataset splitting (train/val/test)  
   - Fine-tuned hyperparameters for balanced accuracy across all classes  

3. **Evaluation Metrics**  
   - Precision, Recall, mAP@50, F1-score  
   - Real-time inference speed (FPS) measured on test videos

4. **Inference & Real-Time Detection**  
   - Model deployed to detect vehicles in surveillance footage  
   - Bounding boxes color-coded by category:
     - 🔴 Red → Threat
     - 🟩 Green → Safe (Friendly)

---

## 📊 Results

![Safe Truck Detection]("C:\Users\ArukshitaDubey\Downloads\Picture1.jpg")
![Threat Truck Detection]("C:\Users\ArukshitaDubey\Downloads\Picture2.jpg")


---

## Future Scope
- Integrate **drone video streams** for real-time inference  
- Expand dataset with **night vision and infrared** imagery  
- Add **object tracking** (e.g., DeepSORT) to follow threats over time  
- Implement **alert system** for immediate operator notification  

---

## 🧑‍💻 Author

**Arukshita Dubey**   
📧 [https://www.linkedin.com/in/arukshita-dubey-811b22249/]

---

## Citation
If you use this dataset or build upon this model, please cite:  
> Arukshita Dubey (2025). *AI for Threat Detection in Defense* — A YOLOv8-based deep learning system for real-time classification of civilian, safe, and hostile vehicles.

---

