# VCFGR: Voice-based Conversational Recommender Systems with Feature-adaptive Graph Representation
## Abstract
  Conversational Recommender Systems (CRS) have become an important emerging research direction in the recommendation systems area, with their innate advantage of capturing user preferences through interactive dialogue and unveiling the reasons behind recommendations. 
    However, most of the current CRS are text-based, overlooking the potential of users' voice features, which could enhance accessibility, provide more diverse data insights, and increase user engagement.
    In this paper, we propose a novel recommendation framework named *Voice-based Conversational Recommender Systems with Feature-adaptive Graph Representation* (**VCFGR**), which strives to expand the recommendation paradigm and embrace a broader user base.
    Our key idea is to capture the intrinsic correlation between voice and text information, maintain consistency in the voice feature-preference representation, and personalize the user experience.
    An adaptive graph strategy then seamlessly integrates all representation information of the user, aiming to learn user-item interaction patterns and facilitate the prediction of user preferences.
    Experimental results in two real-world datasets are documented to evidence the feasibility and effectiveness of our proposed method.

## Requirements

```
conda create -n VCFGR python=3.9
conda activate VCFGR
pip install -r requirements.txt
```

## Datasets
You can get the audio datasets from [GoogleDrive](https://drive.google.com/file/d/1FnpYhMaeskckxGheKjar0U4YHIdDKM6K/view). Please extract the data under the `./data/{dataset_name}/mp3/`

## How to run VCFGR

### MFE

- Coat

```
python run_MFE.py --dataset=coat --epochs=35 --lr=0.0005 --test=1 --neg_num=3 
```

- Movielens-1m

```
python run_MFE.py --dataset=movielens1m --epochs=35 --lr=0.0005 --test=1 --neg_num=5 
```

### AGIP

- Coat

```
python main.py --weight_decay=1e-4 --lr=0.001 --n_layers=3 --dataset=coat --recdim=64 --neg_num 3 --ens_ratio 0.8
```

- Movielens-1m

```
python main.py --weight_decay=1e-4 --lr=0.001 --n_layers=3 --dataset=movielens1m --recdim=64 --neg_num 5 --ens_ratio 0.6
```



## Benchmarking

Coat:
|   Metrics   | VCFGR |
| ----------- | ----------- |
|  F1@10   |    **12.68**   |
|  Precision@10   |    **8.24**   |
| Recall@10   |    **27.47**   |
|  NDCG@10    |    **18.68**   |

[//]: # (## Citation)

[//]: # ()
[//]: # (You are welcome to cite our paper:)

[//]: # (```)

[//]: # ()
[//]: # (```)
