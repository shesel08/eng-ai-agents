Training dataset - https://universe.roboflow.com/project/drone-object-detection-5twsu/dataset/1

Train set - 2005 Images
Valid Set - 573 Images
Test Set - 285 Images

1. Downloaded the test videos using yt-dlp.

2. Created 24 clips when drone is visible using ffmpeg. 

3. Created frames 1/5 fps which resulted in 684 frames for both test videos. 

4. After training the model, 61/684 frames had detections and were saved to /detections folder.

## Output folder
/tracked_output - This has 2 videos tracking 61 frames & 34 total track(s) spawned.