# MTA-LSTM in TensorFlow

TensorFlow implementation of paper [Topic-to-Essay Generation with Neural Networks](http://ir.hit.edu.cn/~xcfeng/xiaocheng%20Feng's%20Homepage_files/final-topic-essay-generation.pdf).

## Motivation: 

The origin [implementation](https://github.com/hit-computer/MTA-LSTM) only provides the MTA-LSTM model, and the code is out-of-date.
In this repo, all three models in the paper are implemented in TensorFlow. And the latest TensorFlow seq2seq and RNNWrapper apis are utilized to make the code clean. 

**If you find this repo is helpful, a star would be so nice!**

## Prerequisites
- Python3
- TensorFlow >= 1.7

## Implementation Notes
1. TAV-LSTM: feed topic embedding average to a forward network to obtain initial state of decoder.
2. TAT-LSTM: at each time step, compute attention on the topic embedding using Bahdanau Attention, and concat with input to the decoder.
3. MTA-LSTM: maintain a **coverage vector** to record the whether topic information has been expressed during the training.

**Note**: beam search used in the origin repo is **NOT SUPPORTED**.

You can refer to the code for more details. If you meet any problems, feel free to raise a issue. 

For the data preprocessing, you may refer to the origin paper and process your own data.

## Generated Examples
Below are some examples  generated by three models (in Chinese):

---

Topic words:  留学 职业规划

TAV-LSTM: 现在 在 一 家 国企 上班 ， 离家 太 远 的 样子 ， 所以 我 想 去 云南 ， 想 去 一 家 公司 工作 ， 但是 我 想 去 外地 工作 ， 我 想 去 大 城市 发展 ， 但是 父母 供 我 见识 ， 我 应该 怎么 做 ？ 人 的 宝宝 应该 怎么 办 ？

TAT-LSTM:  委托 转型 。 入 金融 行业 的 本科生 ， 在 一 所 211 ， 本科 专业 的 考虑 ， 已经 工作 两 年 ， 现在 想 转 专业 的 课程 ， 然后 再 考 个 证 ， 然后 再 去 找 资料 ， 但是 不 知道 怎么 做 。 我 想 问问 大家 有 没 有 什么 好 的 建议 ， 我 很 想 知道 报名 的 资料 ， 以及 专业 知识 结构 ， 以及 专业 知识 ， 还有 什么 办法 可以 让 自己 的 努力 ？ 谢谢

MTA-LSTM: 我 是 一 名 大三 的 学生 ， 今年 九月 去 德国 读 金融 硕士 ， 现在 想 出国 读研 ， 但是 我 觉得 自己 不 喜欢 这个 专业 ， 想 问问 各位 前辈 们 ， 澳洲 的 学校 和 澳洲 的 教育 学校 有 哪些 差距 ？ 我 想 去 那里 发展 ， 但是 我 真的 很 迷茫 ， 我 不 知道 该 怎么 选择 。 。 的 话 我 应该 选择 什么 专业 呢 ？ 大学 大学 读书 梦想 我 该 如何 选择 ？ 感激 

---

Topic words: 爱情 恋爱

TAV-LSTM: 我 和 她 是 异地 恋 ， 她 很 喜欢 她 ， 我 很 想 她 和 她 在 一起 ， 我 想 留住 她 ， 但是 又 不 会 主动 找 她 聊天 ， 她 说 我 是 不 是 很 好 ， 但 我 真的 很 想 分手 。 他 却 不 愿意 和 他 做 朋友 ， 我 该 怎么 办 ？

TAT-LSTM:  女神 沿海 的 ， 我 的 家庭 条件 很 好 ， 所以 很 矛盾 ， 我 很 想 知道 他们 的 生活 是 什么 ？ 我 想 说 的 是 ， 我 自己 不 喜欢 这样 的 人 ， 所以 想 请教 一下 各位 ， 我 应该 怎么 做 才 能 让 她 更 好 地 说服 自己 ？ 和 上海 女 朋友 和 女 朋友 ， 有 什么 建议 ？ 或者 说 可以 ， 我 的 时间 应该 如何 选择 ？ 的 时候 ， 我 是 学 什么 ， 我 指 的 是 为了 职业 规划 ，

MTA-LSTM: 我 是 一个 宅男 ， 我 是 一个 男生 ， 其次 是 因为 我 对 她 很 好 ， 我 也 很 喜欢 他 ， 但是 她 不 主动 给 我 说 ， 我 就 不 想 跟 她 说 了 ， 我 该 怎么 办 ？ 她 说 我 不 喜欢 她 ， 我 该 怎么 办 ？ 她 说 我 不 喜欢 她 ， 我 该 怎么 办 ？ 她 说 我 不 喜欢 她 ， 我 该 怎么 办 ？ 她 说 我 不 喜欢 她 ， 我 该 怎么 办 ？