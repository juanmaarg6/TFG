# Bachelor's Thesis: Mathematical Analysis of Convolutional Neural Networks and Explainable Instance Segmentation

**DentCAM-RCNN — Mathematical foundations, dental instance segmentation, and explainable AI**

Joint Bachelor's Thesis in **Computer Science and Engineering** and **Mathematics**, University of Granada (June 2025).  
**Final grade:** 9.54/10 in both degrees.

**Thesis materials:** [Full thesis](docs/bachelors_thesis.pdf) · [Defense presentation](docs/thesis_presentation.pdf)  
**Implementation:** [DentCAM-RCNN notebook](dentcam_rcnn.ipynb) · [Mask R-CNN source](mrcnn/) · [Dependencies](requirements.txt)

## Overview

This thesis brings together two complementary perspectives on deep convolutional neural networks:

1. **Mathematical analysis:** a general framework for understanding the properties of deep convolutional feature extractors, based on semi-discrete frames, Lipschitz-continuous nonlinearities, and pooling operators.
2. **Computer vision and explainability:** an adaptation of Mask R-CNN for instance-level segmentation of teeth in panoramic dental radiographs, extended with Grad-CAM visualizations to interpret individual predictions. This implementation is named **DentCAM-RCNN**.

The goal is to connect theoretical understanding of convolutional representations with a practical, experimentally evaluated image-analysis application.

**Keywords:** Convolutional Neural Networks, Mathematical Modeling, Wavelets, Computer Vision, Deep Learning, Instance Segmentation, Explainable Artificial Intelligence, Grad-CAM.

## Key results

DentCAM-RCNN was evaluated on the thesis test set using detection, segmentation, and explainability metrics. The principal reported results are:

| Metric | Test-set result |
| --- | ---: |
| F1-score (detection) | **96.04%** |
| Precision (detection) | **97.36%** |
| Dice similarity coefficient (DSC) | **87.76%** |
| Intersection over Union (IoU) | **79.23%** |

The thesis also evaluates AP@50, recall, Hausdorff distance, and explanation metrics (deletion, insertion, stability, and Grad-CAM overlap), broken down by dental category. Comparisons with the original baseline and classical unsupervised segmentation methods are reported in the [full thesis](docs/bachelors_thesis.pdf).

**Scope:** These figures are results of the study's specific dataset and evaluation protocol; they do not establish clinical performance or generalization to external hospitals or imaging systems.

## Part I — Mathematical analysis of CNNs

The mathematical component builds on Mallat's analysis of scattering networks and the broader framework developed by Wiatowski and Bölcskei. Deep convolutional feature extractors are studied through:

- General semi-discrete frames and convolutional filtering.
- Lipschitz-continuous activation functions and pooling operators.
- Mathematical properties of feature representations under spatial transformations.
- Translation-related invariance properties of deep feature extractors under the assumptions of the framework.

This component provides a theoretical perspective on how deep convolutional architectures can produce increasingly robust feature representations. The exact assumptions, definitions, and proofs are given in the [thesis](docs/bachelors_thesis.pdf).

## Part II — DentCAM-RCNN

### Instance segmentation

DentCAM-RCNN adapts **Mask R-CNN** to the instance segmentation of teeth in panoramic dental radiographs. The implementation uses a **ResNet-101 backbone with a Feature Pyramid Network (FPN)**, a Region Proposal Network (RPN), RoI alignment, and task-specific branches for classification, bounding-box regression, and mask prediction.

A COCO-pretrained model is fine-tuned for the dental domain. The work evaluates both detection and segmentation quality, with results reported by dental category.

![Mask R-CNN architecture used in the study](img/fig_1.png)

### Explainability with Grad-CAM

A Grad-CAM adaptation is applied to instance-level predictions to produce heatmaps highlighting image regions that influence the corresponding classification output. The implementation analyzes the `roi_align_classifier` feature representation and uses per-instance class scores for explanation.

The explainability analysis includes both qualitative examples and quantitative measurements, rather than relying exclusively on visual inspection.

![Grad-CAM explanation workflow](img/fig_2.png)

### Qualitative results

