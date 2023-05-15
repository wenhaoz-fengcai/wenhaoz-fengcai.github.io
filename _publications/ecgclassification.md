---
title: "ECG heartbeat classification using deep transfer learning with convolutional neural network and STFT technique"
collection: publications
permalink: /publication/ecgclassification
date: 2022-06-28
venue: 'The 4th International Conference on Computing and Data Science'
paperurl: 'https://arxiv.org/pdf/2206.14200'
---
<span style="color:red">*Best paper award*</span>.
Electrocardiogram (ECG) is a simple non-invasive measure to identify heart-related issues such as irregular heartbeats known as arrhythmias. While artificial intelligence and machine learning is being utilized in a wide range of healthcare related applications and datasets, many arrhythmia classifiers using deep learning methods have been proposed in recent years. However, sizes of the available datasets from which to build and assess machine learning models is often very small and the lack of well-annotated public ECG datasets is evident. In this paper, we propose a deep transfer learning framework that is aimed to perform classification on a small size training dataset. The proposed method is to fine-tune a general-purpose image classifier ResNet-18 with MIT-BIH arrhythmia dataset in accordance with the AAMI EC57 standard. This paper further investigates many existing deep learning models that have failed to avoid data leakage against AAMI recommendations. We compare how different data split methods impact the model performance. This comparison study implies that future work in arrhythmia classification should follow the AAMI EC57 standard when using any including MIT-BIH arrhythmia dataset.