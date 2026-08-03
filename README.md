AI-Enabled MBRT System for Rapid Microbial Detection in Milk

📌 Overview

Milk is one of the most widely consumed food products, but it is highly susceptible to microbial contamination during collection, transportation, and storage. Conventional microbial quality assessment methods are often labor-intensive, time-consuming, and dependent on manual observation, making them unsuitable for continuous real-time monitoring.

This project presents an AI-enabled Milk Quality Assessment System that automates the Methylene Blue Reduction Test (MBRT) using computer vision, machine learning, and edge computing. The proposed system continuously monitors the colour variation of methylene blue dye during microbial growth and automatically classifies milk quality into Fresh, Mildly Spoiled, or Spoiled without human intervention.

By integrating embedded hardware, image processing, and artificial intelligence, the system provides a fast, reliable, low-cost, and scalable solution for real-time microbial detection in dairy applications.

🚀 Project Highlights
🥛 Automated Methylene Blue Reduction Test (MBRT)
🤖 AI-based milk spoilage classification
📷 Real-time image acquisition using ESP32-CAM
🌡️ Automatic temperature control at 37°C
🎨 RGB and temporal feature extraction
🌲 Random Forest-based microbial classification
💻 Edge deployment on Intel UP Xtreme
🌐 Real-time monitoring through a web dashboard
⚡ Fast inference suitable for industrial deployment
📖 Background

The Methylene Blue Reduction Test (MBRT) is a well-established biochemical method used to estimate microbial activity in milk.

Fresh milk retains the blue colour of methylene blue for a longer period.
As microbial activity increases, bacteria consume dissolved oxygen and reduce the dye.
The blue colour gradually fades, indicating microbial growth.

Traditionally, this colour transition is monitored manually, making the process subjective and susceptible to human error.

The proposed system automates this entire workflow by combining image acquisition, feature extraction, and machine learning.

⚙️ System Workflow


The complete system consists of the following stages:

1. Sample Preparation
Milk samples are collected.
Methylene Blue reagent is added.
Samples are placed inside the incubation chamber.
2. Temperature-Controlled Incubation

A custom-designed heating circuit maintains the samples at

37°C

using

ESP8266 Controller
DS18B20 Temperature Sensor
Relay Driver
Nichrome Heating Element

This ensures proper MBRT incubation conditions throughout the experiment.

3. Image Acquisition

An ESP32-CAM captures images of the milk samples at regular intervals throughout the incubation period.

The imaging setup includes

Uniform LED illumination
Fixed camera position
Controlled background
Consistent Region of Interest (ROI)

This guarantees reliable colour measurement.

4. Feature Extraction

Each captured image undergoes image processing to obtain discriminative colour features.

Extracted features include

RGB Features
Mean Red
Mean Green
Mean Blue
Temporal Features
ΔR
ΔG
ΔB
Rate of colour change
Cumulative colour variation
Time elapsed

These features effectively characterize the microbial reduction process occurring during MBRT.

5. Data Preprocessing

The extracted features are preprocessed before model training.

Processing includes

Min-Max normalization
Label encoding
Stratified train-test split
Five-fold cross-validation

Dataset split

80% Training
20% Testing
6. Machine Learning Classification

Four supervised learning algorithms are evaluated.

Random Forest
Support Vector Machine (SVM)
Distance-Weighted K-Nearest Neighbour (DW-KNN)
Extreme Gradient Boosting (XGBoost)

The classifiers predict one of three milk quality classes:

🟢 Fresh
🟡 Mildly Spoiled
🔴 Spoiled
7. Best Model Selection

Performance is evaluated using

Accuracy
Precision
Recall
Specificity
F1-score
ROC-AUC

Among all evaluated models,

Random Forest achieved the highest overall performance and was selected for deployment.

8. Edge Deployment

The trained Random Forest model is deployed on an

Intel UP Xtreme Edge Computer

for real-time inference.

The edge system performs

Image acquisition
ROI extraction
Feature extraction
Classification
Result visualization

without requiring cloud connectivity.

9. Web Dashboard

Prediction results are displayed through a lightweight web interface, providing

Predicted milk quality
Real-time monitoring
Easy visualization
User-friendly interaction

This enables rapid decision-making for dairy operators.

🛠 Hardware Components
Intel UP Xtreme Edge Computer
ESP32-CAM
ESP8266
DS18B20 Temperature Sensor
Relay Module
Nichrome Heating Element
White LED Illumination
Power Supply
💻 Software Stack
Python 3.11
OpenCV
NumPy
Pandas
Scikit-learn
Flask
Gradio
Ubuntu Linux
📊 Machine Learning Models Evaluated
Model	Purpose
Random Forest	Final deployment model
Support Vector Machine	Performance comparison
Distance-Weighted KNN	Baseline classifier
XGBoost	Ensemble learning comparison
📈 Performance Evaluation

The models are evaluated using multiple performance metrics.

Accuracy
Precision
Recall
Specificity
F1-score
ROC-AUC

Random Forest consistently demonstrated superior classification performance, robustness, and suitability for real-time edge deployment.

🌍 Applications

The proposed system can be deployed in

🥛 Dairy Farms
🏭 Milk Processing Industries
🚛 Milk Collection Centres
🧪 Food Quality Testing Laboratories
🏪 Cold Storage Facilities
📦 Supply Chain Monitoring
🔬 Research Laboratories
✨ Advantages
Fully automated MBRT analysis
Eliminates subjective manual inspection
Real-time microbial quality assessment
Low-cost embedded implementation
High classification accuracy
Edge AI deployment with low latency
Scalable for industrial applications
Easy integration with IoT-based monitoring systems
🔮 Future Enhancements
Deep learning-based feature extraction
Smartphone-based milk quality monitoring
Cloud-enabled analytics dashboard
Multi-parameter milk quality assessment
Explainable AI (XAI) for prediction interpretation
FPGA-based hardware acceleration for ultra-low latency inference
Large-scale deployment in dairy supply chains
