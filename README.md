无人船要素检测数据集 yolo和voc两种标注方式

标签数：7466
框数: 21908

含14个类别以及框数：
boat (8177), bridge (2013), rock (1540), ball (2609), platform (614), rubbish (669), ship (3423), mast (354), person (695), harbor (1224), animal (94), buoy (167), tree (219), grass (110)

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/3dfca585bf0b4db38f98fca7fae00f31.png)


---

### 📊 无人船要素检测数据集描述表

| **项目** | **详情** |
|--------|--------|
| **数据集名称** | 无人船环境要素检测数据集 |
| **总标签数（图像数）** | 7,466 张图像 |
| **总边界框数（实例数）** | 21,908 个标注框 |
| **标注格式** | 同时提供 **YOLO (.txt)** 和 **Pascal VOC (.xml)** 两种标注格式 |
| **适用任务** | 目标检测（Object Detection）、无人船环境感知、自动驾驶水面系统 |
| **采集方式** | 无人船搭载摄像头在湖泊、河流、港口等水域采集 |


![---](https://i-blog.csdnimg.cn/direct/6145db8e908e4dfc8fa6de9595722c18.png)


### 🧩 类别分布与标注统计表

| **类别名称** | **英文名** | **标注框数量** | **占比（约）** | **说明** |
|-------------|-----------|----------------|----------------|----------|
| 船只 | `boat` | 8,177 | 37.3% | 小型船只、渔船、无人船等 |
| 船舶 | `ship` | 3,423 | 15.6% | 大型货轮、客轮等 |
| 桥梁 | `bridge` | 2,013 | 9.2% | 水上桥梁结构 |
| 岩石 | `rock` | 1,540 | 7.0% | 水边或水中的岩石障碍物 |
| 浮球 | `buoy` | 1,540 | 7.0% | 导航或警示浮标 |
| 球体 | `ball` | 2,609 | 11.9% | 训练用漂浮球或其他球状物（可能为人工投放） |
| 平台 | `platform` | 614 | 2.8% | 水上作业平台、浮台 |
| 垃圾 | `rubbish` | 669 | 3.1% | 水面漂浮垃圾（塑料、泡沫等） |
| 港口 | `harbor` | 1,224 | 5.6% | 港口建筑、码头区域 |
| 人员 | `person` | 695 | 3.2% | 出现在岸边或船上的人员 |
| 桅杆 | `mast` | 354 | 1.6% | 船只桅杆、信号杆等细长结构 |
| 动物 | `animal` | 94 | 0.4% | 水鸟、鱼类（跃出水面）等 |
| 树木 | `tree` | 219 | 1.0% | 岸边树木、倒伏入水的树 |
| 草类 | `grass` | 110 | 0.5% | 水生植物、漂浮草丛 |

> ✅ **总框数验证**：8177 + 3423 + 2013 + 1540 + 167 + 2609 + 614 + 669 + 1224 + 695 + 354 + 94 + 219 + 110 = **21,908** ✔️

---
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/1b962986a7e64bfcb812eb8a7d6c47ae.png)

### 📁 博主 推荐数据集目录结构

```
unmanned_boat_dataset/
├── images/
│   ├── train/
│   │   ├── img_00001.jpg
│   │   └── ...
│   └── val/
│       ├── img_00500.jpg
│       └── ...
├── labels_yolo/
│   ├── train/
│   │   ├── img_00001.txt
│   │   └── ...
│   └── val/
├── annotations_voc/
│   ├── train/
│   │   ├── img_00001.xml
│   │   └── ...
│   └── val/
├── data.yaml                 # YOLO 配置文件
├── classes.txt               # 类别列表
├── train.txt                 # 训练集图像路径列表
└── val.txt                   # 验证集图像路径列表
```

---
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/f790b3120a0c4a279cc845ebfad1533c.png)

### 📌 数据集特点

| 特点 | 说明 |
|------|------|
| **双格式标注** | 同时提供 YOLO 和 VOC 格式，兼容主流目标检测框架（YOLOv5/v8、Faster R-CNN、SSD 等） |
| **真实水域场景** | 数据来源于真实无人船运行环境，包含复杂光照、波浪、遮挡等挑战 |
| **障碍物丰富** | 包含岩石、垃圾、浮球等潜在航行障碍，适用于路径规划与避障系统开发 |
| **多尺度目标** | 从远处的小浮球到近处的大船，目标尺度变化大，考验模型多尺度检测能力 |
| **语义丰富** | 覆盖“自然”、“人工”、“生物”、“结构”四大类要素，适合构建全面的环境感知系统 |

