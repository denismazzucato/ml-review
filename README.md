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

> References in the tables refer to the bibliography inside the review.



## Complete methods

### SMT-based Formal Methods

|           Author Reference |                                                       Tool Name |            Supported Layers |      Activations |                              Dataset | Benchmarks |
| -------------------------: | --------------------------------------------------------------: | --------------------------: | ---------------: | -----------------------------------: | ---------: |
| Pulina and Tacchella [126] |                                                                 | fuly-connected feed-forward |          sigmoid |                                      |            |
|                Ehlers [60] |                    [Planet](https://github.com/progirep/planet) |            piecewise linear |             ReLU |                                MNIST |            |
|           Katz et al. [92] |                                                        Reluplex | fuly-connected feed-forward |             ReLU |                              ACAS Xu |            |
|           Katz et al. [93] | [Marabou](https://github.com/NeuralNetworkVerification/Marabou) |            piecewise linear | piecewise linear |                              ACAS Xu |            |
|         Bastani et al. [8] |                                                                 |            piecewise linear |             ReLU |                   MNIST and CIFAR-10 |            |
|          Huang et al. [86] |                          [DLV](https://github.com/verideep/dlv) |            piecewise linear |             ReLU | MNIST, CIFAR-10, GTSRB, and ImageNet |            |
|    Narodytska et al. [120] |                                                                 |   Binarized Neural Networks |                  |                                MNIST |            |
|          Cheng et al. [30] |                                                                 |   Binarized Neural Networks |                  |                      MNIST and GTSRB |            |

### MILP-based Formal Methods

|      Author Reference |                                             Tool Name |             Supported Layers |       Activations |            Dataset | Benchmark |
| --------------------: | ----------------------------------------------------: | ---------------------------: | ----------------: | -----------------: | --------: |
|     Cheng et al. [29] |                                                       |             piecewise linear | ReLU and *arctan* |                    |           |
| Fischetti and Jo [67] |                                                       |             piecewise linear |              ReLU |              MNIST |           |
|    Brunel et al. [22] |                                                   BaB |             piecewise linear |              ReLU |            ACAS Xu |           |
|    Drutta et al. [58] | [Sherlock](https://github.com/souradeep-111/sherlock) | fully-connected feed-forward |              ReLU |                    |           |
|    Tjeng et al. [149] |   [MIPVerify](https://github.com/vtjeng/MIPVerify.jl) |             piecewise linear |              ReLU | MNIST and CIFAR-10 |           |

### Other Complete Formal Methods

|   Author Reference |                                                  Tool Name |               Supported Layers |                 Activations |           Dataset | Benchmark |
| -----------------: | ---------------------------------------------------------: | -----------------------------: | --------------------------: | ----------------: | --------: |
|  Ruan et al. [134] |                [DeepGO](https://github.com/trustAI/DeepGO) |               piecewise linear | ReLU, *sigmoid*, and *tanh* |             MNIST |           |
|  Wang et al. [163] | [ReluVal](https://github.com/tcwangshiqi-columbia/ReluVal) |   fully-connected feed-forward |                        ReLU |           ACAS Xu |           |
|  Wang et al. [164] | [Neurify](https://github.com/tcwangshiqi-columbia/Neurify) | feed-forward and convolutional |                        ReLU |           ACAS Xu |           |
|  Tran et al. [153] |                   [NNV](https://github.com/verivital/nnv/) |   fully-connected feed-forward |                        ReLU | MNIST and ACAS Xu |           |
|  Tran et al. [154] |                   [NNV](https://github.com/verivital/nnv/) |   fully-connected feed-forward |                        ReLU | MNIST and ACAS Xu |           |
|  Tran et al. [156] |                   [NNV](https://github.com/verivital/nnv/) |               piecewise linear |                        ReLU |   VGG16 adn VGG19 |           |
|    Bak et al. [11] |            [NNENUM](https://github.com/stanleybak/nnenum/) |               piecewise linear |                        ReLU |           ACAS Xu |           |
|  Yang et al. [172] |            [NNENUM](https://github.com/stanleybak/nnenum/) |                                |                        ReLU |           ACAS Xu |           |
| Singh et al. [142] |        [RefineZono](https://github.com/stanleybak/nnenum/) |               piecewise linear |                        ReLU | MNIST and ACAS Xu |           |

## Incomplete methods

### Abstract Interpretation-based Formal Methods

|          Author Reference |                                          Tool Name |             Supported Layers |                 Activations |                                           Dataset | Benchmark |
| ------------------------: | -------------------------------------------------: | ---------------------------: | --------------------------: | ------------------------------------------------: | --------: |
|          Gehr et al. [72] |                                                AI2 |             piecewise linear |                        ReLU |                                MNIST and CIFAR-10 |           |
|        Singh et al. [140] |    DeepZ - [ERAN](https://github.com/eth-sri/eran) |                              | ReLU, *sigmoid*, adn *tanh* |                                MNIST and CIFAR-10 |           |
|        Singh et al. [141] | DeepPoly - [ERAN](https://github.com/eth-sri/eran) |                              | ReLU, *sigmoid*, adn *tanh* |                                MNIST and CIFAR-10 |           |
|        Singh et al. [143] |   k-ReLU - [ERAN](https://github.com/eth-sri/eran) |                              |                        ReLU |                                MNIST and CIFAR-10 |           |
|       Muller et al. [118] |                                                    |                              |                        ReLU |                                          CIFAR-10 |           |
|           Li et al. [105] |                                                    |             piecewise linear |                        ReLU |                                MNIST and CIFAR-10 |           |
|        Urban et al. [161] |    [Libra](https://github.com/Caterinaurban/Libra) | fully-connected feed-forward |                        ReLU | Adult, COMPAS, German Credit, and Japanese Credit |           |
| Prabhakar and Afzal [125] |                                                    | fully-connected feed-forward |                        ReLU |                                           ACAS Xu |           |
| Sotoudeh and Thakur [145] |                                                    | fully-connected feed-forward | ReLU, *sigmoid*, and *tanh* |                                           ACAS Xu |           |
|       Elboher et al. [62] |                                                    | fully-connected feed-forward |                        ReLU |                                           ACAS Xu |           |
|         Baader et al. [5] |                                                    | fully-connected feed-forward |                        ReLU |                                                   |           |
|         Wang et al. [165] |                                                    | fully-connected feed-forward | ReLU, *sigmoid*, and *tanh* |                                                   |           |

### Other Incomplete Formal Methods

|         Author Reference |                                          Tool Name |                               Supported Layers |                           Activations |            Dataset | Benchmark |
| -----------------------: | -------------------------------------------------: | ---------------------------------------------: | ------------------------------------: | -----------------: | --------: |
|       Xiang et al. [169] |                                                    |                   fully-connected feed-forward |           ReLU, *sigmoid*, and *tanh* |                    |           |
|    Wong and Kolter [167] |                                                    |                               piecewise linear |                                  ReLU | Mnist and ImageNet |           |
| Raghunathan et al. [129] |                                                    | fully-connected feed-forward (only one hidden) |                                  ReLU |                    |           |
|    Dvijotham et al. [59] |                                                    |                   fully-connected feed-forward |                             arbitrary |              MNIST |           |
|        Weng et al. [166] |                              Fast-Lin and Fast-Lip |                   fully-connected feed-forward |                                  ReLU |              MNIST |           |
|       Zhang et al. [173] | [CROWN](https://github.com/CROWN-Robustness/Crown) |                   fully-connected feed-forward | ReLU, *sigmoid*, *tanh*, and *arctan* | MNIST and CIFAR-10 |           |
|     Boopathy et al. [16] |   [CNN-Cert](https://github.com/AkhilanB/CNN-Cert) |                                  convolutional |                                       |                    |           |
|           Ko et al. [95] |  [POPQORN](https://github.com/ZhaoyangLyu/POPQORN) |                        recurrent: LSTM and GRU |                                       |                    |           |
|       Zhang et al. [175] |                                                    |                                        vanilla |                                  ReLU |  safety properties |           |

# How to Repeat our Experiments

Our benchmarks can be run directly from this repo. For each tool we provide the container configuration file to easily run and repeat our benchmarks.

Thus, the only prerequisite in order to run our experiments is to install [singularity](https://sylabs.io/). Sometimes, we even provide the [docker](https://www.docker.com/) version.

...