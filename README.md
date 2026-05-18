# MICGAN: Mutual Information Compensation GAN

[![Paper](https://img.shields.io/badge/Paper-IEEE%20SPL%202024-blue)](#citation)
[![Code](https://img.shields.io/badge/Code-PyTorch-orange)](#environment)

Official PyTorch implementation of the paper:

**Mutual Information Compensation for High-Fidelity Image Generation With Limited Data**  
Published in **IEEE Signal Processing Letters (SPL), 2024**.

> This repository releases the official code for MICGAN. The code is simple and follows a standard GAN training/inference pipeline, so users can directly check the corresponding Python scripts for running details.

## News

- **2024**: MICGAN was published in **IEEE Signal Processing Letters**, Vol. 31, pp. 2145--2149.
- Code is now publicly released for research use.

## Overview

Limited data availability is a long-standing challenge in high-fidelity image generation. Existing up-sampling based generators may suffer from information loss during progressive resolution recovery, making it difficult to faithfully restore images with consistent resolution and distribution.

MICGAN addresses this problem from an information-theoretic perspective. The key idea is to compensate for the mutual information decay in generator features by introducing **dense frequency skip connections**. These connections enhance the propagation of high-frequency components across generator layers, thereby improving image fidelity under limited-data settings.

The proposed method contains three sub-architectures with different feature fusion strategies:

- **MICGAN-A**
- **MICGAN-C**
- **MICGAN-S**

Extensive experiments on thirteen datasets demonstrate the effectiveness of MICGAN compared with existing data-efficient GAN methods.

## Abstract

Limited data availability poses a perennial challenge in the field of generative image generation. However, current up-sampling methods suffer from inherent deficiencies, resulting in generators' failure to faithfully restore images with identical resolution and distribution. This is primarily evident in the diminishing mutual information as image resolution increases. Considering the above issue, we propose MICGAN, a data-efficient Generative Adversarial Network (GAN) that compensates for mutual information in every layer output feature of the generator through dense frequency skip connections. MICGAN is grounded in information theory, offering a robust theoretical foundation for mitigating mutual information decay. Additionally, we demonstrate that the augmented mutual information primarily stems from increased high-frequency components in images. Furthermore, we introduce three sub-architectures--MICGAN-A, MICGAN-C, and MICGAN-S--each employing distinct feature fusion methods. Extensive experiments across thirteen diverse datasets validate the advancements and effectiveness of MICGAN compared to state-of-the-art methods.

## Method Highlights

MICGAN is designed around the following observations:

- Mutual information tends to decrease as the image resolution increases during generation.
- This information decay harms high-fidelity reconstruction, especially under limited-data training.
- High-frequency components are closely related to the compensated mutual information.
- Dense frequency skip connections can strengthen high-frequency feature propagation.
- Frequency-aware feature fusion improves data-efficient image generation.

## Environment

The code was developed and tested with the following environment:

```bash
python==3.7
pytorch==1.7.1
cudatoolkit==10.2
```

A typical Conda environment can be created by:

```bash
conda create -n micgan python=3.7
conda activate micgan

conda install pytorch==1.7.1 torchvision cudatoolkit=10.2 -c pytorch
```

Other dependencies can be installed according to the actual package requirements of the released code.

## Usage

Please refer to the scripts in this repository for training, testing, and inference.

The code is intentionally kept simple, and the running logic can be directly checked from the corresponding Python files.

## Repository Description

Recommended GitHub repository description:

```text
Official PyTorch implementation of MICGAN: Mutual Information Compensation for High-Fidelity Image Generation With Limited Data, IEEE Signal Processing Letters 2024.
```

Recommended GitHub topics:

```text
micgan
gan
image-generation
limited-data
mutual-information
frequency-domain
pytorch
ieee-signal-processing-letters
fregan
```

These keywords can help users find the repository when searching for the paper title, MICGAN, or limited-data GAN code.

## Acknowledgement

This code is based on and inspired by **FreGAN**:

**FreGAN: Exploiting Frequency Components for Training GANs Under Limited Data**

We sincerely thank the authors of FreGAN for their great work. Their frequency-aware GAN framework provides an important foundation for limited-data image generation and strongly inspired the development of this project.

## Citation

If you find this work useful for your research, please consider citing our paper:

```bibtex
@article{zhai2024mutual,
  title={Mutual information compensation for high-fidelity image generation with limited data},
  author={Zhai, YiKui and Long, ZhiHao and Pan, WenFeng and Chen, CL Philip},
  journal={IEEE Signal Processing Letters},
  volume={31},
  pages={2145--2149},
  year={2024},
  publisher={IEEE}
}
```

Please also consider citing FreGAN:

```bibtex
@article{wang2022fregan,
  title={FreGAN: Exploiting frequency components for training GANs under limited data},
  author={Wang, Zhe and Chi, Ziqiu and Zhang, Yanbing and others},
  journal={Advances in Neural Information Processing Systems},
  volume={35},
  pages={33387--33399},
  year={2022}
}
```

## CITATION.cff

To make the repository easier to cite on GitHub, we recommend adding a `CITATION.cff` file to the root directory of this repository.

A suggested `CITATION.cff` file is:

```yaml
cff-version: 1.2.0
message: "If you use this code, please cite our IEEE Signal Processing Letters paper."
title: "Mutual Information Compensation for High-Fidelity Image Generation With Limited Data"
authors:
  - family-names: "Zhai"
    given-names: "YiKui"
  - family-names: "Long"
    given-names: "ZhiHao"
  - family-names: "Pan"
    given-names: "WenFeng"
  - family-names: "Chen"
    given-names: "C. L. Philip"
date-released: 2024-01-01
url: "https://github.com/yikuizhai/MICGAN"
preferred-citation:
  type: article
  title: "Mutual Information Compensation for High-Fidelity Image Generation With Limited Data"
  authors:
    - family-names: "Zhai"
      given-names: "YiKui"
    - family-names: "Long"
      given-names: "ZhiHao"
    - family-names: "Pan"
      given-names: "WenFeng"
    - family-names: "Chen"
      given-names: "C. L. Philip"
  journal: "IEEE Signal Processing Letters"
  volume: 31
  start: 2145
  end: 2149
  year: 2024
```

The DOI can be added after confirming the official IEEE DOI.

## License

Please refer to the license file in this repository.

The paper is published by IEEE. The use of the manuscript and related materials should follow IEEE copyright policies.

