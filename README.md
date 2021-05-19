# A Review of Formal Methods applied to Machine Learning

Our goal is to find a common benchmark able to effectively compare tools in the review

    Caterina Urban and Antoine Miné, 2021, A Review of Formal Methods applied to Machine Learning, 2104.02466

This repo will ease users in the process of choosing the best fitting analyzer for your purposes, as well as giving an overview of the current state-of-the-art in verification of machine learning systems.

**Table of Context**
- [A Review of Formal Methods applied to Machine Learning](#a-review-of-formal-methods-applied-to-machine-learning)
- [Benchmark Overview](#benchmark-overview)
- [Testing Progress Report](#testing-progress-report)
  - [Complete methods](#complete-methods)
    - [SMT-based Formal Methods](#smt-based-formal-methods)
    - [MILP-based Formal Methods](#milp-based-formal-methods)
    - [Other Complete Formal Methods](#other-complete-formal-methods)
  - [Incomplete methods](#incomplete-methods)
    - [Abstract Interpretation-based Formal Methods](#abstract-interpretation-based-formal-methods)
    - [Other Incomplete Formal Methods](#other-incomplete-formal-methods)
- [How to Repeat our Experiments](#how-to-repeat-our-experiments)

# Benchmark Overview

Here we show benchmarks used to test tools in the review. Obviously, a common single benchmark would be optimal in order to compare every analyzer, but this is inadmissible. Due to different input requirements, network compatibility, property tested, a single benchmark does not exist.
However, we identified a restricted number of general-purpose benchmarks in order to effectively compare tools among each other.

All the available benchmarks are summarized below:

|            Benchmark Id |              Property | Dataset |                                                               Supported Model |
| ----------------------: | --------------------: | ------: | ----------------------------------------------------------------------------: |
|      `local_robustness` |      Local Robustness |   MNIST | Neural Networks with fully-connected feed-forward layers and ReLU activations |
| `functional_properties` | Functional Properties | ACAS Xu | Networks with fully-connected feed-forward layers and ReLU activations |

# Testing Progress Report

In this section, we report the tool testing status, for tools already tested we display which test has been used, cf. column **Benchmark**. We broadly distinguish between *Complete* and *Incomplete methods*.

<!-- We broadly distinguish between analyzers that apply verification after the model is developed *Model Deployed*, during the training phase *Model Training*, and during its preparation *Data Preparation*. -->

> References in the tables refer to the bibliography inside the review.

<!-- ## Model Deployed

In addition, we further distinguish between *Complete* and *Incomplete methods*. -->

## Complete methods

### SMT-based Formal Methods

|           Author Reference |                                                            Name |            Supported Layers |      Activations |                              Dataset | Benchmark |
| -------------------------: | --------------------------------------------------------------: | --------------------------: | ---------------: | -----------------------------------: | --------: |
| Pulina and Tacchella [126] |                                                                 | fuly-connected feed-forward |          sigmoid |                                      |      TODO |
|                Ehlers [60] |                    [Planet](https://github.com/progirep/planet) |            piecewise linear |             ReLU |                                MNIST |      TODO |
|           Katz et al. [92] |                                                        Reluplex | fuly-connected feed-forward |             ReLU |                              ACAS Xu |      TODO |
|           Katz et al. [93] | [Marabou](https://github.com/NeuralNetworkVerification/Marabou) |            piecewise linear | piecewise linear |                              ACAS Xu |      TODO |
|         Bastani et al. [8] |                                                                 |            piecewise linear |             ReLU |                   MNIST and CIFAR-10 |      TODO |
|          Huang et al. [86] |                          [DLV](https://github.com/verideep/dlv) |            piecewise linear |             ReLU | MNIST, CIFAR-10, GTSRB, and ImageNet |      TODO |
|    Narodytska et al. [120] |                                                                 | fuly-connected feed-forward |                  |                                MNIST |      TODO |
|          Cheng et al. [30] |                                                                 | fuly-connected feed-forward |                  |                      MNIST and GTSRB |      TODO |

### MILP-based Formal Methods

|             Reference |                                                  Name |                     ML model |       Activations |          Benchmark | Progress |
| --------------------: | ----------------------------------------------------: | ---------------------------: | ----------------: | -----------------: | -------: |
|     Cheng et al. [29] |                                                       |             piecewise linear | ReLU and *arctan* |                    |     TODO |
| Fischetti and Jo [67] |                                                       |             piecewise linear |              ReLU |              MNIST |     TODO |
|    Brunel et al. [22] |                                                   BaB |             piecewise linear |              ReLU |            ACAS Xu |     TODO |
|    Drutta et al. [58] | [Sherlock](https://github.com/souradeep-111/sherlock) | fully-connected feed-forward |              ReLU |                    |     TODO |
|    Tjeng et al. [149] |   [MIPVerify](https://github.com/vtjeng/MIPVerify.jl) |             piecewise linear |              ReLU | MNIST and CIFAR-10 |     TODO |
### Other Complete Formal Methods

## Incomplete methods

### Abstract Interpretation-based Formal Methods

### Other Incomplete Formal Methods

# How to Repeat our Experiments

Our benchmarks can be run directly from this repo. For each tool we provide the container configuration file to easily run and repeat our benchmarks.

Thus, the only prerequisite in order to run our experiments is to install [singularity](https://sylabs.io/). Sometimes, we even provide the [docker](https://www.docker.com/) version.

...