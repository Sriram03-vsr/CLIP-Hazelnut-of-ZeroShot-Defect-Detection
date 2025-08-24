# CLIP-Hazelnut-of-ZeroShot-Defect-Detection
Zero-Shot Defect Classification on Hazelnuts using OpenAI’s CLIP model. This project leverages vision-language embeddings to classify hazelnut defects without task-specific training, enabling fast and scalable quality inspection for agricultural and industrial applications.
CLIP Zero-Shot Defect Classification

This project demonstrates zero-shot defect classification using OpenAI’s CLIP model on the hazelnut subset of the MVTec-AD dataset
.
It enables defect detection without task-specific training — useful for automated quality inspection in agriculture and industry.

 Overview

This project performs:

 Download & setup of the MVTec-AD hazelnut dataset

 Implementation of a Pydantic configuration for defect classification

 Creation of a CLIP-based zero-shot classifier

 Running classification on the test set

 Generating a confusion matrix & analysis

 Providing observations and recommendations

 Setup

Install dependencies:

pip install -r requirements.txt


Run the complete workflow:

python scripts/complete_workflow.py

 Project Structure

spec.py → Pydantic configuration (classes, prompts, model)

clip_ac.py → Core CLIP classifier implementation

scripts/ → Utilities (dataset setup, analysis, git workflow)

data/ → Contains the MVTec-AD hazelnut subset

 Hazelnut Defect Classes

The hazelnut subset includes:

good → Normal hazelnuts

crack → Hazelnuts with cracks

cut → Hazelnuts with cuts

hole → Hazelnuts with holes

print → Hazelnuts with print defects

 Usage
Quick Start
from clip_ac import run_classification
from scripts.run_classification_and_analysis import generate_confusion_matrix, analyze_results

# Run classification
results = run_classification("data/hazelnut/test")

# Generate confusion matrix
cm = generate_confusion_matrix(results)

# Analyze results
analysis = analyze_results(results)

Custom Configuration
from spec import DefectClassificationSpec
from clip_ac import CLIPDefectClassifier

# Define custom config
config = DefectClassificationSpec(
    class_names=["good", "crack", "cut", "hole", "print"],
    prompts=[
        "a photo of a perfect hazelnut",
        "a photo of a cracked hazelnut",
        "a photo of a cut hazelnut",
        "a photo of a hazelnut with holes",
        "a photo of a hazelnut with print defects"
    ],
    model_name="ViT-L/14"
)

# Initialize classifier
classifier = CLIPDefectClassifier(config)

 Results & Analysis

The system outputs:

 Overall accuracy metrics

 Per-class performance

 Confidence score distribution

 Misclassification patterns

Recommendations for improvement

 Git Workflow

Clone the repository

Create/checkout a feature branch

Implement changes

Commit modifications

Merge back into main

Verify with git log and git show

Notes

The MVTec-AD dataset must be downloaded manually from the official site

CLIP model weights are auto-downloaded on first run

GPU acceleration is used if available

Results include detailed analysis & improvement suggestions

Now it’s GitHub-ready — professional, readable, and structured.

Do you also want me to add GitHub badges (Python version, license, dataset, etc.) at the top for extra polish?

ChatG
