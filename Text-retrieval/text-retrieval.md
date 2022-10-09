<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Repo](#repo)
- [paper](#paper)
- [term weight](#term-weight)
- [ES](#es)
- [datasets](#datasets)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## Repo
- 信息检索优质资源汇总 https://github.com/harpribot/awesome-information-retrieval
- query，doc，profile搜索排序模型 https://github.com/linkedin/detext
- https://github.com/terrifyzhao/text_matching
- https://github.com/TharinduDR/Simple-Sentence-Similarity
- https://github.com/NTMC-Community/MatchZoo-py
- https://github.com/NTMC-Community/awesome-neural-models-for-semantic-match
- https://github.com/MachineLP/TextMatch
- https://github.com/pengming617/text_matching
- https://github.com/shenweichen/DeepMatch
- https://github.com/seatgeek/fuzzywuzzy
- https://github.com/DengBoCong/text-similarity
  
  
## paper

- VIRT: Improving Representation-based Models for Text Matching through Virtual Interaction
  - year:2021 
  - 阅读笔记：
    1. 提出一种将交互模型的知识蒸馏到双塔模型的方法
    2. 将双塔的隐层做交互来模拟交互模型的交互表示，然后跟交互模型的交互表示计算L2损失
    3. 双塔模型的输出做双向注意力计算，得到u和v，u、v、|u-v|、max(u,v)拼接后接分类层
  - code: 

- Paper: Poly-encoders: architectures and pre-training strategies for fast and accurate multi-sentence scoring
  - year: 2020 ICLR
  - 阅读笔记: 
    1. 提出跟bi-encoder推理速度相当，精度与cross-encoder接近的poly-encoder模型，该模型延续的bi-encoder的双transformer结构
    2. 使用m个codex来表征context的global特征，m是超参数，影响推理速度
    3. candidate的表征extand到m个condex，来计算注意力。然后根据注意力得分加权codex，从而得到context的表征，最后和candidate的表征计算得分
  - code: 非官方 https://github.com/sfzhou5678/PolyEncoder


## term weight
- https://github.com/AdeDZY/DeepCT


## ES
- https://github.com/elastic/elasticsearch
- https://github.com/medcl/elasticsearch-analysis-ik
  - 中文分词器
- https://github.com/medcl/elasticsearch-analysis-pinyin
- https://github.com/NLPchina/elasticsearch-analysis-ansj


## datasets
- https://github.com/zejunwang1/CSTS
