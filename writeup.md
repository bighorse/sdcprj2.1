# Writeup: Track 3D-Objects Over Time

Please use this starter template to answer the following questions:

### 1. Write a short recap of the four tracking steps and what you implemented there (filter, track management, association, camera fusion). Which results did you achieve? Which part of the project was most difficult for you to complete, and why?
完成Step 1之后，我观察了10幅不同角度不同帧的点云图，发现了一些特点：
	俯瞰时，可发现liDar对汽车的整体识别效果很好，能够识别出完整的车体。ID_S1_EX2_0.png
    侧面观察，发现liDar对车体的整体识别也非常完整。ID_S1_EX2_1.png
    近距离观察，发现liDar对面向设备的车体部分扫描的很完整很清晰，看不到的部分则不完整，这一点跟俯瞰时不同（俯瞰时可识别出完整车体）。ID_S1_EX2_2～8，range_image_0
    最后一个特点，发现点云图中激光束的颜色跟阳光强度有关，光线强，则激光束偏暖色。ID_S1_EX2_9，range_image_87
    

### 2. Do you see any benefits in camera-lidar fusion compared to lidar-only tracking (in theory and in your concrete results)? 


### 3. Which challenges will a sensor fusion system face in real-life scenarios? Did you see any of these challenges in the project?


### 4. Can you think of ways to improve your tracking results in the future?

