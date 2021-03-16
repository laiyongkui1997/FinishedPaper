# Adavance in Multi-turn Dialogue Comprehension: A Survey

## 一句话总结

总结了近些年来多轮对话理解的一些前沿技术。

## 主要内容

### 模型架构

以Encoder-Decoder架构为主线，由远及近地描述了三个主要的模型架构

- Concatenated Matching
- Separate Interaction
- PrLM-based Interaction

目前最好的方法就是PrLM（预训练语言模型）的架构效果最好了。因此如何训练得到一个Dialogue-related语言模型很关键。

所有架构图如下：

![](/Users/lyk/Desktop/Finished/pic/001-LM_architecture.png)
### 三种预训练方式

预训练语言模型有三种预训练的方式

- 通用目的的预训练（General-purpose Pre-Training）：通用的目标函数（如MLM，NSP，SOP等），使用通用范围的数据
- 领域相关的预训练（Domain-aware Pre-Traning）：使用领域内的数据
- 面向任务的预训练（Task-oriented Pre-Traning）：设计与特定任务相关的目标函数（例如order prediction信息相关的目标函数）

![](/Users/lyk/Desktop/Finished/pic/001-Dialogue_LM.png)

### 未来的方向

#### 现有挑战

如何有效地将PrLM应用到对话文本中。

多人多轮对话文本独有的挑战

- 说话角色的转换
- 复杂的对话结构
- 需要足够的背景知识
- 多语言和多模态的对话场景

#### 可行的方向

##### 对话文本分解

目的：为了得到更为精细的特征。比如可以将不同的说话方进行分别建模。

难点：并不是那么好分。比如多topic的对话句子，不好明确地拆分每个topic的文本。

##### 背景知识基础

目的：背景知识很重要，因此需要考虑到。例如常识能够增强因果推理能力。

##### 对话特定的语言模型

目的：对话特定的语言模型需要大量的对话文本，如何大量获取该语料以减少标注成本。

方法：

- 从free-form和domain-free的预料中模拟对话文本
- 从通用目的的模型迁移到对话特定的模型
- 多领域适配方法

##### 可靠的数据构造

目的：负样本的构造不合理，除了正样本以外的都是负样本，这样随机构造的负样本对模型的能力没啥提升。

##### 多语言和多模态的对话

目的：语言模型能力这么强，可以考虑往其他方面去扩展。