The figures below compare segmentation outputs and explanation maps from the baseline and DentCAM-RCNN on selected examples.

**Dental categories 1–4**

![DentCAM-RCNN qualitative comparison, categories 1–4](img/fig_3.png)

**Dental categories 7–10**

![DentCAM-RCNN qualitative comparison, categories 7–10](img/fig_4.png)

## Repository structure

```text
TFG/
├── dataset/                     # Data assets from the original implementation; check access and reuse rights
├── docs/
│   ├── bachelors_thesis.pdf     # Joint Bachelor's Thesis
│   └── thesis_presentation.pdf  # Defense slides
├── img/                         # Architecture, explainability, and result figures
├── mrcnn/                       # Adapted Mask R-CNN implementation; third-party license applies
├── dentcam_rcnn.ipynb           # Main experiment and analysis notebook
├── requirements.txt             # Dependencies used by the original codebase
├── README.md                    # Project overview and documentation
├── CITATION.cff                 # Machine-readable citation metadata
├── LICENSE                      # CC0-1.0 for eligible original contributions
└── LICENSE_MATTERPORT.txt       # Matterport MIT copyright and license notice
```

## Installation and use

### 1. Clone the unified repository

```bash
git clone https://github.com/juanmaarg6/TFG.git
cd TFG
```

### 2. Prepare a compatible Python environment

Create and activate a virtual environment, then install the project's recorded dependencies:

```bash
python -m venv .venv
# Activate the environment using the command appropriate for your operating system.
pip install -r requirements.txt
```

The historical dependencies include TensorFlow 2.14, Keras 2.14, and the Matterport-derived Mask R-CNN implementation. GPU setup, Python-version compatibility, and platform-specific adjustments may be required. The environment has **not** been independently revalidated on a current system; installing the requirements alone does not guarantee reproducibility.

### 3. Review the dataset and notebook configuration

The notebook and training scripts may expect local paths, pretrained weights, and a specific dental-image dataset structure. Adjust these paths before running any cells. **Do not assume that medical images can be redistributed**: confirm permissions, licensing, and appropriate anonymization before publishing or reusing data.

### 4. Run the notebook

Open [`dentcam_rcnn.ipynb`](dentcam_rcnn.ipynb) in Jupyter Notebook, JupyterLab, or a compatible environment. The notebook contains the workflow for model adaptation, prediction, segmentation assessment, and Grad-CAM visualization.

The original implementation is preserved as research code; it has not been packaged as a maintained library or validated as a clinical application.

## Thesis documents

- [Full Bachelor's Thesis (PDF)](docs/bachelors_thesis.pdf)
- [Defense presentation (PDF)](docs/thesis_presentation.pdf)

The PDFs are linked using English filenames for a consistent repository structure. Their contents retain the language and academic form of the original submitted documents.

## Authorship and acknowledgments

**Juan Manuel Rodríguez Gómez**  
Joint Bachelor's Degree in Computer Science and Engineering and Mathematics  
University of Granada, 2025

DentCAM-RCNN builds upon the open-source Mask R-CNN implementation by **Matterport, Inc.** and the Grad-CAM explainability methodology. The respective original contributions remain attributed to their creators.

## License and third-party materials

**CC0-1.0** applies to the original materials in this repository **only where the author has the rights to make that dedication**. See [`LICENSE`](LICENSE).

The adapted Mask R-CNN source under [`mrcnn/`](mrcnn/) includes code originating from **Matterport, Inc.**, which is distributed under the **MIT License**. Its existing copyright notices and license requirements must be retained. The original notice is provided in [`LICENSE_MATTERPORT.txt`](LICENSE_MATTERPORT.txt). Applying CC0 to the author's own work **does not change the license of third-party code**.

Datasets, images, pretrained weights, and other third-party assets may have independent permissions and usage restrictions; they are **not automatically covered by CC0**. Confirm authorization before sharing medical-image data.

## Citation

If this project is useful for your research, please cite the Bachelor's Thesis or the associated repository. Machine-readable metadata is provided in [`CITATION.cff`](CITATION.cff); GitHub can use it to generate citation formats.
