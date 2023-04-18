# G2S

This is a reference implementation for using G2S loss described in the [ICRA 2021 paper](https://ieeexplore.ieee.org/document/9561441)

> **Multimodal Scale Consistency and Awareness for Monocular Self-Supervised Depth Estimation**
>
>  by [Hemang Chawla](https://scholar.google.com/citations?user=_58RpMgAAAAJ&hl=en&oi=ao), [Arnav Varma](https://scholar.google.com/citations?user=3QSih2AAAAAJ&hl=en&oi=ao), [Elahe Arani](https://www.linkedin.com/in/elahe-arani-630870b2/) and [Bahram Zonooz](https://scholar.google.com/citations?hl=en&user=FZmIlY8AAAAJ).

in the Monodepth2 repository for KITTI Eigen Zhou split. The corresponding checkpoint can be found [here](https://drive.google.com/drive/folders/1_BbMw83cBiIjsxRb1BI66aNMeo1fySoy?usp=sharing).

The official code is available [here](https://github.com/NeurAI-Lab/G2S).

This code is for non-commercial use following the original license from Monodepth2; please see the [license file](LICENSE) for terms.

If you find our work useful in your research please consider citing our paper:

```
@inproceedings{chawla2021multimodal,
  title={Multimodal scale consistency and awareness for monocular self-supervised depth estimation},
  author={Chawla, Hemang and Varma, Arnav and Arani, Elahe and Zonooz, Bahram},
  booktitle={2021 IEEE International Conference on Robotics and Automation (ICRA)},
  pages={5140--5146},
  year={2021},
  organization={IEEE}
}
```


## ⏳ Training


**Monocular training:**
```shell
python train.py --model_name g2s --data_path /path/to/KITTI/raw_data/sync --log_dir /path/to/log/dir/ --g2s --png (if images are in png)
```

**Ground truth generation (Needs to be run once before first evaluation):**
```shell
python export_gt_depth.py --data_path /path/to/KITTI/raw_data/sync --split eigen
```

**Monocular evaluation:**
```shell
python train.py evaluate_depth.py --eval_mono --data_path /path/to/KITTI/raw_data/sync --eval_split eigen --load_weights_folder /path/to/ckpt/folder --png (if images are in png)
```

## 👩‍⚖️ License
Please see the [license file](LICENSE) for terms.
