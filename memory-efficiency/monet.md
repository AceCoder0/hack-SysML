1. 在解决的是什么问题？希望优化模型的显存占用，而且让速度是最快的
2. 为何成功，标志/准是什么？比checkmate 的找解决方案的速度要快，而且更节省显存，额外开销更小
3. 在前人基础上的关键创新是什么？除了checkponit的方案，还考虑了每个算子不同实现带来的收益和开销
4. 关键结果有哪些？
5. 有哪些局限性？如何优化？得根据不同的pytorch版本和cudnn，实现一些算子，这个成本比较高。而且它的实现不支持一些pytorch里的python语法
6. 这个工作可能有什么深远的影响？

看 github 上的 star 163，fork是16。

## 问题
1. 为什么 MONet 比 checkmate 找解决方案的速度快呢？
## 启发：
1. 对优化问题建模，然后利用已知的解题方法去解决问题
2. 