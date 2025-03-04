# Image_Processing
# Video File drive link = https://drive.google.com/file/d/154AeElB_v5F_AJsDmPdAVFGXHtTt9WQN/view?usp=sharing

# Video Droplet Analysis Pipeline

This project processes a video file to analyze droplet behavior through several image processing steps. The pipeline is designed to crop the video, extract and save images, detect and count droplet releases at various stages, perform edge detection and segmentation, and finally calculate the area of each droplet at different stages.

# Overview

# *The pipeline consists of the following steps:*

# Video Cropping
Input: A video file provided via the drive link.
Process: The video is cropped into individual frames using the code in the crop_images.py file, which is called by the main cropping script.
Output: Cropped frames are saved using the save_cropped_images.py script.
# Droplet Release Analysis
Counting Droplets: The droplet_release.py file analyzes 20 frames for each stage, with a gap of 300 frames between stages, to count the number of droplets releasing.
Stage Saving: The save_start_end_frames.py script extracts the starting and ending frames for each droplet release stage, which are later used to determine the percentage reduction in a single droplet’s size.
# Edge Detection and Contouring
Canny Edge Detection: The canny_edge_detection.py file applies Canny edge detection to verify if the droplet contours are being detected properly.
Reflection Adjustment: If reflections interfere with the contouring process, adjust the images manually using image or pixel editing software.
# Segment Contouring:
The segment_contouring.py script is used to assess and improve the quality of the droplet contours.
The cropped_segment_contouring.py file is then used to fine-tune the contour details after the initial segmentation.
# Droplet Area Calculation
Area Measurement: The droplet_area_calculation.py file calculates the area of a single droplet from the saved starting and ending images for each stage. This data is used to compute the percentage reduction in droplet size over time.

# File Structure

*video_file.*
The original video file (download from the provided drive link).
crop_video.py
Main script to initiate video cropping.
crop_images.py
Module responsible for cropping frames from the video.
save_cropped_images.py
Code that saves the cropped images to a designated directory.
droplet_release.py
Script to detect and count droplet releases across stages (20 frames per stage with a 300-frame gap).
save_start_end_frames.py
Code to save the first and last frames of each droplet release stage.
canny_edge_detection.py
Applies Canny edge detection to ensure proper contouring of droplets.
segment_contouring.py
Script to verify and refine droplet contouring through segmentation.
cropped_segment_contouring.py
Module to adjust detailed contouring after segmentation.
droplet_area_calculation.py
Calculates the area of each droplet at the beginning and end of each stage.
Installation & Dependencies

# *The project requires Python 3.x and the following libraries:*

OpenCV
NumPy
Matplotlib
Install the required dependencies using pip:

pip install opencv-python numpy matplotlib
How to Run the Pipeline

Download the Video:
Download the video file from the provided drive link and place it in the project directory.
Crop the Video:
Run crop_video.py to crop the video into frames. This process calls crop_images.py internally.
Save Cropped Images:
The cropped frames are saved automatically via the save_cropped_images.py script.
Analyze Droplet Release:
Execute droplet_release.py to count the number of droplets releasing. This script processes 20 frames per stage, with a 300-frame interval between stages.
Save Stage Frames:
Run save_start_end_frames.py to save the starting and ending frames for each droplet release stage. These images help calculate the reduction in droplet size.
Edge Detection:
Run canny_edge_detection.py to apply edge detection and verify that the droplet contours are being captured properly.
Tip: If reflections are disrupting the contours, adjust the images using your preferred image processing software.
Segment Contouring:
Run segment_contouring.py to refine the contours.
Use cropped_segment_contouring.py for further adjustments if necessary, ensuring detailed and accurate contouring.
Calculate Droplet Area:
Finally, run droplet_area_calculation.py to measure the area of each droplet at the beginning and end of each stage. Use these values to determine the percentage reduction in droplet size.
Expected Results

Cropped Frames: Saved images from the video.
Droplet Counts: Number of droplets detected in 20 frames per stage.
Stage Images: Saved starting and ending frames for each stage.
Edge-Detected Images: Processed images showing droplet contours.
Segmented Contours: Refined images after segmentation.
Area Calculations: Data on the area of droplets, enabling analysis of size reduction over the stages.
Troubleshooting

*Reflection Issues:*
If the droplet contours are not clear due to reflections, adjust the brightness/contrast using any image editing software before running edge detection again.

*Script Errors:*
Ensure all dependencies are installed and file paths are correctly configured.
Contributing



