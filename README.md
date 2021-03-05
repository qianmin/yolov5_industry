# yolov5_industry
yolov5从模型训练到C++部署，一条龙服务！！！！
# 1 训练
```
一：数据摆放

paper_data文件夹内：

①images放入图片
②标注，保存在annotations

二：数据转换为yolo

回到python工程
1.py
2.py

三：训练并且测试

###训练
打开出现的浏览器地址，查看训练准确度
python train.py --img 640 --batch 4 --epoch 100 --data data/myvoc.yaml --cfg models/yolov5s.yaml --weights yolov5s.pt


#训练完测试测试集
python test.py  --data data/myvoc.yaml --weights best.pt --augment


#直接图片测试
 python detect.py --weights best.pt --source data/images/

```
# 2 导出onnx
```
python models/export.py --weights yolov5s.pt --img 640 --batch 1 
```
# 3 qt使用
```
①onnx放进去
②coco.names 改为自己的类别
```
