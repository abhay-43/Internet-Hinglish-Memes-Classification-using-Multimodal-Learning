# Internet Hinglish Memes Classification using Multimodal Learning

## Overview
This project focuses on classifying Internet Hinglish memes using multimodal learning techniques. The aim is to leverage both textual and visual information inherent in memes to accurately categorize them into predefined classes or themes.

## Problem Statement
Within the Memotion 3.0 competition, the project addresses two primary tasks:
- **Task A - Sentiment Analysis**: Classifying memes into positive, negative, or neutral categories based on the underlying sentiment conveyed by the meme content.
- **Task B - Emotion Classification**: Identifying various emotional nuances within memes, including humor, sarcasm, offensiveness, and motivational content. Memes may belong to more than one emotion category.

## Dataset
The dataset is sourced from the Memotion 3.0 competition and includes 10,000 internet memes, with a subset featuring Hinglish (a mix of Hindi and English) text. The dataset is divided into three subsets:
- **Training Set**: 7,000 memes
- **Validation Set**: 1,500 memes
- **Test Set**: 1,500 memes

Each subset includes additional metadata provided in CSV files, including image IDs, labels indicating humor, sarcasm, offensiveness, and motivational content, and the overall sentiment. Optical Character Recognition (OCR) text extracted from the memes is also provided.

## Model Architecture
The project utilizes the following models:
- **DistilBERTMulti**: A multilingual version of the DistilBERT model, trained on 104 languages, including Hindi and English. It is used for text analysis.
- **VGG16**: A convolutional neural network model pre-trained on the ImageNet dataset, used for image analysis.
- **Multimodal Model**: Combines DistilBERTMulti and VGG16 to leverage both text and image features for classification.

### Multimodal Model Structure
- **Text Processing**: Handled by DistilBERTMulti, capturing semantic nuances and contextual cues from the text.
- **Image Processing**: Handled by VGG16, extracting visual features from images.
- **Feature Fusion**: Combines features extracted from both text and images to learn joint representations that capture both visual and textual semantics.

## Performance Metrics

### Task A - Sentiment Analysis

| Model                          | Accuracy | Precision | Recall | F1-score |
|--------------------------------|----------|-----------|--------|----------|
| Text Only (DistilBERTMulti)    | 0.3458   | 0.3353    | 0.3373 | 0.3339   |
| Image Only (VGG16)             | 0.3567   | 0.3723    | 0.3567 | 0.3600   |
| Multimodal (DistilBERTMulti + VGG16) | 0.3687 | 0.3548  | 0.3687 | 0.3563   |

### Task B - Emotion Classification

#### F1-Weighted Scores

| Model                          | Humor (H) | Sarcasm (S) | Offensive (O) | Motivational (M) |
|--------------------------------|-----------|-------------|---------------|------------------|
| Text Only (DistilBERTMulti)    | 0.8659    | 0.8323      | 0.4788        | 0.9326           |
| Image Only (VGG16)             | 0.8996    | 0.8720      | 0.4388        | 0.9475           |
| Multimodal (DistilBERTMulti + VGG16) | 0.9004 | 0.8764 | 0.4198        | 0.9562           |

#### Overall Average Scores

| Model                          | Accuracy | Precision | Recall | F1-score |
|--------------------------------|----------|-----------|--------|----------|
| Text Only (DistilBERTMulti)    | 0.7665   | 0.7934    | 0.7665 | 0.7774   |
| Image Only (VGG16)             | 0.8121   | 0.8029    | 0.8121 | 0.7894   |
| Multimodal (DistilBERTMulti + VGG16) | 0.8203 | 0.7972  | 0.8203 | 0.7882   |

## Conclusion
This project demonstrates the effectiveness of multimodal learning techniques in classifying internet memes, particularly those with Hinglish content. By combining the strengths of textual and visual models, the proposed approach achieves competitive performance in both sentiment analysis and emotion classification tasks. Further work can explore refining the multimodal model and addressing additional tasks like intensity or scale of emotional expression within memes.

## References
- Memotion 3.0 competition dataset
- DistilBERTMulti and VGG16 model architectures
- Results analysis and performance metrics from project documentation
