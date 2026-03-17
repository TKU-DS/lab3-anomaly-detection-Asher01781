**🧠Reflection Questions**

- **The Breakdown Point**: Why is MAD mathematically superior to the Standard Deviation () for this specific task? What would happen to the threshold if a massive spike entered a standard Z-score calculation?

- MAD is mathematically superior to the Standard Deviation because it is based on the median instead of the mean. The median is less affected by extreme values, so the MAD remains stable even if a large spike appears in the data. In contrast, the standard deviation is sensitive to outliers because it squares the deviations from the mean.
- If a massive spike enters a standard Z-score calculation, it will increase the value of σ significantly. This inflates the anomaly threshold, making future anomalies harder to detect because extreme values will appear less unusual.

- **Safe Appends**: Why is it critical that we only window.append(value) _after_ we have verified it is not an anomaly?

- Because if an outlier were added to the window, it would distort the median and MAD used for future calculations. This would reduce the accuracy of the anomaly detection. By rejecting anomalous values first, the sliding window maintains a stable baseline for detecting future anomalies.