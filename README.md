# Awesome Referring Remote Sensing Image Segmentation

![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)

## :loudspeaker: Call for Contribution
We actively welcome:
- :page_facing_up: New papers (CVPR/ICCV/ECCV/JSTARS/TGRS/etc.)
- :computer: Open-source implementations
- :bar_chart: Dataset annotations
- :bookmark_tabs: Technical summaries

## :book: Table of Contents
1. [Technical Background](#rocket-technical-background)
2. [Latest Papers](#newspaper-latest-papers)
3. [Datasets](#floppy_disk-datasets)
4. [Codebases](#computer-codebases)
5. [Evaluation](#chart_with_upwards_trend-evaluation)

## :rocket: Technical Background
Referring Remote Sensing Image Segmentation (RRSIS) combines natural language descriptions with pixel-level understanding of **aerial** or **satellite** imagery. Key challenges include:
- **Multiscale Objects**: Buildings (1-100m) vs Vehicles (2-5m)
- **Sensor Variations**: 0.3m (WorldView) to 10m (Sentinel-2)
- **Linguistic Ambiguity**: "The red-roofed building northeast of the river"
- **Occlusion Complexity**: Partial visibility due to clouds/shadows (avg. 15-30% coverage in satellite imagery)
- **Temporal Dynamics**: Seasonal changes (e.g. snow cover) affecting object appearance
- **Geometric Distortion**: Parallax errors up to 5-10 pixels in oblique aerial views

## :newspaper: Latest Papers
### Segmentation Models
| Method | Year | Venue       | Title | Code |
|--------|------|-------------|-------|------|
| - | 2024 | TGRS | [RRSIS: Referring Remote Sensing Image Segmentation](https://ieeexplore.ieee.org/abstract/document/10458079) | [:computer: Code](https://github.com/zhu-xlab/rrsis) |
| - | 2024 | TGRS | [Exploring Fine-Grained Image-Text Alignment for Referring Remote Sensing Image Segmentation](https://ieeexplore.ieee.org/abstract/document/10816052) | [:computer: Code](https://github.com/Shaosifan/FIANet) |
| - | 2024 | CVPR | [Rotated Multi-Scale Interaction Network for Referring Remote Sensing Image Segmentation](https://openaccess.thecvf.com/content/CVPR2024/html/Liu_Rotated_Multi-Scale_Interaction_Network_for_Referring_Remote_Sensing_Image_Segmentation_CVPR_2024_paper.html) | [:computer: Code](https://github.com/Lsan2401/RMSIN) |
| DANet | 2024 | ACMMM | [Rethinking the Implicit Optimization Paradigm with Dual Alignments for Referring Remote Sensing Image Segmentation](https://dl.acm.org/doi/10.1145/3664647.3681318) | - |
| - | 2025 | Arxiv | [Customized SAM 2 for Referring Remote Sensing Image Segmentation](https://arxiv.org/abs/2503.07266) | - |
| - | 2025 | GRSL | [Multimodal-Aware Fusion Network For Referring Remote Sensing Image Segmentation](https://arxiv.org/abs/2503.11183) | [:computer: Code](https://github.com/Roaxy/MAFN) |
| - | 2024 | IGARSS | [Referring Image Segmentation for Remote Sensing Data](https://ieeexplore.ieee.org/abstract/document/10642726) | - |
| BTDNet | 2025 | Arxiv | [Referring Remote Sensing Image Segmentation via Bidirectional Alignment Guided Joint Prediction](https://arxiv.org/abs/2502.08486) | [:computer: Code](https://github.com/wzk913ysq/BAJP) |
| RSRefSeg | 2025 | IGARSS | [Referring Remote Sensing Image Segmentation with Foundation Models](https://arxiv.org/abs/2501.06809) | [:computer: Code](https://github.com/KyanChen/RSRefSeg) |
| CroBIM | 2024 | Arxiv | [Cross-Modal Bidirectional Interaction Model for Referring Remote Sensing Image Segmentation](https://arxiv.org/abs/2410.08613) | [:computer: Code](https://github.com/HIT-SIRS/CroBIM) |



## :floppy_disk: Datasets
| Year | Dataset     | Size       | Download Links |
|------|-------------|------------|----------------|
| 2024 | RefSegRS    | 4,420 image-caption-mask triplets | [:page_facing_up: Paper](https://ieeexplore.ieee.org/abstract/document/10458079) \| [:floppy_disk: Data](https://github.com/zhu-xlab/rrsis) |
| 2024 | RRSIS-D    | 17,402 image-caption-mask triplets | [:page_facing_up: Paper](https://openaccess.thecvf.com/content/CVPR2024/html/Liu_Rotated_Multi-Scale_Interaction_Network_for_Referring_Remote_Sensing_Image_Segmentation_CVPR_2024_paper.html) \| [:floppy_disk: Data](https://github.com/Lsan2401/RMSIN) |
| 2024 | RISBench | 52,472 image-caption-mask triplets | [:page_facing_up: Paper](https://arxiv.org/abs/2410.08613) \| [:floppy_disk: Data](https://github.com/HIT-SIRS/CroBIM) |



## :computer: Codebases
| Framework | Language | Stars | Features | Reference Code |
|-----------|----------|-------|----------|----------------|
| [MMSegmentation](https://github.com/open-mmlab/mmsegmentation) | Python | ![GitHub Stars](https://img.shields.io/github/stars/open-mmlab/mmsegmentation?style=flat-square) | Multi-model support<br>RSIS pipelines<br>Pre-trained models | [:rocket: Demo](https://github.com/KyanChen/RSRefSeg) |

## :chart_with_upwards_trend: Evaluation
### Core Metrics
#### Basic IoU (Intersection over Union)
$$\text{IoU} = \frac{|P \cap G|}{|P \cup G|}$$
- Where \( P \) = Predicted segmentation, \( G \) = Ground truth
- Fundamental measure for pixel-wise segmentation accuracy

#### Generalized IoU (gIoU)
$$\text{gIoU} = \frac{1}{N} \sum_{i=1}^{N} \text{IoU}_i$$
- Calculated by averaging IoU scores across all test samples
- Reflects average performance on individual instances
- Primary metric (more robust to outliers)

#### Cumulative IoU (cIoU)
$$\text{cIoU} = \frac{\sum_{i=1}^{N} |P_i \cap G_i|}{\sum_{i=1}^{N} |P_i \cup G_i|}$$
- Computes ratio of cumulative intersections to unions
- Sensitive to large target areas (higher variance)

#### Precision@X (Pr@X)
| Threshold | Definition | Typical Value |
|-----------|------------|---------------|
| Pr@0.5 | % samples with IoU > 50% | 65.2% |
| Pr@0.6 | % samples with IoU > 60% | 48.7% |
| Pr@0.7 | % samples with IoU > 70% | 32.1% |
| Pr@0.8 | % samples with IoU > 80% | 15.6% |
| Pr@0.9 | % samples with IoU > 90% | 5.3% |

### Implementation
Standard metric implementation reference:  
[iou_metrics.py](https://github.com/KyanChen/RSRefSeg/blob/release/rsris/evaluation/metrics/iou_metrics.py) based on TorchMetrics.


---
:construction: Project under active development - [Contribution Guidelines](CONTRIBUTING.md)