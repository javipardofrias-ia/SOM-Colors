

## 🎨 SOM\_Colors — Self-Organizing Map for RGB Color Clustering

### 📘 Description

This project implements a **Self-Organizing Map (SOM)** from scratch in Python using NumPy, designed to cluster and visualize randomly generated RGB colors. The goal is to demonstrate how unsupervised neural networks can self-organize and reveal patterns in raw, high-dimensional color data.

The notebook provides a hands-on learning experience by walking through data generation, SOM training, and colorful visualizations to understand how the Kohonen network learns to organize RGB color space.

---

### 🛠️ Requirements

Ensure you have Python 3.8+ and the following libraries installed:

```bash
pip install numpy pandas matplotlib
```

#### Dependencies used:

* `numpy` – matrix operations and color data generation.
* `pandas` – optional (mostly used for structure).
* `matplotlib.pyplot` & `patches` – 2D and 3D visualizations.
* `mpl_toolkits.mplot3d` – 3D color space plotting.
* `math.exp` – used in Gaussian neighborhood function.

---

### 🖼️ Dataset

Unlike other datasets, this project generates its own RGB values:

* **Generated Data:** 100 random RGB color vectors.
* **Range:** Each channel (R, G, B) is sampled from `[0, 255]`.
* **Shape:** The resulting dataset is a NumPy array of shape `(100, 3)`.

This approach ensures full control over input data and allows easy experimentation with color clustering.

---

### 🧠 SOM Network Configuration

The Self-Organizing Map is configured as follows:

| Hyperparameter     | Description                                      | Value  |
| ------------------ | ------------------------------------------------ | ------ |
| `lado_mapa`        | Width/height of the 2D Kohonen map (square grid) | `40`   |
| `periodo`          | Number of training iterations                    | `5000` |
| `learning_rate`    | Initial learning rate for weight adaptation      | `0.07` |
| `normalizar_datos` | Whether to scale input RGB values to \[0, 1]     | `True` |

---

### 🧬 Weight Initialization & Training

Weights are initialized randomly for each neuron in the SOM grid. During training:

1. A random RGB color vector is selected.
2. The **Best Matching Unit (BMU)** — the neuron whose weight vector is closest to the input — is identified using Euclidean distance.
3. The BMU and its neighbors are updated toward the input vector, using a Gaussian neighborhood function.
4. Both the **learning rate** and **neighborhood radius** decay over time for convergence.

This process organizes neurons so that nearby ones represent similar colors, forming natural color gradients across the grid.

---

### 📊 Visualizations

The notebook produces:

* A **3D scatter plot** of the generated RGB data.
* A **2D color grid** displaying the final weights of the SOM, where each neuron shows the color it represents.
* Optional **error tracking** (quantization error per iteration) for monitoring convergence.

These visuals help illustrate how the SOM learns the structure of RGB space and organizes colors meaningfully across a 2D grid.

---

### 🚀 How to Run

1. Download or clone the repository.
2. Open the notebook:

   ```bash
   jupyter notebook SOM_Colors.ipynb
   ```
3. Run the cells sequentially to:

   * Generate random color data.
   * Train the SOM.
   * Visualize the color organization results.

---

### 📌 Applications & Extensions

* Interactive color palette generation.
* Compression of high-dimensional color spaces.
* Unsupervised clustering in visual domains.
* Educational tool for understanding neural networks and unsupervised learning.

You can also adapt the SOM implementation to work with:

* Image pixels
* Color palettes from datasets (e.g., CIFAR-10)
* Real-world color schemes (e.g., fashion or art datasets)


