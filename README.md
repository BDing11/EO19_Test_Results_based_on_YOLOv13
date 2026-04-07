# EO19_Test_Results_based_on_YOLOv13
This repository is about the test results of EO19 using YOLOv13 model.

In the testing results of the ten models presented in this study, YOLOv13 demonstrated the most outstanding performance when considering parameters, FLOPS(floating-point operations per second), and accuracy. Therefore, we present several test results based on YOLOv13.

# Epoch Setting
Due to its distinctive architectural design, YOLOv13 reaches the minimum loss in approximately 55 epochs under identical parameter settings (batch size, image size, etc.), whereas other YOLO-based models tested require around 100 epochs. However, each epoch of YOLOv13 takes longer compared to other YOLO architectures. For example, based on results obtained with an RTX 4090 GPU, YOLOv13n requires about 3 minutes per epoch, while YOLOv12n requires approximately 1 minute and 50 seconds.
| YOLOv12n | YOLOv13n |
|------------------|------------------|
| <img width="600" height="300" alt="results_v12" src="https://github.com/user-attachments/assets/8dd3d09e-abd9-4ea0-bb79-3e2fe1783ca9" />|<img width="600" height="300" alt="results_v13" src="https://github.com/user-attachments/assets/38b743b0-9a25-4313-b3ad-6011a2eaec12" />|
| Figure 1. YOLOv13 Results| Figure 2. YOLOv12 Results|

Figure 1 illustrates a training result of YOLOv12, where the loss curve approaches a plateau around 100 epochs, indicating that neither underfitting nor overfitting occurred. Figure 2 shows a training result of YOLOv13, in which the loss curve exhibits clear signs of overfitting after exceeding 50 epochs. Consequently, this study sets the number of epochs for YOLOv13 at 55.
