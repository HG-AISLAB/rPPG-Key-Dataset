# Dataset for Evaluation
A list of dataset used in the research "Towards Robust Deepfake Detection Based on Heartbeat Analysis"

## Introduction
A list of dataset is derived from FF++ (FaceForensics++), an open dataset for deepfake detection research

## Original Dataset
* **Name**: FF++ (FaceForensics++)
* **Type**: uncompressed videos (raw) and compressed videos (c23, c40)
* **Number of 'Raw' Dataset**: 8,068 fake videos and 1,363 real videos

## Filtered Dataset
* **Number of 'Filtered' Dataset**: 164 videos  (82 real videos and 82 deepfake videos)

## Filtering Criteria
Dataset filtering was performed based on the following criteria:

1. We selected uncompressed videos (raw) to avoid video compression noise, which may affect the quality of the HR signal
2. We selected deepfake videos generated from the same source videos using five different deepfake generation methods
   - Deepfakes
   - Face2Face
   - FaceShifter
   - FaceSwap
   - NeuralTextures
3. We selected the videos based on the following criteria.
   - Videos featuring individuals facing forward
   - Videos without partial occlusion of faces, such as facial hair, glasses, or accessories
   - Videos with only one visible person at any given moment
4. We selected fake videos whose source videos both satisfy the criteria, considering that each fake video was generated based on two source videos

## Experiment Details

* **Objective**: Evaluating the variables of our defined key factors (facial region, extraction interval, rPPG extraction method, and feature engineering method) to understand their impact on the performance of rPPG-based deepfake detection

* **Settings**
  - Control variables: facial region (=R5), extraction interval (=0.1 seconds), rPPG extraction method (=GREEN), and feature engineering method (=feat#1)
  - Envrionment: GPU (GeForce RTX 3060), open source rPPG tool (pyVHR 0.0.4), Python 3.6.9

* **Evaluation**
  - Facial region: Evaluating the differences between real and fake videos in terms of the extracted HR for each facial region (i.e., R1-R9 and Avg)
  - Extraction interval: Evaluating the differences between real and fake videos in terms of the extracted HR for each extraction interval (i.e., 1 second, 0.5 seconds, and 0.1 seconds)
  - rPPG extraction method: Evaluating the differences between real and fake videos in terms of the extracted HR for each rPPG extraction method (i.e., CHROM, GREEN, ICA, LGI, PBV, and PCA)
  - Feature engineering method: Evaluating the differences between real and fake videos in terms of the extracted HR for each feature engineering method (i.e., feat#1, feat#2, and feat#3)
  - Key factor combination analysis: Examining a set of key factor combinations and identified the optimal one that maximizes the performance of rPPG-based deepfake detection
