# EO19_Test_Results_based_on_YOLOv13
This repository is about the test results of EO19 using YOLOv13 model.

In the testing results of the ten models presented in this study, YOLOv13 demonstrated the most outstanding performance when considering parameters, FLOPS(floating-point operations per second), and accuracy. Therefore, we present several test results based on YOLOv13.

Due to its distinctive architectural design, YOLOv13 reaches the minimum loss in approximately 55 epochs under identical parameter settings (batch size, image size, etc.), whereas other YOLO-based models tested require around 100 epochs. However, each epoch of YOLOv13 takes longer compared to other YOLO architectures. For example, based on results obtained with an RTX 4090 GPU, YOLOv13n requires about 3 minutes per epoch, while YOLOv12n requires approximately 1 minute and 50 seconds.
<img width="2400" height="1200" alt="results_v12" src="https://github.com/user-attachments/assets/e5fb4b8a-d2bc-4b5f-9925-a2d8bb82eb65" />
<figcaption>Figure 1. Results of YOLOv12n</figcaption>

