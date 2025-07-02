# MediVLM-Helix-
Sure! Here's a well-structured description of your model **MediVLM-Helix** and its features, suitable for a research paper, portfolio, or project report:

---

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

* **Open-Source TTS Integration**: Converts LLM-generated medical advice or instructions into speech.
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

---

