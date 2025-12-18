# Anomaly Detection in Cloud and Data Systems

This project studies anomaly detection methods for cloud and data system metrics, with a focus on understanding when simple statistical techniques fail and when machine learning approaches become necessary.

The goal is not to maximize benchmark metrics, but to analyze **assumptions, failure modes, and robustness** under realistic system behavior.

---

## Motivation

Cloud and data systems generate time-series signals such as cost, utilization, and workload metrics. Detecting anomalous behavior in these signals is critical for reliability, cost control, and performance monitoring.

While statistical methods (e.g., Z-score) are widely used due to their simplicity, they rely on global distributional assumptions that often break under real-world conditions such as non-stationarity, regime shifts, and contextual anomalies.

This project investigates these limitations and evaluates when ML-based approaches provide practical advantages.

---

## Project Structure

- `data_raw/`  
  Raw synthetic data and real-world datasets (Numenta AWS CloudWatch traces)

- `data_processed/`  
  Cleaned data, engineered features, and anomaly flags used for modeling

- `results/`  
  Saved visualizations and experimental artifacts

- `notebooks/`  
  Exploratory analysis and experiments

- `paper_outline.md`  
  Research-oriented outline describing methods, experiments, and findings

---

## Experiments

### 1. Synthetic Cloud Cost Data
A controlled synthetic dataset was created to simulate cloud cost behavior with injected global outliers. Under these idealized conditions, Z-score based anomaly detection achieves perfect performance, illustrating its effectiveness when global statistical assumptions hold.

### 2. Real Cloud System Data
Real AWS CloudWatch CPU utilization data exhibits noise, non-stationarity, and regime changes. In this setting, Z-score fails to detect many anomalous behaviors, while Isolation Forest using contextual features demonstrates improved robustness.

---

## Key Findings

- Statistical methods perform well when anomalies are extreme and globally separable.
- Real-world cloud workloads violate global stationarity assumptions.
- ML-based methods that incorporate local context are more robust under evolving system behavior.

---

## Research Direction

This work supports ongoing research interests in **machine learning for data systems**, anomaly detection under non-stationarity, and practical monitoring of cloud workloads.

Future extensions include forecast-based anomaly detection and multi-metric system modeling.
