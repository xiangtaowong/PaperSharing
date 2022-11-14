# Efficient Self-supervised Vision Pretraining with Local Masked Reconstruction


## Questions:
1. global masked reconstruction and operate on a large number of image patches.
<!-- 1. The global masked reconstruction mechanism in current generative self-supervised methods like MAE and BEiT is computationally demanding. -->
2. The benefits of attending to far-away patches in reconstruction
remain unclear.

## Innovations:
1. We propose local masked reconstruction (LoMaR), performing masked reconstruction within a small window of 7×7 patches on a simple Transformer encoder.
   1. They find it more computation-efficient on pretraining high-resolution images.
   2. It motivates us to limit the range of attention used in the reconstruction.

## Ｓignificances:
1. Improve the trade-off between efficiency and accuracy compared to global masked reconstruction over the entire image.


## Methods:
1. Different from MAE:
   1. Sample a region with k×k patches to perform masked reconstruction instead of from the full number of patches.
      1. we find that it is sufficient to recover the missing information with only some local visual clues.
   2. We replace the heavy-weight decoder in MAE with a lightweight MLP head. We feed all image patches directly into the encoder, including masked and visible patches.
      1. Experiments show that these architectural changes bring more performance gain to the local masked reconstruction in small windows.



## Code:
[Code](https://github.com/junchen14/LoMaR)


## Mine Thoughts:
1. How to choose suitable patch location? 