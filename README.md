# TFG - Análisis de Redes Convolucionales y Técnicas de Explicabilidad para Arquitecturas Neuronales Profundas para la Segmentación de Instancias

## Resumen

**PALABRAS CLAVE**: Redes Neuronales Convolucionales, Modelización Matemática, Ondículas, Visión por Computador, Aprendizaje Profundo, Segmentación de Instancias, Inteligencia Artificial Explicable.

Este Trabajo de Fin de Grado combina dos enfoques complementarios: por un lado, el desarrollo de una modelización matemática general de las redes neuronales convolucionales (CNN), y por otro, la implementación y evaluación de un modelo de segmentación de instancias en imágenes dentales con técnicas de inteligencia artificial explicable.

En la parte teórica, se extiende el análisis de Mallat sobre redes de dispersión mediante el marco propuesto por Wiatowski y Bölcskei, que permite caracterizar CNN profundas mediante marcos semi-discretos generales, funciones de activación y operadores de pooling Lipschitz-continuos. Bajo esta formulación, se demuestra la invarianza vertical a traslaciones, es decir, la creciente robustez del extractor de características ante desplazamientos espaciales conforme se profundiza en la red.

En la parte experimental, se aplica la arquitectura Mask R-CNN a la segmentación de instancias dentales en radiografías panorámicas. Se adapta el modelo preentrenado al dominio específico mediante ajuste fino y se le incorpora Grad-CAM siguiendo las adaptaciones propuestas por Inbaraj et al., con el objetivo de mejorar su interpretabilidad. La evaluación incluye métricas de detección, segmentación (DSC, IoU, HD) y explicabilidad (Deletion, Insertion, Stability, $\text{IoU}_{\text{Grad-CAM}}$), desglosadas por categoría dental.

El modelo ajustado alcanza un F1-Score del 96.04 %, una precisión del 97.36 %, un DSC del 87.76 % y un IoU del 79.23 % en el conjunto de test, superando ampliamente tanto al modelo base como a métodos clásicos de segmentación no supervisados. Estos resultados se consolidan mediante una comparación cuantitativa con estudios recientes que utilizan la arquitectura Mask R-CNN en tareas similares, donde el modelo propuesto destaca por su rendimiento robusto y balanceado, incluso con un volumen intermedio de datos.

Los resultados obtenidos refuerzan el valor de las CNN ajustadas al dominio y complementadas con técnicas de explicabilidad post-hoc como Grad-CAM, tanto para alcanzar precisión de estado del arte como para dotar de transparencia a modelos aplicables en contextos clínicos.

## Abstract

**KEYWORDS**: Convolutional Neural Networks, Mathematical Modeling, Wavelets, Computer Vision, Deep Learning, Instance Segmentation, Explainable Artificial Intelligence.

This Bachelor's Thesis combines two complementary approaches: on the one hand, the development of a general mathematical modeling of convolutional neural networks (CNNs), and on the other, the implementation and evaluation of an instance segmentation model on dental images using explainable artificial intelligence techniques.

In the theoretical part, Mallat's analysis of scattering networks is extended through the framework proposed by Wiatowski and Bölcskei, which enables the characterization of deep CNNs via general semi-discrete frames, activation functions, and Lipschitz-continuous pooling operators. Under this formulation, hierarchical translation invariance is demonstrated, that is, the increasing robustness of the feature extractor to spatial shifts as network depth increases.

In the experimental part, the Mask R-CNN architecture is applied to the instance segmentation of dental structures in panoramic radiographs. The pretrained model is fine-tuned to the specific domain and enhanced with Grad-CAM, following the adaptations proposed by Inbaraj et al., with the goal of improving its interpretability. The evaluation includes detection, segmentation (DSC, IoU, HD), and explainability metrics (Deletion, Insertion, Stability, $\text{IoU}_{\text{Grad-CAM}}$), broken down by dental category.

\noindent The fine-tuned model achieves a F1-Score of 96.04 %, a precision of 97.36 %, a DSC of 87.76 %, and an IoU of 79.23 % on the test set, significantly outperforming both the baseline model and classical unsupervised segmentation methods. These results are reinforced by a quantitative comparison with recent studies that employ the Mask R-CNN architecture for similar tasks, where the proposed model stands out for its robust and balanced performance, even with an intermediate data volume.

The results obtained highlight the value of CNNs adapted to the specific domain and complemented with post-hoc explainability techniques such as Grad-CAM, both for achieving state-of-the-art accuracy and for providing transparency to models intended for clinical applications.
