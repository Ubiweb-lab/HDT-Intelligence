# Human Digital Twin Intelligence Platform

**Human Digital Twin Intelligence: Integrating Multimodal AI and Generative Models for Non-Intrusive Health and Activity Monitoring**

This repository contains the research code, documentation, and experimental workflow for developing a Human Digital Twin (HDT) platform that combines multimodal sensing, deep learning, radar-based vital sign monitoring, and Large Language Models (LLMs) for privacy-preserving health and activity monitoring.

The project aims to support non-intrusive monitoring of human activity, behaviour, vital signs, and well-being in real-world indoor environments such as homes, workplaces, laboratories, community health spaces, and aged-care settings.

---

## Project Overview

Current human activity recognition and health-monitoring systems often rely on fragmented, intrusive, or single-source sensing approaches. Many systems also provide limited explanation of how activity or physiological patterns are detected.

This project investigates how multiple sensing modalities can be integrated into an explainable Human Digital Twin platform. The system uses environmental and wearable sensors to model human activity and physiological responses, while LLMs generate natural-language summaries to make system outputs more interpretable and human-centred.

The platform is designed around four principles:

1. **Privacy-preserving sensing**  
   Use of non-intrusive sensing technologies, including radar, passive infrared, and depth sensing, to reduce reliance on identifiable video data.

2. **Multimodal activity and vital sign modelling**  
   Integration of wearable and environmental sensors to capture movement, context, respiration, and heart-related indicators.

3. **Explainable AI**  
   Use of LLMs to convert complex sensor outputs into clear summaries and explanations.

4. **Human-centred digital health**  
   Development of an interpretable system that can support future health, well-being, and community monitoring applications.

---

## Research Aims

The project aims to:

- Develop a multimodal sensing framework for human activity recognition.
- Estimate vital-sign indicators using radar-based and wearable sensing.
- Fuse wearable, radar, and environmental sensor data into a Human Digital Twin model.
- Use deep learning models to recognise physical activities and behavioural patterns.
- Use LLMs to generate interpretable, conversational summaries of system outputs.
- Evaluate model accuracy, reliability, usability, interpretability, and user trust.
- Create an ethically managed multimodal dataset for future AI and digital health research.

---

## Sensing Modalities

The HDT platform may include the following sensing technologies:

| Sensor Type | Purpose |
|------------|---------|
| IMU sensors | Capture body movement, acceleration, orientation, and functional activity patterns |
| mmWave radar | Support non-contact activity sensing and vital sign monitoring |
| Hexoskin smart vest | Record reference physiological signals such as respiration and heart rate |
| Depth sensors | Capture non-identifiable body posture and movement structure |
| Passive infrared sensors | Detect movement and occupancy patterns in indoor environments |
| Wearable ECG or heart-rate devices | Provide reference physiological measurements for validation |

---

## AI and Data Analysis Pipeline

The project follows a multimodal AI pipeline:

1. **Data Collection**  
   Participants perform functional physical activities while data are collected from wearable and environmental sensors.

2. **Pre-processing**  
   Sensor data are synchronised, cleaned, filtered, and segmented into fixed-length time windows.

3. **Human Activity Recognition**  
   Deep learning models are trained to classify activities such as sitting, standing, walking, lying, and transitional movements.

4. **Vital Sign Estimation**  
   Radar and wearable data are analysed to estimate physiological indicators such as breathing-rate and heart-rate-related patterns.

5. **Multimodal Fusion**  
   Activity, context, and physiological data are combined to construct a Human Digital Twin representation.

6. **LLM-based Explanation**  
   LLMs convert processed model outputs into natural-language summaries, explanations, and conversational responses.

7. **Evaluation**  
   System performance is assessed using classification, estimation, agreement, usability, and trust metrics.

---

## Role of Large Language Models

LLMs are used to make the Human Digital Twin more understandable to researchers, participants, and future users.

They may support:

- Plain-language summaries of activity and vital sign patterns.
- Explanations of why the system inferred a particular activity or pattern.
- Conversational interaction with processed HDT outputs.
- Structured reports for researchers or health professionals.
- Improved transparency and usability of AI-generated outputs.

LLMs are not used to make clinical diagnoses or provide medical advice. Their outputs are constrained to processed, anonymised, and validated system results.

---

## Example Use Case

A future HDT summary may look like:

> During the activity session, the participant completed several transitions from sitting to standing and walking. The system detected mostly light-intensity movement, with stable breathing-rate trends during seated and standing activities. Increased movement variability was observed during walking tasks.

This type of summary is intended to make technical model outputs easier to interpret while preserving privacy and avoiding unsupported clinical claims.

---

## Repository Structure

