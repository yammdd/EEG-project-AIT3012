# EE2Graphnet: A Graph Neural Networks Approach for EEG classification

A lightweight summary of our computational neuroscience project combining **Graph Neural Networks (GNNs)** and **Hidden Markov Models (HMMs)** for EEG classification.

---

## 👥 Contributors

<table>
  <tr>
    <td align="center">
        <a href="https://github.com/AriusTXB"><img src="https://github.com/AriusTXB.png" width="80" style="border-radius:50%">
        </a>
        <br>
        <a href="https://github.com/AriusTXB" style="text-decoration:none;">
            <strong>Bao X. Tran</strong>
        </a>
        <br>
        <sub>Project Manager</sub>
    </td>
    <td align="center">
        <a href="https://github.com/its6ueq"><img src="https://github.com/its6ueq.png" width="80" style="border-radius:50%">
        </a>
        <br>
        <a href="https://github.com/its6ueq" style="text-decoration:none;">
            <strong>Bang D.H. Nguyen</strong>
        </a>
        <br>
        <sub>Visualization Lead</sub>
    </td>
    <td align="center">
        <a href="https://github.com/yammdd"><img src="https://github.com/yammdd.png" width="80" style="border-radius:50%">
        </a>
        <br>
        <a href="https://github.com/yammdd" style="text-decoration:none;">
            <strong>Dan T. Bui</strong>
        </a>
        <br>
        <sub>Signal Preprocessing Lead</sub>
    </td>
    <td align="center">
        <a href="https://github.com/martamgesha"><img src="https://github.com/martamgesha.png" width="80" style="border-radius:50%">
        </a>
        <br>
        <a href="https://github.com/martamgesha" style="text-decoration:none;">
            <strong>Hiep T. Phan</strong>
        </a>
        <br>
        <sub>Documentation Lead</sub>
    </td>
    <td align="center">
        <a href="https://github.com/NaHieu2005"><img src="https://github.com/NaHieu2005.png" width="80" style="border-radius:50%">
        </a>
        <br>
        <a href="https://github.com/NaHieu2005" style="text-decoration:none;">
            <strong>Hieu V. Le</strong>
        </a>
        <br>
        <sub>Feature Extraction Lead</sub>
    </td>
    <td align="center">
        <a href="https://github.com/darkjeanne"><img src="https://github.com/darkjeanne.png" width="80" style="border-radius:50%">
        </a>
        <br>
        <a href="https://github.com/darkjeanne" style="text-decoration:none;">
            <strong>Tu H. Nguyen</strong>
        </a>
        <br>
        <sub> Machine Learning Lead</sub>
    </td>
  </tr>
</table>

## 🚀 Overview

This project proposes **EE2GraphNet**, an end-to-end framework that:

* Learns EEG spatial structure using a **learnable adjacency matrix**.
* Models temporal dynamics using **Gaussian HMM**.
* Fuses both into a **hybrid feature representation** for classification.

Pipeline includes:

* Preprocessing (Filtering, ICA, segmentation)
* Latent-state modeling (HMM)
* Graph-based classification (GNN)

---

## 🧠 Motivation

EEG signals are:

* Noisy & non-stationary
* Spatially structured (electrode network)
* Temporally dynamic (latent neural states)

Traditional CNNs ignore non-Euclidean structure; classical ML relies on handcrafted features. Our method unifies **probabilistic temporal modeling** and **graph learning**.

---

## 📚 Method Summary

### 1️⃣ Preprocessing

* Bandpass 0.1–20 Hz
* Notch 50 Hz
* ICA for artifact rejection
* Epoch segmentation (1s)

### 2️⃣ HMM Features

* Train Gaussian HMM on PCA-reduced features
* Compute posterior probabilities γ(t)
* Concatenate with EEG features to form hybrid input

### 3️⃣ Graph Neural Network

* Learnable adjacency matrix (task-specific connectivity)
* Residual GCN layers
* Global pooling → MLP classifier

---

## 🧪 Experiments

Dataset: 25 subjects

* Train: subjects 1–20
* Test: subjects 21–25 (subject-independent split)

Models evaluated:

* Classical ML (LR, LDA, SVM, XGBoost)
* Deep models (EEGNet, Conformer, Transformer, GNN)

### Key Findings

* GNN achieves highest accuracy (~87%)
* DL models outperform classical ML

---

## 📊 Result Highlights

* Classical ML peaks ~83%
* Deep models reach 78–87%
* **GNN + HMM = best performance**
* Sub-millisecond inference for GNN & EEGNet

---

## 📈 Architecture Diagram

* EEG preprocessing → HMM states → Hybrid features → GNN → Classifier

---

## 📝 Conclusion

Jointly modeling **spatial connectivity** (via GNN) and **temporal dynamics** (HMM) provides a strong foundation for robust EEG classification.

---

## 🙏 Acknowledgements

Special thanks to the instructors and TAs of the Computational Neuroscience course for guidance and support.
