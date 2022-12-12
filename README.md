# Rice-Disease-Detection
The project tells us whether or not an image of a rice plant is healthy using image classification. Where I live, rice is a very important resource and a major part of our economy, so it is extremely important for us to be able to monitor the condition of the rice crops.

# The Algorithm
The algorithm was trained using the Jetson Nano using a retrained resnet18 model, the dataset consists of images of rice leaves classified under 'healthy', 'leafblight' and 'brownspot'. To test the model, you can use the imagenet.py program to input a test image and outputs the determined label the image is under.

# Running this project
0. Follow the setup of the docker container on and ensure you have everything set up. 
- https://github.com/dusty-nv/jetson-inference/blob/master/docs/aux-docker.md 
- https://github.com/dusty-nv/jetson-inference/blob/master/docs/building-repo-2.md

1. Ensure that you have the model (resnet18.onnx) and the dataset provided here (or you may use your own dataset) downloaded onto the Jetson Nano within the jetson-inference/python/training/classification/models directory for the model and jetson-inference/python/training/classification/data for the dataset.
2. Go into the docker container (cd into jetson-inference and enter 'docker/run.sh' then cd into jetson-inference/python/training/classification.
3. 
