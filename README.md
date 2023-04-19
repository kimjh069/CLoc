# CLoc: Confident Initial Estimation of Long-Term Visual Localization Using a Few Sequential Images in Large-Scale Spaces

<img src=figures/NEB1_model.png width="300" height="150"><img src=figures/NEB2_model.png width="300" height="150"><img src=figures/SFB_model.png width="300" height="150">




This repository provides datasets for visual localization, as published in the IEEE Sensors Journal. The datasets, created for indoor visual localization with sequential images, address two major challenges: "long-term" and "large-scale". We hope our datasets can aid the development of visual localization algorithms.

You can download our datasets [here](https://drive.google.com/drive/folders/12e2J_Eg7lICdEyDwDxKJHEDBoy5ytwAS?usp=sharing).

## Introduction

The lack of publicly available datasets for sequential visual localization in large-scale indoor spaces has been a significant obstacle for advancing the field. This repository aims to provide datasets that contribute to the progress of sequential visual localization research. Our datasets encompass three indoor spaces within university buildings. For more details, please refer to our paper, [CLoc](https://ieeexplore.ieee.org/abstract/document/10068431).

## Dataset Description

There are 3 datasets labeled as "NEB1", "NEB2", and "SFB", respectively. Each dataset has two folders: "Database" and "Query". The structure of our datasets is as follows:

### Database folder

- `images`: The database images.
- `features`: We use NetVLAD for global descriptors and SuperPoint for local features, which are saved in `global-feats-netvlad.h5` and `feats-superpoint-n4096-r1024.h5`, respectively.
- `sfm_model`: COLMAP-based database model. You might want to check [HLoc](https://github.com/cvg/Hierarchical-Localization) and [COLMAP](https://github.com/colmap/colmap) to understand how to use the COLMAP-based database model for visual localization.

### Query folder

- `intrinsic`: The intrinsic camera parameters of the camera that captured the query images.
- `query_sequences`: The sequential query images are split into folders containing no more than 50 images each.
- `ground_truth`: The 6-DoF ground truth poses for images in each query sequence are saved in query_images_gt.pickle files. Each ground truth pose of a query image is saved as 'query_path': [position(x, y, z), quaternion(w, x, y, z)] in the file. The position(x, y, z) represents the translation vector (in meters) from the world coordinate system to the camera coordinate system, and quaternion(w, x, y, z) denotes the orientation of the camera with respect to the world coordinate system as a unit quaternion.

## Sample Result Videos
The sample result videos of our algorithm, CLoc, can be found in the `videos' folder. These videos showcase a comparison between CLoc and a one-shot visual localization (OVL) method by rendering colored point clouds onto the image plane using the estimated poses.

The videos display, from left to right, the OVL result, the query frame, and the CLoc result. To provide clearer visualization, the video playback is slowed down to 0.2 times the frame rate of the original video captured by a smartphone camera.

## BibTex Citation
If you use any of the above data for your research, or use any of the results in our paper, please consider citing [CLoc](https://ieeexplore.ieee.org/abstract/document/10068431).

```
@article{kim2023cloc,
  author={Kim, Joohyung and Hyeon, Janghun and Choi, Hyunga and Jang, Bumchul and Jeong, Bokyeon and Doh, Nakju},
  journal={IEEE Sensors Journal},
  title={CLoc: Confident Initial Estimation of Long-Term Visual Localization Using a Few Sequential Images in Large-Scale Spaces},
  year={2023},
  volume={23},
  number={8},
  pages={8613-8629},
  doi={10.1109/JSEN.2023.3253872}}
}
```
