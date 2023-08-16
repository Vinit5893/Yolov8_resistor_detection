# Yolov8_resistor_detection
- Detcection of resistor as object using custom data set.


## Dataset used in the model.

1. I have trained the data set using a set of 4422 images and its corresponding yolo formatted labels.
These files can be seen at location [Yolov8_resistor_detection/train](train/)
2. The files (486 images and lables) used to validate the trained model is located at [Yolov8_resistor_detection/valid](valid/)
3. To test test the model some more images and lables are located at [Yolov8_resistor_detection/test](Yolov8_resistor_detection/test)
4. I have used the refference training model as [YOLOv8n](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8n.pt). Click the link to dirctly download.

- You can find the similar and even more data set from the website [https://universe.roboflow.com/](https://universe.roboflow.com/)

- I have also downloaded my data set from there. https://universe.roboflow.com/isha-74mjj/yolov5-u3oks/dataset/3

- Note :- I did not annotate my images i.e. I have just downloaded the per-annotated images and used the same to train my model.
    - You can choose to do it yourself and then export the lables of the images in yolo format.

## Training 
Install the requirements to train your model by this command.

        pip install ultralytics

Then run the [Train_Model_local.py](Train_Model_local.py)


This python program will get a refference weight [YOLOv8n](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8n.pt) and use it to train the model based on our custom data set.

- Indicate the path, train and val directories in the [config.yaml](config.yaml) file with all the different classes defined in the object detection (based on the number of objectes to be detected).
- We can set the number of epochs to improve the accuracy of trained model.


- Note :- This task is resource hungry so suggested to run it on gpu to reduce the load and time required to complete the training.

To solve the issue stated in the above note, I have used Google Collab to run this python program as it offers free gpu to accelerate our task. The procedure is as follows.

1. Upload all the [train](train/) and [valid](valid/) directory to the google drive and specify the [config_collab.yaml](config_collab.yaml) file with correct path.
2. Now run the [Train_model_collab.ipynb](Train_model_collab.ipynb) file to execute the training procedure.

Once the training is done we have the output of the trained data in our runs directory. We can further analyse the output and improve our model by using various techniques.

## Deploy

Now comes the fun part where we can validate our trained model using real time senarios.
I have used some [videos](videos/) to detect the presence of these resistors for which we have been training the model for.

- Run the  [predict.py](predict.py) file to validate the results based on real time application
- A bounding box should be created on the output video indicating that the object have been detected.

## Output 
- You can view the Training results at location [runs/detect/train](runs/detect/train) .
- You can view the real time output at location [videos](videos/)

### Thats all, now you have five options -
1. Enjoy your output.
2. Scratch your head as to what went wrong in the procedure in case of invalid or no detection.
3. Try to debug and figure out the potential improvements 
4. Contact me to get claifications. (Disclaimer - I am also new to this field.)
5. Change your career!!!!!

### Refference : [Youtube video - Computer vision engineer](https://www.youtube.com/watch?v=Z-65nqxUdl4&t=1848s)

# THANK YOU