# EO19 Testing Results based on YOLOv13
This repository is about the test results of EO19 using YOLOv13 model.

In the testing results of the ten models presented in this study, YOLOv13 demonstrated the most outstanding performance when considering parameters, FLOPS(floating-point operations per second), and accuracy. Therefore, we present several test results based on YOLOv13.

## Epoch Setting
Due to its distinctive architectural design, YOLOv13 reaches the minimum loss in approximately 55 epochs under identical parameter settings (batch size, image size, etc.), whereas other YOLO-based models tested require around 100 epochs. However, each epoch of YOLOv13 takes longer compared to other YOLO architectures. For example, based on results obtained with an RTX 4090 GPU, YOLOv13n requires about 3 minutes per epoch, while YOLOv12n requires approximately 1 minute and 50 seconds.
| YOLOv12n | YOLOv13n |
|------------------|------------------|
| <img width="600" height="300" alt="results_v12" src="https://github.com/user-attachments/assets/8dd3d09e-abd9-4ea0-bb79-3e2fe1783ca9" />|<img width="600" height="300" alt="results_v13" src="https://github.com/user-attachments/assets/38b743b0-9a25-4313-b3ad-6011a2eaec12" />|
| Figure 1. YOLOv12 Results| Figure 2. YOLOv13 Results|

Figure 1 illustrates a training result of YOLOv12, where the loss curve approaches a plateau around 100 epochs, indicating that neither underfitting nor overfitting occurred. Figure 2 shows a training result of YOLOv13, in which the loss curve exhibits clear signs of overfitting after exceeding 50 epochs. Consequently, this study sets the number of epochs for YOLOv13 at 55.

## Training Results
Figure 3 shows the YOLO v13 training results with 55 epochs, a batch size of 16, and an image size of 640.
<img width="2400" height="1200" alt="results" src="https://github.com/user-attachments/assets/9d0f6aea-edaa-46bd-a25c-fce2be63d5f2" />

Figure 3. The results of EO19 using YOLOv13n

The Precision–Recall (PR) curve provides a comprehensive view of the trade-off between precision and recall across varying confidence thresholds, thereby serving as a robust indicator of detection performance. The obtained value of 0.869 demonstrates that the model achieves a high level of accuracy in correctly identifying and classifying targets while maintaining satisfactory coverage(as shown in Figure 4). Although this performance reflects strong overall reliability, further optimization may still be required to address challenging cases such as small-object detection or highly overlapping samples.
<img width="2250" height="1500" alt="PR_curve" src="https://github.com/user-attachments/assets/23e3ee90-62be-408f-b5ac-bb6559cd4ef3" />

Figure 4. The PR-curve of EO19 using YOLOv13n

