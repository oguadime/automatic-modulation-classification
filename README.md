2# automatic-modulation-classification
Deep learning for automatic modulation classification from raw I/Q signals using 1D CNN and ResNet architectures on the RadioML 2016.10a dataset.

## Overview

Automatic modulation classification is a fundamental task in wireless communications and signal intelligence. In this project, raw I/Q samples are used as input to deep neural networks that learn discriminative features directly from the signal. The repository includes model development, training, evaluation, and performance analysis for both a baseline 1D CNN and a custom 1D ResNet architecture.

## Results

Under the standard stratified train-validation-test split over both modulation class and SNR, the 1D CNN achieved **56.80%** test accuracy, while the 1D ResNet achieved **60.44%** test accuracy. Accuracy increased with SNR for both architectures, with the ResNet outperforming the CNN across most moderate and high SNR levels.

At higher SNR values, both models performed much better. The CNN reached about **84.41%** accuracy at **18 dB**, while the ResNet reached about **91.05%** accuracy at **14 dB** and remained above **90%** across several high-SNR test levels. These results show that both architectures benefit from cleaner signals, with the ResNet delivering the stronger overall high-SNR performance.

To study robustness under distribution shift, a second experiment trained the models only on high-SNR samples and tested them on separate low-SNR samples. In this more challenging setting, performance dropped substantially for both models, with the CNN achieving **18.45%** test accuracy and the ResNet achieving **19.17%**. Even under this setup, the ResNet retained a small but consistent advantage.
