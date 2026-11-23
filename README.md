# Denoising Autoencoder (DAE) on MNIST

**Goal:** design, implement and evaluate a multi-layer Denoising Autoencoder that learns to recover clean handwritten digits from inputs corrupted with Gaussian noise (standard deviation 0.5).

| Step | What is done |
|---|---|
| 1. Data Preparation | Load MNIST, normalise to [0, 1], flatten to 784-d, build clean and noisy (σ = 0.5, clipped to [0, 1]) versions |
| 2. Architecture | 784 → 256 (ReLU) → 128 (ReLU, bottleneck) → 256 (ReLU) → 784 (Sigmoid) |
| 3. Training | Adam optimiser, MSE loss, 20 epochs, batch size 256 |
| 4. Results and Analysis | 3 × 5 grid: clean test image / noisy input / DAE reconstruction |

**Running on Kaggle:** click **Add Data** (right sidebar), search for an MNIST dataset (e.g. *MNIST in CSV* or *MNIST Dataset*) and add it. The loader in Section 1 finds it automatically under `/kaggle/input`. If no dataset is attached, it falls back to `keras.datasets.mnist`, which needs **Internet: On** in the notebook settings. No GPU is required.
