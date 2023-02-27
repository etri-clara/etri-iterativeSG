##### ETIR-Iterative SG Model
## Proposed Iterative Scene Graph Generation Model Architecture
![plot](./intro_img.jpg)
###### *Black(line: ResNet), Red(line: Encoder)
###### *Black(bold line: VoVNet), Red(bold line: Centneramsk), Blue(bold line: Our proposed methodology)

---

## Performance Evaluation
###### B.P.:	Backbone Parameter / T.P.:	Total Parameter
|Ref.|Backbone|Detector|B.P.|T.P.|GPU|EA|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|A|ResNet-101|DETR|44.5 M|93.3 M|A100|4|
|B|VoVNet_v2_39_FPN|DETR|52.6 M|79.1 M|A100|4|
|C|VoVNet_v2_57_FPN|DETR|68.9 M|95.4 M|A100|4|
|D|VoVNet_v2_99_FPN|DETR|96.9 M|123.4 M|A100|4|
|E|VoVNet_v2_39_FPN|Centermask|52.6 M|103.2 M|A100|4|
|F|VoVNet_v2_57_FPN|Centermask|68.9 M|119.4 M|A100|4|
|G|VoVNet_v2_99_FPN|Centermask|96.9 M|147.5 M|A100|4|

###### Epoch: 250,000 / α, β: 0.07, 0.75 / I.T.: Inference Time  
|Model|R@20/50/100|ng-R@20/50/100|zR@20/50/100|mR@20/50/100|I.T (sec)|
|:---:|:---:|:---:|:---:|:---:|:---:|
|[1]|21.79/27.12/29.72|22.72/30.52/35.47|1.34/2.74/3.84|11.15/15.61/17.70|-|
|A|19.39/23.72/26.08|19.77/26.41/30.69|0.74/2.98/3.42|10.54/12.92/14.43|0.100324|
|B|11.07/13.88/15.33|11.40/15.52/18.27|0.45/1.34/1.34|6.49/8.15/10.19|0.110973|
|C|11.01/14.01/15.57|11.34/15.56/18.58|0.89/1.34/1.34|6.04/8.81/9.99|0.112564|
|D|10.50/13.30/14.85|10.71/14.71/17.59|0.45/0.89/1.34|5.90/7.66/8.77|0.938817|
|E|-|-|-|-|-|-|
|F|**24.98/27.98/29.49**|**27.06/33.32/37.54**|**3.35/4.91/6.70**|**10.99/13.08/14.38**|**0.124565**|
|G|-|-|-|-|-|

|Model|AP|AP50|AP75|APs|APm|API|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|A|13.4691|24.9608|12.3987|3.6703|7.9725|18.334|
|B|7.1613|14.757|5.9463|0.6114|2.3128|10.6247|
|C|7.4402|15.4658|6.2069|0.5512|2.4282|10.9120|
|D|6.9651|14.2869|5.9436|0.4463|2.4215|10.1461|
|E|-|-|-|-|-|-|
|F|**24.2753**|**34.8707**|**25.5894**|**8.6716**|**14.2439**|**32.3165**|
|G|-|-|-|-|-|-|

|Model|SGMeanRecall@20|SGMeanRecall@50|SGMeanRecall@100|
|:---:|:---:|:---:|:---:|
|A|0.1054|0.1292|0.1443|
|B|0.0649|0.0815|0.1019|
|C|0.0604|0.0881|0.0999|
|D|0.0590|0.0766|0.0877|
|E|-|-|-|
|F|**0.1099**|**0.1308**|**0.1438**|
|G|-|-|-|

