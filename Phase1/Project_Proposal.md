# ML 402331 – IoT Machine Learning Project
## Phase 1: Project Proposal
### IoT Network Intrusion Detection Using Machine Learning

**Student:** Abdalrhman Al Mallad  
**University ID:** 2410069  
**Project track:** Software-only (instructor approval pending)

## 1. Project Idea and Motivation
This project proposes a machine-learning-based intrusion detection system for Internet of Things (IoT) networks. IoT devices communicate with gateways, servers and cloud services, creating opportunities for cyberattacks such as denial-of-service (DoS), distributed denial-of-service (DDoS), scanning and other malicious activities. The proposed system will analyze network-traffic records and classify each record as normal or malicious. The intended users are IoT network administrators and security analysts who need an additional automated way to identify suspicious network activity.

## 2. Problem Statement
IoT networks contain many connected devices and generate large volumes of network traffic. Manually inspecting this traffic is difficult, and rule-based detection may fail to identify unfamiliar or changing attack patterns. The project will investigate whether supervised machine-learning models can distinguish normal IoT network traffic from attack traffic using measurable network-flow features. The system will be developed and evaluated using a public dataset; therefore, its results will represent performance on the available benchmark data and will not, by themselves, prove performance on every real-world IoT network.

## 3. Research Question and Objectives
**Research question:** How accurately can machine-learning classification models detect malicious activity in IoT network traffic using the ToN_IoT network dataset, while avoiding data leakage from identifier features?

Objectives:
- Prepare and inspect the selected ToN_IoT network-traffic data.
- Build a binary classifier that predicts normal (0) or attack (1) traffic.
- Establish a baseline model and evaluate it using accuracy, precision, recall, F1-score and a confusion matrix.
- Compare the baseline with ensemble and SVM-based models in later project phases.
- Replay dataset records as a simulated live stream for a software-only demonstration, subject to instructor approval.

## 4. Machine-Learning Task, Target and Features
**Task type:** Supervised binary classification.  
**Target label:** `label` (0 = normal traffic, 1 = attack traffic), as defined for the selected ToN_IoT network dataset.

Planned input features will be selected from network-flow attributes, such as protocol, service, connection duration, packet/byte counts and other available traffic statistics. Exact feature names will be confirmed after downloading and inspecting the chosen CSV file. Identifier-like fields (for example, source/destination IP addresses, raw timestamps or record identifiers) will be reviewed carefully and excluded where they could cause target leakage or unrealistic memorization. Categorical features will be encoded and numeric features handled through a scikit-learn preprocessing pipeline.

## 5. Dataset and Data Plan (Software-only Track)
**Dataset:** ToN_IoT Network Dataset, published by UNSW Canberra. The official project page describes heterogeneous IoT/IIoT data and provides processed CSV datasets, including network data, labels, feature descriptions and train/test samples. The dataset includes normal and attack events and is intended for AI-based cybersecurity research.

**Official source:** https://research.unsw.edu.au/projects/toniot-datasets

**Why it fits:** It is IoT/IIoT-focused, contains labelled normal and attack traffic, and is suitable for supervised intrusion-detection experiments. The selected network CSV will be checked to ensure that it contains at least 5,000 records, as required for the software-only track in Phase 2. The exact file name, row count, class distribution and final feature list will be recorded after downloading and inspecting the dataset; these values are not assumed in this proposal.

**Data acquisition and preparation plan:**
1. Download the processed network CSV from the official UNSW source.
2. Inspect dimensions, data types, missing values, duplicates and class balance.
3. Define the binary target from the published label field.
4. Remove irrelevant or leakage-prone identifiers.
5. Encode categorical columns and scale numeric columns where required.
6. Use a stratified train/test split and keep the test set untouched until evaluation.

For Phase 2, a Python script will replay rows from the dataset at a controlled interval to simulate a live stream. No physical sensors are planned because this proposal uses the software-only track.

## 6. Tools and Implementation Plan
Python 3, Google Colab/Jupyter, pandas, NumPy, scikit-learn, Matplotlib/Seaborn and GitHub. The notebook will document data loading, initial inspection and a starter linear-regression exercise using a small public dataset, as requested by the course brief. The main ToN_IoT project is a classification task; therefore, the linear-regression exercise is only a course starter exercise and not the final intrusion-detection model. A simulated CSV stream will be implemented in Python in Phase 2.

## 7. Related Work
1. Alsaedi, A., Moustafa, N., Tari, Z., Mahmood, A. N., & Anwar, A. (2020). “TON_IoT Telemetry Dataset: A New Generation Dataset of IoT and IIoT for Data-Driven Intrusion Detection Systems.” *IEEE Access*, 8, 165130–165150. https://doi.org/10.1109/ACCESS.2020.3022862. This work introduces the ToN_IoT dataset and evaluates machine-learning methods for IoT/IIoT intrusion detection.
2. Moustafa, N., Ahmed, M., & Ahmed, S. (2020). “Data Analytics-Enabled Intrusion Detection: Evaluations of ToN_IoT Linux Datasets.” 2020 IEEE 19th International Conference on Trust, Security and Privacy in Computing and Communications. https://doi.org/10.1109/TrustCom50675.2020.00100. This study evaluates intrusion detection using the Linux component of the ToN_IoT data collection.
3. Dharini, N., Janani, V. S., & Katiravan, J. (2026). “Efficient detection of intrusions in TON-IoT dataset using hybrid feature selection approach.” *Scientific Reports*, 16, Article 7763. https://doi.org/10.1038/s41598-026-37834-y. This recent work discusses feature selection and reducing dependence on IP- and port-based identifiers to improve generalization. **Verify the bibliographic details before final submission.**

## 8. Phase 1 Deliverables and Current Status
Deliverables prepared for this phase: project proposal; selected software-only track and dataset plan; ML task, target and planned features; related work; tools plan; and a starter Colab notebook. The course brief requires instructor approval for the software-only track. Approval has not yet been confirmed, so this remains an action item and must not be represented as approved. Team size in the brief is 2–3 students; if this is an individual project, instructor approval is also required.

**Student contribution:** Abdalrhman Al Mallad — project selection, literature review, dataset plan, proposal preparation and initial notebook setup.

## References
UNSW Canberra. *The ToN_IoT Datasets*. https://research.unsw.edu.au/projects/toniot-datasets
