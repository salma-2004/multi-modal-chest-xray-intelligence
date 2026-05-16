# Multi-Modal Chest X-Ray Intelligence System

**Author:** Salma Khairy

This project implements a dual-mode multi-modal chest X-ray intelligence system.

## Overview

The system supports two independent modes:

1. **Report Generation Mode**  
   Generates a structured radiology report (Findings and Impression) directly from a chest X-ray image.

2. **QA Mode (RAG-Based Clinical Question Answering)**  
   Retrieves visually similar chest X-ray cases using CLIP and FAISS, then uses the retrieved reports as context for grounded question answering.

## Dataset

The project uses the provided Kaggle dataset:

- `simhadrisadaram/mimic-cxr-dataset`

## Models Used

### MedGemma 4B (Mandatory)
- Medical vision-language model.
- Used for report generation and clinical question answering.

### CLIP + FAISS
- CLIP extracts image embeddings.
- FAISS performs efficient similarity search.
- Used to retrieve similar cases for the RAG pipeline.

### ColPali (Mandatory)
- Integrated as the required multimodal retrieval model.
- Included for model comparison and retrieval analysis.

## System Architecture

1. Load chest X-ray images.
2. Generate reports using MedGemma.
3. Build a small report database.
4. Extract image embeddings using CLIP.
5. Store embeddings in FAISS.
6. Retrieve similar cases.
7. Use retrieved reports as context.
8. Answer clinical questions using MedGemma.
9. Provide an interactive Gradio demo.

## Features

- Dual-mode multi-modal system
- Structured radiology report generation
- RAG-based clinical question answering
- Image similarity retrieval
- Model comparison
- End-to-end Gradio demo

## Model Comparison Summary

| Model | Purpose | Strength | Limitation |
|------|------|------|------|
| MedGemma 4B | Report Generation + QA | Strong medical reasoning | Requires gated access |
| CLIP + FAISS | Retrieval | Fast similarity search | Not medically specialized |
| ColPali | Multimodal Retrieval | Powerful retrieval model | High GPU requirements |

## How to Run

1. Open the notebook in Google Colab.
2. Enable GPU runtime.
3. Run all cells in order.
4. Open the Gradio public link.
5. Test both Report Generation and QA modes.


