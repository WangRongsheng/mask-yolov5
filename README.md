## dataset制作

[https://github.com/WangRongsheng/make-your-yolov5_dataset](https://github.com/WangRongsheng/make-your-yolov5_dataset)

## dataset配置

> 看案例`dataset`

查看数据集下的`data.yml`是否正确

## yolov5下载

```html
git clone https://github.com/ultralytics/yolov5
```

## yolov5修改

`yolov5`->`models`->`yolov5s.yaml`->`nc：`改成你的类别数

## yolov5训练

```html
python train.py --data ../dataset/data.yaml --cfg models/yolov5s.yaml --batch-size 8

python train.py --data ../dataset/data.yaml --cfg models/yolov5m.yaml --batch-size 4

python train.py --data ../dataset/data.yaml --cfg models/yolov5l.yaml --batch-size 2

python train.py --data ../dataset/data.yaml --cfg models/yolov5x.yaml --batch-size 2
```

## yolov5推断

```html
python detect.py --weights runs/exp0/weights/best.pt --source 0  # webcam

python detect.py --weights runs/exp0/weights/best.pt --source file.jpg  # image 

python detect.py --weights runs/exp0/weights/best.pt --source file.mp4  # video

python detect.py --weights runs/exp0/weights/best.pt --source path/  # directory
```

## yolov5部署

[https://github.com/WangRongsheng/mask-yolov5-fastapi](https://github.com/WangRongsheng/mask-yolov5-fastapi)

## yolov5连接手机进行检测

1. 安卓/IOS下载`IP摄像头`；
2. 记住app里面提供的`ip地址`；
3. 打开yolov5项目，执行命令：
```python
python detect.py --weights runs/exp0/weights/best.pt --source http://admin:admin@+ip地址

举例：
python detect.py --weights runs/exp0/weights/best.pt --source http://admin:admin@192.168.1.186:8081
```

参考：[yolov5目标检测连接手机摄像头实现方法](https://www.bilibili.com/video/BV1Bz4y1S7za)
