# Multi-Resolution Segmentation of Solar Photovoltaic Systems Using Deep Learning

Repository for the machine learning and remote sensing based model with examples described in Kleebauer, M.; Marz, C.;Reudenbach, C; Braun, M., Multi-Resolution Segmentation of Solar Photovoltaic Systems Using Deep Learning. 


## Abstract
Existing deep learning networks for solar photovoltaic system segmentation focus almost exclusively on single image sources, both in terms of sensors used and image resolution. This often prevents the wide deployment of such networks. Our research introduces a novel network trained on a diverse range of image data, spanning UAVs, aerial and satellite imagery at both native and aggregated resolutions of 0.1 m, 0.2 m, 0.3 m, 0.8 m, 1.6 m and 3.2 m. Using extensive hyperparameter tuning, we first determined the best possible parameter combinations for the network based on the DeepLabV3 ResNet101 architecture. We then trained a model using the wide range of different image sources. The final network offers several advantages at once. It outperforms networks trained with single image sources in multiple test applications as measured by the F1-Score (95.27%) and IoU (91.04%), and since the training includes image data in a diverse range, it can also be applied to a variety of target imagery. The model is made freely available for further applications.

## Materials
In the work the datasets of 3 different publications are combined. The first dataset mentioned here is aerial imagery from the Federal Agency for Cartography and Geodesy (BKG) in Germany in the state of North Rhine-Westphalia with a native resolution of 10 cm [[Mayer et al. 2020](https://github.com/kdmayer/PV_Pipeline)]. Other datasets used were imagery data within China obtained from unmanned aerial vehicles (UAV) in Hai'an country, area imagery from the Provincial Geomatics Center (PGC) of Jiangsu, and satellite imagery from Gaofen-2 and Beijing-2with resolutions of 10 cm, 30 cm, and 80 cm, respectively, with masks of existing PV plants [[Jiang et al. 2021](https://zenodo.org/record/5171712)]. The recently published dataset [[Kasmi et al. 2023](https://github.com/gabrielkasmi/bdappv)] combines overflight imagery in France from the Geoservices portal of the National Institute of Geographic and Forest Information (IGN) with a native resolution of 20 cm on the one hand and imagery acquired with GEE with 10 cm native resolution around different locations in Germany on the other hand. Subsequently, the datasets were combined to 6 different resolution variants. An exemplary representation is shown in the following figure. 

<p align="center">
  <img src="figures/trainingsamples.png">
</p>
Illustration of the different training images, with each their of corresponding resolution level labeled at the top. The images with PV systems are shown on the left and the masks for training are shown on the right, with the PV systems highlighted in white. Details on the preparation are explained in the publication. 


## Models trained with single-resolution images

<p align="center">
  <img src="figures/prediction_single_res.png">
</p>

Illustration of the different predictions, where each exemplary image is labeled according to resolution levels. The horizontal label refers from left to right to the underlying image and the mask, next to it to the dataset used for training the respective models. The red box indicates that the resolution of the training and the test application are the same.

## Model trained with multi-resolution images
<p align="center">
  <img src="figures/prediction_multi_res.png" width="50%">
</p>
Comparison of the single-resolution trained networks versus the final multi-resolution trained network. From left to right, first are the images and masks, next are the predictions of the single. res networks suitable for each image. The predictions of the multi res. network on the right are shown.

## Model
The final model is stored on Zenodo, after downloading it can simply be placed in the 'weights' folder. 

## Usage
Examples of hyperparameter tuning, training, validation and prediction can be found in 'scripts'. 

## Funding
This work is developed in the OASES Project - "Development and Demonstration of a Sustainable Open Access AU-EU Ecosystem for Energy System Modelling". The project is part of the LEAP-RE Program. LEAP-RE has received funding from the European Union ’s Horizon 2020 Research and Innovation Program under Grant Agreement 963530. The Research is funded by Bundesministerium für Bildung und Forschung (03SF067) to University of Kassel, Research funding providing by South African National Energy Development Institute (SANEDI) and Department of Science and Innovation (DSI) to CSIR for LEAP-RE OASES project.
