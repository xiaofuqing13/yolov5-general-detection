# YOLOv5 通用目标检测框架

YOLOv5 是由 Ultralytics 开发的实时目标检测框架，本仓库基于 YOLOv5 v7.0 版本，支持在自定义数据集上训练目标检测模型。框架支持多种模型规格（n/s/m/l/x），提供从数据预处理到模型部署的完整流程。

## 痛点与目的

- **问题**：目标检测任务需要高性能的检测框架，但从零搭建检测模型工程量大
- **方案**：基于 YOLOv5 v7.0 框架，支持一键式训练、验证、推理和导出
- **效果**：在 COCO 数据集上达到 SOTA 级别的检测精度和速度平衡

## 检测效果

![检测效果](images/detection_result.png)

## 核心功能

- **多规格模型**：YOLOv5n/s/m/l/x 五种规格，速度与精度灵活选择
- **训练与评估**：支持自定义数据集训练，输出 mAP、PR 曲线、混淆矩阵
- **多格式推理**：支持图片、视频、摄像头实时检测
- **模型导出**：支持导出为 ONNX、TensorRT、CoreML 等多种部署格式
- **数据增强**：Mosaic、MixUp、HSV 变换等丰富的数据增强策略

## 使用方法

### 安装依赖

```bash
pip install -r requirements.txt
```

### 推理检测

```bash
python detect.py --weights yolov5s.pt --source data/images
```

### 训练模型

```bash
python train.py --data coco128.yaml --weights yolov5s.pt --epochs 100
```

### 验证评估

```bash
python val.py --data coco128.yaml --weights runs/train/exp/weights/best.pt
```

## 技术栈

| 组件 | 技术 |
|------|------|
| 框架 | PyTorch |
| 检测算法 | YOLOv5 v7.0 |
| 数据增强 | Mosaic, MixUp |
| 损失函数 | CIoU Loss |
| 推理加速 | ONNX, TensorRT |

## 许可证

GPLv3 许可证
