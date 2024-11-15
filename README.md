# VLM_SFT

## Introduction

- VLM 微调训练基于 LLama-Factory 构建。

## Getting started

### 多模态图像数据集准备
- 数据格式：
```
[
  {
    "conversations": [
      {
        "from": "human",
        "value": "<image>人类指令"
      },
      {
        "from": "gpt",
        "value": "模型回答"
      }
    ],
    "images": [
      "图像路径（必填）"
    ]
  }
]
```
- 对于上述格式的数据，data/dataset_info.json 中的数据集描述应为：
```
"数据集名称": {
  "file_name": "data.json",
  "formatting": "sharegpt",
  "columns": {
    "messages": "conversations",
    "images": "images"
  }
}
```
- 举例：加入coco_train_2017数据集，首先将下载好的图片放到 data/ 下
- 然后将处理好的 coco_train_2017.json 文件放到 data/ 下
- 最后在 dataset_info.json 文件中加入coco_train_2017 数据信息：
```
"coco_train": {
  "file_name": "coco_train_2017.json",
  "formatting": "sharegpt",
  "columns": {
    "messages": "messages",
    "images": "images"
  },
  "tags": {
    "role_tag": "role",
    "content_tag": "content",
    "user_tag": "user",
    "assistant_tag": "assistant"
  }
}
```

### Qwen2VL 微调
- 进入页面后选择模型名称 ```Qwen2VL-7B-Instruct/Qwen2VL-72B-Instruct```
- 输入本地模型路径
- 选择微调方法
- 输入数据路径
- 选择数据集
- 根据需求设置其他参数
- 点击开始即可进入训练

### LLama3.2-vision 微调
- 进入页面后选择模型名称 ```LlamaVision3.2-11B-Instruct/LlamaVision3.2-90B-Instruct```
- 输入本地模型路径
- 选择微调方法
- 输入数据路径
- 选择数据集
- 根据需求设置其他参数
- 点击开始即可进入训练




