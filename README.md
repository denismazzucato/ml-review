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
| `functional_properties` | Functional Properties | ACAS Xu |        Networks with fully-connected feed-forward layers and ReLU activations |

# Testing Progress Report

In this section, we report the tool testing status, for tools already tested we display which test has been used, cf. column **Benchmark**. We broadly distinguish between *Complete* and *Incomplete methods*.

<!-- We broadly distinguish between analyzers that apply verification after the model is developed *Model Deployed*, during the training phase *Model Training*, and during its preparation *Data Preparation*. -->

> References in the tables refer to the bibliography inside the review.

<!-- ## Model Deployed

In addition, we further distinguish between *Complete* and *Incomplete methods*. -->

## Complete methods

### SMT-based Formal Methods

|           Author Reference |                                                       Tool Name |            Supported Layers |      Activations |                              Dataset | Benchmark |
| -------------------------: | --------------------------------------------------------------: | --------------------------: | ---------------: | -----------------------------------: | --------: |
| Pulina and Tacchella [126] |                                                                 | fuly-connected feed-forward |          sigmoid |                                      |      TODO |
|                Ehlers [60] |                    [Planet](https://github.com/progirep/planet) |            piecewise linear |             ReLU |                                MNIST |      TODO |
|           Katz et al. [92] |                                                        Reluplex | fuly-connected feed-forward |             ReLU |                              ACAS Xu |      TODO |
|           Katz et al. [93] | [Marabou](https://github.com/NeuralNetworkVerification/Marabou) |            piecewise linear | piecewise linear |                              ACAS Xu |      TODO |
|         Bastani et al. [8] |                                                                 |            piecewise linear |             ReLU |                   MNIST and CIFAR-10 |      TODO |
|          Huang et al. [86] |                          [DLV](https://github.com/verideep/dlv) |            piecewise linear |             ReLU | MNIST, CIFAR-10, GTSRB, and ImageNet |      TODO |
|    Narodytska et al. [120] |                                                                 |   Binarized Neural Networks |                  |                                MNIST |      TODO |
|          Cheng et al. [30] |                                                                 |   Binarized Neural Networks |                  |                      MNIST and GTSRB |      TODO |

### MILP-based Formal Methods

|      Author Reference |                                             Tool Name |             Supported Layers |       Activations |            Dataset | Benchmark |
| --------------------: | ----------------------------------------------------: | ---------------------------: | ----------------: | -----------------: | --------: |
|     Cheng et al. [29] |                                                       |             piecewise linear | ReLU and *arctan* |                    |      TODO |
| Fischetti and Jo [67] |                                                       |             piecewise linear |              ReLU |              MNIST |      TODO |
|    Brunel et al. [22] |                                                   BaB |             piecewise linear |              ReLU |            ACAS Xu |      TODO |
|    Drutta et al. [58] | [Sherlock](https://github.com/souradeep-111/sherlock) | fully-connected feed-forward |              ReLU |                    |      TODO |
|    Tjeng et al. [149] |   [MIPVerify](https://github.com/vtjeng/MIPVerify.jl) |             piecewise linear |              ReLU | MNIST and CIFAR-10 |      TODO |

### Other Complete Formal Methods

|   Author Reference |                                                  Tool Name |               Supported Layers |                 Activations |           Dataset | Benchmark |
| -----------------: | ---------------------------------------------------------: | -----------------------------: | --------------------------: | ----------------: | --------: |
|  Ruan et al. [134] |                [DeepGO](https://github.com/trustAI/DeepGO) |               piecewise linear | ReLU, *sigmoid*, and *tanh* |             MNIST |      TODO |
|  Wang et al. [163] | [ReluVal](https://github.com/tcwangshiqi-columbia/ReluVal) |   fully-connected feed-forward |                        ReLU |           ACAS Xu |      TODO |
|  Wang et al. [164] | [Neurify](https://github.com/tcwangshiqi-columbia/Neurify) | feed-forward and convolutional |                        ReLU |           ACAS Xu |      TODO |
|  Tran et al. [153] |                   [NNV](https://github.com/verivital/nnv/) |   fully-connected feed-forward |                        ReLU | MNIST and ACAS Xu |      TODO |
|  Tran et al. [154] |                   [NNV](https://github.com/verivital/nnv/) |   fully-connected feed-forward |                        ReLU | MNIST and ACAS Xu |      TODO |
|  Tran et al. [156] |                   [NNV](https://github.com/verivital/nnv/) |               piecewise linear |                        ReLU |   VGG16 adn VGG19 |      TODO |
|    Bak et al. [11] |            [NNENUM](https://github.com/stanleybak/nnenum/) |               piecewise linear |                        ReLU |           ACAS Xu |      TODO |
|  Yang et al. [172] |            [NNENUM](https://github.com/stanleybak/nnenum/) |                                |                        ReLU |           ACAS Xu |      TODO |
| Singh et al. [142] |        [RefineZono](https://github.com/stanleybak/nnenum/) |               piecewise linear |                        ReLU | MNIST and ACAS Xu |      TODO |

## Incomplete methods

### Abstract Interpretation-based Formal Methods

|          Author Reference |                                          Tool Name |             Supported Layers |                 Activations |                                           Dataset | Benchmark |
| ------------------------: | -------------------------------------------------: | ---------------------------: | --------------------------: | ------------------------------------------------: | --------: |
|          Gehr et al. [72] |                                                AI2 |             piecewise linear |                        ReLU |                                MNIST and CIFAR-10 |      TODO |
|        Singh et al. [140] |    DeepZ - [ERAN](https://github.com/eth-sri/eran) |                              | ReLU, *sigmoid*, adn *tanh* |                                MNIST and CIFAR-10 |      TODO |
|        Singh et al. [141] | DeepPoly - [ERAN](https://github.com/eth-sri/eran) |                              | ReLU, *sigmoid*, adn *tanh* |                                MNIST and CIFAR-10 |      TODO |
|        Singh et al. [143] |   k-ReLU - [ERAN](https://github.com/eth-sri/eran) |                              |                        ReLU |                                MNIST and CIFAR-10 |      TODO |
|       Muller et al. [118] |                                                    |                              |                        ReLU |                                          CIFAR-10 |      TODO |
|           Li et al. [105] |                                                    |             piecewise linear |                        ReLU |                                MNIST and CIFAR-10 |      TODO |
|        Urban et al. [161] |    [Libra](https://github.com/Caterinaurban/Libra) | fully-connected feed-forward |                        ReLU | Adult, COMPAS, German Credit, and Japanese Credit |      TODO |
| Prabhakar and Afzal [125] |                                                    | fully-connected feed-forward |                        ReLU |                                           ACAS Xu |      TODO |
| Sotoudeh and Thakur [145] |                                                    | fully-connected feed-forward | ReLU, *sigmoid*, and *tanh* |                                           ACAS Xu |      TODO |
|       Elboher et al. [62] |                                                    | fully-connected feed-forward |                        ReLU |                                           ACAS Xu |      TODO |
|         Baader et al. [5] |                                                    | fully-connected feed-forward |                        ReLU |                                                   |      TODO |
|         Wang et al. [165] |                                                    | fully-connected feed-forward | ReLU, *sigmoid*, and *tanh* |                                                   |      TODO |

### Other Incomplete Formal Methods

|         Author Reference |                                          Tool Name |                               Supported Layers |                           Activations |            Dataset | Benchmark |
| -----------------------: | -------------------------------------------------: | ---------------------------------------------: | ------------------------------------: | -----------------: | --------: |
|       Xiang et al. [169] |                                                    |                   fully-connected feed-forward |           ReLU, *sigmoid*, and *tanh* |                    |      TODO |
|    Wong and Kolter [167] |                                                    |                               piecewise linear |                                  ReLU | Mnist and ImageNet |      TODO |
| Raghunathan et al. [129] |                                                    | fully-connected feed-forward (only one hidden) |                                  ReLU |                    |      TODO |
|    Dvijotham et al. [59] |                                                    |                   fully-connected feed-forward |                             arbitrary |              MNIST |      TODO |
|        Weng et al. [166] |                              Fast-Lin and Fast-Lip |                   fully-connected feed-forward |                                  ReLU |              MNIST |      TODO |
|       Zhang et al. [173] | [CROWN](https://github.com/CROWN-Robustness/Crown) |                   fully-connected feed-forward | ReLU, *sigmoid*, *tanh*, and *arctan* | MNIST and CIFAR-10 |      TODO |
|     Boopathy et al. [16] |   [CNN-Cert](https://github.com/AkhilanB/CNN-Cert) |                                  convolutional |                                       |                    |      TODO |
|           Ko et al. [95] |  [POPQORN](https://github.com/ZhaoyangLyu/POPQORN) |                        recurrent: LSTM and GRU |                                       |                    |      TODO |
|       Zhang et al. [175] |                                                    |                                        vanilla |                                  ReLU |  safety properties |      TODO |

# How to Repeat our Experiments

Our benchmarks can be run directly from this repo. For each tool we provide the container configuration file to easily run and repeat our benchmarks.

Thus, the only prerequisite in order to run our experiments is to install [singularity](https://sylabs.io/). Sometimes, we even provide the [docker](https://www.docker.com/) version.

...