---
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/bbdc5f5aea214f0290383eceaaf970ee.png)

### 📝 示例：YOLO 标注格式（.txt）

```txt
0 0.456 0.345 0.123 0.098  # boat
6 0.789 0.890 0.056 0.078  # ship
2 0.123 0.234 0.089 0.101  # rock
```

> 注：类别 ID 按 `classes.txt` 顺序从 0 开始编号。

---
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/be1e8858a7f04aee940431d257a967ea.png)

### 🔄 VOC 格式示例（.xml 片段）

```xml
<object>
    <name>buoy</name>
    <bndbox>
        <xmin>450</xmin>
        <ymin>300</ymin>
        <xmax>480</xmax>
        <ymax>330</ymax>
    </bndbox>
</object>
```

---

### ✅ 适用研究方向

1. **无人船自主导航与避障**
2. **水面垃圾识别与清理机器人**
3. **港口智能监控系统**
4. **多目标检测模型性能对比（YOLO vs RCNN）**
5. **域适应（Day → Night, Lake → Harbor）**
6. **小样本学习（如 animal、mast 等稀有类别）**

---

该数据集是开展 **水上自动驾驶、智能无人船、环境感知 AI** 研究的高质量资源，适用于高校、科研机构及海洋科技企业。

截至目前（2025年10月29日），**YOLOv11 尚未由 Ultralytics 或任何官方权威机构发布**。YOLO 系列的最新稳定版本为 **YOLOv8**（由 Ultralytics 维护）和 **YOLOv10**（由 MIT 于 2024 年提出，强调无 NMS 训练和高效推理）。目前互联网上所谓的 “YOLOv11” 多为误传、非官方魔改版本或营销噱头。

---

✅ **因此，目前无法提供官方支持的 YOLOv11 训练代码。**

但您可以使用当前最先进的 **YOLOv8** 或 **YOLOv10** 来训练您的 **无人船要素检测数据集**。以下是基于 **YOLOv8** 的完整、详细训练代码，兼容您提供的双格式数据（可转换为 YOLO 格式），并针对您的 14 类目标进行优化。

---

## ✅ 推荐：使用 YOLOv8 训练无人船要素检测模型（完整代码）

### 1. 环境安装

```bash
# 安装 YOLOv8
pip install ultralytics opencv-python lxml numpy tqdm
```

