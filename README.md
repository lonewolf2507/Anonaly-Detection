# Anomaly Detection

## Introduction

Anomaly detection is crucial for analyzing sensor data in various industries. With the rise of IoT, identifying unusual data points has become essential for boosting productivity, security, and preventing failures.

### Project Objectives

Our project aims to:

1. Compare three anomaly detection algorithms for accuracy.
2. Find the month with the most anomalies.
3. Identify the key features contributing to anomalies in sensor data.

These findings can enhance the performance of the VEGA shrink wrapper, reducing downtime and improving operational efficiency.

## Dataset Information

### Data Source

The dataset utilized in this research was sourced from the European research and innovation project IMPROVE. It consisted of machine data related to a degrading component recorded over the course of a year.

### Machine Description

The data pertains to the Vega shrink wrapper, a machine produced by OCME, and widely employed in large production lines within the food and beverage industry. The primary function of this machine is to gather bottles or cans, wrap them in plastic film, and then use heat-shrinking to fit the wrapped items into predetermined package sizes.

### Blade Assembly Significance

The cutting assembly within the Vega shrink wrapper holds particular significance in achieving the machine's high availability objective. Proper blade setup and maintenance are crucial for this purpose. The high rotational speed and metal casing of the blade prevent visual inspection while in use. Hence, monitoring the degradation of the blades becomes essential to enhance machine dependability and minimize unscheduled downtime due to failed cuts.

### Data Features

The dataset included various features, such as motor torque, lag error, speed, and position for both the blade and wrapper. Additionally, performance measurements (e.g., vax) were part of the data.

### Machine Modes and Speeds

The Vega shrink wrapper is capable of operating in eight different modes, each with several available speeds. The recorded data had a time resolution of 4 milliseconds, providing detailed insights into the machine's operation.

This dataset forms the foundation of our research, enabling us to explore anomaly detection and predictive maintenance for the Vega shrink wrapper, with the ultimate goal of improving machine dependability and reducing unscheduled downtime.

## Model Training

### Anomaly Detection Methods

Anomaly detection encompasses various methods, each suited to different data scenarios and performance requirements. The primary categories of anomaly detection methods include:

- **Statistical Methods**: These models characterize normal behavior and identify anomalies based on deviations from the norm.

- **Density-Based Methods**: Anomalies are detected as low-density data points in the feature space.

- **Clustering-Based Methods**: These methods group data and identify anomalies as data points that fall outside of clusters.

- **Rule-Based Methods**: Anomalies are identified using pre-defined rules or thresholds.

- **Deep Learning-Based Methods**: Neural networks, such as Autoencoders, are used to identify deviations in data patterns.

- **Ensemble Methods**: Multiple anomaly detection methods are combined for improved accuracy.

- **Time-Series-Specific Methods**: Specialized techniques like statistical process control, exponential smoothing, and ARIMA are used for time-series data.

### Algorithms Employed

In this study, we employed a diverse set of algorithms to train our models, representing different categories:

- **One-class SVM (Support Vector Machine)**: A density-based approach, One-class SVM is well-suited for anomaly detection, particularly for non-linearly separable high-dimensional data. It requires only normal data for training.

- **K-means**: While primarily a clustering algorithm, K-means can be integrated into an anomaly detection pipeline. It can help identify clusters that may contain anomalous data points.

- **Autoencoder**: Falling under deep learning methods, Autoencoders excel at learning complex data patterns. They can be employed for both unsupervised and supervised anomaly detection, generalizing to unseen anomalies not present in the training data.

### Method Selection

The choice of the anomaly detection method depends on the specific characteristics of the data and the desired performance. Each method offers unique advantages, and our project explores the potential benefits of One-class SVM, K-means, and Autoencoder for detecting anomalies in machine sensor data.

In summary, One-class SVM is advantageous for handling non-linearly separable high-dimensional data with minimal training data requirements, K-means can identify clusters containing anomalous data, and Autoencoder excels at learning complex patterns and can be applied to both supervised and unsupervised anomaly detection scenarios.

## Results

### Relationships between Algorithms

In our research, we observed varying levels of correlation between different anomaly detection algorithms. Specifically, K-means and OC-SVM displayed a notably higher negative correlation with each other compared to their correlation with the Autoencoder.

### Possible Explanations

We propose a couple of factors that might contribute to this observed behavior:

1. **Dimensionality Reduction**: The Autoencoder's role in dimensionality reduction could be a key factor. By reducing noise and eliminating irrelevant features from the data, the Autoencoder might mitigate issues that K-means and OC-SVM encounter. This dimensionality reduction can lead to more focused representations of the data.

2. **Nonlinear Relationships**: Another factor may lie in the Autoencoder's ability to learn nonlinear relationships within the data. This capacity can be especially beneficial for datasets characterized by complex and nonlinear patterns. K-means and OC-SVM may struggle to capture such intricate relationships, potentially resulting in their lower correlation with the Autoencoder.

These insights highlight the importance of considering both data characteristics and algorithm capabilities when selecting the most suitable anomaly detection approach for a given dataset. The observed correlations shed light on the potential advantages of employing the Autoencoder in scenarios where nonlinear relationships and dimensionality reduction are paramount.

## Discussion

In this project, we explored anomaly detection in unlabeled machine sensor data from the VEGA shrink wrapper using three distinct algorithms: K-Means, OC-SVM, and Autoencoder. Our findings can be summarized as follows:

- **Algorithm Performance**:
  - Autoencoder outperformed the others, showcasing its effectiveness in detecting anomalies in unlabeled data.
  - K-Means demonstrated promise, albeit with slightly lower accuracy than the Autoencoder.
  - OC-SVM faced challenges due to limited labeled data, emphasizing the utility of unsupervised learning for unlabeled datasets.

- **Kurtosis Analysis**:
  - April and August exhibited the highest anomaly occurrences, warranting further investigation into potential manufacturing issues during these months.

- **Feature Contributions**:
  - Temperature and pressure features emerged as significant contributors to anomalies, offering insights for root cause analysis and prevention.

Our study introduces novel approaches to anomaly detection, combining diverse algorithms, leveraging kurtosis for temporal insights, and providing valuable manufacturing process insights. However, it's essential to acknowledge our study's limitations, such as its specificity to the VEGA shrink wrapper and the need for further research on labeled datasets.

In conclusion, our project advances anomaly detection in manufacturing processes, potentially enhancing efficiency and productivity while acknowledging areas for future exploration and refinement.

## Conclusion

In this study, we aimed to detect anomalies in unsupervised machine sensor data from the VEGA shrink wrapper using three algorithms: OC-SVM, k-means, and an autoencoder. Key findings and insights include:

- **Algorithm Performance**:
  - Autoencoder outperformed OC-SVM and k-means in detecting anomalies due to its ability to capture underlying data patterns.
  - OC-SVM struggled due to assumptions of Gaussian distribution, limiting its performance.
  - K-means primarily focused on clustering and couldn't effectively detect anomalies.

- **Temporal Insights**:
  - Month 4 exhibited the highest anomaly occurrences, possibly linked to increased production demands or external factors.
  - Blade position and lag error were significant contributors to anomalies, suggesting mechanical issues or maintenance needs.

Our study underscores the effectiveness of the autoencoder algorithm for unsupervised anomaly detection in machine sensor data. Further data analysis can yield valuable insights for enhancing machine performance and reliability. Exploring advanced deep learning methods like CNNs and RNNs presents intriguing avenues for future research in this domain.

In summary, this study emphasizes the importance of anomaly detection in machine sensor data, with the autoencoder algorithm proving effective. Insights gained from anomaly analysis can lead to improved production processes and machine reliability.
