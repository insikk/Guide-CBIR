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

# Visual Vocabularies

* 2012 [Learning Vocabularies over a Fine Quantization](http://cmp.felk.cvut.cz/~perdom1/papers/mikulik_ijcv12.pdf) by Andrej Mikulik, Michal Perdoch, Ondrej Chum, Jirı Matas
    * With larger training set (11B descriptors), large vocab size is acceptable
    * 16M vocab size
    * Larger the vocab size, the better performance. 
        * larger than 16M has small gain. 
        * larger than 64M vocab is not possible due to memory limitation
    * Training Set: 6 million images were downloaded from FLICKR. Explicitly remove all images in testsets.
    * Approximate Hierarchical k-menas
        * two-level tree
        * For 16M vocab tree, each level has 4K nodes on average
        * Assignment step use approximate nearest neighbor algorithm with [FLANN](https://github.com/mariusmuja/flann)
        * The whole procedure takes about one day on a cluster of 20 computers
        * Refer Section 5. Large Vocabulary Generation for more details 
    * Proposed PR similarity measure give better discriminitative power than using Hamming Embedding. *Comment: However, many CBIR still uses HE over PR similiary, why?*

* 2008 [Hamming embedding and weak geometric consistency for large scale image search](https://hal.inria.fr/inria-00316866/document/) by Herve Jegou, Matthijs Douze, and Cordelia Schmid
    * Visual words has quantization error. 
    * This error result in bad matching.
    * Hamming Embedding divdies each vornoi cell (each visual word) so mitigate quantization error.

* 2007 [Object retrieval with large vocabularies and fast spatial matching](http://ieeexplore.ieee.org/document/4270197/) by James Philbin, Ondrej Chum, Michael Isard, Josef Sivic, Andrew Zisserman
    * 1M vocab size is the best for Oxford5k dataset (5k scale, 16.7M descriptors)
    * Approximate k-means (AKM)
        * forest of 8 randomized kd-tree
    * Hierarchical k-means (HKM)
        * [Scalable Recognition with a Vocabulary Tree](http://www-inst.eecs.berkeley.edu/~cs294-6/fa06/papers/nister_stewenius_cvpr2006.pdf)(UKBench dataset paper)'s vocabulary tree concept
        * 6 level, 10 cluster for each level       
    * How long does it take to build? Not mentioned
    * What software can we use to build? Not mentioned

# Selected Projects

Many people shared their work to the community. Thanks for their efforts. 

## Feature Extraction

* Hessian Affine + SIFT feature (quantized uint8, 128d). https://github.com/insikk/hesaff

## Geometric Verification

* Fast Spatial Matching (10x faster than RANSAC when number of coresspondence are about 100)
   * C++ Implementation: https://github.com/tsattler/geometric_burstiness
   * Python biding: https://github.com/insikk/geometric_burstiness/tree/pybind
   
## Large Scale K-means clustering

* Billion Scale. [PQk-means](https://github.com/DwangoMediaVillage/pqkmeans)


# Not closely realated to CBIR, but may help to improve CBIR

## Fine-grained Classification

## 3D Modeling

* Structure from Motion
    * Opensource Software. Colmap: https://github.com/colmap/colmap

## Image Segmentation

* Mask R-CNN
    * Caffe2 Model. Detectron: https://github.com/facebookresearch/Detectron

## Image / Feature Pyramid

* Feature Pyramidal Network
    * Caffe2 Model. Detectron: https://github.com/facebookresearch/Detectron
