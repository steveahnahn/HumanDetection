# HumanDetection

Python script that searches through files/directories that contains images and videos and runs YOLOv4 Object Detection Algorithm to detect if the files contain any humans. Saves a snapshot of the positive detections and logs a file of all detections into a new directory.

If a consistent feed of images or videos are fed in through collected surveillance and any humans are positively detected, an option to be notified through SMS using Twilio or Email are available.

## YOLOv4 OpenCV
'You Only Look Once' ML model is CPU intensive, using the --tiny_yolo flag will give the option to run a smaller and faster model for quick processing at the cost of accuracy.

The number of optional flags:
1. '--twilio' flag gives the option to be notified by SMS through Twilio when an image or video frame contains a positive hit of a human
2. '--email' flag gives the option to be notified by Email when an image or video frmae contains a positive hit of a human.
  - Both email and SMS notifications need to be pre-configured before functionality works.
3. '--continuous' flag pertains to video files where the entire clip will be examined for human detections and will not stop at the first occurrence.
4. '--frames' flag will give the option to change the frame rate at which the detection is run on video files. The higher "nth frame", the less frames it will examine, thereby increasing speed but lowering accuracy
5. '--confidence' flag will adjust the confidence threshold that that controls the detection alert (1-99). Lowering confidence increases chance for false positives.


## Requirements
At the time of creation Python 3.7 or less works in tandem with Tensorflow, Python 3.8 compatability is not available.
- tensorflow
- cvlib
- opencv-python
- twilio