The training results of every categories using YOLOv13 are shown in the table below.
| Class | Images | Instances | Box(P) | R | mAP50 | mAP75 | mAP50-95 |
|-------|---------|------------|--------|---|--------|--------|-----------|
| all | 2462 | 5394 | 0.88 | 0.815 | 0.805 | 0.728 | 0.652 |
| Larva_Crambidae | 112 | 163 | 0.894 | 0.716 | 0.829 | 0.656 | 0.576 |
| Adult_Crambidae | 52 | 59 | 0.934 | 0.915 | 0.948 | 0.944 | 0.825 |
| Larva_Noctuidae | 101 | 312 | 0.895 | 0.849 | 0.869 | 0.803 | 0.679 |
| Adult_Noctuidae | 64 | 106 | 0.872 | 0.864 | 0.896 | 0.803 | 0.679 |
| Larva_Linacaidae | 126 | 199 | 0.83 | 0.8 | 0.839 | 0.719 | 0.711 |
| Adult_Linacaidae | 27 | 27 | 0.85 | 0.889 | 0.895 | 0.889 | 0.778 |
| Larva_Nymphalidae | 28 | 49 | 0.812 | 0.714 | 0.734 | 0.554 | 0.531 |
| Adult_Nymphalidae | 61 | 85 | 0.93 | 1 | 0.989 | 0.989 | 0.940 |
| Larva_Papilionidae | 25 | 28 | 0.886 | 0.852 | 0.915 | 0.891 | 0.824 |
| Adult_Papilionidae | 60 | 74 | 0.873 | 0.959 | 0.939 | 0.854 | 0.725 |
| Larva_Sphingidae | 31 | 41 | 0.871 | 0.913 | 0.941 | 0.924 | 0.824 |
| Adult_Sphingidae | 63 | 65 | 0.984 | 0.933 | 0.961 | 0.946 | 0.894 |
| Larva_Scarabaeidae | 72 | 157 | 0.842 | 0.871 | 0.877 | 0.807 | 0.708 |
| Adult_Scarabaeidae | 87 | 130 | 0.856 | 0.896 | 0.856 | 0.685 | 0.588 |
| Larva_Elateridae | 60 | 108 | 0.856 | 0.75 | 0.814 | 0.637 | 0.578 |
| Adult_Elateridae | 30 | 30 | 0.833 | 0.9 | 0.935 | 0.9 | 0.8 |
| Larva_Coccinellidae | 42 | 118 | 0.845 | 0.449 | 0.53 | 0.492 | 0.428 |
| Adult_Coccinellidae | 61 | 80 | 0.923 | 0.939 | 0.927 | 0.839 | 0.734 |
| Larva_Cerambycidae | 22 | 42 | 0.832 | 0.619 | 0.718 | 0.573 | 0.479 |
| Adult_Cerambycidae | 151 | 166 | 0.944 | 0.91 | 0.903 | 0.794 | 0.719 |
| Adult_Chrysomelidae | 78 | 163 | 0.817 | 0.875 | 0.819 | 0.703 | 0.619 |
| Larva_Chrysomelidae | 12 | 60 | 0.878 | 0.6 | 0.475 | 0.405 | 0.352 |
| Fulgoridae | 203 | 341 | 0.561 | 0.944 | 0.976 | 0.944 | 0.852 |
| Flatidae | 21 | 21 | 0.915 | 0.917 | 0.911 | 0.911 | 0.911 |
| Delphacidae | 81 | 200 | 0.842 | 0.805 | 0.837 | 0.686 | 0.608 |
| Cicadellidae | 180 | 236 | 0.878 | 0.9 | 0.877 | 0.808 | 0.708 |
| Miridae | 159 | 176 | 0.914 | 0.904 | 0.934 | 0.828 | 0.598 |
| Aphididae | 151 | 1733 | 0.863 | 0.757 | 0.743 | 0.543 | 0.489 |
| Gryllotalpidae | 143 | 163 | 0.957 | 0.987 | 0.985 | 0.799 | 0.662 |
| Acrididae | 147 | 227 | 0.948 | 0.833 | 0.913 | 0.764 | 0.697 |

Table 1. Results of all categories using YOLOv13n

##  Detecting Results
This study developed a user interface for invoking the YOLOv13 model, enabling control or selection of parameters such as weight files, Intersection over Union (IoU), confidence threshold, and detection targets (including images, videos, and surveillance footage). Figures 3 and 4 present the nine images involved in detection, all of which are drawn from the validation set to prevent data leakage.

| Original | Detection |
|----------|----------|
| <img src="https://github.com/user-attachments/assets/e7d05320-2695-4d9d-a892-bb3e4e526b36" width="600"/> | <img src="https://github.com/user-attachments/assets/14ebdc22-ff36-465c-bf4a-7e3243491ca8" width="600"/> |
| Figure 3. Original Image(Adult) | Figure 4. Detection Image(Adult) |

Figure 4 illustrates the test results with a confidence threshold of 70% and an Intersection over Union (IoU) of 70%. All 17 detected samples were correctly identified and classified. Within Aphididae (the small image in the second row, second column), 9 samples were detected out of 9 present, with 2 missed detections. This outcome highlights that, under overlapping conditions, the dataset and model still have room for improvement in small-object detection.

Figures 5 and 6 present the detection results for larval classification within EO19.

| Original | Detection |
|----------|----------|
| <img src="https://github.com/user-attachments/assets/f9dd0dcd-184a-4199-ada7-d4be912bbea0" width="600"/> | <img src="https://github.com/user-attachments/assets/a97b94a1-4dc6-4731-8d8b-7a1f61ae0945" width="600"/> |
| Figure 5. Original Image(Larva) | Figure 6. Detection Image(Larva) |

Due to the high similarity among larvae and the difficulty of obtaining images, we present the detection results at a confidence threshold of 50% (as shown in Figure 6). In these results, the larva of Coccinellidae (small image in the first row, first column) was misclassified as a larva of Nymphalidae, while the larva of Scarabaeidae was misclassified as Noctuidae (third row, second column), reflecting the real-world challenge of high inter-species similarity. The larva of Crambidae was not detected (second row, second column), which is likely due to its strong resemblance to its surrounding environment. The larva of Papilionidae exhibited missed detections at low confidence (third row, third column), which is presumed to result from the limited number of original samples in its category, leading to a long-tail effect.





