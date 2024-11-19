FOOTBALL ANALYSIS - TEAM & PLAYER SKILL TRACKER
https://github.com/user-attachments/assets/186fb763-caea-46a0-ad10-7499ca4eef07

I worked on a Football Analysis System that focuses on advanced computer vision techniques to analyze football match videos. The goal is to track players and the ball, differentiate teams, detect key positions on the pitch, and represent all this in a tactical radar view for spatial analysis. This is useful for coaches, analysts, and fans to better understand match dynamics.

I used a variety of advanced tools and libraries:
● YOLO v8x: For real-time object detection to track players and the ball.
● UMAP: For dimensionality reduction, enabling team differentiation based on features
like color.
● K-Means Clustering: To separate clusters of players, referees, and goalkeepers.
● Keypoint Detection: For identifying important pitch features such as corner lines,
the center circle, and goal areas.
● Homography Matrix: To project the detected features onto a top-down radar-like
view of the pitch.
● Visualization tools like Supervision Bounding Boxes, Ellipse Annotators, and
labeled frames were used to provide clear insights.

The workflow is as follows:
1. Input: A video of match highlights is provided.
2. Object Detection: YOLO v8x detects players, the ball, and referees. We set
parameters like:
○ Batches and Epochs: To train the model on detecting these objects.
○ Image Size (imgsz): For scaling input images.
○ Confidence Threshold: To filter predictions with low reliability.
3. Dimensionality Reduction: UMAP is applied to reduce features and separate players based on team colors.
4. Clustering: K-means clustering groups players, referees, and goalkeepers into distinct categories.
5. Keypoint Detection: Critical pitch lines (like the goal line, center circle, and penalty area) are identified using line detection techniques.
6. Homography Application: The detected points are transformed into a top-down tactical view.
7. Output: The radar view shows players as dots with spatial and ball possession analysis for better tactical insights.

several challenges:
● Handling occlusions: Players often overlap, making object detection tricky.
● Lighting variations: Videos had uneven lighting, affecting detection quality.
● Pitch variations: Different stadiums have varying markings and perspectives,
requiring robust homography calibration.
● Keypoint accuracy: Detecting small pitch lines precisely in complex scenes was
tough.
● Real-time Processing: Ensuring the system works efficiently on videos with
thousands of frames.

The system successfully:
● Differentiated teams and referees using color-based embeddings and clustering.
● Provided a real-time top-down radar view with accurate player and ball positions.
● Detected pitch features like corner lines, the center circle, and goal lines with high
precision.
● Delivered meaningful spatial analytics, like ball territory and player positions, which
are invaluable for tactical planning.

Uniqueness:
The combination of object detection, dimensionality reduction, and clustering for team separation is innovative. Additionally:
   
● The keypoint detection and homography application enable a top-down tactical radar view that is uncommon in typical sports analysis systems.
● The system doesn’t just detect but provides real-time spatial analysis of the match, making it practical for live match analysis.
