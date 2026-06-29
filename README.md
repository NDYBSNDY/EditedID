# EditedID 

Official implementation of:

**Optimizing ID Consistency in Multimodal Large Models:  Facial Restoration via Alignment, Entanglement, and Disentanglement**

---

## 🔥 News
- [2026/06] The code has been released.
- [2026/02] Paper accepted to ICLR :)
- Code release is in progress.

---

## 📌 Overview

We propose a unified framework for optimizing identity consistency in multimodal large models through:

- Alignment
- Entanglement
- Disentanglement

This repository will provide inference and training code for facial restoration and ID-preserving generation.

---

## 🛠️ Setup

This code was tested with Python 3.8, Pytorch 1.11 using pre-trained models through huggingface / diffusers. Specifically, we implemented our method over Latent Diffusion and Stable Diffusion. Additional required packages are listed in the requirements file. The code was tested on a Tesla NVIDIA RTX 4090 24GB.

---

## 📄 Quickstart

Create & Activate Conda Environment:

```bibtex
conda create -n EditedID python=3.8 -y
conda activate EditedID
```
Install compatible PyTorch packages:

```bibtex
pip install torch==2.1.0 torchvision==0.16.0 torchaudio==2.1.0 --index-url https://download.pytorch.org/whl/cu121
```
Reactivate Environment (if needed):

```bibtex
conda deactivate
conda activate EditedID  # Re-activate to apply changes
```


## ⚠️ Hyperparameter Description

- INIT_NUM: Initial mixing weight value controlling latent space trajectory Alignment in the alignment module. Higher values accelerate alignment updates but increase feature loss risk. Values in range yield smoother alignment trajectories, preserving input features from different sources and preventing cross-source feature contamination (enhancing Disentanglement).0-0.1

- FINA_STEP: Number of steps to forcibly align latent spaces from different sources. Use smaller values when total diffusion steps are limited to avoid over-alignment.

- TOTAL_STEPS_DPM: Start/end steps for DPM-Solver++ invocation (symmetric in inversion/reconstruction trajectories). 

- OVERLAP_WEIGHT: Fusion weights for overlapping regions (where a + b = 1). Scenario-dependent recommendations:(a,b)


---

## 📄 Citation

If you find this work useful, please cite:

```bibtex
@inproceedings{xxx2026id,
  title={Optimizing ID Consistency in Multimodal Large Models: Facial Restoration via Alignment, Entanglement, and Disentanglement},
  author={Yuran Dong, Hang Dai∗, Mang Ye∗},
  booktitle={ICLR},
  year={2026}
}
```

## 🙏 Acknowledgements

This project is inspired by and builds upon prior works, especially:

- **Null-text Inversion**  
- **Prompt-to-Prompt**

We sincerely thank the authors for making their ideas and code publicly available.

---

## 📬 Contact

**Email:** 1278536892@qq.com
