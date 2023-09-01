
- https://github.com/huggingface/peft
- https://github.com/thunlp/OpenDelta
- https://github.com/adapter-hub/adapter-transformers

- [高效组合多个LoRA模块以实现跨任务泛化](https://mp.weixin.qq.com/s/QlTxcwdtOt8NizqqBzo6yg)

- LLM-Adapters: An Adapter Family for Parameter-Efficient Fine-Tuning of Large Language
  - 提出大模型微调用的adapter训练系统框架，包含常用的adapter，lora
  - https://github.com/AGI-Edgerunners/LLM-Adapters

- QLora
  - [QLoRA：一种高效LLMs微调方法，48G内存可调65B 模型，调优模型Guanaco 堪比Chatgpt的99.3%！](https://zhuanlan.zhihu.com/p/632229856)
  - 使用4位的NormalFloat（Int4）量化和Double Quantization技术。4位的NormalFloat使用分位数量化，通过估计输入张量的分位数来确保每个区间分配的值相等，
  Double Quantization是将额外的量化常数进行量化。
  - 梯度检查点会引起显存波动，从而造成显存不足问题。通过使用Paged Optimizers技术，使得在显存不足的情况下把优化器从GPU转义到CPU中。
  - QLora张量使用时，会把张量 反量化 为BF16，然后在16位计算精度下进行矩阵乘法。
  - https://github.com/artidoro/qlora
  - https://huggingface.co/blog/4bit-transformers-bitsandbytes
    - 介绍及使用


### 2022
- P-Tuning v2: Prompt Tuning Can Be Comparable to Fine-tuning Universally Across Scales and Tasks
  - <details>
    <summary>阅读笔记: </summary>
    1. 相比P-tuning v1只在输入部分添加连续的prompt token，v2在每一层添加prompt token  <br>
    2. 做抽取任务时，类似与bert做token分类，直接对每个位置的输出做分类  <br>
    3. 探索：
        1）分类任务使用更少的prompt token，抽取任务使用更多的prompt
        2）先使用多任务的方式微调参数，再单个任务微调能有一定的提升
        3）在靠近输出的模型层上添加prompt token，能获得更好的效果  <br>
        4）Deep Prompt Tuning:在每一层添加prompt token,方法是先设定输入的prompt token，使用全连接层为每个token生成每层的k和v向量
    <img src="" align="middle" />
    </details>

### 2021
- LORA: LOW-RANK ADAPTATION OF LARGE LANGUAGE MODELS
  - [[code]](https://github.com/microsoft/LoRA)
  - <details>
    <summary>阅读笔记: </summary>
    1. 提出了一种低秩自适应的模型微调方式：freeze整个模型的参数，在每个transformer层注入可训练的秩分解矩阵来适应下游任务  <br>
    2. 对self-attention中的q k v以及输出投射层进行了测试，发现在q v上添加lora层与在所有权重上添加效果相同，都取得了最好的效果  <br>
    3. 随着rank的提高，模型并没有取得更好的效果，原因是low-rank已经捕获了足够的信息  <br>
    4. 低秩矩阵与相应的模型层的权重呈现很强的相关性 <br>
    <img src="./assets/lora.jpg" align="middle" />
    </details>