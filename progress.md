# Progress Log

This file tracks daily and weekly progress for the research project.

Format:
- Date:
- What was completed:
- Next steps:

------------------------------------------------------------------------------

- Date: 2025-12-11
    - What was completed:
        - Set up project structure and requirements.txt
        - Created EDA.ipynb in Codespaces
        - Generated synthetic cloud cost dataset and saved to data_processed
        - visualized time-series with injected anomalies
    
    - Next Steps:
        - Implement Isolation Forest as First anomaly detection baseline
-------------------------------------------------------------------------------

- Date: 2025-12-12
  - What was completed:
        - Implemented Isolation Forest for cost anomaly detection
        - Visualized predicted anomalies vs ground truth
    - Next steps:
        - Quantitatively evaluate precision and recall
--------------------------------------------------------------------------------

- Date: 2025-12-12
  - What was completed:
        - Implemented Z-score statistical baseline
        - Compared statistical vs ML-based anomaly detection
    - Next steps:
        - Summarize results in comparison table
---------------------------------------------------------------------------------
- Date: 2025-12-12
  - What was completed:
        - Completed baseline comparison between Z-score and Isolation Forest
        - Analyzed tradeoffs and limitations of statistical vs ML-based methods
    - Next steps:
        - Extend to more realistic datasets and contextual anomalies
---------------------------------------------------------------------------------
- Date: 2025-12-18
  - Dataset:
        - NAB realAWSCloudwatch EC2 CPU utilization
  - What was completed:
        - Implemented forecast-based anomaly detection using moving-average forecasting
        - Computed residuals and flagged anomalies using a 99.5th percentile threshold
        - Saved forecast residual dataset and visualization artifact
  - Artifacts generated:
        - data_processed/aws_cloudwatch/cpu_forecast_residuals.csv
        - results/aws_cloudwatch/forecast_residual_anomalies.png
  - Next steps:
        - Summarize tradeoffs across Z-score vs Isolation Forest vs Forecasting
