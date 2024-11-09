---
layout: page
title: Supervised Learning Models for Manufacturing Quality Control
importance: 3
category: work
---

### Introduction
In today's competitive manufacturing landscape, delivering products of pristine quality is paramount. While computer vision techniques like semantic segmentation and object detection have revolutionized automated inspection, they face a significant challenge: new product lines lack the extensive labeled training data needed for these models. This data scarcity can compromise quality control effectiveness for novel products.

### Project Objectives & Role
During this internship project, I focused on enhancing existing supervised models through:
1. Dataset preprocessing optimization
2. Architectural innovations:
   - Evaluating transformer-based architectures for segmentation
   - Testing newer YOLO variants for detection
3. Hyperparameter tuning for performance optimization

### Methods
We evaluated two primary approaches:

**Segmentation Models:**
- Compared UperNet (CNN-based) baseline with SegFormer (transformer-based)
- Conducted extensive hyperparameter optimization
- Measured performance using IoU scores

**Object Detection Models:**
- Evaluated YOLOv8 series against YOLOv5s baseline
- Tested multiple model variants (YOLOv8s, YOLOv8m, YOLOv8x)
- Assessed using mAP@IoU=0.5 metric

### Results

**Segmentation Model Performance:**

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

**Object Detection Model Performance:**

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
        <td>5 min</td>
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

### Impact
The project achieved significant improvements:
- 7.5% increase in segmentation performance with optimized SegFormer
- 6% improvement in detection accuracy with YOLOv8x
- Enhanced capability to detect subtle defects
- More efficient quality control processes

### References
[1] T. Xiao, Y. Liu, B. Zhou, Y. Jiang, and J. Sun, "Unified Perceptual Parsing for Scene Understanding," arXiv.org, Jul. 26, 2018.

[2] E. Xie, W. Wang, Z. Yu, A. Anandkumar, J. M. Alvarez, and P. Luo, "SegFormer: Simple and Efficient Design for Semantic Segmentation with Transformers," arXiv:2105.15203 [cs], Oct. 2021.

[3] A. Dosovitskiy et al., "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale," arXiv:2010.11929 [cs], Oct. 2020.

[4] C.-Y. Wang, A. Bochkovskiy, and H.-Y. M. Liao, "YOLOv7: Trainable bag-of-freebies sets new state-of-the-art for real-time object detectors," arXiv:2207.02696 [cs], Jul. 2022.
