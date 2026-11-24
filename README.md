# 纱由美 JP-Extra 语音模型

[下载权重和推理配置](https://github.com/RobinwithLove/sayumi/releases/tag/jpextra-20261125)

三套日语语音模型分别训练，适用于 [Style-Bert-VITS2 2.7.0 JP-Extra](https://github.com/litagin02/Style-Bert-VITS2/tree/2.7.0)。保留全部 29 份推理权重，文件名中的 `e` 表示训练轮数，`s` 表示训练步数。

| 声线 | `model_assets` 下的目录 | 检查点 | 最终检查点 |
| --- | --- | ---: | --- |
| 纱由美表人格 | `sayumi_public_jpextra` | 10 | `e58_s9976` |
| 纱由美里人格 | `sayumi_private_jpextra` | 10 | `e48_s9936` |
| 夏乃由语 | `sayumi_streamer_jpextra` | 9 | `e200_s9000` |

## 加载模型

1. 下载并解压 `sayumi-jpextra-inference-configs.zip`。把其中 `model_assets` 下的三个模型目录放进 Style-Bert-VITS2 的 `model_assets`。
2. 下载需要的 `.safetensors`，放进文件名前缀对应的模型目录。该目录下的检查点共用 `config.json` 和 `style_vectors.npy`。
3. 启动 Style-Bert-VITS2 Editor，选择声线和检查点，语言选日语，风格可先用 `Neutral`。需要项目专名的读法时，将配置包 `dictionary` 中的补充条目合并进本地用户词典，再重启 Editor。

`SHA256SUMS.txt` 列出了 29 份权重和推理配置包的 SHA-256。
