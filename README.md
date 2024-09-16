# Emotion_Based_Music_Recommendation_System

>>MELODORA aims to create a personalized music recommendation system using real-time emotion detection. The system captures a user's facial expression through the webcam, determines their emotional state, and recommends a playlist of songs that match their mood using pre-selected data from Spotify or predefined CSV files containing song metadata. Here's a breakdown of how each component works:

Components of the Project
Emotion Detection (Python, OpenCV, TensorFlow, and Haar Cascade):

The emotion detection system uses a pre-trained convolutional neural network (CNN) model (model.h5), which takes in real-time video frames from the user's webcam.
Haar Cascade (haarcascade_frontalface_default.xml) is used to detect and extract the face from each video frame.
The extracted face is converted to grayscale and resized to a 48x48 pixel image, which is then passed through the CNN model to predict the user's current emotional state (angry, happy, sad, etc.).
Depending on the predicted emotion, the system refers to predefined CSV files containing songs labeled for each emotion (e.g., "songs/angry.csv" for anger) and displays a list of songs.
Music Recommendation System:

Based on the detected emotion, the system pulls music data from CSV files that contain song names, albums, artists, and links to the song on platforms like Spotify.
These CSV files are organized such that each emotion has its own corresponding file containing relevant songs.
Real-Time Video Capture (OpenCV and Python):

OpenCV captures real-time video using the user's webcam. This is achieved through cv2.VideoCapture().
The captured frames are processed to detect faces and predict emotions in real-time.
The VideoCamera class handles the real-time streaming and pauses emotion prediction temporarily after each detection to avoid rapid switching.
User Interface (HTML, CSS, Bootstrap, and jQuery):

The HTML page provides the user interface where the user can see the real-time facial recognition feed and the recommended songs.
Bootstrap is used for styling, providing a clean and responsive layout for the web page.
The video feed is displayed on one side of the interface, and the recommended songs are shown on the other side, making the interface intuitive and interactive.
The result area dynamically updates with song recommendations as emotions are detected and processed in real-time.


>>Flow of the System:

The user opens the webpage and gives access to the webcam. The video feed starts, and the system captures live footage of the user’s face.
Face Detection and Emotion Prediction:

The face detection algorithm (Haar Cascade) detects the user’s face from the video feed.
The face is processed and passed through the pre-trained CNN model to detect the user's current emotion.
Music Recommendation:

Based on the detected emotion, the system reads from the appropriate CSV file to retrieve a list of recommended songs.
The songs are displayed in a table with details such as the song name, album, artist, and a clickable link to the song on Spotify or other platforms.
