Jeaf Dean：
应该用一个模型去做很多事情，多任务。比如用一个模型训练差不多，然后去其他类似任务上做finetune。理想状态是用一个模型做所有的事情。

当前每个任务用一个模型训练，而这些模型的起点是一堆随机的浮点数，那训练起来肯定很慢，因为它对世界没有上下文概念，要通过大量数据建立起这个联系。

如果要达到上述理想状态，有很多问题要解决。比如一定是一个 sparsely activated model, 那对于一个特定的任务，肯定不希望把整个机房的芯片都激活来完成这个任务，需要在这个大模型里找到一个跟此任务相关的路径，其他无关模块不会被激活。

Chris Re：
有很多问题待解决：不同人之间如何共享模型？性能问题

## 问题：
### 1. 未来计算芯片如何发展？

Jeaf：好消息是 GPU 跟 CPU 不同，它离界限还比较远，还有几轮迭代会演进。另外是算法，当模型特别大，又具有稀疏性时，这样容量非常大，但是计算某个任务时只是部分激活。训练时也是类似，不需要每个样本都更新一次所有参数，只是更新其中一部分。

### 2. 量子计算机对ML有什么影响？
Jeaf：量子计算机是聚焦在解决某系问题上

### 3. 多任务处理的结果有多好？
Jeaf：如你所说，多任务处理的结果不是非常好。我认为目前多任务的边界/数量并没有真正发挥出来，比如一个模型处理1w或10w任务。这种是多模态的，把事物的视觉表征，语言表征，音频表征结合，真正在处理新任务时只需要少数样本。

Chris Re：目前效果不好，但是他看好这个领域  。

Jeaf：无监督学习，结果经常不是很成功，但我任务问题主要是大部分研究尝试学习无监督的表征，然后做有监督的训练，而非交叉一些有监督的样本。加入有监督的样本后，效果会好一些。当你有上千个任务，有无监督的算法，用一些有监督的样本，能够指导应该关注哪些东西。

Chris Re：当结合视觉和语言，我们主要在医疗领域，相比单独处理，有一些成果。

### 4. 人脑有相关性检索功能，比如输入未接触过的信息，它会基于听觉、视觉或语义相似性回想起一些信息。