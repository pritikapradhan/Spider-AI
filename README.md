# Spider AI

This project uses artificial intelligence to tell the user what type of spider is being shown. There are 15 different types of spiders the program is trained to recognize: a black widow, blue tarantula, etc. I made this program because I strongly dislike spiders but also want to know what kind I would be dealing with. Using the 15 most common spiders makes the AI very helpful to me.


## The Algorithm

I retrained an image classification model, resent18, with a dataset of different spider species. When it is used, it uses imagenet.py to classify a given image of a spider.

## Running this project

1. Have the jetson inference library downloaded and python3.
2. Login into your nano.
3. The dataset I used was https://www.kaggle.com/datasets/gpiosenka/yikes-spiders-15-species so download and unzip it in jetson-inference/python/training/classification
4. Navigate back to the jetson-inference directory and run the docker by using the docker/run.sh command.
5. To train the program, run python3 train.py --model-dir=models/spiders data/spiders from inside the docker.
6. Once it is done traning, you can set up the program with NET=models/spiders and DATASET=data/spiders and finally run imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/spiders/1.jpg black_widow.jpg to test an image.
7. It should show the image and the class it belongs, with numbers 0-14 to correspond to the species as they are listed.

[View a video explanation here](video link)# Spider-AI
