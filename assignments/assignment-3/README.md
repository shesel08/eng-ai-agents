Training dataset - https://universe.roboflow.com/project/drone-object-detection-5twsu/dataset/1

Train set - 2005 Images
Valid Set - 573 Images
Test Set - 285 Images

1. Downloaded the test videos using yt-dlp.

2. Created 24 clips when drone is visible using ffmpeg. 

3. Created frames 1/5 fps which resulted in 684 frames for both test videos. 

4. After training the model, 617/684 frames had detections and were saved to /detections folder.

## Experiments
With yolo8 model - 61 detections (notebook - assignment_3_yolo8.ipynb)
With yolo26 model - 172 detections (notebook - assignment_3_yolo26.ipynb)
With RT-DETR model - 617 detections (notebook - assignment_3_RT_DETR.ipynb, output and detections folder correspond to this model)

## Output folder
/output - This has 2 videos tracking 617 frames & 553 total track(s) spawned.