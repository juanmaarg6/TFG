# TFG - Análisis de Redes Convolucionales y Técnicas de Explicabilidad para Arquitecturas Neuronales Profundas para la Segmentación de Instancias

## Resumen

**PALABRAS CLAVE**: Redes Neuronales Convolucionales, Modelización Matemática, Ondículas, Visión por Computador, Aprendizaje Profundo, Segmentación de Instancias, Inteligencia Artificial Explicable.

Este Trabajo de Fin de Grado combina dos enfoques complementarios: por un lado, el desarrollo de una modelización matemática general de las redes neuronales convolucionales, y por otro, la adaptación y evaluación de un modelo de segmentación de instancias en imágenes dentales mediante técnicas de inteligencia artificial explicable.

En la parte matemática, se extiende el análisis de Mallat sobre redes de dispersión mediante el marco propuesto por Wiatowski y Bölcskei, que permite caracterizar redes neuronales convolucionales profundas mediante marcos semi-discretos generales, funciones de activación y operadores de pooling Lipschitz-continuos. Bajo esta formulación, se demuestra la invarianza vertical a traslaciones, es decir, la creciente robustez del extractor de características ante desplazamientos espaciales conforme se profundiza en la red.

En la parte experimental, se aplica la arquitectura Mask R-CNN a la segmentación de instancias dentales en radiografías panorámicas. Se adapta el modelo preentrenado al dominio específico mediante ajuste fino y se le incorpora Grad-CAM siguiendo las adaptaciones propuestas por Inbaraj et al., con el objetivo de mejorar su interpretabilidad. La evaluación incluye métricas de detección, segmentación (DSC, IoU, HD) y explicabilidad (Deletion, Insertion, Stability, $\text{IoU}_{\text{Grad-CAM}}$), desglosadas por categoría dental.

En la parte informática, se aplica la arquitectura Mask R-CNN a la segmentación de instancias dentales en radiografías panorámicas. Se adapta un modelo preentrenado en COCO al dominio específico mediante ajuste fino y se implementa la técnica de explicabilidad Grad-CAM siguiendo las adaptaciones propuestas por Inbaraj et al., con el objetivo de facilitar la comprensión de sus predicciones. A esta propuesta la hemos denominado DentCAM-RCNN. La evaluación incluye métricas de detección (Precision, Recall, F1-Score, AP@50), segmentación (DSC, IoU, HD) y explicabilidad (Deletion, Insertion, Stability, $\text{IoU}_{\text{Grad-CAM}}$), desglosadas por categoría dental.

DentCAM-RCNN alcanza un F1-Score del 96.04%, una precisión del 97.36 %, un DSC del 87.76% y un IoU del 79.23% en el conjunto de test, superando ampliamente tanto al modelo base como a métodos clásicos de segmentación no supervisados. Estos resultados se consolidan mediante una comparación cuantitativa con estudios recientes que utilizan la arquitectura Mask R-CNN en tareas similares, donde el modelo propuesto destaca por su rendimiento robusto, incluso con un volumen intermedio de datos.

Los resultados obtenidos refuerzan el valor de las redes neuronales convolucionales ajustadas al dominio y complementadas con técnicas de explicabilidad post-hoc como Grad-CAM, tanto para alcanzar resultados precisos como para dotar de explicabilidad a modelos aplicables en el análisis automatizado de radiografías dentales.

## Abstract

**KEYWORDS**: Convolutional Neural Networks, Mathematical Modeling, Wavelets, Computer Vision, Deep Learning, Instance Segmentation, Explainable Artificial Intelligence.

This Bachelor’s Thesis combines two complementary approaches: on the one hand, the development of a general mathematical modeling of convolutional neural networks, and on the other, the adaptation and evaluation of an instance segmentation model on dental images using explainable artificial intelligence techniques.

In the mathematical part, Mallat’s analysis of scattering networks is extended through the framework proposed by Wiatowski and Bölcskei, which allows deep convolutional neural networks to be characterized via general semi-discrete frames, activation functions, and Lipschitz-continuous pooling operators. Under this formulation, vertical translation invariance is demonstrated, meaning the increasing robustness of the feature extractor to spatial displacements as the network depth increases.

In the computational part, the Mask R-CNN architecture is applied to the task of instance segmentation in panoramic dental radiographs. A model pretrained on COCO is fine-tuned to the specific domain, and the explainability technique Grad-CAM is implemented following the adaptations proposed by Inbaraj et al., with the aim of facilitating the understanding of its predictions. We have named this approach DentCAM-RCNN. The evaluation includes detection metrics (Precision, Recall, F1-Score, AP@50), segmentation metrics (DSC, IoU, HD), and explainability metrics (Deletion, Insertion, Stability, $\text{IoU}_{\text{Grad-CAM}}$), all broken down by dental category.

DentCAM-RCNN achieves an F1-Score of 96.04%, a precision of 97.36%, a DSC of 87.76%, and an IoU of 79.23% on the test set, significantly outperforming both the base model and classical unsupervised segmentation methods. These results are further supported by a quantitative comparison with recent studies using the Mask R-CNN architecture for similar tasks, where the proposed model stands out for its robust performance, even with an intermediate data volume.

The results obtained highlight the value of convolutional neural networks tailored to the domain and enhanced with post-hoc explainability techniques such as Grad-CAM, both for achieving accurate results and for providing interpretability to models applicable to the automated analysis of dental radiographs.
