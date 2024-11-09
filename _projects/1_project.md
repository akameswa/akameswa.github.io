---
layout: page
title: Automated Filtering of Synthetic Training Data for Manufacturing QC
importance: 1
category: work
related_publications: false
---

### Introduction
In today's competitive manufacturing landscape, delivering products of pristine quality is paramount. For industry leaders like Apple, manual inspection is impractical given the immense scale of production. A critical challenge emerges when introducing new product lines: the lack of extensive training data for defect detection models. This data scarcity can potentially compromise quality control for novel products, directly impacting consumer satisfaction and manufacturing efficiency.

### Project Objectives
This internship project addressed two key challenges:
1. Evaluating and implementing automated methods to filter synthetic training data, focusing on removing unrealistic artificially generated images
2. Improving the quality of training datasets for defect detection models through systematic comparison of filtering approaches

### Methods
The cornerstone of effective supervised machine learning models lies in the quality of training data. While Apple employs artificial image generation techniques for new products, this process often yields unrealistic images that compromise model performance. To reduce the burden on human labellers, we investigated four automated approaches:

<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; margin: 20px 0;">
    <div style="text-align: center;">
        <img src="/assets/img/classification-model-histogram.png" width="200" height="150" alt="Classification Model Results" style="width: 100%; height: auto;">
        <em>Figure 1: Classification Model</em>
    </div>
    <div style="text-align: center;">
        <img src="/assets/img/voxel.png" width="200" height="150" alt="Voxel Embeddings" style="width: 100%; height: auto;">
        <em>Figure 2: Voxel Embeddings</em>
    </div>
    <div style="text-align: center;">
        <img src="/assets/img/mm1-histogram.png" width="200" height="150" alt="Multimodal Model Results" style="width: 100%; height: auto;">
        <em>Figure 3: Multimodal Model</em>
    </div>
    <div style="text-align: center;">
        <img src="/assets/img/image-reward-histogram.png" width="200" height="150" alt="ImageReward Results" style="width: 100%; height: auto;">
        <em>Figure 4: ImageReward</em>
    </div>
</div>

1. The classification model, initially trained to distinguish between escape and overkill cases, failed to transfer effectively to our use case.
2. Embeddings from pre-trained models available in Voxel [3] showed significant overlap between realistic and unrealistic images.
3. Our internal foundational multimodal model yielded similar scores across images, failing to provide clear differentiation.
4. The ImageReward model [2] demonstrated the best performance in filtering unrealistic images.

### Results and Discussion
The ImageReward model [2] emerged as the most effective solution, demonstrating superior performance in filtering unrealistic images. By implementing a threshold score of -2, we successfully eliminated approximately 25% of unrealistic images from a dataset of 2000 images. This achievement is particularly significant as it required no manufacturing-specific training.

### Personal Contribution
As an intern, I led the evaluation of multiple automated filtering approaches and implemented the successful ImageReward-based solution. This work directly contributed to streamlining the data preprocessing pipeline and enhancing the efficiency of defect detection processes for new products.

### References
[1] D. Weimer, B. Scholz-Reiter, and M. Shpitalni, "Design of deep convolutional neural network architectures for automated feature extraction in industrial inspection," CIRP Annals, vol. 65, no. 1, pp. 417–420, 2016, doi: https://doi.org/10.1016/j.cirp.2016.04.072.

[2] J. Xu et al., "ImageReward: Learning and Evaluating Human Preferences for Text-to-Image Generation," arXiv.org, Jun. 06, 2023. https://arxiv.org/abs/2304.05977

[3] "FiftyOne — FiftyOne 0.19.1 documentation," docs.voxel51.com. https://docs.voxel51.com/