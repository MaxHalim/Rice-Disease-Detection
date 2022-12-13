# Rice-Disease-Detection
The project tells us whether or not an image of a rice plant is healthy using image classification. Where I live, rice is a very important resource and a major part of our economy, so it is extremely important for us to be able to monitor the condition of the rice crops.
![image](https://user-images.githubusercontent.com/111213472/207396617-33814b67-26e1-46c1-ba75-b81f0f5b369d.png)


# The Algorithm
The algorithm was trained using the Jetson Nano using a retrained resnet18 model, the dataset consists of images of rice leaves classified under 'healthy', 'leafblight' and 'brownspot'. To test the model, you can use the imagenet.py program to input a test image and outputs the determined label the image is under.




# Running this project
0. Follow the setup of the docker container on and ensure you have everything set up. 
- https://github.com/dusty-nv/jetson-inference/blob/master/docs/aux-docker.md 
- https://github.com/dusty-nv/jetson-inference/blob/master/docs/building-repo-2.md

1. Ensure that you have the model (resnet18.onnx) and the dataset provided here (or you may use your own dataset) downloaded onto the Jetson Nano within the jetson-inference/python/training/classification/models directory for the model and jetson-inference/python/training/classification/data for the dataset.

2. Go into the docker container (cd into jetson-inference and enter 'docker/run.sh' then cd into jetson-inference/python/training/classification.

3. ls into models just to check if your model is actually there

![image](https://user-images.githubusercontent.com/111213472/207396899-0b4f50fd-1c27-47b9-9592-853d864c4d25.png)
 
4. Run this command to test for one image - imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/leafblight/DSC_0400.jpg rice.jpg - The directory test/leafblight/DSC_0400.jpg can be changed to whichever directory you want.
- This command will run the imagenet program and will input an image of your choice and then will output the image and it's determined group. You should be able to find a file named 'rice.jpg' or whatever else you chose to name it.
![image](https://user-images.githubusercontent.com/111213472/207397185-98e62b75-7710-4152-8b7e-c508741f5fab.png)
![image](https://user-images.githubusercontent.com/111213472/207397421-c54a0406-e21b-4c8f-b069-3799474b7ef9.png)


5. To test the rest of the dataset, run imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/<Category 1 Name> $DATASET/test_output_<Category 1 Name>



Here is a link to my [Demonstration Video](https://youtu.be/rDJ6o25FVDo).