###### Epoch: 100,000 / α, β: 0.07, 0.75 / I.T.: Inference Time  
|Model|R@20/50/100|ng-R@20/50/100|zR@20/50/100|mR@20/50/100|I.T (sec)|
|:---:|:---:|:---:|:---:|:---:|:---:|
|A|-|-|-|-|-|
|B|-|-|-|-|-|
|C|6.40/8.18/9.46|6.67/9.27/11.07|0.00/0.045/0.089|3.34/4.25/6.25|0.117365
|D|5.61/7.38/8.53|5.53/7.91/10.00|0.00/0.045/0.089|2.97/3.65/4.27|0.116621
|E|18.35/20.85/22.11|19.43/23.92/27.05|0.89/2.90/3.35|7.56/9.84/10.44|0.119549
|F|16.91/19.09/20.14|18.07/22.54/25.60|0.45/2.23/2.46|7.27/8.54/9.02|0.124869
|G|11.24/12.88/13.78|11.88/15.00/16.98|0.22/0.67/0.156|4.10/4.96/5.56|0.152235

|Model|AP|AP50|AP75|APs|APm|API|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|A|-|-|-|-|-|-|
|B|-|-|-|-|-|-|
|C|4.6338|10.0964|3.8084|0.1029|0.9584|6.6563|
|D|3.8670|8.4700|3.1530|0.2860|0.7840|5.4020|
|E|13.4100|23.6500|12.7300|2.8400|4.9200|19.5900|
|F|12.9729|23.2963|12.0455|2.5266|4.7236|18.9786|
|G|7.2027|12.5070|6.7806|1.1368|2.4701|10.2745|

|Model|SGMeanRecall@20|SGMeanRecall@50|SGMeanRecall@100|
|:---:|:---:|:---:|:---:|
|A|-|-|-|
|B|-|-|-|
|C|0.0334|0.0425|0.0625|
|D|0.0297|0.0365|0.0427|
|E|0.0756|0.0984|0.1044|
|F|0.0727|0.0854|0.0902|
|G|0.0410|0.0496|0.0556|

---

## Evaluation Demonstration
![plot](./evaluation_demo_img.jpg)

---

## Requirements
The following packages are needed to run the code.
```python
python==3.8.5 / PyTorch==1.8.2

[Requirements]
$ conda create --name iterative_sg python==3.8.5
$ conda activate iterative_sg
$ pip3 install torch==1.8.2 torchvision==0.9.2 torchaudio==0.8.2 --extra-index-url https://download.pytorch.org/whl/lts/1.8/cu111
$ pip install h5py imantics easydict scikit-learn scipy pandas
$ pip3 install opencv-python==4.5.5.64

[detectron2==0.6 installation]
$ python -m pip install 'git+https://github.com/facebookresearch/detectron2.git'
```

---

