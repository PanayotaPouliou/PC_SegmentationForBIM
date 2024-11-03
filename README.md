# PC_SegmentationForBIM
This repository provides a comprehensive pipeline for segmenting 3D point cloud data of buildings to identify key architectural elements: walls, roofs, and floors. Utilizing deep learning, this model allows for accurate segmentation, making it easier to analyze and understand building structures from point cloud data.

# **Dataset**
The model was trained using the "Annotated point clouds of buildings: a segmented dataset of single-family houses" dataset, which can be accesed here: [Dataset](https://data.mendeley.com/datasets/3thtp7mc6z/2). The dataset contains 2.904 geometries of single-family houses in the form of annotated Point Clouds, and was developed in order to train 3D Generative Adversarial Networks with architecturally relevant data. More specificaly the geometries are segmented within 3 classes: wall, roof, floor. The points of the point clouds are saved in .pts files while their labels are saved in .seg files.

DOI: 10.17632/3thtp7mc6z.2
URL ID: [https://data.mendeley.com/datasets/3thtp7mc6z](https://data.mendeley.com/datasets/3thtp7mc6z)
AUTHOR(S): Pouliou, Panayota; Horvath, Anca-Simona; Palamas, George

PUBLISHER(S)
Mendeley Data

# **Training**
For the training a learning rate schedule that decays the initial learning rate by half every 20 epochs was used. In this example, we use 60 epochs.
You can download the pre-trainde model [here](https://drive.google.com/drive/folders/1mDqX4-oOtAMqLNulawHCt-rX47Rv-ARq?usp=sharing] 

# **Validation**

![LOSS](https://github.com/PanayotaPouliou/PC_SegmentationForBIM/blob/main/plots/loss_accuracy.png)


## Visual inspection of the models performanse

![INSPECTION](https://github.com/PanayotaPouliou/PC_SegmentationForBIM/blob/main/plots/Visual_inspection.png)

### Visualization with the missclassified points within a sample point cloud

![MISSCLASS](https://github.com/PanayotaPouliou/PC_SegmentationForBIM/blob/main/plots/missclassified_points.png)


# **mIoU**

The calculated mean Intersection over Union (mIoU) of approximately 0.802 indicates that our point cloud segmentation model performs well overall, effectively capturing the spatial characteristics of the different classes in the dataset. This score suggests that the model achieves a good balance between precision and recall across various classes.

However, examining the IoU scores per class reveals some important insights.

The first class (rood) demonstrates an IoU of approximately 0.804, reflecting a strong performance in segmenting this class and suggesting that the model effectively identifies and delineates its boundaries. The second class (wall), with an IoU of around 0.880, is the best-performing class, indicating that the model excels in recognizing and segmenting this particular category, potentially due to clearer features or more substantial training data associated with it.

In contrast, the third class (floor) scores an IoU of about 0.720, which, while still reasonable, suggests some challenges in accurately predicting this class. This lower score could indicate that the model struggles with the variability of the fourth class or that it may require more targeted training data or further tuning to improve its segmentation accuracy. Overall, while the model shows promising results, the variation in IoU scores highlights areas for potential improvement, especially for the fourth class and the need to ensure all classes are represented in both training and evaluation datasets.

![miou](https://github.com/PanayotaPouliou/PC_SegmentationForBIM/blob/main/plots/mIoU_per_class.png)



