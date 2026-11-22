# YouTube walkthrough — CoffeeVision

**Suggested title:** I Built an AI-Assisted Coffee Ripeness Classification Prototype | CoffeeVision

**Target length:** 6–8 minutes  
**Important:** Say clearly that the initial code was generated with substantial AI assistance and that the notebook has not yet been successfully executed/validated. Do not present mock UI confidence values as measured model accuracy.

## 0:00–0:35 — Opening

"Hi everyone. In this video, I’m introducing CoffeeVision, an experimental project exploring how computer vision and AI could help assess coffee cherry ripeness and coffee bean quality. The motivation is to explore whether image-based analysis could support more consistent initial sorting. This is a prototype, not a production grading tool."

## 0:35–1:20 — The problem

"Coffee cherries pass through different ripeness stages. If sorting is inconsistent, cherries at different stages can be processed together. Coffee beans can also have visible defects. My project explores these as two related but separate classification problems: cherry ripeness and bean quality."

Show example images only if you have permission to use them. Explain that lighting, camera angle, background, variety, and image quality can affect visual classification.

## 1:20–2:15 — What I created

"CoffeeVision has two parts. First, a notebook that outlines a machine-learning experiment for coffee cherry ripeness. Second, a browser interface where a user can upload an image and view an AI-generated analysis. The interface is a prototype; it is not yet connected to the trained models in the notebook."

Show the HTML upload screen. Do not claim that the three model options currently run actual MobileNetV2 or InceptionV3 inference.

## 2:15–3:35 — Notebook walkthrough

"The notebook is structured around data preparation, class inspection, exploratory analysis, baseline experiments, improved training configurations, and evaluation. The cherry dataset code expects four labels: unripe, semi-ripe, ripe, and overripe."

Explain these terms in your own words:
- CNN: learns visual patterns from image pixels.
- Data augmentation: creates varied training examples through transformations.
- Batch normalisation: helps stabilise training.
- Dropout: reduces reliance on particular neurons and can help reduce overfitting.
- Early stopping: stops training when validation performance stops improving.
- Confusion matrix: shows which classes are confused with one another.

"The notebook also contains proposed experiments involving ResNet18, InceptionResNetV2, YOLOv11, and YOLOv12. These are code workflows in the notebook; I will only report results after I have run and checked them."

## 3:35–4:35 — How the current web prototype works

"The current HTML accepts an image, previews it, and sends it to a Claude vision API request. The selected model name is currently used in the prompt; it does not actually load the corresponding TensorFlow or YOLO model. That is an important limitation I identified during code review."

Show the upload and results layout, but label any output as an AI-generated visual assessment rather than a validated measurement.

## 4:35–5:45 — Challenges and what I learned

"One challenge was distinguishing a polished interface from a functioning machine-learning pipeline. A model name in a dropdown does not mean that model is being executed. I also identified that API credentials must never be exposed in browser code or public repositories. The notebook needs execution, dataset checks, and a reproducible evaluation before its performance can be claimed."

## 5:45–6:50 — Next steps

"My next steps are to run the four-class coffee cherry experiment, verify the dataset and class mapping, train and evaluate one model, save the model weights, and connect a secure backend inference endpoint to the interface. After that, I can develop a separate bean-defect dataset and classifier."

## 6:50–7:10 — Closing

"CoffeeVision is an early learning and research prototype. I’m sharing the code and its current limitations openly, and I plan to document the improvements as I validate the system. Thank you for watching."

## Questions to prepare for

1. **Did you write all the code yourself?**  
   "No. I used Claude and other AI assistance to generate substantial parts of the initial code. I am being transparent about that. My current work is reviewing the generated implementation, understanding the pipeline, validating it, and improving it."

2. **Have you trained the models?**  
   "The notebook contains training workflows, but the uploaded version has no saved execution outputs. I cannot claim successful training or accuracy yet."

3. **Does the web app use MobileNetV2 or InceptionV3?**  
   "Not currently. The dropdown changes the prompt label, while the browser code sends the image to Claude. Connecting actual trained models is a planned improvement."

4. **Can a coffee business rely on the result?**  
   "Not yet. It needs representative data, controlled evaluation, external testing, and validation with coffee experts before operational use."

5. **What did you personally contribute?**  
   Describe only work you actually performed: defining the problem, organising the project, reviewing the generated code, documenting limitations, testing, and implementing any fixes you personally complete.
