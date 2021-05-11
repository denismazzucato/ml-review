# A Review of Formal Methods applied to Machine Learning

    Caterina Urban and Antoine Miné, 2021, A Review of Formal Methods applied to Machine Learning, 2104.02466

**Table of Context**
- [A Review of Formal Methods applied to Machine Learning](#a-review-of-formal-methods-applied-to-machine-learning)
- [Testing Progress Report](#testing-progress-report)
  - [Model Deployed](#model-deployed)
    - [Complete methods](#complete-methods)
      - [SMT-based methods](#smt-based-methods)
      - [MILP-based methods](#milp-based-methods)
    - [Other complete methods](#other-complete-methods)
    - [Incomplete methods](#incomplete-methods)
  - [Model Training](#model-training)
  - [Data Preparation](#data-preparation)

# Testing Progress Report

We broadly distinguish between analyzers that apply verification after the model is developed *Model Deployed*, during the training phase *Model Training*, and during its preparation *Data Preparation*.

> References in the tables refer to the bibliography inside the review.

## Model Deployed

In addition, we further distinguish between *Complete* and *Incomplete methods*.

### Complete methods

#### SMT-based methods

|                  Reference |                                                            Name |            Supported Layers |      Activations |                            Benchmark | Progress |
| -------------------------: | --------------------------------------------------------------: | --------------------------: | ---------------: | -----------------------------------: | -------: |
| Pulina and Tacchella [126] |                                                                 | fuly-connected feed-forward |          sigmoid |                                      |     TODO |
|                Ehlers [60] |                    [Planet](https://github.com/progirep/planet) |            piecewise linear |             ReLU |                                MNIST |     TODO |
|           Katz et al. [92] |                                                        Reluplex | fuly-connected feed-forward |             ReLU |                              ACAS Xu |     TODO |
|           Katz et al. [93] | [Marabou](https://github.com/NeuralNetworkVerification/Marabou) |            piecewise linear | piecewise linear |                              ACAS Xu |     TODO |
|         Bastani et al. [8] |                                                                 |            piecewise linear |             ReLU |                   MNIST and CIFAR-10 |     TODO |
|          Huang et al. [86] |                          [DLV](https://github.com/verideep/dlv) |            piecewise linear |             ReLU | MNIST, CIFAR-10, GTSRB, and ImageNet |     TODO |
|    Narodytska et al. [120] |                                                                 | fuly-connected feed-forward |                  |                                MNIST |     TODO |
|          Cheng et al. [30] |                                                                 | fuly-connected feed-forward |                  |                      MNIST and GTSRB |     TODO |

#### MILP-based methods

|             Reference |                                                  Name |                     ML model |       Activations |          Benchmark | Progress |
| --------------------: | ----------------------------------------------------: | ---------------------------: | ----------------: | -----------------: | -------: |
|     Cheng et al. [29] |                                                       |             piecewise linear | ReLU and *arctan* |                    |     TODO |
| Fischetti and Jo [67] |                                                       |             piecewise linear |              ReLU |              MNIST |     TODO |
|    Brunel et al. [22] |                                                   BaB |             piecewise linear |              ReLU |            ACAS Xu |     TODO |
|    Drutta et al. [58] | [Sherlock](https://github.com/souradeep-111/sherlock) | fully-connected feed-forward |              ReLU |                    |     TODO |
|    Tjeng et al. [149] |   [MIPVerify](https://github.com/vtjeng/MIPVerify.jl) |             piecewise linear |              ReLU | MNIST and CIFAR-10 |     TODO |
### Other complete methods

### Incomplete methods



## Model Training


## Data Preparation

