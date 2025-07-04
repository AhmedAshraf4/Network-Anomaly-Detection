# 🛰️ Network Anomaly Detection (Unsupervised Learning)

This project applies unsupervised clustering techniques to detect anomalies in network traffic using the KDD Cup 1999 dataset. The goal is to identify potential cyber-attacks in unlabeled data using clustering algorithms and evaluate their performance using precision, recall, F1-score, and entropy.

---

## 📊 Dataset
- Name: KDD CUP 1999 (25% subset used)
- Description: Simulated network traffic with features like:
  - Protocol type
  - Service
  - Source/Destination IP
  - Port numbers
  - Attack type (used only for evaluation)

---

## 🧠 Algorithms Used
- K-Means Clustering
  - Partitions data into k clusters minimizing within-cluster variance.
  - Tested with multiple cluster sizes: k = [7, 15, 23, 31, 45].
  - Performance evaluated at each cluster count.
- Spectral Clustering
  - Suitable for non-convex shaped data.
  - Steps:
    1. Build similarity graph (e.g., k-NN or fully connected)
    2. Compute adjacency and degree matrices
    3. Derive the graph Laplacian
    4. Compute eigenvectors of Laplacian
    5. Apply K-Means to the new representation
- DBSCAN (Density-Based Spatial Clustering of Applications with Noise)
  - Groups points by local density.
  - Robust to noise and doesn’t require specifying number of clusters.
- Parameters:
  - eps (radius of neighborhood)
  - minPoints (minimum points within eps to form a core)
- Uses Euclidean distance
- Tuned using k-distance graph for optimal eps

**🔍 DBSCAN Results:**
- Precision: 43.245
- Recall: 53.46
- F1-Score: 49.91
- Entropy: 0.549

- Agglomerative Clustering
  -  Hierarchical bottom-up clustering:
      1. Start with each point as a separate cluster
      2. Merge closest clusters iteratively  
  -  Drawback: Computational complexity is O(n² log n)

---

## 🧪 Performance Metrics
- Precision: How many predicted anomalies were correct?
- Recall: How many actual anomalies were detected?
- F1-Score: Harmonic mean of precision and recall
- Entropy: Measures the uncertainty/randomness in clustering

