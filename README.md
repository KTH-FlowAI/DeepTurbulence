# Predictions of turbulent shear flows using deep neural networks

## Introduction

The code in this repository features a MATLAB implementation of the model for wall turbulence proposed by [Moehlis *et al.*](https://iopscience.iop.org/article/10.1088/1367-2630/6/1/056/meta) (2004, New J. Phys.). The time series generated are used to train neural networks that can predict the time evolution of the coefficients of the nine-equation model. More details about the implementation and the results from the training are available in ["Predictions of turbulent shear flows using deep neural networks", P.A. Srinivasan, L. Guastoni, H. Azizpour, P. Schlatter, R. Vinuesa](https://link.aps.org/doi/10.1103/PhysRevFluids.4.054603) (2019, *Phys. Rev. Fluids*; also available in [arXiv](https://arxiv.org/abs/1905.03634))

## Data generation

The MATLAB scripts in [Data generator (Moehlis model)](https://github.com/lguas/Deepturb/tree/master/Data%20generator%20(Moehlis%20model)) are used to generate and visualize the training, validation and test datasets for the neural networks architectures. In particular:
* [moehlis_model_script.m](https://github.com/lguas/Deepturb/blob/master/Data%20generator%20(Moehlis%20model)/moehlis_model_script.m) generates a single time series
* [moehlis_data_gen.m](https://github.com/lguas/Deepturb/blob/master/Data%20generator%20(Moehlis%20model)/moehlis_data_gen.m) generates a user-defined number of series and gather them in a single MATLAB file
* [plot_amplitudes.m](https://github.com/lguas/Deepturb/blob/master/Data%20generator%20(Moehlis%20model)/plot_amplitudes.m) and [visualize_fields.m](https://github.com/lguas/Deepturb/blob/master/Data%20generator%20(Moehlis%20model)/visualize_fields.m) can be used to check the amplitudes of the different modes and visualize the corresponding flow fields

## Training neural networks

Once the time series dataset is created, neural networks can be trained on this dataset. Two different architectures can be chosen, multilayer perceptron (MLP) networks or Long short-term memory (LSTM) networks.

## Prediction of new time series

The trained model can be used to predict new timeseries, based on a initial sequence of *p* elements. Some trained models are available in [this folder](https://github.com/lguas/Deepturb/tree/master/Neural%20networks%20models/trained_nn_models)
