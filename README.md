# ASL Translate App

A real-time American Sign Language (ASL) to English text translation app built using deep learning and computer vision. This project aims to bridge communication gaps for the Deaf and Hard-of-Hearing community by converting ASL sentences captured through a webcam into readable English text on the screen.

## Project Purpose:

The goal of this project is to build an end-to-end system that:
- Accepts live video input from a webcam
- Detects and interprets full ASL sentences using hand gestures, body posture, and facial expressions
- Outputs fluent English translations in real time

## Proposed Model Overview:

We will use a two-stage deep learning pipeline trained on the [2M-FLORES-ASL dataset](https://huggingface.co/datasets/facebook/2M-Flores-ASL):

1. Video to ASL Gloss Prediction:  
   - Uses MediaPipe to extract keypoints (hands, pose, face) from each frame  
   - A sequence model (BiLSTM / Transformer) is trained to predict ASL gloss (e.g., "SHE GO STORE")

2. Gloss to English Sentence Translation:
   - Fine-tunes a transformer-based language model (e.g., T5 or BART)  
   - Converts ASL gloss to fluent English (e.g.,"She is going to the store.")

## Dataset:

- 2M-FLORES-ASL: Includes over 2,000 video samples of real ASL sentences with aligned gloss and English text
- Stored securely via Azure Blob Storage for team access and efficient retrieval
