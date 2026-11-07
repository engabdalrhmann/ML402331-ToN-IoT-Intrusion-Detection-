# ML 402331 – IoT Network Intrusion Detection

**Student:** Abdalrhman Al Mallad  
**University ID:** 2410069

## Project overview
IoT Network Intrusion Detection Using Machine Learning. The project investigates supervised machine-learning models to distinguish normal from malicious IoT network traffic using the ToN_IoT network dataset.

## Dataset
**ToN_IoT Network Dataset**  
Official source: https://research.unsw.edu.au/projects/toniot-datasets

The exact CSV filename, row count, class distribution and final feature list will be recorded after the selected file is downloaded and inspected. The raw dataset is not stored in this repository because of its size.

## Machine-learning task
Supervised binary classification:
- `0` = normal traffic
- `1` = attack traffic

Planned features include network-flow attributes such as protocol, service, connection duration, packet/byte counts and other available traffic statistics. Identifier-like fields will be reviewed for leakage risk.

## Tools
Python 3, Google Colab/Jupyter, pandas, NumPy, scikit-learn, Matplotlib/Seaborn and GitHub.

## Repository structure
- `Phase1/Project_Proposal.md` — Phase 1 proposal.
- `Phase1/Phase1_Starter_Linear_Regression.ipynb` — starter notebook.

## Approval status
The software-only track and individual-work status are pending instructor approval. They must not be treated as approved until the instructor confirms.
