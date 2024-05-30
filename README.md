
书生·浦语大模型的发展历程
![image](https://github.com/rudykon/InternLM/assets/15075498/fbea8743-b990-4dc9-b8f4-124998ec8883)

InternLM2面向不同的使用需求，每个规格包含三个模型版本
![image](https://github.com/rudykon/InternLM/assets/15075498/b9c49be0-f3f7-468d-aad8-339d9504129d)

InternLM2的主要亮点:超长上下文、综合性能全面提升、优秀的对话和创作体验、工具调用能力整体升级、突出的数理能力和实用的数据分析功能。
![image](https://github.com/rudykon/InternLM/assets/15075498/be868e37-ee49-4635-b75a-9ffdf677f2ac)

从模型到应用典型流程
![image](https://github.com/rudykon/InternLM/assets/15075498/92a97771-3961-4a95-b9de-ffdb6c46fc06)

InternLM2拥有优秀的开发工具箱或者开放应用测试平台，方便用户对大模型进行二次开发
![image](https://github.com/rudykon/InternLM/assets/15075498/6e4b8501-79d6-4298-91f7-fc38ebc48f47)


InternLM2 技术报告阅读笔记摘要：

基础设施：模型训练使用高效的轻量级预训练框架InternEvo进行模型训练。语言模型架构选择了Transformer，InternLM2遵循LLaMA的结构设计原则，并作了改进。

预训练：
预训练数据准备了通用领域文本数据、编程语言相关数据以及长文本数据
![image](https://github.com/rudykon/InternLM/assets/15075498/59471e76-830a-4ec6-8b52-c83dde3195a7)
![image](https://github.com/rudykon/InternLM/assets/15075498/47e37d8e-7378-44d7-a448-f8a3cd41b23b)
预训练设置采用GPT-4的分词方法，因为其在压缩大量文本内容方面的高效性表现出色。
预训练过程分为三个阶段。第一阶段，使用不超过4k长度的预训练语料库。第二阶段，加入了50%不超过32k长度的预训练数据。第三阶段，引入了特定能力增强数据。

对齐：包括监督微调（SFT）和基于人类反馈的强化学习（RLHF）两个阶段。
监督微调（SFT）阶段，使用了一个包含1000万条指令数据实例的 dataset。
强化学习（RLHF）阶段，提出条件在线RLHF（COOL RLHF）。COOL RLHF首先引入条件奖励机制来调和多样化的偏好，使奖励模型可以根据特定条件动态地将注意力分配给不同的偏好，从而最优地整合多个偏好。此外，COOL RLHF采用多轮在线RLHF策略，使语言模型能够快速适应新的人类反馈，减少奖励作弊的发生。
Long-Context Finetuning阶段，为了在微调后保持大模型的长序列理解能力，我们沿用了之前工作中的做法，即在SFT（逐句 fine-tuning）和RLHF（强化学习人类反馈）中继续使用长序列预训练数据。具体来说，我们使用了两类数据：一类来自书籍的长序列文本，另一类是来自GitHub仓库的数据。
Tool-Augmented LLMs阶段，增加通用工具调用、代码解释器作为特殊工具。

评估分析：InternLM2系列在具有相似参数数量的模型中表现良好。专项领域也不错。
![image](https://github.com/rudykon/InternLM/assets/15075498/dc74f549-a491-4118-8303-34f353153d46)
![image](https://github.com/rudykon/InternLM/assets/15075498/eb05e86b-b886-4b7c-9219-a770e100f783)



