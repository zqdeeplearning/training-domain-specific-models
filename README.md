# training-domain-specific-models
Training domain specific object detection models.

Faster-RCNN implementation is based on faster-rcnn.pytorch by jwyang. Thanks!

https://github.com/jwyang/faster-rcnn.pytorch

# Preparation

## clone repo
Lets start off by cloning this repo.

```
git clone https://github.com/kentaroy47/training-domain-specific-models.git
```

## Download models
We need to prepare Resnet101 and Resnet18 Faster-RCNN model.

```
cd training-domain-specific-models
mkdir models/
cd models
# resnet101 COCO trained model
wget https://www.dropbox.com/s/dpq6qv0efspelr3/faster_rcnn_1_10_9771.pth?dl=0
# resnet18 COCO trained model
wget TBD
cd ..
```

## download dataset
we prepared two survillance videos.
we will try to train a domain specific model based on such domain.

```
mkdir images
# download coral video
wget https://storage.googleapis.com/noscope-data/videos/coral-reef-long.mp4
mv coral-reef-long.mp4 coral.mp4

# download jackson video
wget TBD

```

## setup dataset
If the models and the video are set, we can prepare the dataset.

1. The video is converted to JPEG.
2. Res101 model generates the teacher labels.
3. The dataset is prepared in a PASCAL_VOC format for training.

This is done in a single script.

Just run:

```
python make_dataset.py
```

### shortcut..
We prepared a res101 teacher labels in the link bellow if you want to take a short cut.
