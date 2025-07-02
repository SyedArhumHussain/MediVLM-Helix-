# MediVLM-Helix-

##  MediVLM-Helix: A Vision-Language Model for Medical Assistance

**MediVLM-Helix** is an AI-powered **Vision-Language Medical Assistance System** designed to interpret **handwritten prescriptions**, extract key information, and provide clinical support through natural language understanding and audio feedback. It integrates OCR, LLM, and TTS technologies into a unified architecture optimized for medical use cases.

---

###  Key Features & Modules

####  1. **OCR Module**

* **Tesseract Engine**: Extracts text from scanned or photographed medical prescriptions.
* **Preprocessing (OpenCV, PIL)**: Enhances image quality for accurate OCR through binarization, noise removal, and contrast adjustment.
* **NER (Named Entity Recognition)**: Identifies and extracts medical fields such as patient name, drug names, dosage, and instructions.

####  2. **LLM Module**

* **LLaMA3-8B (4-bit Quantized)**: A lightweight, high-performance language model used for clinical understanding and question-answering.
* **LoRA Fine-Tuning**: Custom fine-tuning enables domain adaptation for healthcare-specific terminology and dialogues.
* **Safety Prompts**: Injected prompt constraints ensure ethical and safe interactions, avoiding harmful or non-medical advice.

####  3. **TTS Module**

* **TTS Integration**: Converts LLM-generated medical advice or instructions into speech.
* **Audio Output (.mp3)**: Produces clear, patient-friendly voice responses for accessibility, including multilingual support.

####  4. **User Interface**

* **Input Modalities**: Accepts both text-based and image-based user inputs for flexible interactions.
* **Output Modalities**: Returns outputs as either written text or spoken audio, supporting multimodal communication.

---

### Use Cases

* **Prescription Understanding**: Automatically digitizes and interprets handwritten prescriptions.
* **Patient Assistance**: Provides spoken and textual guidance to patients regarding medication and symptoms.
* **Accessibility Support**: Helps visually impaired or illiterate users understand prescriptions using audio output.
* **Clinical Q\&A**: Supports basic symptom checking and medication queries through the LLM.

Here’s a polished technical write-up about your **OCR dataset and research work** for **MediVLM-Helix**, focusing on features, implementation, and research aspects — avoiding app-style language and emphasizing scholarly/engineering detail:

---

##  OCR Dataset and Research in MediVLM-Helix

###  Dataset Overview

The **OCR module** in MediVLM-Helix is trained and evaluated using a comprehensive dataset consisting of:

* **300,000 synthetic and scanned prescription images** for training
* **200 real-world handwritten prescriptions** for testing and validation

The training corpus includes a diverse mix of typed, semi-structured, and handwritten medical prescriptions. These samples reflect variations in layout, font, noise levels, and handwriting styles to simulate real clinical environments.

---

###  Key Dataset Features

* **Diversity in Input Types**: Includes prescriptions in various formats such as printed, scanned, mobile-captured, and noisy handwritten documents.
* **Multilingual Text**: Although the initial phase is English-centric, data also includes Pashto/Urdu terms for regional medicine names and patient instructions.
* **Annotation Format**: Data is annotated using structured XML/JSON formats for:

  * `patient_name`
  * `doctor_name`
  * `medication_name`
  * `dosage`
  * `frequency`
  * `duration`
  * `instructions`
* **Augmentation Techniques**: Applied to increase robustness of OCR:

  * Skew and rotation
  * Gaussian blur and ink-bleed simulation
  * Variable lighting and low-contrast conditions


###  OCR Technical Implementation

#### Preprocessing Pipeline

* **Image Normalization** using OpenCV (grayscale, thresholding, and noise filtering)
* **Layout Detection** for multi-column or block-structured text
* **Region Segmentation** to isolate prescription fields

#### OCR Engine

* Based on **Tesseract 5**, fine-tuned with custom medical lexicons and language models
* Integrated with **PaddleOCR’s lightweight detectors** (in experimental branches)

#### Post-OCR Processing

* **NER (Named Entity Recognition)** module using spaCy + rule-based patterns to extract fields from free text
* **Confidence Scoring** to reject low-certainty outputs and flag manual verification

---

###  Model Testing and Evaluation

A separate test set of **200 real-world handwritten prescriptions** was used to validate OCR accuracy. Key evaluation metrics:

* **Character Error Rate (CER):** \~8.1%
* **Field-level Extraction Accuracy:** \~91% across high-confidence samples
* **Entity-level F1 Score:** 0.87 for medication names, 0.83 for dosage patterns

Observations:

* Errors primarily occurred in highly illegible handwriting and overlapping text regions.
* Domain-specific spell-checking and lexicon-assisted post-processing improved final readability and extraction accuracy.


---

