# ZTA-RAD: Zero Trust Architecture – Risk Assessment Dataset

## Quick Start
This repository presents ZTA-RAD, a dataset for risk assessment of Insider Threats, designed under the paradigm of Zero Trust Architecture (ZTA).
The dataset was derived and expanded from the CERT Insider Threat Dataset, incorporating metrics from logon, devices, and HTTP access, and labeled into low, medium, and high risk using two approaches:

- Expert curation;
- Classification by multiple LLMs (Grok, ChatGPT, Gemini, Copilot, and DeepSeek).

Experiments with MLP, Random Forest, and SVM were conducted in balanced and imbalanced scenarios, highlighting the impact of SMOTE on model training.
It is recommended to use a Linux environment for better compatibility and performance.

### README.md structure
- Dependencies
- Components
- Hardware
- Software
- Repository Structure
- Environment

### Dependencies 
- Python 3.11+
- Numpy 2.1.2
- Pandas 2.2.3
- Scikit-learn 0.13.0
- Imbalanced-learn (SMOTE) 0.12.3
- Matplotlib 3.9.2
- Seaborn 0.13.2 
- TensorFlow 2.15.0
- Keras 3.5.0

### Components
- ZTA-RAD Dataset: enriched logs from logon, devices, and HTTP, derived from CERT Dataset.
- Risk labeling: human expert + inference from 5 LLMs.
- Classifiers: MLP, Random Forest, and SVM.
- Balancing: SMOTE technique to reduce bias.
- ML Pipelines: preparation, training, validation, and model evaluation.

### Hardware
- Multicore CPU (≥ 4 cores)
- RAM ≥ 16GB
- Storage ≥ 10GB (to handle CERT fragments + ZTA-RAD)
- (Optional) CUDA-enabled GPU for neural network acceleration

### Software
- Linux (Ubuntu/Debian or Fedora) recommended
- Docker (optional, for reproducibility packaging)

### Repository Structure

#data – balanced and imbalanced datasets
- Balanced datasets → Feature sets and labeling produced by the expert and the Gemini model, balanced using SMOTE.
- Imbalanced datasets → Feature sets and labeling produced by LLMs (Grok, ChatGPT, Gemini, Copilot, and DeepSeek).

#source
- insider_trhreats_V3.ipynb → 01_setup_dataset.ipynb
Preprocessing and consolidation of ZTA-RAD (cleaning, unification, and structuring).

- treinamento_especialista.ipynb → 02_risk_labeling.ipynb
Risk labeling with human expert.

- treinamento_gemini.ipynb → 03_risk_labeling_LLM.ipynb
Risk labeling with LLM (e.g., Gemini) – part of the hybrid labeling process.

#figures
- Generated figures and plots.

### Setting the Environment

# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
