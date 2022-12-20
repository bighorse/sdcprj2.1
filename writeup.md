[//]: # (Image References)

[ID_S1_EX2_0]: ./writeup_imgs/ID_S1_EX2_0.png
[ID_S1_EX2_1]: ./writeup_imgs/ID_S1_EX2_1.png
[ID_S1_EX2_2]: ./writeup_imgs/ID_S1_EX2_2.png
[ID_S1_EX2_3]: ./writeup_imgs/ID_S1_EX2_3.png
[ID_S1_EX2_4]: ./writeup_imgs/ID_S1_EX2_4.png
[ID_S1_EX2_5]: ./writeup_imgs/ID_S1_EX2_5.png
[ID_S1_EX2_6]: ./writeup_imgs/ID_S1_EX2_6.png
[ID_S1_EX2_7]: ./writeup_imgs/ID_S1_EX2_7.png
[ID_S1_EX2_8]: ./writeup_imgs/ID_S1_EX2_8.png
[ID_S1_EX2_9]: ./writeup_imgs/ID_S1_EX2_9.png
[range_image_0]: ./writeup_imgs/range_image_0.png
[range_image_87]: ./writeup_imgs/range_image_87.png
[labels_vs_detected_objects_screenshot_1]: ./writeup_imgs/labels_vs_detected_objects_screenshot_1.png

# Writeup: Track 3D-Objects Over Time

### 1. Write a short recap of the four tracking steps and what you implemented there (filter, track management, association, camera fusion). Which results did you achieve? Which part of the project was most difficult for you to complete, and why?

After completing Step 1, I observed 10 point cloud images from different angles and different frames, and found some characteristics:
 * When looking down, it can be found that LiDar has a good overall recognition effect on the car and can recognize the complete car body. ![ID_S1_EX2_0]
 * Observing from the side, it is found that LiDar's overall recognition of the car body is also very complete. ![ID_S1_EX2_1]
 * Observing closely, it is found that the lidar scans the facing part of the car body completely and clearly, while the part that cannot be seen is incomplete, which is different from when looking down (the complete car body can be recognized when looking down). ![ID_S1_EX2_2]![ID_S1_EX2_3]![ID_S1_EX2_4]![ID_S1_EX2_5]![ID_S1_EX2_6]![ID_S1_EX2_7]![ID_S1_EX2_8]![range_image_0]
 * The last feature is that the color of the laser beam in the point cloud image is related to the intensity of sunlight. If the light is strong, the laser beam is warmer. ![ID_S1_EX2_9]，![range_image_87]

After completing Step 2, I learned how to generate a BEV-map through coordinate conversion, and then get the intensity layer, height layer, and density layer, and compare the three layers to the RGB layer, so that the pre-trained model in the field of Computer Vision can be applied up.

After completing Step 3, by observing the generated objects_in_bev_labels_in_camera map, it is found that LiDar cannot recognize distant vehicles (because no point cloud is formed), but compared to the misidentification of buildings by image recognition technology, LiDar technology does not have this question.

![labels_vs_detected_objects_screenshot_1]

### 2. Do you see any benefits in camera-lidar fusion compared to lidar-only tracking (in theory and in your concrete results)? 

Obtaining 3D point clouds through LiDar, and then applying the mature Computer Vision pre-trained model, can achieve very accurate recognition of large objects such as vehicles, and its effect is better than 2D image recognition. However, lidar is not good at recognizing small objects and details of objects, such as speed limit signs, traffic lights, etc. Camera-based image recognition technology is better in these aspects, so I think camera-lidar fusion technology is very necessary.

### 3. Which challenges will a sensor fusion system face in real-life scenarios? Did you see any of these challenges in the project?

The sensor fusion system requires multiple sensors, including lidar, camera, etc., and there are more than one, so the cost will be high. In addition, because the image recognition models of lidar and camera need to be inferred separately, when doing this project, I feel that the program is very complicated, and the requirements for computing performance are also very high.

### 4. Can you think of ways to improve your tracking results in the future?

Learn the darknet and fpn_resnet models, then improve the recognition accuracy by adjusting the parameters.