# Multitask Learning for QUIC Traffic Classification

A deep learning project for analyzing QUIC network traffic using a multitask Convolutional Neural Network (CNN) under limited labeled data.

## Overview

This project applies multitask learning to QUIC traffic analysis. A shared neural network representation is used to perform three related tasks simultaneously:

- Traffic classification
- Bandwidth prediction
- Duration prediction

The approach is designed to make better use of limited labeled network traffic data by learning shared representations across multiple prediction tasks.

## Methodology

The model processes network traffic features and uses a shared CNN-based representation followed by task-specific output layers.

The three outputs are:

1. **Bandwidth** — predicts the bandwidth category.
2. **Duration** — predicts the traffic duration category.
3. **Traffic Class** — classifies the type of network traffic.

A mask is also used for the traffic classification task to support the multitask learning setup.

## Model Architecture

The neural network consists of:

- Shared CNN layers for feature extraction
- Fully connected layers for shared representations
- Separate classification heads for bandwidth, duration, and traffic class
- Softmax activation for the three prediction tasks

The model is trained jointly using categorical cross-entropy losses for all three tasks.

## Training

The model uses:

- Adam optimizer
- Categorical cross-entropy loss
- Batch size: 64
- 20 training epochs
- Validation data for monitoring model performance

## Technologies

- Python
- TensorFlow / Keras
- NumPy
- Wireshark

## Purpose

This project was developed to explore multitask learning for network traffic analysis and to investigate how shared representations can support multiple prediction tasks when labeled network traffic data is limited.
