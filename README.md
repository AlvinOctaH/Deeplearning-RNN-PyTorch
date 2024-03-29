# RNN PyTorch

----------------
## Table of contents

- [Introduction to RNN and PyTorch](#Introduction-to-RNN-and-PyTorch)
  - What is Recurrent Neural Network (RNN)?
  - What is PyTorch?
- [Preparing the dataset](#Preparing-the-dataset)
  - Heatmap
  - Data Preprocessing
- [RNN Structure](#RNN-Structure)

----------
## Introduction to RNN and PyTorch
### What is Recurrent Neural Network (RNN)?
<p align="justify">
A recurrent neural network (RNN) is a type of artificial neural network that is particularly well-suited for processing sequential data or time series data. Unlike traditional feedforward neural networks, RNNs have loops in their network which allow information to persist and be passed from one step to the next. This allows them to effectively model and learn from sequential patterns and dependencies in data, such as those found in natural language, speech, handwriting, or sensor data. The key to this capability is the hidden state (or memory) within the RNN's internal loops, which captures information about what has been calculated previously. This hidden state acts as an internal memory that updates at each time step as it processes new inputs, informed by its prior state. Through this recurrent structure and dynamic memory ability, RNNs can very naturally process inputs of varying lengths. While powerful, training traditional RNNs can be challenging due to exploding or vanishing gradient problems. However, more sophisticated RNN architectures like LSTMs and GRUs have been developed to help mitigate these issues. 
</p>

<p align="center">
    <img width="600" src="https://media.geeksforgeeks.org/wp-content/uploads/20231204125839/What-is-Recurrent-Neural-Network-660.webp" alt="Recurrent Neural Network (RNN">
</p>

**Source :** [geeksforgeeks.org](https://www.geeksforgeeks.org/introduction-to-recurrent-neural-network/), [amazon.com](https://aws.amazon.com/what-is/recurrent-neural-network/#:~:text=A%20recurrent%20neural%20network%20(RNN,complex%20semantics%20and%20syntax%20rules.)).

### What is PyTorch?
<p align="justify">
PyTorch is an open-source machine learning (ML) framework based on the Python programming language and the Torch library. Torch is an open-source ML library used for creating deep neural networks and is written in the Lua scripting language. It's one of the preferred platforms for deep learning research. The framework is built to speed up the process between research prototyping and deployment. 
</p>

**Source :** [techtarget.com](https://www.techtarget.com/searchenterpriseai/definition/PyTorch), [pytorch.org](https://pytorch.org/).

## Preparing the dataset 
<p align="justify">
This repository uses a dataset of semester results of engineering students from a university. This data was obtained from Kaggle and titled "<a href="https://www.kaggle.com/datasets/sankha1998/student-semester-result/data">Semester Result of Technical Students</a>". The dataset contains information about students' performance, including their roll numbers (converted to random numbers for privacy), college code, subjects taken, and the semester CGPA (Cumulative Grade Point Average) achieved. It represents a real-world scenario where predicting a student's future academic performance can be challenging. According to the dataset provider, predicting the next semester's CGPA is a complex task. However, analyzing a student's past performance can provide valuable insights for making such predictions.
</p>

### 1. Heatmap
<p align="justify">
The first step of preparing the dataset is to look for correlations between variables using heatmaps to take important variables that can be used as RNN input. Heatmaps are effective for visualizing large datasets by representing data values with colors. This allows data scientists and software engineers to quickly identify patterns, trends, and variations in the data. The implementation of the heatmap is shown in the following figure:
</p>
<p align="center">
    <img width="600" src="https://github.com/AlvinOctaH/Deeplearning-RNN-PyTorch/blob/main/assets/Heatmap_RNN.png" alt="Heatmap">
</p>
<p align="justify">
In this repository I use RNN to predict semester 5 grades. As can be seen from the heatmap, only semester 1 to 4 grade variables are correlated with semester 5 grades, so those grades will be the input features for RNN.
</p>

### 2. Data Preprocessing
<p align="justify">
Data preprocessing in the case of this dataset is done by removing variables or columns from the dataset that are not needed, then cleaning the data from missing or NaN values. The results of data preprocessing get 169 rows of clean data, the results can be seen in the following figure:
</p>
<p align="center">
    <img width="300" src="https://github.com/AlvinOctaH/Deeplearning-RNN-PyTorch/blob/main/assets/datacleaned.png" alt="Data Preprocessing">
</p>

## RNN Structure
