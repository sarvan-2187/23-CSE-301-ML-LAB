# 06-K-Means-Clustering

## Task 1: Old Faithful Geyser Eruptions Segmentation
- Dataset: [06-kmeans-dataset-task-1.csv](06-kmeans-dataset-task-1.csv), the Old Faithful geyser data (Yellowstone National Park, Wyoming, USA) from R's `datasets::faithful`, via [Rdatasets](https://github.com/vincentarelbundock/Rdatasets)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/06-K-Means-Clustering/kmeans-task-1.ipynb)

### Solution
The dataset has 272 eruptions, each with the eruption duration (`eruptions`, minutes) and the waiting time to the next eruption (`waiting`, minutes). Both features are standardised because they are on very different scales. The elbow method and silhouette scores for k = 2 to 6 both point to k = 2 (silhouette score 0.745), so K-Means with k = 2 is applied. It segments the eruptions into two groups:

| Cluster | Eruptions | Mean duration | Mean waiting time |
|---|---|---|---|
| Short | 98 | 2.05 min (1.6–3.4) | 54.6 min (43–71) |
| Long | 174 | 4.30 min (3.1–5.1) | 80.1 min (64–96) |

Short eruptions are followed by short waits and long eruptions by long waits. The clusters and their centroids are plotted.

## Task 2: Image Compression
- Image: [06-kmeans-image-task-2.png](06-kmeans-image-task-2.png), a 396 x 396 x 3 centre crop of scikit-learn's sample `flower.jpg`
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/06-K-Means-Clustering/kmeans-task-2.ipynb)

### Solution
The 396 x 396 x 3 image (56,775 unique colours) is reshaped into 156,816 pixels, each an (R, G, B) point. K-Means with K = 16 groups these pixels into 16 colours. Each pixel is then replaced by its cluster's centroid colour, so the image only needs a 16-colour palette plus a 4-bit index per pixel instead of 24 bits. This reduces the size from 3,763,584 bits (459.4 KB) to 627,648 bits (76.6 KB), a 6x compression, with little visible loss. The notebook shows the original and compressed images side by side, the learned 16-colour palette, and a comparison for K = 2, 4, 8, 16 and 32.
