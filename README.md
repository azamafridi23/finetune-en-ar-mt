# Finetuning Helsinki-NLP/opus-mt-tc-big-en-ar on WIT3 Dataset

This repository contains the code used to fine-tune the `Helsinki-NLP/opus-mt-tc-big-en-ar` model on the **WIT3 (Web Inventory of Transcribed and Translated Talks)** dataset for English-to-Arabic machine translation.

## Overview

The objective of this project is to adapt the pre-trained `Helsinki-NLP/opus-mt-tc-big-en-ar` model to the domain-specific context of the WIT3 dataset, which consists of transcribed and translated talks. Fine-tuning on this dataset ensures improved performance in translating English texts to Arabic, particularly within the context of the dataset's domain.

## Dataset

The dataset used is the **WIT3: Web Inventory of Transcribed and Translated Talks**, which contains high-quality English-to-Arabic translations derived from transcriptions of TED talks.

### Dataset Splits

- **Training Set**: Used for model fine-tuning.
- **Validation Set**: Monitored performance during training to prevent overfitting.
- **Test Set**: Used for final evaluation of the model's performance.

## Fine-Tuning Approach

To retain the pre-trained knowledge of the model while improving its domain-specific translation capability, the following strategies were implemented:

1. **Layer Freezing**:
   - The embedding layer and the first three encoder and decoder layers were frozen to preserve foundational language knowledge.
   - The remaining layers were fine-tuned to adapt the model to domain-specific technical terminology.

2. **Evaluation on Multiple Datasets**:
   - The model was evaluated on the **FLORES-101** dataset to verify the retention of its pre-trained multilingual capabilities.

## Results

### WIT3 Dataset

- **Baseline Model BLEU Score**: 11.2
- **Fine-Tuned Model BLEU Score**: 17.4
  - Achieved after 30 epochs with a batch size of 16.
  - Demonstrated substantial improvement, especially in translating complex technical terms.

### FLORES-101 Dataset

- **Baseline Model BLEU Score**: 30.8
- **Fine-Tuned Model BLEU Score**: 29.8
  - A slight decrease, but the model retained most of its pre-trained generalization capability.

These results illustrate that the fine-tuning process effectively enhanced the model's capacity to handle domain-specific translations while maintaining robust pre-trained knowledge.

