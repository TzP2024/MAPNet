# Efficient RGB-D Co-Salient Object Detection via Modality-Aware Prompting
RGB-D co-salient object detection (RGB-D Co-SOD) is aiming at identifying and detecting salient objects in a set of correlated images and depth maps. The majority of existing RGB-D Co-SOD approaches comprehensively fine-tune the dual-stream encoder–decoder framework and fuse the RGB and depth features through a complex feature-fusion strategy that is expensive to train owing to the large number of parameters that are updated during the feature extraction and fusion processes. Therefore, this study proposes a simple and effective modality-aware prompting network (MAPNet) for efficient RGB-D Co-SOD training. MAPNet trains an RGB-D Co-SOD through two approaches, namely modal fusion and consensus feature extraction, using a multimodal prompt generator (MPG) and consensus feature extraction module (CFEM), respectively. Specifically, the MPG module guides the depth features in the fine-tuned backbone network from the RGB features obtained in the frozen backbone network for fusion in hyperbolic spaces to generate multilevel modal cues that are subsequently injected into the fine-tuned backbone network for efficient modal fusion. CFEM uses RGB features to generate an image salient prior, combines the salient prior with the highest level of fusion features to obtain the central point, and uses the salient features closer to the central point as the consensus features of the image group. In addition, contrast loss is introduced to separate the synergistic salient features from the non-synergistic salient features to obtain pure co-salient features. The trained MAPNet obtained state-of-the-art performance on three baseline datasets (RGBD CoSal1k, RGBD CoSal150, and RGBD CoSeg183).

# Framework Overview
![image](https://github.com/TzP2024/MAPNet/blob/main/images/MAPNet.jpg)
Fig. 1 Overview structure of the proposal MAPNet. The MPG fuses RGB features with depth features to generate complementary multimodal feature cues, which are subsequently injected into the fine-tuning network to guide multimodal feature fusion. CFEM uses the a priori image information and fused features to obtain consensus features for the image group. Finally, the consensus and fusion features are sequentially fed into the decoder to generate co-feature object predictions.

# Requirements
Python 3.7+, Pytorch 1.5.0+, Cuda 10.2+, TensorboardX 2.1, opencv-python If anything goes wrong with the environment, please check requirements.txt for details.
# Results
Comparison with the previous state-of-the-art methods with different training sets:
![image](https://github.com/TzP2024/MAPNet/blob/main/images/table.png)

![image](https://github.com/TzP2024/MAPNet/blob/main/images/compri.png)


# Dataset
Download the RGBD Co-SOD dataset from [Baidu](https://pan.baidu.com/s/1HOVfAk65FHoJn-ftTHozfA?pwd=61wt) pwd:61wt

# Saliency Maps
Download the teacher model MAPNet saliency maps from [Baidu](https://pan.baidu.com/s/1nGj_VUFhVkNsTjR6cyF2Bw?pwd=cek9) pwd:cek9 
