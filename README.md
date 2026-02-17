# 🦎 Camouflaged Object Detection with Boundary Localization In Complex Backgrounds
**Camouflaged Object Detection (COD)** is one of the most challenging problems in computer vision because the target objects intentionally or naturally blend into their surroundings.

This project proposes a **CNN-based deep learning framework** that not only detects camouflaged objects but also **accurately localizes their boundaries**, even in **low-contrast and complex scenes**.

## 🎯 **Objectives**

* ✅ Detect camouflaged objects in complex environments
* ✅ Accurately localize object boundaries
* ✅ Reduce background interference
* ✅ Improve robustness and generalization

---

## 📐 **System Architecture**

The proposed system is designed using a **Dual-Branch Encoder–Decoder Convolutional Neural Network (CNN)** architecture for accurate camouflaged object detection and precise boundary localization.

<p align="center">
  <img src="images/proposed%20methodology.png" width="500"
       style="border: 3px solid #2f80ed; border-radius: 12px; padding: 8px; box-shadow: 0px 4px 14px rgba(0,0,0,0.25);">
</p>

The architecture consists of:

* 🧠 **Encoder Network** → Extracts hierarchical visual features  
* 🔄 **Decoder Network** → Reconstructs spatial resolution  
* 🟢 **Segmentation Head** → Predicts binary camouflage mask  
* 🔵 **Boundary Head** → Predicts object contour map  

The dual-output design improves segmentation accuracy while ensuring sharp and precise boundary localization.

---

## 🧠 **Proposed Methodology**

The system follows a structured pipeline for detecting camouflaged objects in complex backgrounds.

### ➤ **1️⃣ Input Image Acquisition**

* RGB images are collected from benchmark datasets such as **CAMO, COD10K, and NC4K**  
* Images contain naturally or intentionally hidden objects in forests, underwater scenes, grasslands, and rocky terrains  
* Corresponding **pixel-level ground truth masks** are used for supervised training  
* Boundary maps are derived from masks for explicit contour supervision  

### ➤ **2️⃣ Image Preprocessing**

To ensure stable CNN training and uniform input size:

* Images are resized to **256 × 256** resolution  
* Pixel values are normalized to the range **[0,1]**  
* Noise reduction and enhancement applied if required  
* Ground truth masks resized accordingly  
* Boundary maps generated using edge detection techniques  
* Enhances subtle texture and edge variations critical for camouflage detection  

### ➤ **3️⃣ CNN-Based Feature Extraction (Encoder)**

The encoder extracts hierarchical features through multiple convolutional and pooling layers:

* Early layers → Capture low-level features (edges, textures)  
* Intermediate layers → Learn structural patterns  
* Deep layers → Extract high-level semantic context  
* Pooling layers → Reduce spatial dimension while preserving salient camouflage cues  

### ➤ **4️⃣ Feature Reconstruction (Decoder)**

The decoder restores spatial resolution for pixel-level prediction:

* Upsampling layers increase feature map size  
* Convolution layers refine spatial details  
* Recovers fine object contours lost during pooling  
* Essential for accurate segmentation and boundary localization
  
### ➤ **5️⃣ Dual Output Heads (Mask & Boundary Prediction)**

* 🟢 **Segmentation Mask Head** → Produces binary mask separating object from background  
* 🔵 **Boundary Head** → Predicts precise object contours  

This dual-branch supervision enhances contour sharpness and segmentation quality.

### ➤ **6️⃣ Loss Computation & Optimization**

During training:

* Mask Loss → Measures segmentation accuracy  
* Boundary Loss → Penalizes incorrect edge predictions  
* Total Loss = Combination of both losses  
* Optimizer (Adam) used for parameter updates  
* Backpropagation improves detection and boundary localization performance  

### ➤ **7️⃣ Model Validation & Performance Evaluation**

After training, the model is evaluated on unseen data:

* Quantitative Metrics → Dice Score, IoU  
* Qualitative Evaluation → Visual comparison of masks and boundary overlays  
* Boundary visualization ensures precise contour localization  

---



## 📂 **Datasets Used**

The model is trained and evaluated using **benchmark camouflaged object detection datasets** with pixel-level annotations.

### 🗂️ **CAMO Dataset**

A widely used dataset containing challenging low-contrast camouflaged scenes.

🔗 **Link:**
[https://sites.google.com/view/ltnghia/research/camo](https://sites.google.com/view/ltnghia/research/camo)

### 🗂️ **COD10K Dataset**

A large-scale camouflaged object detection dataset with diverse and complex backgrounds.

🔗 **Link:**
[https://paperswithcode.com/dataset/cod10k](https://paperswithcode.com/dataset/cod10k)

### 🗂️ **NC4K Dataset**

An extended evaluation dataset used to test the **generalization capability** of COD models.

🔗 **Link:**
[https://github.com/lartpang/awesome-segmentation-saliency-dataset](https://github.com/lartpang/awesome-segmentation-saliency-dataset)
*(Refer to the **NC4K** entry)*

## 🛠️ **Technologies Used**

* **Python**
* **Convolutional Neural Networks (CNN)**
* **PyTorch / TensorFlow**
* **OpenCV**
* **NumPy**
* **Matplotlib**
* **Jupyter Notebook**

## 📊 **Output Results**

The model generates:

* 🟢 **Binary segmentation masks**
* 🔵 **Boundary localization maps**
* 🖼️ **Overlay visualizations** highlighting camouflaged objects

---

## 📁 **Folder Structure**

The project follows a **well-organized and modular folder structure** to ensure clarity, scalability, and ease of maintenance.

<p align="center">
  <img src="images/Folder%20Structure.png" width="500" 
       style="border: 3px solid #2f80ed; border-radius: 12px; padding: 8px; box-shadow: 0px 4px 12px rgba(0,0,0,0.2);">
</p>

### 🗂️ **The Folder is Organised into**

* 📂 **images/** → Contains project images, visualizations, and documentation assets  
* 📂 **mask/** → Stores ground-truth segmentation masks used for training and evaluation  
* 📄 **train.py** → Script for model training  
* 📄 **test.py** → Model testing and evaluation  
* 📄 **model.py** → CNN architecture definition  
* 📄 **metrics.py** → Performance evaluation metrics (IoU, Dice, etc.)  
* 📄 **splitdata.py** → Dataset splitting utility  
* 📄 **makeedges.py** → Boundary map generation logic  
* 📄 **showboundary2.py** → Boundary visualization module  
* 📄 **app.py** → Deployment / inference interface  

---

## 🚀 **Applications**

* 🛡️ Defense and surveillance
* 🏥 Medical image analysis
* 🐾 Wildlife monitoring
* 🌊 Underwater exploration
* 🚨 Search and rescue operations

### ⭐ *If you like this project, don’t forget to star the repository!*