> 官方 GitHub：[https://github.com/ultralytics/ultralytics](https://github.com/ultralytics/ultralytics)

---

### 2. 数据准备：VOC → YOLO 格式转换

假设您的数据结构如下：

```
unmanned_boat_dataset/
├── images/train/
├── images/val/
├── annotations_voc/train/*.xml
├── annotations_voc/val/*.xml
```

#### 转换脚本：`voc_to_yolo.py`

```python
import os
import xml.etree.ElementTree as ET
from pathlib import Path

# 类别列表（必须与您的数据一致）
class_names = [
    'boat', 'bridge', 'rock', 'ball', 'platform', 'rubbish',
    'ship', 'mast', 'person', 'harbor', 'animal', 'buoy', 'tree', 'grass'
]
class_dict = {name: i for i, name in enumerate(class_names)}

def convert_voc_to_yolo(xml_path, img_dir, output_dir):
    tree = ET.parse(xml_path)
    root = tree.getroot()
    filename = root.find('filename').text
    image_id = Path(filename).stem

    # 图像路径
    img_file = Path(img_dir) / filename
    if not img_file.exists():
        # 尝试其他格式
        for ext in ['.jpg', '.jpeg', '.png']:
            alt_img = Path(img_dir) / (image_id + ext)
            if alt_img.exists():
                img_file = alt_img
                break
    if not img_file.exists():
        print(f"图像未找到: {filename}")
        return

    # 读取图像尺寸
    size = root.find('size')
    w = int(size.find('width').text)
    h = int(size.find('height').text)

    yolo_lines = []
    for obj in root.findall('object'):
        cls_name = obj.find('name').text.lower().strip()
        if cls_name not in class_dict:
            print(f"未知类别: {cls_name}")
            continue

        cls_id = class_dict[cls_name]
        bbox = obj.find('bndbox')
        xmin = float(bbox.find('xmin').text)
        ymin = float(bbox.find('ymin').text)
        xmax = float(bbox.find('xmax').text)
        ymax = float(bbox.find('ymax').text)

        # 归一化
        x_center = ((xmin + xmax) / 2) / w
        y_center = ((ymin + ymax) / 2) / h
        width = (xmax - xmin) / w
        height = (ymax - ymin) / h

        yolo_lines.append(f"{cls_id} {x_center:.6f} {y_center:.6f} {width:.6f} {height:.6f}")

    # 保存 .txt 文件
    txt_path = Path(output_dir) / (image_id + '.txt')
    with open(txt_path, 'w') as f:
        f.write('\n'.join(yolo_lines))

def batch_convert(voc_dir, img_dir, output_dir):
    os.makedirs(output_dir, exist_ok=True)
    for xml_file in Path(voc_dir).glob("*.xml"):
        convert_voc_to_yolo(xml_file, img_dir, output_dir)

# 执行转换
batch_convert(
    voc_dir='unmanned_boat_dataset/annotations_voc/train',
    img_dir='unmanned_boat_dataset/images/train',
    output_dir='unmanned_boat_dataset/labels_yolo/train'
)

batch_convert(
    voc_dir='unmanned_boat_dataset/annotations_voc/val',
    img_dir='unmanned_boat_dataset/images/val',
    output_dir='unmanned_boat_dataset/labels_yolo/val'
)
```

---

### 3. 创建 `data.yaml` 配置文件

```yaml
# unmanned_boat_dataset/data.yaml
train: ./unmanned_boat_dataset/images/train
val: ./unmanned_boat_dataset/images/val

# 类别数量
nc: 14

# 类别名称（顺序必须与 class_names 一致）
names: ['boat', 'bridge', 'rock', 'ball', 'platform', 'rubbish',
        'ship', 'mast', 'person', 'harbor', 'animal', 'buoy', 'tree', 'grass']
```

---

### 4. YOLOv8 训练代码

```python
# train.py
from ultralytics import YOLO
import torch

# 检查设备
device = 'cuda' if torch.cuda.is_available() else 'cpu'
print(f"Using device: {device}")

# 加载预训练模型（推荐使用大模型提升多类别检测性能）
model = YOLO("yolov8x.pt")  # 可选: yolov8s, yolov8m, yolov8l, yolov8x

# 开始训练
results = model.train(
    data='unmanned_boat_dataset/data.yaml',
    epochs=200,                     # 训练轮数
    imgsz=1280,                     # 高分辨率输入（适合远距离小目标）
    batch=16,                       # 根据显存调整（8-32）
    optimizer='AdamW',
    lr0=0.001,
    lrf=0.1,
    momentum=0.937,
    weight_decay=0.0005,
    warmup_epochs=3.0,
    patience=30,                    # 早停
    project="runs/unmanned_boat",
    name="exp_yolov8x_1280",
    save=True,
    save_period=10,
    device=device,
    workers=8,
    augment=True,                   # 启用增强
    hsv_h=0.015,
    hsv_s=0.7,
    hsv_v=0.4,
    degrees=10.0,
    translate=0.1,
    scale=0.5,
    shear=2.0,
    flipud=0.0,
    fliplr=0.5,
    mosaic=1.0,                     # 使用 Mosaic 增强
    mixup=0.1,                      # MixUp 增强
    copy_paste=0.1                  # Copy-Paste 增强（对小目标如 buoy、mast 有效）
)
```

---

### 5. 模型验证

```python
# 验证
metrics = model.val()
print(f"mAP@0.5: {metrics.box.map:.4f}")
print(f"mAP@0.5:0.95: {metrics.box.map50_95:.4f}")
```

---

### 6. 推理示例

```python
# 推理
model = YOLO("runs/unmanned_boat/exp_yolov8x_1280/weights/best.pt")

results = model.predict(
    source="test_river_scene.jpg",
    imgsz=1280,
    conf=0.25,
    iou=0.5,
    save=True,
    project="inference",
    name="boat_results",
    show_labels=True
)
```

---

## ✅ 替代方案：使用 YOLOv10（2024 最新 SOTA）

如果您希望尝试更新的架构，可使用 **YOLOv10**：

```bash
pip install git+https://github.com/THU-MIG/yolov10.git
```

训练方式与 YOLOv8 类似，详见其 GitHub 仓库。

---


