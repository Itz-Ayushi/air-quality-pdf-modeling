# 🌬️ Air Quality Analysis: PDF Learning
### Non-Linear Modeling via Roll-Number Parameterization

This project implements a custom pipeline to transform real-world $NO_2$ concentration data and model its behavior using a Gaussian-type Probability Density Function (PDF).

---

## 🛠️ The Workflow

1.  **Ingest:** $NO_2$ features from the *India Air Quality Dataset*.
2.  **Clean:** Numerical conversion and outlier/null removal.
3.  **Warp:** Apply a student-specific non-linear transformation.
4.  **Model:** Estimate parameters for a Gaussian-style fit.
5.  **Verify:** Visualize the overlap between data and the learned curve.

---

## 🧬 Mathematical Framework

### 1. Unique Transformation
Each data point $x$ is mapped to $z$ using parameters $a_r$ and $b_r$ derived from a specific **University Roll Number**:

$$z = x + a_r \sin(b_r x)$$

### 2. Gaussian PDF Learning
The transformed distribution is modeled as:

$$\hat{p}(z) = c \cdot e^{-\lambda (z - \mu)^2}$$

Where:
* $\mu$: Shift (Mean)
* $\lambda$: Concentration (Precision)
* $c$: Normalization constant

---

## 📊 Data Mapping

| Input Variable | Process | Output |
| :--- | :---: | :--- |
| **$NO_2$ Concentration** | $\rightarrow$ | **Transformed $z$** |
| **Roll Number** | $\rightarrow$ | **Model Parameters ($\mu, \lambda, c$)** |



<img width="584" height="455" alt="image" src="https://github.com/user-attachments/assets/40f7b8e4-7c86-4fd3-8ccc-e30e2769067b" />


---

## 📈 Key Results
* **Unique Distortions:** The roll-number parameters create distinct data "shapes" for every user.
* **High Fidelity:** Despite the non-linear warping, the Gaussian-type PDF effectively captures the density of the transformed feature.
* **Visual Proof:** The overlay of $\hat{p}(z)$ on the histogram confirms the model's predictive accuracy.

## 🏁 Conclusion
By bridging environmental data with non-linear math, this project demonstrates that even "distorted" real-world signals maintain statistical properties that can be captured by parameterized density functions.
