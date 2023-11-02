# Machine-Failure-Predictions

Introduction

This project focuses on predicting machine failures. The dataset contains information related to the performance of machines, including features such as torque, tool wear, temperature, air temperature, and binary indicators for various failure modes.

Project Objective

The main goal of this project is to develop a predictive maintenance model that can accurately predict machine failures based on the provided features. This predictive model can help businesses in:

Lowering production costs by avoiding unexpected machine failures.

Maintaining high production quality by preventing machine failures.

Enabling timely maintenance and replacement of tools and machines.

Improving overall operational efficiency.

To achieve this objective, you can explore, analyze, and model the dataset to create a robust machine learning or predictive maintenance solution.

Dataset Description

The dataset consists of three main files:

train.csv: This is the training dataset containing 136,429 rows and 14 columns. The target variable, indicating machine failure, is binary and not located in the last column to align with the original dataset's ordering.

test.csv: This is the test dataset, and the goal is to predict the probability of machine failure for the data points in this file.

The dataset contains the following features:

Type: A categorical variable representing product quality variants (L for low, M for medium, and H for high).

Air Temperature [K]: Generated using a random walk process and normalized to have a standard deviation of 2 K around 300 K.

Process Temperature [K]: Generated using a random walk process, normalized to have a standard deviation of 1 K, and added to the air temperature plus 10 K.

Rotational Speed [rpm]: Calculated from a power of 2860 W, overlaid with normally distributed noise.

Torque [Nm]: Torque values are normally distributed around 40 Nm with a standard deviation of 10 Nm and no negative values.

Tool Wear [min]: Tool wear values are affected by the quality variants (H/M/L) and add 5/3/2 minutes of tool wear to the used tool in the process.

Machine Failure: A binary indicator of machine failure, consisting of five independent failure modes:

Tool Wear Failure (TWF): The tool will be replaced or fail at a randomly selected tool wear time between 200 ~ 240 mins.

Heat Dissipation Failure (HDF): Occurs when the difference between air and process temperature is below 8.6 K, and the rotational speed is below 1380 rpm.

Power Failure (PWF): Happens when the product of torque and rotational speed (in rad/s) falls below 3500 W or goes above 9000 W.

Overstrain Failure (OSF): Occurs when the product of tool wear and torque exceeds specific thresholds for different product variants (L/M/H).

Random Failures (RNF): Each process has a 0.1% chance of failure regardless of its process parameters.

If any of the above failure modes are true for a data point, the 'Machine Failure' label is set to 1, indicating a machine failure.