```text
hdt-intelligence/
├── data/                   # Data storage placeholders; raw participant data are not committed
├── docs/                   # Project documentation, protocols, and ethics-related templates
├── notebooks/              # Exploratory analysis and model development notebooks
├── src/                    # Source code for processing, modelling, and evaluation
│   ├── preprocessing/      # Sensor cleaning, filtering, synchronisation, and segmentation
│   ├── models/             # Deep learning and multimodal fusion models
│   ├── radar/              # Radar signal-processing and vital sign estimation modules
│   ├── imu/                # IMU processing and activity recognition modules
│   ├── llm/                # LLM summarisation and explanation components
│   └── evaluation/         # Metrics, validation, and visualisation utilities
├── tests/                  # Unit and integration tests
├── configs/                # Experiment and model configuration files
├── scripts/                # Training, evaluation, and data-processing scripts
├── requirements.txt        # Python dependencies
├── environment.yml         # Optional conda environment file
└── README.md
```

---

## Installation

> Installation instructions will be updated as the research codebase matures.

Clone the repository:

```bash
git clone https://github.com/<your-org>/<your-repo>.git
cd <your-repo>
```

Create a Python environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Alternatively, using conda:

```bash
conda env create -f environment.yml
conda activate hdt-intelligence
```

---

## Example Workflow

```bash
# Pre-process multimodal sensor data
python scripts/preprocess_data.py --config configs/preprocessing.yaml

# Train a human activity recognition model
python scripts/train_har_model.py --config configs/har_model.yaml

# Estimate radar-based vital signs
python scripts/run_vital_sign_estimation.py --config configs/radar_vitals.yaml

# Generate an LLM-based summary from processed outputs
python scripts/generate_summary.py --input outputs/session_results.json
```

---

## Evaluation Metrics

The system may be evaluated using:

### Human Activity Recognition

- Accuracy
- Precision
- Recall
- F1-score
- AUC-ROC
- Confusion matrices
- Leave-one-subject-out validation
- k-fold cross-validation

### Vital Sign Estimation

- Mean absolute error
- Root mean squared error
- Correlation coefficients
- Intraclass correlation coefficients
- Bland-Altman analysis
- Agreement with wearable or ECG-derived reference data

### Explainability and Usability

- Participant and researcher feedback
- Explanation clarity
- Perceived trust
- Usability assessment
- Expert review of LLM-generated summaries

---

## Data Governance and Ethics

This project involves human participant data and must be conducted under appropriate ethics approval.

Important data-handling principles:

- Raw participant data must not be committed to this repository.
- Identifiable or sensitive data must be securely stored in approved institutional systems.
- Data must be anonymised or de-identified before analysis where possible.
- Access to participant data must be restricted to authorised research personnel.
- LLM-based summaries must use only processed and approved system outputs.
- The system must not provide clinical diagnosis or medical advice.

---

## Privacy and Safety Notes

This platform is a research prototype. It is not a medical device and should not be used for clinical decision-making without further validation, regulatory review, and appropriate health-sector governance.

Radar, wearable, and environmental sensing outputs may contain uncertainty. All AI-generated classifications, vital-sign estimates, and LLM summaries should be reviewed carefully and interpreted within the limits of the study design.

---

## Technologies

The project may use:

- Python
- PyTorch
- TensorFlow
- NumPy
- SciPy
- pandas
- scikit-learn
- Matplotlib
- Radar signal-processing libraries
- LLM APIs or locally hosted language models
- Wearable and sensor SDKs

---

## Team and Collaborators

This project is led by researchers at Auckland University of Technology (AUT), bringing together expertise in:

- Artificial intelligence
- Pervasive computing
- Human activity recognition
- Wireless and radar sensing
- Vital sign monitoring
- Human-computer interaction
- Public health
- Physical activity and well-being
- Responsible and explainable AI

---

## Funding

This work is associated with the **DCT Project Development Fund 2026** project:

**Human Digital Twin Intelligence: Integrating Multimodal AI and Generative Models for Non-Intrusive Health and Activity Monitoring**

---

## Citation

If you use this repository or build on this work, please cite the project or associated publications once available.

```bibtex
@misc{hdt_intelligence_2026,
  title        = {Human Digital Twin Intelligence: Integrating Multimodal AI and Generative Models for Non-Intrusive Health and Activity Monitoring},
  author       = {Yongchareon, Sira and collaborators},
  year         = {2026},
  institution  = {Auckland University of Technology},
  note         = {Research project repository}
}
```

---

## License

The license for this repository will be confirmed before public release.

Recommended options:

- MIT License for open-source research code.
- Creative Commons license for non-code documentation.
- Restricted access terms for datasets involving human participant data.

---

## Contact

For questions about the project, please contact:

**A/Prof. Sira Yongchareon**  
Auckland University of Technology  
AUT AI Research Centre  
Email: sira.yongchareon@aut.ac.nz
