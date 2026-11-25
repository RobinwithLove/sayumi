# 纱由美里人格 · JP-Extra 第二轮

这个目录收录 2026-11-26 整理的里人格独立模型。训练使用 Style-Bert-VITS2 2.7.0 JP-Extra，batch size 为 8，共 20 轮，每轮 207 步并保存一份推理权重。20 份权重共用本目录的配置和风格向量。

## 选哪份权重

- **验证集综合第 1 名** · [e17 / s3519](sayumi_private_jpextra_e17_s3519.safetensors)，综合分 **0.914764**，可作为首选试听。
- **说话人分第 1 名** · [e14 / s2898](sayumi_private_jpextra_e14_s2898.safetensors)，说话人分 **0.747399**。
- **训练最终存档** · [e20 / s4140](sayumi_private_jpextra_e20_s4140.safetensors)，综合排名第 4，综合分 0.902116。

## 验证集排行

评分使用里人格自己的 22 条固定验证音频，共 501 个参考假名字符。ASR 分来自 Anime Whisper 转写后的假名字符准确率，说话人分是 WeSpeaker 在合成音与对应原音之间的平均余弦相似度。综合分为 70% ASR 分与 30% 说话人分的加权和。

排行按本轮 `epoch_scores.csv` 的原始综合分从高到低排列。[下载完整 CSV](epoch_ranking.csv)

| 排名 | 权重 | ASR | 说话人 | 综合分 | 标注 |
| ---: | --- | ---: | ---: | ---: | --- |
| 1 | [e17 / s3519](sayumi_private_jpextra_e17_s3519.safetensors) | 0.988024 | 0.743823 | **0.914764** | 综合和 ASR 第一 |
| 2 | [e19 / s3933](sayumi_private_jpextra_e19_s3933.safetensors) | 0.976048 | 0.737531 | 0.904493 |  |
| 3 | [e18 / s3726](sayumi_private_jpextra_e18_s3726.safetensors) | 0.972056 | 0.739126 | 0.902177 |  |
| 4 | [e20 / s4140](sayumi_private_jpextra_e20_s4140.safetensors) | 0.970060 | 0.743580 | 0.902116 | 最终存档 |
| 5 | [e13 / s2691](sayumi_private_jpextra_e13_s2691.safetensors) | 0.972056 | 0.730730 | 0.899658 |  |
| 6 | [e11 / s2277](sayumi_private_jpextra_e11_s2277.safetensors) | 0.974052 | 0.721368 | 0.898247 |  |
| 7 | [e16 / s3312](sayumi_private_jpextra_e16_s3312.safetensors) | 0.972056 | 0.725509 | 0.898092 |  |
| 8 | [e15 / s3105](sayumi_private_jpextra_e15_s3105.safetensors) | 0.966068 | 0.734885 | 0.896713 |  |
| 9 | [e12 / s2484](sayumi_private_jpextra_e12_s2484.safetensors) | 0.974052 | 0.715822 | 0.896583 |  |
| 10 | [e3 / s621](sayumi_private_jpextra_e3_s621.safetensors) | 0.968064 | 0.728353 | 0.896151 |  |
| 11 | [e14 / s2898](sayumi_private_jpextra_e14_s2898.safetensors) | 0.958084 | 0.747399 | 0.894878 | 说话人分第一 |
| 12 | [e6 / s1242](sayumi_private_jpextra_e6_s1242.safetensors) | 0.960080 | 0.741439 | 0.894488 |  |
| 13 | [e5 / s1035](sayumi_private_jpextra_e5_s1035.safetensors) | 0.970060 | 0.711854 | 0.892598 |  |
| 14 | [e2 / s414](sayumi_private_jpextra_e2_s414.safetensors) | 0.970060 | 0.688960 | 0.885730 |  |
| 15 | [e10 / s2070](sayumi_private_jpextra_e10_s2070.safetensors) | 0.972056 | 0.683792 | 0.885577 |  |
| 16 | [e1 / s207](sayumi_private_jpextra_e1_s207.safetensors) | 0.958084 | 0.710251 | 0.883734 |  |
| 17 | [e4 / s828](sayumi_private_jpextra_e4_s828.safetensors) | 0.964072 | 0.687511 | 0.881104 |  |
| 18 | [e8 / s1656](sayumi_private_jpextra_e8_s1656.safetensors) | 0.952096 | 0.711770 | 0.879998 |  |
| 19 | [e9 / s1863](sayumi_private_jpextra_e9_s1863.safetensors) | 0.946108 | 0.724604 | 0.879657 |  |
| 20 | [e7 / s1449](sayumi_private_jpextra_e7_s1449.safetensors) | 0.946108 | 0.715710 | 0.876988 |  |

## 旧版同集复测

旧版 `sayumi_private_jpextra_e20_s4000.safetensors` 在同一组 22 条验证音频上的 ASR 为 0.970060，说话人分为 0.750728，综合分为 0.904260。本轮 e17 的综合分高 0.010504。选用权重时，可以对照陌生句子的里人格口吻、句尾时值和音色连续性。

## 加载模型

1. 在 Style-Bert-VITS2 的 `model_assets` 下创建 `sayumi_private_jpextra_v2_20261126`。
2. 下载所选权重、[config.json](config.json) 和 [style_vectors.npy](style_vectors.npy)，放进该目录。从 GitHub 下载时，可在权重文件页点击 Download 取回完整的 Git LFS 文件。
3. 在 Editor 里选择新目录和对应权重，语言选择日语，风格选择 `Neutral`。该模型以 44.1 kHz 输出。

推理配置保留原模型的结构、采样和风格设置，移除了两项服务器训练清单路径。文件完整性可用同目录的 [SHA256SUMS.txt](SHA256SUMS.txt) 校验。

模型基于 [JP-Extra 基模](https://huggingface.co/litagin/Style-Bert-VITS2-2.0-base-JP-Extra) 微调，可在 [Style-Bert-VITS2 2.7.0](https://github.com/litagin02/Style-Bert-VITS2/tree/2.7.0) 中加载。
