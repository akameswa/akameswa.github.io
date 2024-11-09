---
layout: page
title: Unsupervised Anomaly Detection for Manufacturing QC
importance: 2
category: work
---

### Introduction 
In manufacturing quality control, manual defect inspection becomes impractical at scale. While computer vision techniques like semantic segmentation and object detection [1] have revolutionized automated inspection, they face a significant challenge: new product lines lack the extensive labeled training data needed for these models. This data scarcity can compromise quality control effectiveness for novel products.

### Project Objectives & Role
In this internship project, I led the evaluation of unsupervised anomaly detection approaches for manufacturing quality control. The key objectives were:
1. Evaluate and compare ten different anomaly detection models, focusing on:
   - Processing capability for non-square images
   - Heat map generation quality
   - Model size and inference speed
   - Detection accuracy (recall)
2. Identify the most effective model for production deployment

### Methods
We evaluated ten different anomaly detection models, focusing on their ability to process non-square images and produce meaningful heat maps. The models were trained on defect-free (OK) samples and tested on defective (NG) samples.

### Results 
Three models emerged as top performers:

<div class="table-responsive">
  <table class="table">
    <thead>
      <tr>
        <th>Model</th>
        <th>Heatmap Quality</th>
        <th>Inference Speed</th>
        <th>Model Size</th>
        <th>Recall</th>
        <th>Conclusion</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>EfficientAd [2]</td>
        <td>Accurate</td>
        <td>2.3 min</td>
        <td>30 MB</td>
        <td>0.55607</td>
        <td>Best</td>
      </tr>
      <tr>
        <td>Reverse Distillation [3]</td>
        <td>Little Noisy</td>
        <td>1.8 min</td>
        <td>340 MB</td>
        <td>0.40068</td>
        <td>Good</td>
      </tr>
      <tr>
        <td>Padim [4]</td>
        <td>Noisy</td>
        <td>45.8 sec</td>
        <td>563 MB</td>
        <td>0.19527</td>
        <td>Not Good</td>
      </tr>
    </tbody>
  </table>
</div>

EfficientAd [2] demonstrated superior performance with:
- Most accurate heat map generation
- Smallest model size (30 MB)
- Highest recall score (0.55607)
- Effective localization of anomalous regions

### Impact
The unsupervised models serve multiple purposes:
- Generate annotation data for supervised models
- Assist in data quality inspection
- Identify anomaly signals including:
  - Defects
  - Lighting variations
  - Layout differences
- Flag potentially defective samples without pre-existing annotations

### References
[1] D. Weimer, B. Scholz-Reiter, and M. Shpitalni, "Design of deep convolutional neural network architectures for automated feature extraction in industrial inspection," CIRP Annals, vol. 65, no. 1, pp. 417–420, 2016.

[2] K. Batzner, L. Heckler, and R. König, "EfficientAD: Accurate Visual Anomaly Detection at Millisecond-Level Latencies," arXiv.org, Mar. 25, 2023.

[3] H. Deng and X. Li, "Anomaly Detection via Reverse Distillation from One-Class Embedding," arXiv.org, 2022.

[4] T. Defard, Aleksandr Setkov, A. Loesch, and Romaric Audigier, "PaDiM: a Patch Distribution Modeling Framework for Anomaly Detection and Localization," arXiv, Nov. 2020.
