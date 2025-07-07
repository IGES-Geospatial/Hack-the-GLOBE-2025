Several students have mentioned memory issues with DBSCAN \- and I wanted to write a few additional thoughts. Before blaming the environment, consider the mathematical implications of what your script is attempting to do (Algorithmic Complexity, Memory Pressure, etc). In the case of DBSCAN, we noted (thanks Neel) that the scitkit-learn implementation of DBSCAN is insufficiently vectorized ([https://stackoverflow.com/questions/16381577/scikit-learn-dbscan-memory-usage](https://stackoverflow.com/questions/16381577/scikit-learn-dbscan-memory-usage)) In addition to the recommendations/suggestions offered by that thread, consider stepping back to the preprocessing phase (e.g. averaging samples, scaling variables, reducing dimensionality, etc).

Further, based on the data profiling phase earlier, we’ve learned that we have a large dataset with 715,326 observations (samples, actually) and 64 columns. The default `min_samples` of 5 is a standard starting point, but for a dataset of this size, you might consider a larger value to define a more substantial neighborhood for forming clusters and to potentially classify fewer points as noise.

A common heuristic is to set `min_samples` to be at least twice the dimensionality of your data. Without preprocessing or dimensionality reduction the dimensionality is 64 (the number of columns). This would suggest a `min_samples` of at least 128\.

However, the best value often requires some experimentation. You could try values significantly larger than 5, perhaps starting with something like 50, 100, or even larger, and observe how the number of clusters and noise points changes. A larger `min_samples` will generally result in fewer, larger clusters and more noise points. This sort of experimentation in (hyper) parameter tuning is an inevitable component of most ML workflows, and the ability to both understand the parameters themselves, what they mean, and how they affect the model outputs is an essential skill that can really set you above the rest. Parameters, hyperparameters, their meanings, and their effects are directly tied to the specific model architecture being utilized.

Consider what constitutes a meaningful cluster in the context of your observation data. How many closely located observations would you expect to form a natural grouping? This domain knowledge can also help guide your choice of `min_samples`. Should coordinate information even be considered during clustering? What information are you hoping to obtain via cluster identification?

One option for minimizing total RAM consumption for some of these intensive processes is to extract a reproducible sample from the dataset like so:

\# Define the sample size (adjust as needed based on available RAM and desired representativeness)

sample\_size \= 100000  \# Example: Sample 100,000 rows

\# Sample the DataFrame

\# Using .sample() is a straightforward way to get a random sample.

\# set a random\_state for reproducibility

source\_df\_sample \= source\_df.sample(n=min(len(source\_df), sample\_size), random\_state=42)

print(f"Original DataFrame shape: {source\_df.shape}")

print(f"Sampled DataFrame shape: {source\_df\_sample.shape}")

Original DataFrame shape: (716031, 64\)

Sampled DataFrame shape: (100000, 64\)

However, creating a truly REPRESENTATIVE sample is difficult.