## Dataset
We use the Visual Genome filtered data widely used in the Scene Graph community. 
Please see the public repository of the paper  [Unbiased Scene Graph Generation repository](https://github.com/KaihuaTang/Scene-Graph-Benchmark.pytorch/blob/master/DATASET.md) on instructions to download this dataset. After downloading the dataset you should have the following 4 files: 
- `VG_100K `directory containing all the images
- `VG-SGG-with-attri.h5` 
- `VG-SGG-dicts-with-attri.json` (Can be found in the same repository [here](https://github.com/KaihuaTang/Scene-Graph-Benchmark.pytorch/tree/master/datasets/vg))
- `image_data.json` (Can be found in the same repository [here](https://github.com/KaihuaTang/Scene-Graph-Benchmark.pytorch/tree/master/datasets/vg))

---

## Train Iterative Model
To enable faster model convergence, we pre-train DETR on Visual Genome. We replicate the DETR decoder weights three times, and initialize our models three decoders with it. For convenience, the pretrained weights (with the decoder replication) are made available [here](https://drive.google.com/drive/folders/1CdcYdcYEvkZHz-I1IFF8sBxVMWSyWIkh?usp=share_link). To use these weights during training, simply use the `MODEL.WEIGHTS <Path to downloaded checkpoint>` flag in the training command.

Our proposed iterative model can be trained using the following command:
```python
python train_iterative_model.py --resume --num-gpus <NUM_GPUS> --config-file configs/iterative_model.yaml OUTPUT_DIR <PATH TO CHECKPOINT DIR> DATASETS.VISUAL_GENOME.IMAGES <PATH TO VG_100K IMAGES> DATASETS.VISUAL_GENOME.MAPPING_DICTIONARY <PATH TO VG-SGG-dicts-with-attri.json> DATASETS.VISUAL_GENOME.IMAGE_DATA <PATH TO image_data.json> DATASETS.VISUAL_GENOME.VG_ATTRIBUTE_H5 <PATH TO VG-SGG-with-attri.h5> MODEL.DETR.OVERSAMPLE_PARAM <Alpha Value> MODEL.DETR.UNDERSAMPLE_PARAM <Twice the Beta Value> SOLVER.CLIP_GRADIENTS.CLIP_VALUE 0.01 SOLVER.IMS_PER_BATCH 12 MODEL.DETR.NO_OBJECT_WEIGHT 0.1 MODEL.WEIGHTS <PATH TO DETR Pretrained Model>
```
To set the `α` value use `MODEL.DETR.OVERSAMPLE_PARAM` flag, and set the `β` value using the `MODEL.DETR.UNDERSAMPLE_PARAM`. Note that `MODEL.DETR.UNDERSAMPLE_PARAM` should be specified as twice the desired β value. So for `β=0.75` use `MODEL.DETR.UNDERSAMPLE_PARAM 1.5`.

**Note**: If the code fails, try running it on a single GPU first in order to allow some preprocessed files to be generated. This is a one-time step. Once the code runs succesfully on a single GPU, you can run it on multiple GPUs as well. Additionally, the code, by default, is configured to run on 4 GPUs with a batch size of 12. If you run out of memory, change the batch size by using the flag `SOLVER.IMS_PER_BATCH <NUM IMAGES IN BATCH>`.

To evaluate the code, use the following command:
```python
python train_iterative_model.py --resume --eval-only --num-gpus <NUM_GPUS> --config-file configs/iterative_model.yaml OUTPUT_DIR <PATH TO CHECKPOINT DIR> DATASETS.VISUAL_GENOME.IMAGES <PATH TO VG_100K IMAGES> DATASETS.VISUAL_GENOME.MAPPING_DICTIONARY <PATH TO VG-SGG-dicts-with-attri.json> DATASETS.VISUAL_GENOME.IMAGE_DATA <PATH TO image_data.json> DATASETS.VISUAL_GENOME.VG_ATTRIBUTE_H5 <PATH TO VG-SGG-with-attri.h5>
```
You can find our model weights for `α=0.07` and `β=0.75` [here](https://drive.google.com/drive/folders/1L2H2e-UfyKfbbmM34LaJfT6S49VTfZDY?usp=share_link). To use these weights during evaluation, simply use the `MODEL.WEIGHTS <Path to downloaded checkpoint>` flag in the evaluation command. To check if the code is running correctly on your machine, the released checkpoint should give you the following metrics on the Visual Genome test set `VG_test`.

---

### IterativeSG
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="@inproceedings{Yu2022CoCaCC,
  title   = {Iterative Scene Graph Generation},
  author  = {Siddhesh Khandelwal and Leonid Sigal},
  year    = {NeurIPS 2022}
}"><pre class="notranslate"><code>
@inproceedings{Yu2022CoCaCC,
  title   = {Iterative Scene Graph Generation},
  author  = {Siddhesh Khandelwal and Leonid Sigal},
  year    = {NeurIPS 2022}
}
</code></pre></div>

### CenterMask
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="@inproceedings{Yu2022CoCaCC,
  title   = {centerMask: Real-Time Anchor-Free Instance Segmentation},
  author  = {Lee, Youngwan and Park, Jongyoul},
  year    = {CVPR 2020}
}"><pre class="notranslate"><code>
@inproceedings{lee2020centermask,
  title   = {enterMask: Real-Time Anchor-Free Instance Segmentation},
  author  = {Lee, Youngwan and Park, Jongyoul},
  year    = {CVPR 2020}
}
</code></pre></div>
