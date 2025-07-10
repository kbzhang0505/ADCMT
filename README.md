# ADCMT: An Augmentation-Free Dynamic Contrastive Multi-Task Transformer for UGC-VQA

**Paper**: [ADCMT: An Augmentation-Free Dynamic Contrastive Multi-Task Transformer for UGC-VQA](https://ieeexplore.ieee.org/document/11006507)

**Authors**: Hui Li, Kaibing Zhang, Jie Li, Xinbo Gao, Guang Shi 

**Published in**: IEEE Transactions on Broadcasting, 2025  

---

## I. Introduction

This repository provides the official implementation and reproduction instructions for our IEEE TBC 2025 paper:  
**ADCMT: An Augmentation-Free Dynamic Contrastive Multi-Task Transformer for UGC-VQA**.  
ADCMT tackles the complex multi-source distortions in user-generated videos without relying on artificial data augmentation, by leveraging a novel multi-task transformer and a dynamic supervised contrastive learning strategy.

![Overall model architecture of ADCMT.](ims/overview.jpg)

---

## II.  Quick Start

1. Clone the repository

   ```bash
   git clone https://github.com/kbzhang0505/ADCMT.git
   cd ADCMT
   ```

2. Prepare Datasets

   This project supports mainstream UGC-VQA datasets, including KoNViD-1k, CVD2014, LIVE-Qualcomm, LIVE-VQC, YouTube-UGC, and LSVQ-Subset. **Please extract frame-level video features offline in advance, and organize dataset splits and management according to the meta files provided under the `data/` directory.** The file structure of this project is organized as follows:

   ```bash
   ADCMT/
   ├── data/                  # Dataset meta files and splits
   ├── models/                # Model implementations
   ├── modules/               # Method modules
   ├── tools/                 # Utility functions
   ├── main_ADCMT.py          # Main training entry
   ├── sample_LSVQ.py         # LSVQ subset sampling script
   ├── shell_ADCMT.py         # Batch experiment shell script
   ├── V_feat_Dataset.py      # PyTorch Dataset class definition
   ├── README.md              # Project documentation
   ```
   
3. Feature Extraction

   It is recommended to use the same ResNet50 model as in the paper for frame-level feature extraction. Please refer to the script `tools/CNN_feature_generator.py`.

All contrastive experiments are performed on Intel Xeon Silver 4210R CPU and Nvidia RTX3090 GPU.

Noting that the results may be still not the same among different implement devices. See [randomness@Pytorch Docs](https://pytorch.org/docs/stable/notes/randomness.html).

---

## III. Citation

If you find this work or code useful in your research, please consider citing our paper:

```bibtex
@ARTICLE{11006507,
  author={Li, Hui and Zhang, Kaibing and Li, Jie and Gao, Xinbo and Shi, Guang},
  journal={IEEE Transactions on Broadcasting}, 
  title={ADCMT: An Augmentation-Free Dynamic Contrastive Multi-Task Transformer for UGC-VQA}, 
  year={2025},
  volume={},
  number={},
  pages={1-16},
  keywords={Augmentation-free;multi-task transformer;supervised contrastive learning;user generated content;video quality assessment},
  doi={10.1109/TBC.2025.3565888}}
```

