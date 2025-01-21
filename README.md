# Mixture of Features on Lexicon3D

This was a modification atop the work done for Lexicon3D.

![image](https://github.com/user-attachments/assets/98f89ad1-5d8a-499e-afbb-2420c1b61ab4)

The paper for the work done is: [MoF-Paper.pdf](https://github.com/Exorust/MoF-Lexicon3D/blob/main/Chandrahas_Tejaswini_final_paper.pdf)


## Environment Setup

Please install the required packages and dependencies according to the `requirements.txt` file. 

In addition, 
- in order to use the LSeg model, please follow [this repo](https://github.com/pengsongyou/lseg_feature_extraction) to install the necessary dependencies.
- in order to use the Swin3D model, please follow [this repo](https://github.com/microsoft/Swin3D) and [this repo](https://github.com/Yukichiii/Swin3D_Task) to install the necessary dependencies.

Finally, please download the ScanNet dataset from the official website and follow the instructions [here](https://github.com/pengsongyou/openscene/blob/main/scripts/preprocess) to preprocess the ScanNet dataset and get RGB video frames and point clouds for each scannet scene.

## Feature Extraction

To extract features from the foundation models, please run the corresponding scripts in the `lexicon3d` folder. For example, to extract features from the LSeg model, please run the following command:

```bash
python fusion_scannet_clip.py  --data_dir dataset/ScanNet/openscene/  --output_dir  dataset/lexicon3d/clip/ --split train --prefix clip
```

This script will extract features from the LSeg model for the ScanNet dataset. The extracted features will be saved in the `output_dir` folder, containing the feature embeddings, points, and voxel grids.

## Acknowledgements
This repo is built based on the fantastic work [OpenScene](https://github.com/pengsongyou/openscene). We also thank the authors of [P3DA](https://github.com/mbanani/probe3d) and the authors of all relevant visual foundation models for their great work and open-sourcing their codebase. 
