#Run file 2151013078_NguyenPhuQuy_OPIXray.ipynb on colab

Training
change root to DOAM

 cd DOAM
modify OPIXray_ROOT in data/OPIXray.py :

 OPIXray_ROOT = 'OPIXray_Dataset/train/'    # path to trainset of OPIXray Dataset
run train.py

 python train.py --image_sets 'OPIXray_Dataset/train/train_knife.txt' --transfer './weights/ssd300_mAP_77.43_v2.pth' --save_folder './checkpoints'
--save_folder: the path to save the checkpoint while training.

--dataset_root: the path to the training dataset.

--image_sets: the path to a TXT file that saves all the picture names used for training.

--transfer: indicates the path to SSD pre-trained weight(available at here).

Notes: The model can converge after 60 ~ 80 epoch training, and long-time training will lead to over fitting.
Testing
change root to DOAM

 cd DOAM
modify OPIXray_ROOT in data/OPIXray.py :

 OPIXray_ROOT = "OPIXray_Dataset/test/"    # path to testset of OPIXray Dataset
run test.py

 python test.py --imagesetfile 'OPIXray_Dataset/test/test_knife.txt' --trained_model './weights/DOAM.pth' 
--imagesetfile: the path to a TXT file that saves all the picture names used for testing.
test_knife.txt: total testset
test_knife-1.txt: occlusion level 1 (no or slight occlusion).
test_knife-2.txt: occlusion level 2 (partial occlusion).
test_knife-3.txt: occlusion level 3 (severe or full occlusion).
our model is available at here, password is 2abm



