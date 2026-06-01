# Drone Fleet Decision Support System

A data-driven Decision Support System (DSS) designed to assist drone fleet operators in making operational decisions during large-scale inspection missions.


## Overview

Modern drone fleets generate massive amounts of telemetry and operational data, including battery status, GPS location, flight duration, environmental conditions, and mission information.

Despite having access to large volumes of data, operators still face critical operational questions:

* Can the drone safely complete the mission?
* Should it return to base due to battery limitations?
* Is the weather creating unacceptable operational risk?
* Should the mission be delayed or rerouted?
* Is a backup drone required?

This project explores how telemetry and environmental data can be transformed into actionable recommendations through a Decision Support System (DSS).

The goal is to convert raw UAV operational data into meaningful insights that support faster, safer, and more consistent decision-making.


## Problem Statement

Drone fleet operations often rely on manual monitoring and operator experience.

As mission complexity increases, decision-making becomes more difficult due to:

* Battery uncertainty
* Environmental risk
* Long-distance missions
* Multiple simultaneous drones
* Real-time operational constraints

A poor decision can lead to:

* Mission failure
* Battery depletion
* Emergency landings
* Equipment damage
* Increased operational cost

This project investigates how data analytics and rule-based decision models can reduce these risks.



## Objectives

The project aims to:

* Analyze UAV operational telemetry data
* Identify key risk indicators affecting mission success
* Create decision-support features from raw data
* Generate operational recommendations
* Build a foundation for future dashboard and DSS development



## Dataset

### Raw Dataset

| File | Description |
|--------|-------------|
| [SurveilDrone-Net23.csv](data/raw/SurveilDrone-Net23.csv) | Original UAV telemetry dataset |

### Processed Dataset

| File | Description |
|--------|-------------|
| [SurveilDrone_Net23_DSS_ready_cleaned.csv](data/processed/SurveilDrone_Net23_DSS_cleaned.csv) | Cleaned dataset used for analysis |

### Analysis Notebook

| File | Description |
|--------|-------------|
| [W3_Data_Cleaning.ipynb](notebooks/W3_Data_Cleaning.ipynb) | Data cleaning and preprocessing workflow |

### Included Data Categories

| Category         | Examples                          |
| ---------------- | --------------------------------- |
| Flight Telemetry | Velocity, acceleration, altitude  |
| Navigation       | GPS coordinates, distance to base |
| Battery          | Battery level, power consumption  |
| Mission Data     | Mission ID, mission type          |
| Environment      | Wind speed, temperature, weather  |
| Surveillance     | Object detection metrics          |



## Data Processing Pipeline

```text
Raw UAV Dataset
       ↓
Data Inspection
       ↓
Data Cleaning
       ↓
Feature Engineering
       ↓
Risk Assessment
       ↓
Decision Recommendation
       ↓
DSS-ready Dataset
```

---

## Data Cleaning

The raw dataset undergoes multiple preprocessing steps:

### Data Validation

* Missing value inspection
* Duplicate detection
* Data type validation
* Range validation

### Operational Validation

* Battery percentage validation
* GPS coordinate validation
* Distance validation
* Wind speed validation
* Flight duration validation

### Data Transformation

* Standardized data types
* Cleaned operational records
* Feature generation
* Risk label creation



## Feature Engineering

Several analytical features are derived from the original dataset.

### Generated Features

| Feature                | Purpose                              |
| ---------------------- | ------------------------------------ |
| speed_mps              | Calculate overall drone speed        |
| acceleration_magnitude | Measure movement intensity           |
| battery_risk_level     | Evaluate battery risk                |
| weather_risk_level     | Evaluate environmental risk          |
| distance_risk_level    | Evaluate return feasibility          |
| mission_feasibility    | Assess mission completion likelihood |
| overall_risk_score     | Aggregate operational risk           |
| recommended_action     | Generate operational recommendation  |



## Decision Recommendation Engine

The project generates recommendation labels based on operational conditions.

### Possible Recommendations

| Recommendation      |
| ------------------- |
| Continue Mission    |
| Return to Base      |
| Change Flight Path  |
| Delay Mission       |
| Deploy Backup Drone |
| Emergency Landing   |

These recommendations are generated using rule-based decision logic and will later serve as the foundation for more advanced predictive models.



## Repository Structure

```text
Drone-DSS
│
├── data
│   ├── raw
│   └── processed
│
├── notebooks
│
├── scripts
│
├── reports
│
├── dashboard
│
├── model
│
└── docs
```



## Technologies

* Python
* Pandas
* NumPy
* Jupyter Notebook
* Google Colab
* Git
* GitHub



## Future Development

Planned enhancements include:

* Interactive dashboard development
* Real-time fleet monitoring
* Mission risk prediction
* Battery consumption forecasting
* Explainable decision recommendations
* Fleet-level operational optimization



## Key Outputs

The project currently produces:

* Cleaned UAV dataset
* Data dictionary
* Risk assessment features
* Recommendation labels
* Analytical notebooks
* Reproducible preprocessing pipeline

