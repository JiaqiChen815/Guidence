# SpikingViT
感谢您对我们的模型感兴趣。如果您在运行我们的代码时遇到了**未解决的问题**，那么，这个文档将会帮助您解决这些问题。如果仍然没有解决您的问题，请随时联系我们，欢迎在我们的[github](https://github.com/Chrazqee/SpikingVit)仓库提问。

## Conda 环境以及依赖
我们推荐您新建**conda**环境来运行本项目代码。
```bash
conda create -n spikingVit python=3.10
conda activate spikingVit

pip install -r requirements.txt
```

## 运行脚本
我们强烈建议您在 **Linux** 平台上运行我们的代码, 因为在 **Windows** 平台上运行的时候，会出现错误。主要错误我们分析为多进程调用导致无法运行成功。

在运行脚本之前，确保您的 `.sh` 脚本文件已经具备执行权限。可以在终端运行以下命令：
```bash
sudo chmod +x ./train_gen1/4.sh
```
如此，您便可以运行脚本，执行我们的代码了。在终端运行以下命令：
```bash
./train_gen1/4.sh
```
## 可能遇到的问题
### 1. 数据集的加载
在训练的过过程中，如果遇到多多管道加载数据集出现 assert 错误，那么我们建议您可以更改 num_workers 的大小，通过调整，可以解决问题。

### 2. 多 GPU 训练速度慢
我们建议您在训练过程中建议使用单 GPU 进行训练，这样可以提高训练速度。因为多GPU涉及到同步的问题，并且多 GPU 的交互走的是 PCI 总线，因此会导致训练速度变慢。

### 3. 模型输出的大小与论文中的模型大小不一致
这个问题是 pytorch_lightning 包的统计机制导致的问题，如果想看模型的真实大小，我们建议将模型单独拿出来，再计算模型的大小。如果您感觉有困难，请联系我们，我们将提供我们的代码给您。

### 4. 如有问题，欢迎联系我们，我们将更新此条目

## 引用
如果您发现我们的工作对您的研究有所帮助，请考虑在您的文献引用中加入以下BibTeX条目：
```Tex
@misc{project_acknowledgment,
  author = {Lixing Yu, Hanqi Chen, Ziming Wang, Shaojie Zhan, Jiankun Shao, Qingjie Liu, and Shu Xu},
  title = {SpikingViT: a Multi-scale Spiking Vision Transformer Model for Event-based Object Detection},
  howpublished = {IEEE Transactions on Cognitive and Developmental Systems},
  year = {2024},
  note = {}
}
```
并且，不要忘记引用我们致谢的项目，在[这里](thanks.md)找到它们。

