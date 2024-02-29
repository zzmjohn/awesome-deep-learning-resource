


# 数据筛选

- What Makes Good Data for Alignment? A Comprehensive Study of Automatic Data Selection in Instruction Tuning
  - year: 2023
  - 先对数据进行复杂性和质量评分，再通过多样性进行数据筛选
  - code: https://github.com/hkust-nlp/deita
  - [DEITA-大模型指令微调的数据高效筛选方法](https://zhuanlan.zhihu.com/p/675928711)

- MoDS: Model-oriented Data Selection for Instruction Tuning
  - year: 2023
  - 首先使用deberta模型对数据质量进行打分，得到质量较高的数据集
  - 基于K-center-greedy方法，从得到的数据中获取最大多样化的数据子集
  - 基于种子子集微调一个大模型，基于该大模型对1中高质量数据集进行预测，使用奖励模型获取不能很好预测结果的数据，这样的数据对大模型难度更高，最后将难例数据和数据子集混合起来，训练最终效果更好的模型
  - code: https://github.com/CASIA-LM/MoDS
  - [高质量指令数据筛选方法-MoDS](https://zhuanlan.zhihu.com/p/671183709)


- From Quantity to Quality: Boosting LLM Performance with Self-Guided Data Selection for Instruction Tuning
  - year: 2023
  - 指令数据筛选：首先基于聚类的方法筛选出多样性比较高的少量样本，然后对模型进行微调
  - 基于微调的大模型计算样本的指令跟随难度，即模型预测答案的概率越小，对模型来说难度越高，使用这样的样本继续训练能够带来更好的效果
  - code：https://github.com/MingLiiii/Cherry_LLM
  

- LIMA: Less Is More for Alignment
  - year: 2023
  - 仅仅使用高质量的少量数据，便得到一个效果很好的大模型
  - 在多轮对话上，添加30个高质量的多轮对话链，使得模型的多轮对话能力显著提升
  - [Meta AI 重磅推出LIMA！媲美GPT-4、无需RLHF就能对齐](https://mp.weixin.qq.com/s/sbIa-fIHvMlp-2aYtCtVLQ)