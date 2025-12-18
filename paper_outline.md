# Paper Outline

## 1. Introduction
    - Anomaly detection is critical for monitoring cloud and data systems
    - Statistical methods rely on global assumptions that often break in real workloads
    - This work contrasts statistical and ML-based approaches under controlled and realistic settings

## 2. Related Work
    - Anomaly detection approaches
    - Cost optimization in data systems
    - Key references

## 3. Method
- Data sources
    - Synthetic cloud cost time-series with injected anomalies
    - Real-world AWS CloudWatch CPU utilization data from the Numenta Anomaly Benchmark

- Feature engineering
    - Raw metric values
    - Contextual features using rolling statistics (rolling mean and rolling standard deviation)
    - Feature engineering designed to capture local behavior under non-stationary workloads

- Models
    - Statistical baseline: Z-score based anomaly detection
    - Machine learning baseline: Isolation Forest using contextual features

## 4. Experiments
- Experimental Setup
    - We evaluate anomaly detection methods on both synthetic and real-world time-series data to contrast performance under controlled and realistic conditions. Synthetic data allows precise control over anomaly characteristics, while real cloud workloads introduce noise, non-stationarity, and regime shifts.

- Datasets
    - Synthetic cloud cost dataset with injected global outliers
    - AWS CloudWatch CPU utilization traces from the Numenta Anomaly Benchmark

- Evaluation Approach
    - Visual inspection of anomaly regions
    - Qualitative comparison between statistical and ML-based detectors
    - Emphasis on robustness under distributional shift rather than only metric optimization

- Implementation details

## 5. Results & Discussion
    - Statistical Baseline: Z-Score
        - On the synthetic dataset, Z-score achieves perfect precision and recall, as injected anomalies are large global deviations from otherwise stable behavior. This highlights the effectiveness of simple statistical methods when assumptions of global stationarity hold.

        - However, on real cloud workload data, Z-score fails to detect many anomalous periods. Distributional shifts and contextual changes in system behavior violate the global statistical assumptions, causing anomalies to appear statistically normal when compared against the full historical distribution.

    - Machine Learning Baseline: Isolation Forest
        - To address these limitations, Isolation Forest is applied using contextual features derived from rolling statistics. By modeling local behavior rather than relying on a single global distribution, Isolation Forest detects anomalous patterns in real workloads, including regime changes and contextual deviations missed by Z-score.

        - While Isolation Forest may introduce additional false positives under controlled conditions, it demonstrates superior robustness under realistic operating conditions where system behavior evolves over time.

    - Key Observations
        - Statistical methods perform well when anomalies are extreme and globally separable
        - Real-world cloud systems exhibit non-stationarity and contextual anomalies
        - ML-based methods incorporating local context provide more reliable detection under realistic workloads

    - Forecast-Based Anomaly Detection (Residuals)
        - We evaluate a forecasting-based detector that models expected behavior and flags anomalies as large residuals between observed and predicted values. Using a rolling-window moving average baseline, we compute residuals and identify anomalous points via a high-quantile threshold on absolute residual magnitude.
        - Unlike Z-score, which relies on a single global distribution, forecasting-based detection adapts to local behavior and can surface contextual deviations during non-stationary periods. This provides an interpretable middle-ground between simple statistical thresholds and ML-based Isolation Forest.


## 6. Conclusion & Future Work
    - This study demonstrates that while simple statistical anomaly detection methods are effective under idealized assumptions, real-world cloud and data systems require models that adapt to evolving behavior. Context-aware machine learning approaches such as Isolation Forest provide increased robustness under non-stationary workloads.

    - Future work includes extending the analysis to forecasting-based anomaly detection and multi-metric system signals.