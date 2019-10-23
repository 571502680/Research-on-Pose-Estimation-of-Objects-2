# Research-on-Pose-Estimation-of-Objects-2
物体位姿估计研究-2：复现位姿估计论文《Real-Time Seamless Single Shot 6D Object Pose Prediction》

物体位姿估计交流群：756535271，欢迎各位大佬入群交流！

# Environment and dependencies

The code is tested on Linux with CUDA v8 and cudNN v5.1. The implementation is based on PyTorch 0.3.1 and tested on Python2.7. The code requires the following dependencies that could be installed with conda or pip: numpy, scipy, PIL, opencv-python

# Downloading and preparing the data

Inside the main code directory, run the following to download and extract (1) the preprocessed LINEMOD dataset, (2) trained models for the LINEMOD dataset, (3) the trained model for the OCCLUSION dataset, (4) background images from the VOC2012 dataset respectively.
```
wget -O LINEMOD.tar --no-check-certificate "https://onedrive.live.com/download?cid=05750EBEE1537631&resid=5750EBEE1537631%21135&authkey=AJRHFmZbcjXxTmI"
wget -O backup.tar --no-check-certificate "https://onedrive.live.com/download?cid=0C78B7DE6C569D7B&resid=C78B7DE6C569D7B%21191&authkey=AP183o4PlczZR78"
wget -O multi_obj_pose_estimation/backup_multi.tar --no-check-certificate  "https://onedrive.live.com/download?cid=05750EBEE1537631&resid=5750EBEE1537631%21136&authkey=AFQv01OSbvhGnoM"
wget https://pjreddie.com/media/files/VOCtrainval_11-May-2012.tar
wget https://pjreddie.com/media/files/darknet19_448.conv.23 -P cfg/
tar xf LINEMOD.tar
tar xf backup.tar
tar xf multi_obj_pose_estimation/backup_multi.tar -C multi_obj_pose_estimation/
tar xf VOCtrainval_11-May-2012.tar
```
Alternatively, you can directly go to the links above and manually download and extract the files at the corresponding directories. The whole download process might take a long while (~60 minutes).

# Training the model

To train the model run,
```
python train.py datafile cfgfile initweightfile
```
e.g.
```
python train.py cfg/ape.data cfg/yolo-pose.cfg backup/ape/init.weights
```
# Reference

《Real-Time Seamless Single Shot 6D Object Pose Prediction》

https://github.com/microsoft/singleshotpose
