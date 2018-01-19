# Guide-CBIR (Content Based Image Retrieval)
Guide to the Content Based Image Retrieval.

Welcome you to step in the world of Content Based Image Retrieval. 

This guide will help you to find what great works are done previously, and which direction of this field is going.

Let's explore togehter! Good luck on your journey. :)

# Awesome Curation

* CBIR related papers, and usefule links https://github.com/willard-yuan/awesome-cbir-papers

# Survey
Good resource to follow great works doen previously.

* SIFT Meets CNN: A Decade Survey of Instance Retrieval
    * by Liang Zheng, Yi Yang, Qi Tian https://arxiv.org/abs/1608.01807
    * Description on Local Descriptors
    * Transition from SIFT (and other descriptors) to CNN features
    * Overview of Two Image Retreival System (Visual BoW + Indexing v.s. Approximated Nearest Neighbor)
    * Introduction of Popular Datasets (Holidats, Ukbench, Oxford5k)
    
    
* 


# Personal Remark on Selected Papers
These are my remark on some papers. Please correct me, if there is any mistake.

* Fine-tuning CNN Image Retrieval with No Human Annotation
    * by Filip Radenović, Giorgos Tolias, Ondřej Chum https://arxiv.org/abs/1711.02512
    * [Matlab Source]()
    * State-of-the-Art Image Retrieval Model on Oxford, Paris, and Holidays Dataset
    * Automatic Labeling for hard postivie/negative example using information from Structure from Motion
    * Introducing GeM Pooling Layer (Generalization of Approximate Max Pooling and Mean Pooling)
    * VGG, ResNet    
    * Related Paper
        *  R-MAC



# Dataset
Most popular dataset is for Landmark retreival datasets, which are Oxford5k and Paris6k)
There are other datasets, and they have their own characterestics. 


* The Stanford Mobile Visual Search Data Set (SMVS)

* [Oxford buildings (Oxford5k, Oxford105k)](http://www.robots.ox.ac.uk/~vgg/data/oxbuildings/)
   * 5k images 
   * 100k images from Flicker + 5k images above. Used for large scale testing
   
* UKBench (University of Kentucky dataset) [download from this archived site](https://archive.org/details/ukbench)
   * 10200 images. 2550 clusters of size 4
   * Provides DoG detector + 128d SIFT descriptor
   * No keypoint is provided. (at least not available now)
   * 7.8M descriptors in total

# Selected Projects

Many people shared their work to the community. Thanks for their efforts. 

## Feature Extraction

* Hessian Affine + SIFT feature (quantized uint8, 128d). https://github.com/insikk/hesaff

## Geometric Verification

* Fast Spatial Matching (10x faster than RANSAC when number of coresspondence are about 100)
   * C++ Implementation: https://github.com/tsattler/geometric_burstiness
   * Python biding: https://github.com/insikk/geometric_burstiness/tree/pybind


# Not closely realated to CBIR, but may help to improve CBIR

## Fine-grained Classification

## 3D Modeling

* Structure from Motion

## Image Segmentation

* Mask R-CNN

## Image / Feature Pyramid

* Feature Pyramidal Network
