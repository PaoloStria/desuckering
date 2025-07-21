# 🍇 Automatic Detection of Suckers and Watersprouts in Grapevines  
## 🤖 Computer Vision for Robotic Suckering

This repository contains the resources and materials developed for a thesis project on the automatic detection of suckers and watersprouts (undesired shoots) in grapevines, using state-of-the-art computer vision techniques. The system leverages YOLOv11-Seg instance segmentation models to support automated suckering operations in vineyards.

---

### 📂 Repository Contents

- 🗂️ **best.pt** — Trained weights of the YOLOv11-Seg model achieving the best performance.
- 📥 **dataset** — The full dataset is **not stored directly in this repository** due to file size restrictions.  
  Instead, you can download it from Zenodo (see below).

---


## 🏷️ Class Names

The YOLOv11-Seg model was trained to segment the following classes:

- `sucker` — undesired basal shoot (pollone)
- `ground` — soil/background
- `support` — vineyard support pole
- `trunk` — main vine trunk
- `watersprout` — undesired vigorous shoot (succhione)

Feel free to adjust or expand the classes if you further fine-tune the model or extend the dataset.

---


### 📥 Download the Dataset

Due to GitHub file size restrictions, the full dataset is hosted externally on Zenodo.

Download it here:  
➡️ [Automatic Detection of Suckers and Watersprouts – dataset (Zenodo)](https://zenodo.org/records/16020164)

## 🌱 Project Overview

Suckering is a fundamental operation in vineyard management: it involves removing non-productive shoots (suckers and watersprouts) that grow from the base or trunk of the vine, competing for vital resources and negatively affecting yield quality.

This project presents a computer vision system designed to automatically detect these undesired shoots in the lower part of the vine. The workflow includes:

- 🧑‍🌾 **Dataset creation**: Field data collection in a Tuscan vineyard, frame extraction, and multi-class manual/automatic annotation using Roboflow and the SAM2 model.
- 🧠 **Model training**: Fine-tuning a YOLOv11-Seg instance segmentation model on the custom dataset (PSV-Seg), experimenting with data augmentation and preprocessing strategies.
- 📈 **Evaluation**: Performance measured via precision, recall, F1-score, and confusion matrices, with detailed analysis of class-wise results and model limitations.

The project materials can be used as a starting point for further development of robotic platforms for autonomous suckering, and as a dataset benchmark for future computer vision research in precision agriculture.

---


## 📊 Example: Model Performance

Below is the normalized confusion matrix obtained on the test set using the best YOLOv11-Seg model:

<p align="center">
  <img src="images/confusion_matrix.png" width="500"/>
</p>

*Confusion matrix showing class-wise segmentation performance.*

---

🔎 Model Limitations & Future Work
As shown in the confusion matrix above, the recognition rate for the sucker class is relatively low. However, this is still an encouraging result: the model was able to generalize and detect underrepresented classes, despite their scarcity in the training images.

This limitation is mainly due to the fact that the new dataset is among the first specifically designed for the segmentation of grapevine shoots, with a strong focus on robotic consistency and environmental variability.
Given the time constraints—the entire project was completed in just 3 months—it was not possible to collect more images or perform ultra-precise multi-class segmentation for every instance.

Nonetheless, the current results demonstrate the potential of computer vision for autonomous sucker and watersprout detection in real-world vineyard scenarios.

Future work will focus on expanding the dataset—especially with new annotated examples of the sucker class under a wider range of lighting and environmental conditions—and refining the annotation process.
This will enable further improvements in detection performance and make the model more flexible and robust for practical deployment.

---

## ⚡ How to Use

1. 📥 **Download and unzip** the dataset if you wish to train or test models.
2. 🏋️‍♂️ **Use the provided weights** (`best.pt`) with YOLOv11-Seg-compatible code to run inference or continue fine-tuning.
3. 📑 **Refer to the PowerPoint presentation** for a quick overview of objectives, methodology, results, and possible future directions.

---

### 🔄 Model Fine-Tuning

The provided `best.pt` weights can be used as a starting point for further fine-tuning on new datasets or under different conditions.  
**To improve the detection of suckers (polloni), it is highly recommended to further expand the dataset with additional annotated images containing suckers, especially in varied lighting and environmental conditions.**



## 📖 Citation

If you use this dataset or code, please cite:  
**Paolo Strianese**, "Automatic detection of suckers and watersprouts in grapevines: computer vision system for agricultural robots", University of Milano-Bicocca, 2025.

---

## 📬 Contact

For more information:  
**Paolo Strianese**  
paolostria@gmail.com
