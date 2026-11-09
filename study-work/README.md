# Study work

Theses, coursework and technical tasks. The code is linked where I could make it public.

| Project | What it is | Result | Code |
|---|---|---|---|
| [Surgical Instrument Segmentation](surgical-instrument-segmentation.md) | U-Net on robotic surgery video, with a data audit that turned Dice 0.000 into an honest number | Dice 0.846 ± 0.071 (leave-one-surgery-out) | [repo](https://github.com/moh246/surgical-instrument-segmentation) |
| [Pneumonia Detection from Chest X-rays](pneumonia-detection.md) | Fine-tuned VGG16 on NIH ChestX-ray14 with a patient-level split, subgroup analysis and DICOM inference (Udacity nanodegree) | F1 0.44 (radiologist average 0.387) | [repo](https://github.com/moh246/pneumonia-detection-xray) |
| [EEG Seizure Detection with Caregiver Alerts](eeg-seizure-detection.md) | SVM on 13 EEG features from CHB-MIT, with a Python service that alerts a caregiver (BSc thesis, team project) | About 77% sensitivity; graded A+ | [repo](https://github.com/moh246/eeg-seizure-detection) |
| [Cephalometric Landmark Loss](cephalometric-landmarks.md) | Geometry-aware loss for 19 landmark heatmaps, using the distances and angles between landmarks | Working loss and training loop, tested on synthetic data | [repo](https://github.com/moh246/cephalometric-landmark-loss) |
| [Facial Expression Retargeting](facial-expression-retargeting.md) | Transfer a person's facial expression to a 3D character with two graph-convolutional VAEs and a latent mapping (ITI diploma thesis, team of four) | Working pipeline on 3D face meshes | |
| [Chest X-ray Multi-label Classification](chest-xray-multilabel.md) | DenseNet-121 on the NIH Chest X-ray dataset, patient-level split, served with FastAPI in Docker | F1 0.83 | |

[Back to profile](../README.md)
