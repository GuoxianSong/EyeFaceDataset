# EyeFaceDataset
The dataset can be found at this link:
https://drive.google.com/drive/folders/1PWq3gJKoDo6m-ANgl9erqEbUuYn0Ihts
for paper "Real-time 3D Face-Eye Performance Capture of a Person Wearing VR Headset".

# IReye dataset.
This dataset is collected using Fove 0 HMD. It contains 7 subjects. We use its debug tool and screen recorder to collect data.
For each data collection, we first calibrate users eye using default program, then collect images as well as labels.
The calibration needs 10-20 seconds, and it will come up with signal at right bottom of screen "Calibration has ended.".
There are two way to collect data. 1. Use debug tool provide by Fove to record images and label, then use some OCR technique to extract numbers.
2.Use current Fove SDK API to directly collect images and labels, which is available now.

For pupil location, you can refer to code from https://github.com/YutaItoh/3D-Eye-Tracker. It needs modify some conventional size as well as parameters
to get a good pupil tracking. 
For pupil size, we use classical watershed segmentation to extract pupil region and find its size.

Some functions in the "FoveEyeDataProcess.py" might help you normalize the dataset.

# HMD Face
This dataset is collected using a mac camera. To extract 3DMM parameter, we use CoarseNet from https://github.com/Juyong/3DFace.
The code "Align.py" is to create a corresponding 3D face mesh.
To align HMD with face, we provide a code "HMDgh.gh" file. This is a grasshopper script for Rhino5. You need to download the Rhino5 and get the plug-in Grasshopper. You might need to adjust the HMD to face distance and scale of HMD.

For any inquire, please email to me at guoxian001@e.ntu.edu.sg
Please only use this data within your group, and not to share with others.

# Paper
If you feel this dataset help your research, please cite the following. 

@inproceedings{Song:2018, 
author = {Song, Guoxian and Cai, Jianfei and Cham, Tat-Jen and Zheng, Jianmin and Zhang, Juyong and Fuchs, Henry},
title = {Real-time 3D Face-Eye Performance Capture of a Person Wearing VR Headset},
booktitle = {Proceedings of the 26th ACM International Conference on Multimedia},
year = {2018},
pages = {923--931},
}
