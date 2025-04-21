# 自然语言处理：机器翻译

机器翻译语言方向为英文到中文。

## 数据集

使用AI Challenger 2017中的英中机器文本翻译数据集，超过1000万的英中对照的句子对作为数据集合。其中，训练集合占据绝大部分，为12904955对，验证集合8000对，测试集A 8000条，测试集B 8000条。

可以从这里下载：[英中翻译数据集](https://challenger.ai/datasets/translation)

![dataset](https://github.com/user-attachments/assets/406a2f4d-d044-4df8-86fe-cc50ecf2288a)

## 用法

### 数据预处理

得到验证集数据：

```bash
$ python convert_valid.py
```

提取训练和验证样本（得到文件data.pkl）：
```bash
$ python pre_process.py
```

得到词表样本（得到文件vacob.pkl）：

```bash
$ python data_gen.py
```

### 训练

```bash
$ python train.py
```

要想可视化训练过程，在终端中运行：
```bash
$ tensorboard --logdir path_to_current_dir/logs
```

本人电脑比较的垃圾，使用了云端modelscope平台的GPU设备（查了一下是3090），batch_size=128的情况下，每一轮epoch用时1.6小时左右，最终训练5轮，损失还比较大，虽然是在稳步下降，但是降低速度非常慢，预估可能需要200轮左右的训练。

以下是翻译的一些实例展示

![Snipaste_2025-04-07_14-49-46](https://github.com/user-attachments/assets/68a399f8-102c-43ab-8976-d2deea137cbb)



