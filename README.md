Final Project for COMSW 4995

# DeepDiffChrome

[DeepDiff: Deep-learning for predicting Differential
gene expression from histone modifications](https://academic.oup.com/bioinformatics/article/34/17/i891/5093224)

```
@article{ArDeepDiff18,
author = {Sekhon, Arshdeep and Singh, Ritambhara and Qi, Yanjun},
title = {DeepDiff: DEEP-learning for predicting DIFFerential gene expression from histone modifications},
journal = {Bioinformatics},
volume = {34},
number = {17},
pages = {i891-i900},
year = {2018},
doi = {10.1093/bioinformatics/bty612},
URL = {http://dx.doi.org/10.1093/bioinformatics/bty612},
eprint = {/oup/backfile/content_public/journal/bioinformatics/34/17/10.1093_bioinformatics_bty612/2/bty612.pdf}
}
```
## Training Model
To train, validate and test the model for celltypes "Cell1" and "Cell2": 




&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;python train.py --cell_1=Cell1 --cell_2=Cell2  --model_name=raw_d --epochs=120 --lr=0.0001 --data_root=data/ --save_root=Results/



### Other Options
1. To specify DeepDiff variation: \
--model_name= \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;raw_d: difference of HMs \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;raw_c: concatenation of HMs \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;raw: raw features- difference and concatenation of HMs \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;raw_aux: raw features and auxiliary Cell type specific prediction features \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;aux: auxiliary Cell type specific prediction features \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;aux_siamese: auxiliary Cell type specific prediction features with siamese auxiliary \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;raw_aux_siamese: raw features and auxiliary Cell type specific prediction features with siamese auxiliary 

2. To save attention maps: \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;use option --save_attention_maps : saves Level II attention values in .txt file 

3. To change rnn size: \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;--bin_rnn_size=32 




### Testing
To only test on a saved model: \
python train.py --test_on_saved_model --model_name=raw_d --data_root=data/ --save_root=Results/  

### Note: Due to the acceptable file sizes, we could not upload our training data and the model checkpoints.
