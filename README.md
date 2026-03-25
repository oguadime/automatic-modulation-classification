# automatic-modulation-classification
Deep learning for automatic modulation classification from raw I/Q signals using 1D CNN and ResNet architectures on the RadioML 2016.10a dataset.

## Overview

Automatic modulation classification is a fundamental task in wireless communications and signal intelligence. In this project, raw I/Q samples are used as input to deep neural networks that learn discriminative features directly from the signal. The repository includes model development, training, evaluation, and performance analysis for both a baseline 1D CNN and a custom 1D ResNet architecture.

## Results

On the standard test split, the 1D CNN achieved **56.80%** accuracy, while the 1D ResNet achieved **60.44%** accuracy. Accuracy generally improved as SNR increased, and the ResNet delivered stronger performance across most moderate and high SNR levels.

To study robustness under distribution shift, a second experiment trained the models on high-SNR samples and tested them on separate low-SNR samples. In this setting, performance dropped substantially for both models, with the CNN achieving **18.45%** test accuracy and the ResNet achieving **19.17%**. Even under this more challenging setup, the ResNet retained a small but consistent advantage.
