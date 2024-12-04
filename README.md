# Mask-RCNN-using-Dtectron2-
The Detectron 2 MaskRCNN implementation for the PanNuke Dataset.
(https://warwick.ac.uk/fac/cross_fac/tia/data/pannuke)).

# Dataset information
The dataset consists of 481 visual fields, of which 312 are randomly sampled from more than 20K whole slide images at different magnifications, from multiple data sources. In total the dataset contains 205,343 labeled nuclei, each with an instance segmentation mask.

The ground truth annotation samples are shown in the figure below:
![image](https://github.com/user-attachments/assets/4a0095b3-c697-4646-a54b-4f972f9446e8)
 Each instance of the 5 cell classes are annotated separately (Red: Neoplastic; Green: Inflammatory; Dark Blue: Connective; Yellow: Dead; Orange: Epithelial)

The MaskRCNN instance segmentation model was developed using Facebook AI reseach's (FAIR) Detectron 2 framework.
![image](https://github.com/user-attachments/assets/4e3c5be6-b6ba-4aeb-b231-0ffc185dfa45)

The 'Pannuke_dataset' folder contains the original dataset with seperate sub-folders for images and masks. The mask folder contains sub-folders for each cell type present under which each cell instance is given as a separate mask image.

# Data Preprocessing
The 'pannuke_pre_processing.ipynb' notebook is used to pre-process and convert the original dataset in a structure that detectron 2 expects.

# Data Training and Inference
On succesfully running the pre-processing notebook, a folder called 'final_pannule_dataset' is created along with the train.json and val.json files which are in coco format.

The created folder and json annotation files can be now used to train the MaskRCNN model using the 'pannuke_maskrcnn_training.ipynb' notebook. Inference is done in the same notebook.
