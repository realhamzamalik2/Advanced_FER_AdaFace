# **Enhanced FER-AdaFace: Adaptive Facial Expression Recognition**

This repository presents an improved implementation of **Facial Expression Recognition (FER)** using the **AdaFace** classifier on top of the **POSTER** transformer backbone. It refines and extends previous approaches by optimizing data preprocessing, training strategies, and model performance.

---

## 📌 **Features**
- ✅ **Refactored Training Pipeline** for better efficiency and modularity.  
- ✅ **Optimized Model Architecture** to improve feature extraction and classification.  
- ✅ **Custom Data Augmentation** strategies for robustness.  
- ✅ **Enhanced Logging & Visualization** for better interpretability.  
- ✅ **Fine-Tuned Hyperparameters** to achieve higher accuracy on the **RAF-DB dataset**.  

---

## 🔧 **Installation**

### **1️⃣ Clone the Repository**
```bash
git clone https://github.com/realhamzamalik2/Advanced_FER_AdaFace
cd Advanced_FER_AdaFace
```
### **2️⃣ Install Dependencies**
```bash
pip install -r requirements.txt
```
## **📂 Dataset & Pretrained Models**
### **📁 Dataset Structure**
Download the RAF-DB dataset and organize it as follows:

```bash
data/raf-basic/  
├── EmoLabel/  
├── list_patition_label.txt  
├── Image/aligned/  
│   ├── train_00001_aligned.jpg  
│   ├── test_0001_aligned.jpg  
│   ├── ... 
```
 
### **📁 Pretrained Models**
Place pretrained models inside the models/pretrain/ directory:

```bash
models/pretrain/  
├── ir50.pth  
├── mobilefacenet_model_best.pth.tar  
```
## **🚀 Training & Evaluation**
### **🛠️ Train the Model**
```bash
python train.py --gpu 0,1 --batch_size your_batch_size
```

You may adjust batch_size based on your number of GPUs.

### **📊 Evaluate the Model**
```bash
python test.py --checkpoint checkpoint/rafdb_best.pth
```

## **🔍 Project Structure**
```bash
Folder / File	Description
data_preprocessing/	Data loading and preprocessing scripts
models/	Contains the modified POSTER model with AdaFace
