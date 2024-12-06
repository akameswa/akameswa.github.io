---
layout: page
title: Supervised Learning Models for Automated Inspection
importance: 3
img: assets/img/supervised.png
category: work
---

### Introduction
In today's competitive manufacturing landscape, ensuring product quality is crucial for both consumer safety and business success. While computer vision has revolutionized automated inspection, the challenge of limited training data for new product lines creates a significant barrier to implementing effective quality control systems. Our project addresses this critical need by developing and optimizing supervised learning models that can perform reliably even with limited initial data.

### Project Objective
This project aims to enhance manufacturing quality control through advanced computer vision techniques, making automated inspection more accessible and effective for new product lines while reducing the dependency on extensive labeled datasets.

### Methodology

**Segmentation Approach:**
We implemented a dual-model comparison between traditional CNN-based UperNet and transformer-based SegFormer architectures. The SegFormer implementation introduced several key innovations:
- Hierarchical transformer structure for multi-scale feature extraction
- Lightweight MLP decoder for efficient processing
- Optimized hyperparameters for manufacturing contexts

**Object Detection Framework:**
Our detection system evaluated multiple YOLO variants, focusing on balancing accuracy with computational efficiency:

<div class="table-responsive">
  <table class="table">
    <thead>
      <tr>
        <th>Model</th>
        <th>mAP@IoU=0.5</th>
        <th>Inference Speed</th>
        <th>Model Size</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>YOLOv5s</td>
        <td>0.657</td>
        <td>5.0 min</td>
        <td>28 MB</td>
      </tr>
      <tr>
        <td>YOLOv8s</td>
        <td>0.687</td>
        <td>5.2 min</td>
        <td>61 MB</td>
      </tr>
      <tr>
        <td>YOLOv8m</td>
        <td>0.690</td>
        <td>5.8 min</td>
        <td>117 MB</td>
      </tr>
      <tr>
        <td>YOLOv8x</td>
        <td>0.698</td>
        <td>7.4 min</td>
        <td>273 MB</td>
      </tr>
    </tbody>
  </table>
</div>

### Results

**Segmentation Performance:**
The optimized SegFormer model demonstrated superior performance:

<div class="table-responsive">
  <table class="table">
    <thead>
      <tr>
        <th>Model</th>
        <th>IoU Score</th>
        <th>Inference Speed</th>
        <th>Model Size</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>UperNet</td>
        <td>0.645</td>
        <td>8.5 min</td>
        <td>254 MB</td>
      </tr>
      <tr>
        <td>SegFormer</td>
        <td>0.674</td>
        <td>9.8 min</td>
        <td>181 MB</td>
      </tr>
      <tr>
        <td>SegFormer (Optimized)</td>
        <td>0.695</td>
        <td>9.3 min</td>
        <td>181 MB</td>
      </tr>
    </tbody>
  </table>
</div>

This implementation has resulted in:
- 7.5% increase in defect detection accuracy
- 6% improvement in overall inspection efficiency
- Reduced false positive rates by 12%
- Faster deployment for new product lines

### Discussion
The project demonstrates that advanced computer vision techniques can significantly improve manufacturing quality control, even with limited initial training data. The optimized models now serve as a foundation for rapid deployment of automated inspection systems across various manufacturing lines.
- **Social Value:** By enhancing quality control, we contribute to safer consumer products and more efficient manufacturing processes, benefiting both businesses and end-users.

### Personal Contribution
As the lead computer vision engineer on this project, my responsibilities included:
- Implementing and optimizing the SegFormer architecture
- Conducting extensive hyperparameter tuning
- Developing the evaluation framework for model comparison
- Integrating the models into the production environment
- **Role:** My leadership and technical expertise were pivotal in achieving the project's objectives and delivering tangible social benefits.

### References
[1] T. Xiao, Y. Liu, B. Zhou, Y. Jiang, and J. Sun, "Unified Perceptual Parsing for Scene Understanding," arXiv.org, Jul. 26, 2018.

[2] E. Xie, W. Wang, Z. Yu, A. Anandkumar, J. M. Alvarez, and P. Luo, "SegFormer: Simple and Efficient Design for Semantic Segmentation with Transformers," arXiv:2105.15203 [cs], Oct. 2021.

[3] A. Dosovitskiy et al., "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale," arXiv:2010.11929 [cs], Oct. 2020.

[4] C.-Y. Wang, A. Bochkovskiy, and H.-Y. M. Liao, "YOLOv7: Trainable bag-of-freebies sets new state-of-the-art for real-time object detectors," arXiv:2207.02696 [cs], Jul. 2022.
