# CoffeeVision — Coffee Ripeness & Defect Classification (AI-assisted prototype)

> **Project status: experimental / not yet validated.**
> This repository contains AI-generated starter code and a browser prototype. It is not evidence of a trained, tested, or production-ready machine-learning system.

## Project overview

CoffeeVision explores two related computer-vision use cases:

1. **Coffee cherry ripeness:** the notebook defines four dataset classes: `overripe`, `ripe`, `semi_ripe`, and `unripe`.
2. **Coffee bean quality / defects:** the HTML interface describes bean categories such as Specialty, Good Bean, Slight Defect, Defect, and Severe Defect. The current HTML does not implement a dedicated trained bean-defect model.

The project files were generated with substantial AI assistance. They are published transparently as an experimental starting point, not as independently verified model results.

## What's in this repository

- `notebooks/CoffeeVision_experiment_redacted.ipynb` — AI-generated Colab-style experiment scaffold. It contains code for dataset preparation, exploratory plots, baseline and improved CNN/ResNet18/InceptionResNetV2 workflows, YOLOv11/YOLOv12 classification training, and evaluation plots/metrics.
- `prototype/CoffeeVision.html` — front-end prototype for image upload, model-option selection, and displaying a Claude-generated image analysis response.
- `docs/CV_ENTRY.md` — truthful CV wording.
- `docs/YOUTUBE_SCRIPT.md` — suggested explanation for a project walkthrough video.
- `docs/LINKEDIN_POST.md` — launch post draft.
- `docs/UPLOAD_GUIDE.md` — GitHub publishing steps and security checklist.

## Important technical status and limitations

### 1. Notebook execution has not been demonstrated

The uploaded notebook had no saved cell execution counts or outputs. Therefore this repository does **not** currently establish that:
- the dataset downloaded successfully;
- any model training completed;
- saved model weights exist;
- the reported accuracy, precision, recall, or F1 scores are known;
- the experiment is reproducible end to end.

Do not add performance numbers to a CV, README, or video until you execute the notebook and verify them on a held-out test set.

### 2. The HTML model selector is currently a UI label, not model inference

The HTML interface offers MobileNetV2, InceptionV3, and Ensemble options. Its classification function sends the uploaded image to the Anthropic Claude API and includes the selected option's name in the prompt. It does not load or execute MobileNetV2, InceptionV3, TensorFlow, or Keras models. The UI's TensorFlow/Keras metadata is therefore not proof that those frameworks power the browser classification.

### 3. API integration needs redesign before deployment

The HTML calls the Anthropic Messages API directly from browser JavaScript and does not show a secure server-side API-key flow. Do not add an API key to front-end code. A proper version should use a backend service that keeps credentials in environment variables or a secret manager, validates uploads, handles API errors, and returns a structured response.

### 4. Dataset and evaluation need review

Before claiming model quality:
- verify the dataset's licence and permission to redistribute it;
- record the exact dataset version and class counts;
- inspect train/validation/test splits for leakage;
- verify label mappings across Keras and YOLO;
- use a held-out test set only for final evaluation;
- report per-class precision, recall, F1, confusion matrix, and class imbalance;
- compare a simple baseline against improved models;
- save environment versions and training configuration.

## Suggested next milestone

Make one narrow end-to-end workflow work first: coffee cherry ripeness with four classes. Run the notebook in Colab, fix errors, verify the data split, train one model, evaluate it, save its weights, and then build an inference endpoint. Add bean-defect classification as a separate dataset/model only after the cherry workflow is reproducible.

## AI assistance disclosure

AI tools generated substantial portions of the initial notebook and HTML implementation. The repository owner is publishing and documenting the prototype, reviewing its design and limitations, and intends to learn, verify, and improve it. Do not describe generated code as independently authored or claim understanding of components that have not been personally reviewed.
