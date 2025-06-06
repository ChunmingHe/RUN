<p align=center><img src="logo.png" width="200px"> <a href='https://arxiv.org/pdf/2501.18783'><img src='https://img.shields.io/badge/ICML-2025-red'></a> </p>

**RUN: Reversible Unfolding Network for Concealed Object Segmentation, ICML 2025** 

<br> [Chunming He](https://chunminghe.github.io/), [Rihan Zhang](https://scholar.google.com/citations?user=y1hdXhcAAAAJ&hl=en), [Fengyang Xiao](https://scholar.google.com/citations?user=NqdaqA8AAAAJ&hl=en), [Chengyu Fang](https://cnyvfang.github.io/), [Longxiang Tang](https://scholar.google.com/citations?user=3oMQsq8AAAAJ&hl=en), [Yulun Zhang](https://yulunzhang.com), [Linghe Kong](https://www.cs.sjtu.edu.cn/~linghe.kong/), [Deng-Ping Fan](https://dengpingfan.github.io/), [Kai Li](https://kailigo.github.io/), and [Sina Farsiu](https://people.duke.edu/~sf59/) <be>

[[Paper](https://arxiv.org/abs/2501.18783)] [[Models & Results](https://drive.google.com/drive/folders/1rA8RfYDmEkUESsRAEgVVqCj5ImkRNTsE?usp=sharing)]

>**Abstract:** Existing concealed object segmentation (COS) methods frequently utilize reversible strategies to address uncertain regions. However, these approaches are typically restricted to the mask domain, leaving the potential of the RGB domain underexplored. To address this, we propose the Reversible Unfolding Network (RUN), which applies reversible strategies across both mask and RGB domains through a theoretically grounded framework, enabling accurate segmentation. RUN first formulates a novel COS model by incorporating an extra residual sparsity constraint to minimize segmentation uncertainties. The iterative optimization steps of the proposed model are then unfolded into a multistage network, with each step corresponding to a stage. Each stage of RUN consists of two reversible modules: the Segmentation-Oriented Foreground Separation (SOFS) module and the Reconstruction-Oriented Background Extraction (ROBE) module. SOFS applies the reversible strategy at the mask level and introduces Reversible State Space to capture non-local information. ROBE extends this to the RGB domain, employing a reconstruction network to address conflicting foreground and background regions identified as distortion-prone areas, which arise from their separate estimation by independent modules. As the stages progress, RUN gradually facilitates reversible modeling of foreground and background in both the mask and RGB domains, directing the network's attention to uncertain regions and mitigating false-positive and false-negative results. Extensive experiments demonstrate the superior performance of RUN and highlight the potential of unfolding-based frameworks for COS and other high-level vision tasks.   

![](featured.png)




## 🔥 News

- **2025-06-03:** We release the pretrained models and the results.
- **2025-03-10:** We release the code.
- **2025-02-10:** We release this repository and the preprint of the full paper.



## 🔗 Contents

- [x] Usage
- [x] Results
- [x] Citation
- [x] Acknowledgements

## ⚙️ Usage



### 1. Prerequisites

> Note that RUN is only tested on Ubuntu OS with the following environments.

- Creating a virtual environment in terminal: `conda create -n RUN python=3.8`.
- Installing necessary packages: `conda env create -f environment.yml`

### 2. Downloading Training and Testing Datasets

- Download the [training set](https://anu365-my.sharepoint.com/:u:/g/personal/u7248002_anu_edu_au/EQ75AD2A5ClIgqNv6yvstSwBQ1jJNC6DNbk8HISuxPV9QA?e=UhHKSD) (COD10K-train) used for training 
- Download the [testing sets](https://anu365-my.sharepoint.com/:u:/g/personal/u7248002_anu_edu_au/EVI0Bjs7k_VIvz4HmSVV9egBo48vjwX7pvx7deXBtooBYg?e=FjGqZZ) (COD10K-test + CAMO-test + CHAMELEON + NC4K ) used for testing
- Refer to the [COS repository](https://github.com/ChunmingHe/awesome-concealed-object-segmentation) for more datasets.

### 3. Training Configuration

- The pretrained model is stored in [Google Drive](https://drive.google.com/file/d/1OmE2vEegPPTB1JZpj2SPA6BQnXqiuD1U/view?usp=share_link). After downloading, please change the file path in the corresponding code.
```bash
python Train.py  --epoch YOUR_EPOCH  --lr YOUR_LEARNING_RATE  --batchsize YOUR_BATCH_SIZE  --trainsize YOUR_TRAINING_SIZE  --train_root YOUR_TRAININGSETPATH  --val_root  YOUR_VALIDATIONSETPATH  --save_path YOUR_CHECKPOINTPATH
```

### 4. Testing Configuration

Our well-trained model is stored in [Google Drive](https://drive.google.com/drive/folders/1rA8RfYDmEkUESsRAEgVVqCj5ImkRNTsE?usp=sharing). After downloading, please change the file path in the corresponding code.
```bash
python Test.py  --testsize YOUR_IMAGESIZE  --pth_path YOUR_CHECKPOINTPATH  --test_dataset_path  YOUR_TESTINGSETPATH
```

### 5. Evaluation

- Matlab code: One-key evaluation is written in [MATLAB code](https://github.com/DengPingFan/CODToolbox), please follow the instructions in `main.m` and just run it to generate the evaluation results.

### 6. Results download

The prediction results of our RUN are stored on [Google Drive](https://drive.google.com/file/d/1OmE2vEegPPTB1JZpj2SPA6BQnXqiuD1U/view?usp=share_link). Please check.


## 🔍 Results

We achieved state-of-the-art performance on *camouflaged object detection*, *polyp image segmentation*, *medical tubular object segmentation*, and *transparent object detection*. More results can be found in the paper.

<details>
<summary>Quantitative Comparison (click to expand)</summary>

- Results in Table 1 of the main paper
  <p align="center">
  <img width="900" src="fig/fig1.png">
	</p>
  </details>

<details>
<summary>Visual Comparison (click to expand)</summary>

- Results in Figure 4 of the main paper
  <p align="center">
  <img width="900" src="fig/fig2.png">
	</p>
  </details>



## Related Works
[Strategic Preys Make Acute Predators: Enhancing Camouflaged Object Detectors by Generating Camouflaged Objects](https://github.com/ChunmingHe/Camouflageator), ICLR 2024.

[Weakly-Supervised Concealed Object Segmentation with SAM-based Pseudo Labeling and Multi-scale Feature Grouping](https://github.com/ChunmingHe/WS-SAM), NeurIPS 2023.

[Camouflaged object detection with feature decomposition and edge reconstruction](https://github.com/ChunmingHe/FEDER), CVPR 2023.

[Concealed Object Detection](https://github.com/GewelsJI/SINet-V2), TPAMI 2022.

You can see more related papers in [awesome-COS](https://github.com/ChunmingHe/awesome-concealed-object-segmentation).



## 📎 Citation

If you find the code helpful in your research or work, please cite the following paper(s).

```
@article{he2025run,
  title={RUN: Reversible Unfolding Network for Concealed Object Segmentation},
  author={He, Chunming and Zhang, Rihan and Xiao, Fengyang and Fang, Chenyu and Tang, Longxiang and Zhang, Yulun and Kong, Linghe and Fan, Deng-Ping and Li, Kai and Farsiu, Sina},
  journal={ICML},
  year={2025}
}
```

## Concat
If you have any questions, please feel free to contact me via email at chunminghe19990224@gmail.com or chunming.he@duke.edu.

## Acknowledgement
The code is built on [FEDER](https://github.com/ChunmingHe/FEDER) and [SINet V2](https://github.com/GewelsJI/SINet-V2). Please also follow the corresponding licenses. Thanks for the awesome work.

