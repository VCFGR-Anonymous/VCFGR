# VGCR: Voice-Empowered Graph Representation for Voice-based Conversational Recommender Systems
## Abstract
Conversational Recommender Systems (CRs) have become an important emerging research direction in the recommendation systems area, with their innate advantage of capturing user preferences through interactive dialogue and unveiling the reasons behind recommendations. However, existing CRs methods rely on text-based interactions, which can be less user-friendly and may pose significant challenges to users with vision impairments or limited writing abilities. In this paper, we propose a novel recommendation framework named *Voice-Empowered Graph Representation for Voice-based Conversational Recommender Systems* (**VGCR**). This framework captures the intrinsic correlation between voice and historical interactions, representing voice preference within a collaborative filtering paradigm. To better encode the voice characteristics of users, **VGCR** establishes a transit station between voice and text feature information through feature retrieval. In addition, we exploit high-order graph convolutional networks to learn user-item interaction patterns, which smooth all the voice and text representational information, thereby facilitating the prediction of user preferences. Extensive experiments validate the feasibility and consistent superiority of our method over existing text-based recommendation models.

## Requirements

```
conda create -n VGCR python=3.9
conda activate VGCR
pip install -r requirements.txt
```

## Datasets
You can get the audio datasets from [GoogleDrive](https://drive.google.com/file/d/1FnpYhMaeskckxGheKjar0U4YHIdDKM6K/view). Please extract the data under the `./data/{dataset_name}/mp3/`

## How to run VGCR

### Multi-feature extractor

- Coat

```
python run_feature_extractor.py --dataset=coat --epochs=35 --lr=0.0005 --test=1 --neg_num=3 
```

- ML1M-mini

```
python run_feature_extractor.py --dataset=movielens1m --epochs=35 --lr=0.0005 --test=1 --neg_num=5 
```

### Graph information propagation

- Coat

```
python main.py --weight_decay=1e-4 --lr=0.001 --n_layers=3 --dataset=coat --recdim=64 --neg_num 3 --ens_ratio 0.5
```

- ML1M-mini

```
python main.py --weight_decay=1e-4 --lr=0.001 --n_layers=3 --dataset=movielens1m --recdim=64 --neg_num 5 --ens_ratio 0.8 --emb_dropout 0.1
```



## Benchmarking

Coat:
|   Metrics   | VGCR |
| ----------- | ----------- |
|  F1@10   |    **12.28**   |
|  Precision@10   |    **7.98**   |
| Recall@10   |    **26.60**   |
|  NDCG@10    |    **18.27**   |

[//]: # (## Citation)

[//]: # ()
[//]: # (You are welcome to cite our paper:)

[//]: # (```)

[//]: # ()
[//]: # (```)
