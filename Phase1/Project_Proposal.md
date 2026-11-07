# ML 402331 – IoT Machine Learning Project
## Phase 1: Project Proposal
### IoT Network Intrusion Detection Using Machine Learning

**Student:** Abdalrhman Al Mallad  
**University ID:** 2410069  
**Project track:** Software-only (instructor approval pending)

## 1. Project Idea and Motivation
This project proposes a machine-learning-based intrusion detection system for Internet of Things (IoT) networks. It will analyze network-traffic records and classify each record as normal or attack-related. The intended users are IoT network administrators and security analysts who need an additional automated way to identify suspicious activity.

## 2. Problem Statement
IoT networks contain many connected devices and generate large volumes of network traffic. Manually inspecting this traffic is difficult, while rule-based detection may fail to identify changing attack patterns. This project investigates whether supervised machine-learning models can distinguish normal IoT traffic from attack traffic using network-flow features. Results on a benchmark dataset do not, by themselves, prove performance on every real-world IoT network.

## 3. Research Question and Objectives
**Research question:** How effectively can supervised machine-learning models classify normal and attack-related IoT network traffic using selected network-flow features from the ToN_IoT dataset, while avoiding data leakage?

Objectives:
- Inspect and prepare the selected ToN_IoT network data.
- Build a binary classifier for normal (0) and attack (1) traffic.
- Evaluate models using precision, recall, F1-score, confusion matrix and accuracy.
- Compare baseline and more advanced classifiers in later phases.
- Demonstrate a software-only simulated live stream by replaying dataset records, subject to instructor approval.

## 4. Machine-Learning Task, Target and Features
**Task:** Supervised binary classification.  
**Target:** `label` (0 = normal, 1 = attack).  
Candidate features include protocol, source/destination ports, connection duration, source/destination byte and packet counts, and connection state. Identifier-like fields such as IP addresses, raw timestamps and record IDs will be reviewed and excluded where they may cause leakage or unrealistic memorization. Categorical variables will be encoded and numeric variables processed through a reproducible scikit-learn pipeline.

## 5. Dataset and Data Plan
**Dataset:** ToN_IoT Network Dataset, published by UNSW Canberra. The inspected file is `Network_dataset_1.csv`, containing **1,000,000 records and 46 columns**. In the inspected copy, `label=0` (normal) has 208,679 records (20.87%) and `label=1` (attack) has 791,321 records (79.13%). The raw CSV is approximately 140 MB and is not included in this repository; it should be downloaded from the official source and its version verified.

**Official source:** https://research.unsw.edu.au/projects/toniot-datasets

Preparation will include checking data types, missing/invalid values, duplicates and class balance; defining the target; removing leakage-prone identifiers; encoding categorical variables; and using a stratified train/test split. Class imbalance will be considered when choosing metrics. For Phase 2, a Python script will replay rows at a controlled interval to simulate a live stream. No physical sensors are planned for the software-only track.

## 6. Tools and Implementation Plan
Python 3, Google Colab/Jupyter, pandas, NumPy, scikit-learn, Matplotlib/Seaborn and GitHub. The starter notebook contains a small public-dataset linear-regression exercise as requested by the course brief; it is not the final intrusion-detection model because the main project task is classification.

## 7. Related Work
1. Alsaedi, A., Moustafa, N., Tari, Z., Mahmood, A. N., & Anwar, A. (2020). “TON_IoT Telemetry Dataset: A New Generation Dataset of IoT and IIoT for Data-Driven Intrusion Detection Systems.” *IEEE Access, 8*, 165130–165150. https://doi.org/10.1109/ACCESS.2020.3022862
2. Moustafa, N., Ahmed, M., & Ahmed, S. (2020). “Data Analytics-Enabled Intrusion Detection: Evaluations of ToN_IoT Linux Datasets.” 2020 IEEE 19th International Conference on Trust, Security and Privacy in Computing and Communications. https://doi.org/10.1109/TrustCom50675.2020.00100
3. Dharini, N., Janani, V. S., & Katiravan, J. (2026). “Efficient detection of intrusions in TON-IoT dataset using hybrid feature selection approach.” *Scientific Reports, 16*, Article 7763. https://doi.org/10.1038/s41598-026-37834-y

## 8. Expected Outcome
The expected outcome is a reproducible classification pipeline and a comparison of candidate models using class-sensitive evaluation metrics. The report will discuss performance, limitations, class imbalance and the extent to which benchmark results may generalize.

## 9. Repository and Approval Status
GitHub: https://github.com/engabdalrhmann/ML402331-ToN-IoT-Intrusion-Detection-

The course brief requires instructor approval for the software-only track. It also specifies teams of 2–3 students; individual work requires instructor approval. **Neither approval is claimed in this proposal.** The student must obtain confirmation before treating the track and individual arrangement as formally approved.

**Student contribution:** Abdalrhman Al Mallad — project selection, dataset plan, literature review, proposal preparation and initial notebook setup.

## References
UNSW Canberra. *The ToN_IoT Datasets*. https://research.unsw.edu.au/projects/toniot-datasets
