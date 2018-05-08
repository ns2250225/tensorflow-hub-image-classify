# tensorflow-hub-image-classify
Python3使用TF-Hub进行迁移学习（图片分类）

# 机器环境
- win10
- python3.6

# 安装依赖
- pip install tensorflow==1.7.0
- pip install tensorflow-hub

# 准备图片素材
- 注意：每一类至少要100张图片以上，不然会报错
- 把图片分好类放到 photos 文件夹里面

# 训练模型（默认是使用Inception V3）
```
python .\retrain.py --image_dir .\photos\ --saved_model_dir .\mod
el\ --bottleneck_dir .\bottleneck\ --how_many_training_steps 20 --output_labels .\output\output_labels.txt --output_grap
h .\output\retrain.pb
```

# 测试模型（测试单张图片）
```
python .\label_image.py --graph .\output\retrain.pb --labels .\o
utput\output_labels.txt --input_layer=Placeholder --output_layer=final_result --image .\test.jpg
```

# 备注
- 可以使用别的模型来训练
- 在训练模型时加上：--tfhub_module https://tfhub.dev/google/imagenet/mobilenet_v2_100_224/feature_vector/1 