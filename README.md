## Spatial Feedback Learning to Improve Semantic Segmentation in Hot Weather
High-temperature weather conditions induce geometrical distortions in images which can adversely affect the performance of a computer vision model performing downstream tasks such as semantic segmentation. The performance of such models has been shown to improve by adding a restoration network before a semantic segmentation network. The restoration network removes the geometrical distortions from the images and shows improved segmentation results. However, this approach suffers from a major architectural drawback that is the restoration network does not learn directly from the errors of the segmentation network. In other words, the restoration network is not task aware. In this work, we propose a semantic feedback learning approach, which improves the task of semantic segmentation giving a feedback response into the restoration network. This response works as an attend and fix mechanism by focusing on those areas of an image where restoration needs improvement. Also, we proposed loss functions: Iterative Focal Loss (iFL) and Class-Balanced Iterative Focal Loss (CB-iFL), which are specifically designed to improve the performance of the feedback network. These losses focus more on those samples that are continuously miss-classified over successive iterations. Our approach gives a gain of 17.41 mIoU over the standard segmentation model, including the additional gain of 1.9 mIoU with CB-iFL on the Cityscapes dataset.
## Requirements
* PyTorch (version = 0.3.0)
* Python (version = 2.7)
* Jupyter Notebook
* numpy
* tqdm
* torchvision ==0.2.0
## Code Structure and Summary

```  
| 
└───train
│   └───dataset.py         -- Dataloader script for Cityscapes
│   └───erfnet.py          -- Network structure for ErfNet
│   └───erfnet_imagenet.py -- Learning the initial weights for ErfNet
│   └───fill_weights.py    -- Class weights and ErfNet Network weights
│   └───iFL.py             -- Iterative focal loss for the feedback framework.
│   └───Interp.py          -- Layer that warps the input image to get final restored image.
│   └───iouEval.py         -- Evaluation of the model
│   └───main.py            -- Main driver programme
│   └───run_pretrained.py  -- Script to run the pre-trained models that outputs mIoU and segmentation results.
│   └───transform.py       -- Transform the segmentation output in original cityscapes color.
│   └───unet_model.py      -- Modified unet module that takes the feedback 
│   └───utils.py           -- Tranformation input and saving checkpoints
└───val
│   └───gt
│   └───images
└───train_crops       # created by script
│   └───gt
│   └───images
└───val_crops         # created by script
│   └───gt
│   └───images
```
## Dataset Generation
## Training
## Pretrained Models
## Results

![Drag Racing](result.png)


### Contact
shyam.nandan@research.iiit.ac.in 
