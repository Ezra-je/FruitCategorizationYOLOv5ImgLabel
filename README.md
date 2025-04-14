# Fine-Grained Fruit Categorization Utilizing Optimized YOLOv5 Inference on Extensively Annotated Image Sets.

Folder Labeling == Fruit Folder

Our folder labeling is still separate, let's combine it into one first.

=====
1. Place the Fruit folder into yolov5-masta/dataset/
2. Create a process.py file inside the Fruit folder (adjust path_data, file_train, file_test)
3. cd into the Fruit folder
4. run python process.py (to get the test and train txt files)
5. create a yaml file in yolov5-master/data (copy an existing yaml file, then adjust it to our folder labeling)
6. run python train.py --img 416 --data Fruit.yaml --batch 8 --epoch 50 --weights yolov5s.pt (yolov5n, yolov5s, yolov5m)
7. check the training results in yolov5-master/runs/train/ (just check, whether it succeeded or not)
8. run python val.py --data Fruit.yaml --weights runs/train/exp2/weights/best.pt (to get the val folder in yolov5-master\runs)
9. create a folder in yolov5-master/data/ (the folder name is free, testfruit for example)
10. fill the testfruit folder with images to be detected
11. run python detect.py --img 416 --source data/testfruit --weights runs/train/exp2/weights/best.pt --conf-thres 0.4 --save-txt
12. check the detection results, usually in yolov5-masta\runs\detect\
=====

--source (location of the testfruit folder)
--weights (location of the weights, choose best.pt)
