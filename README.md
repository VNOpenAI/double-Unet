# DoubleU-net implementation
implementation of DoubleU-net for lesion boundary Segmentation ( ISIC 2018-task 1)



data: [ISIC2018_task1 Lesion Boundary Segmentaion ](https://challenge2018.isic-archive.com/)

## preprequisites

Before you continue, ensure you meet the following requirements:

* Install python 3 .
* Install needed librarys in requirements.txt by `!pip install -r requirements.txt` .
* Dowload data ISIC2018_task1 Lesion Boundary Segmentation
* Pre-train model :[link here]() (optional)




## Architecture
DoubleU-net include two sub-network, look alike two U-net concatenated.

Input fed into modified U-net and then generate output1,which have the same size as input image.
The sub-network 2 for fine-grained propose, it was build from scratch, the same ideal with U-net but in the net-work2's decoder, skip_connection from encoder1 was fed into.

at the end the output1 and output2 was conatenated in channel axis. So we can get one of those for prediction.
In origin paper, author show that output1 and output2 have the same result


<img src='image/DoubleU-net_Architecture.png'>

### reference: 
[1] origin paper: [DoubleU-Net: A Deep Convolutional Neural
Network for Medical Image Segmentation](https://arxiv.org/pdf/2006.04868.pdf)

[2] ASPP block :[DeepLab: Semantic Image Segmentation with
Deep Convolutional Nets, Atrous Convolution,
and Fully Connected CRFs](https://arxiv.org/pdf/1606.00915v2.pdf)

[3] [Repository 2020-CBMS-DoubleU-Net](https://github.com/DebeshJha/2020-CBMS-DoubleU-Net)

[4] data: [ISIC2018_task1 Lesion Boundary Segmentaion ](https://challenge2018.isic-archive.com/)