Welcome to the nbaPlayerAndFeatureDetection wiki!

Phase 1:
Create a custom dataset and train a Yolov5 convolutional neural network to detect NBA players and other court features.  Here are results from running the trained objected detector on a YouTube video:
![image](https://user-images.githubusercontent.com/79757625/117845910-f4d93180-b24e-11eb-99b8-5d763ba48231.png)
![image](https://user-images.githubusercontent.com/79757625/117845992-07536b00-b24f-11eb-8d77-7805d1165a56.png)
![image](https://user-images.githubusercontent.com/79757625/117846276-484b7f80-b24f-11eb-8b68-5cfc91153e70.png)

Steps
- Run yolov5 on YouTube videos of NBA games
  - Output raw images from YouTube videos
- Manually label images
  - Used https://www.makesense.ai/ to label images
  - It took FOREVER to label 234 images
- Train the yolov5 classifier using Google Colab Pro to leverage a GPU
- Loop
  - Run the trained object detector on more YouTube videos of NBA games
  - Output images and labels
   - Optionally add some extra logic to output more or less of certain types of images to try to balance your dataset
  - Import to https://www.makesense.ai/
  - Manually fix labels (much quicker than manually labeling from scratch but still takes FOREVER)
  - After each iteration I added 200-400 images
- Final dataset contains 1022 labeled images

Phase 2:
Use the detected features to transform the wide-angle perspective camera view to a top-down overlay where the players and basketball can be tracked per image.
