# MCDUT
# Multi-cropping Contrastive Learning and Domain Consistency for Unsupervised Image-to-Image Translation
 
>Recently, unsupervised image-to-image translation methods based on contrastive learning have achieved state-of-the-art results in many tasks. However, in the previous works, the negatives are sampled from the input image itself, which inspires us to design a data augmentation method to improve the quality of the selected negatives. Moreover, the previous methods only preserve the content consistency via patch-wise contrastive learning in the embedding space, which ignores the domain consistency between the generated images and the real images of the target domain. In this paper, we propose a novel unsupervised image-to-image translation framework based on multi-cropping contrastive learning and domain consistency, called MCDUT. Specifically, we obtain the multi-cropping views via the center-cropping and the random-cropping with the aim of further generating the high-quality negative examples. To constrain the embeddings in the deep feature space, we formulate a new domain consistency loss, which encourages the generated images to be close to the real images in the embedding space of the same domain. Furthermore, we present a dual coordinate attention network by embedding positional information into the channel, which called DCA. We employ the DCA network in the design of generator, which makes the generator capture the horizontal and vertical global information of dependency. In many image-to-image translation tasks, our method achieves state-of-the-art results, and the advantages of our method have been proven through extensive comparison experiments and ablation research. 




</p>

## Getting Started
##### Please note that for the sake of convenient uploading, this repository only provides the core code. For the specific code framework, please refer to our proposed SN-DCR, the code of which is located at [SN-DCR](https://github.com/zhihefang/SN-DCR/tree/main/SN-DCR-main). 
### Prerequisites
- Ubuntu 16.04
- NVIDIA GPU + CUDA CuDNN
- Python 3
Please use `pip install -r requirements.txt` to install the dependencies.

## Pretrained Models
We provide  pretrained models for three datasets.
   
| Model | Orange2apple | Horse2zebra | Cat2Dog |

| MCDUT | [Orange2apple](https://pan.baidu.com/s/1BKCJeE5We6knnjJlNnLsUQ) | [Horse2zebra](https://pan.baidu.com/s/13wRzb1xs2BbjGSVTCGeb9g) | [Cat2Dog](https://pan.baidu.com/s/1I2lt-4ZwSbXv_xidseF_0A)

提取码:az14

## Training
- Download `horse2zebra` dataset :
```
bash ./datasets/download_sndcr_dataset.sh horse2zebra
```
- Train the  model:
```
python train.py \
--dataroot=datasets/horse2zebra \
--name=horse2zebra_mcdut \
```
- You can use visdom to view the training loss:
Run `python -m visdom.server` and click the URL http://localhost:8097.

## Inference
- Test the global model:
```
python test.py \
--dataroot=datasets/horse2zebra \
--name=horse2zebra_mcdut \
```
