# Emission–Congestion Decoupling in Urban Traffic Networks

## Overview

This project investigates the relationship between **urban traffic congestion and vehicle emissions**, with a particular focus on whether increasing congestion always results in proportionally higher emissions.

The framework combines real-world traffic data, emission estimation, synthetic intersection-network modelling, decoupling analysis, and machine learning to study emission–congestion behaviour in intersection-dense urban environments.

The project uses **Washington, DC travel-time data** together with simulated intersection-network scenarios and applies **XGBoost classification** to analyse and predict emission–congestion decoupling patterns.

## Objectives

- Analyse the relationship between traffic congestion and estimated vehicle emissions.
- Investigate conditions under which emissions and congestion become decoupled.
- Compare emission–congestion behaviour across different intersection-network configurations.
- Develop a machine-learning model for classifying decoupled and coupled traffic conditions.
- Identify the traffic and network characteristics that contribute most to decoupling behaviour.

## Methodology

The overall workflow consists of the following stages:

**Traffic Data → Speed & Delay Estimation → Congestion Metrics → Emission Estimation → Decoupling Analysis → Network Modelling → Dataset Integration → XGBoost Classification**

### 1. Traffic Data Processing

Real-world travel-time data from Washington, DC is processed to derive traffic characteristics such as:

- Average speed
- Free-flow travel time
- Travel delay
- Congestion index

### 2. Emission Estimation

Vehicle emissions are estimated using a speed-dependent polynomial emission model.

The framework calculates:

- CO₂ emissions per kilometre
- CO₂ emissions per trip

### 3. Emission–Congestion Decoupling

Relative changes in congestion and estimated emissions are analysed to determine whether the two variables follow a coupled relationship or exhibit decoupling behaviour.

A **Decoupling Index** is used to characterize the relationship between changes in congestion and emissions.

### 4. Intersection-Network Modelling

Synthetic intersection networks are used to examine different traffic configurations, including:

- Signalized intersections
- Unsignalized intersections
- High-volume intersections
- Different intersection densities and delay conditions

These scenarios are compared with the real-world Washington, DC data.

### 5. Machine Learning

An **XGBoost Classifier** is trained to classify emission–congestion decoupling behaviour.

The model uses traffic and network characteristics as input features and predicts the decoupling class.

Model evaluation includes:

- Accuracy
- Classification report
- Confusion matrix
- Feature importance analysis

The trained model is saved as:

`xgboost_decoupling_model.pkl`

## Machine Learning Model

The project uses **XGBoost**, a gradient-boosted decision-tree algorithm suitable for classification problems involving nonlinear relationships between multiple features.

The implemented configuration includes:

- 150 estimators
- Maximum tree depth: 4
- Learning rate: 0.1
- Subsample: 0.8
- Column sampling: 0.8
- Random state: 42
- 80/20 train-test split

## Results

The analysis demonstrates that the relationship between congestion and emissions is not necessarily uniform across different urban traffic conditions.

The study identifies conditions where emission behaviour can become decoupled from congestion, particularly under specific combinations of traffic speed, intersection structure, and delay characteristics.

The XGBoost model provides a machine-learning-based classification of decoupling behaviour and enables analysis of the relative importance of the input features.

## Technologies

- **Python**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **XGBoost**
- **Matplotlib**
- **Seaborn**
- **Jupyter Notebook**

## Repository Contents

| File | Description |
|---|---|
| `emission_congesiton.py` | Main Python implementation |
| `Emission_Congesiton.ipynb` | Complete research and analysis workflow |
| `emission-congestion-decoupling paper.pdf` | Research paper |
| `.gitignore` | Git configuration for Python projects |

## Limitations

The current framework relies on **estimated emission values derived from traffic parameters rather than direct real-time emission measurements**. This can affect the accuracy of the estimated emission behaviour.

The present study also focuses on the available Washington, DC data and simulated intersection-network scenarios.

## Future Work

Future development can include:

- Integration of real-time traffic and emission sensor data
- Extension to multiple cities
- Real-time traffic data aggregation
- Advanced spatial and spatio-temporal learning
- Deep-learning-based modelling
- Integration with smart-city traffic management systems

## Research Paper

The research paper associated with this project is available in the repository:

**`emission-congestion-decoupling paper.pdf`**

## Authors

**Kevin Godson A**  
**Shiju George**

---

*This repository contains the implementation and research materials associated with the study of emission–congestion decoupling in intersection-dense urban traffic networks.*
