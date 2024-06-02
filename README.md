<h1>Face Recognition Attendance System</h1>

This project is a Face Recognition-based Attendance System using Python. The system captures
real-time video feed from a webcam, detects faces, recognizes them using pre-trained encodings, 
and marks attendance by writing to a CSV file. The project leverages the 'face_recognition' and
'opencv' libraries for facial detection and recognition.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Functions](#functions)
- [Acknowledgements](#acknowledgements)
- [License](#license)


<h2>Installation</h2>
<h3>Prerequisites</h3>

* Python 3.6 or later<br>
* pip (Python package installer)

<h3>Libraries</h3>
Install the required libraries using pip:

``` bash

pip install opencv-python
pip install face_recognition
pip install numpy
pip install pandas
```

## Usage

1. **Clone the repository:**

    ```sh
    git clone https://github.com/yourusername/face-recognition-attendance-system.git
    cd face-recognition-attendance-system
    ```

2. **Prepare the dataset:**

    Ensure you have a folder named `IP_Project_DataBase` in the root directory containing the images of individuals to be recognized. Each image file should be named after the person in the image (e.g., `John_Doe.jpg`).

3. **Run the script:**

    ```sh
    python main.py
    ```

4. **Interact with the system:**

    The webcam will start and begin processing video frames for face recognition. Press `q` to stop the webcam feed.


## Project Structure

```plaintext
face-recognition-attendance-system/
├── IP_Project_DataBase/        # Folder containing images of individuals to be recognized
├── Attendance.csv              # CSV file where attendance will be recorded
├── main.py                     # Main script for running the face recognition attendance system
├── processed_images.pickle     # Pickle file to store encoded faces
├── README.md                   # Description file of the project
└── requirements.txt            # List of required libraries

```

## Functions

### 1. Loading and Encoding Images

The script reads images from the `IP_Project_DataBase` folder, converts them to RGB, and extracts face encodings using the `face_recognition` library. These encodings are saved to a pickle file for later use.

### 2. Real-Time Face Recognition

The script captures video frames from the webcam, resizes and converts them to RGB, and then detects and encodes faces in the frames. It compares these encodings to the stored encodings to identify individuals.

### 3. Marking Attendance

If a recognized face is detected, the `markAttendance` function logs the person's name, current time, and date in the `Attendance.csv` file. Attendance is only marked once per person per session.

### 4. Displaying Results

The script uses OpenCV to draw rectangles around detected faces in the video feed and labels them with the person's name or a "Not Authorized" message if the face is unrecognized.

## Acknowledgements

This project utilizes the following libraries:

- [OpenCV](https://opencv.org/) for real-time computer vision.
- [face_recognition](https://github.com/ageitgey/face_recognition) for face detection and recognition.
- [NumPy](https://numpy.org/) for numerical operations.
- [Pandas](https://pandas.pydata.org/) for handling CSV files.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

Feel free to contribute to this project by submitting issues or pull requests. For major changes, please open an issue first to discuss what you would like to change.

Happy coding!
