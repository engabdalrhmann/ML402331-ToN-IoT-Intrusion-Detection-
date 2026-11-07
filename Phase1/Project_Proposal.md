# ML 402331 – IoT Machine Learning Project
## Phase 1: Project Proposal
### IoT Network Intrusion Detection Using Machine Learning

**Student:** Abdalrhman Al Mallad  
**University ID:** 2410069  
**Project track:** Software-only — approved by instructor (as confirmed by student)  
**Team arrangement:** Individual project — approved by instructor (as confirmed by student)

## 1. Project Idea
Develop a machine-learning-based intrusion detection approach for IoT network traffic, classifying records as normal or attack-related using the ToN_IoT network dataset.

## 2. Problem Statement
IoT networks generate diverse traffic. Manual inspection is difficult, and rule-based detection may struggle with changing attack patterns. This project evaluates supervised learning for distinguishing normal from attack traffic. Benchmark results do not establish performance on every real-world IoT network.

## 3. Research Question
How effectively can supervised machine-learning models classify normal and attack-related IoT network traffic using selected ToN_IoT network-flow features while avoiding data leakage?

## 4. ML Task, Target and Features
**Task:** supervised binary classification. **Target:** `label` (0 = normal, 1 = attack). Candidate features include protocol, ports, duration, byte/packet counts and connection state. Identifier-like fields will be reviewed for leakage risk.

## 5. Dataset Plan
The inspected `Network_dataset_1.csv` contains **1,000,000 records and 46 columns**. In the inspected copy: label 0 = 208,679 (20.87%); label 1 = 791,321 (79.13%). The raw CSV (approximately 140 MB) is not included. Official source: https://research.unsw.edu.au/projects/toniot-datasets. Data preparation will include checking invalid/missing values, duplicates and class balance; encoding features; removing leakage-prone identifiers; and using a stratified split. Phase 2 will include Python-based CSV replay as a simulated stream.

## 6. Tools
Python 3, pandas, NumPy, scikit-learn, Matplotlib/Seaborn, Google Colab/Jupyter and GitHub. The starter linear-regression notebook is a separate course exercise; the main intrusion-detection task is classification.

## 7. Related Work
1. Alsaedi, A., et al. (2020). “TON_IoT Telemetry Dataset: A New Generation Dataset of IoT and IIoT for Data-Driven Intrusion Detection Systems.” *IEEE Access, 8*, 165130–165150. https://doi.org/10.1109/ACCESS.2020.3022862
2. Moustafa, N., et al. (2020). “Data Analytics-Enabled Intrusion Detection: Evaluations of ToN_IoT Linux Datasets.” 2020 IEEE TrustCom. https://doi.org/10.1109/TrustCom50675.2020.00100
3. Dharini, S., Janani, V. S., & Katiravan, K. (2026). “Efficient detection of intrusions in TON-IoT dataset using hybrid feature selection approach.” *Scientific Reports, 16*, 7763. https://doi.org/10.1038/s41598-026-37834-y

## 8. Expected Outcome
A reproducible classification pipeline and comparison of candidate models, with discussion of class imbalance, benchmark limitations and generalization.

## 9. Approval Status
The student confirms instructor approval for both the individual-project arrangement and the software-only track.
