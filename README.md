## Pose Perfect

Pose Perfect is a webcam-based pose-matching game built with Python, MediaPipe, TensorFlow, OpenCV, and Pygame.  
Match the on‑screen pose within the time limit to earn points and extend your play time.

---

### Features

- **Real‑time pose detection** using MediaPipe and a trained Keras model (`model.h5`)
- **Timer & score system** with bonus time for correct poses
- **High score tracking** saved in `high_score.txt`
- **Multiple poses** with reference images and dynamic level changes
- **Simple UI** built with Pygame

---

### Requirements

- **OS**: Windows (tested)
- **Python**: **3.12.x** (very important)
- **Hardware**: Webcam with a clear view of your full body

Python 3.13+ is **not supported** by MediaPipe at the moment.  
If you use 3.13/3.14, expect import errors like `module 'mediapipe' has no attribute 'solutions'`.

---

### Project Structure

- **`Game.py`** – main game script
- **`model.h5`** – trained pose classification model
- **`labels.npy`** – pose labels corresponding to the model
- **`Background_Images/`** – background and title images
- **`Images/`** – clock, game over screens, etc.
- **`poseImages/`** – reference images for each pose
- **`Fonts/`** – custom font files
- **`high_score.txt`** – stores the best score locally

---

### Installation

#### 1. Install Python 3.12

Download and install Python 3.12 from  
`https://www.python.org/downloads/`  
Make sure you check **“Add python.exe to PATH”** during installation.

#### 2. Clone the repository

```bash
git clone https://github.com/your-username/Pose-Master.git
cd Pose-Master
```

#### 3. Create and activate a virtual environment (recommended)

```bash
py -3.12 -m venv venv
.\venv\Scripts\Activate.ps1   # PowerShell on Windows
```

If `py -3.12` doesn’t work, replace it with the full path to your Python 3.12 executable.

#### 4. Install dependencies

If you have a `requirements.txt`:

```bash
pip install -r requirements.txt
```

Or install directly:

```bash
pip install pygame opencv-python numpy mediapipe tensorflow
```

---

### Running the Game

From the project directory, with the virtual environment activated:

```bash
python Game.py
```

A window titled **“Pose Perfect”** should open and your webcam will activate.

---

### How to Play

- **Home screen**
  - Click **Start** to go to the camera/start page.
  - Click **Quit** to exit.

- **Start page**
  - Your webcam feed appears in the window.
  - You can:
    - Click **Start** to begin the game.
    - Click **Back** to return to the home screen.

- **Game page**
  - A **pose name** is shown at the bottom, with a **pose image** on the right.
  - A **countdown timer** is shown with a clock icon.
  - Match the displayed pose as accurately as you can.
  - If the model detects that your pose matches:
    - Your **score increases**.
    - You **gain extra time**.
    - A **new pose** is selected.
  - If your full body is not visible, you’ll see a warning and a hint image.

- **End screen**
  - Shows:
    - **Score**
    - **Time played**
    - **High score**
    - **Average time per move**
  - Buttons:
    - **Play Again** – start a new game
    - **Main Menu** – back to the home screen

---

### High Score

- The best score is stored in `high_score.txt`.
- You can delete or edit this file to reset the high score.
- It’s recommended to **exclude** it from Git commits (see `.gitignore`).

---

### Suggested `.gitignore`

You can create a `.gitignore` file like:

```gitignore
venv/
__pycache__/
*.pyc
.idea/
high_score.txt
HighScore.txt
```

---

### Troubleshooting

- **MediaPipe / Python version errors**
  - Make sure you are using **Python 3.12** in a virtual environment:
    - `py -3.12 -m venv venv`
    - `.\venv\Scripts\Activate.ps1`
  - Then reinstall dependencies in that environment.

- **Webcam not working**
  - Confirm your webcam works in another app.
  - Close other apps that might be using the camera.
  - Run `python Game.py` from the project folder so relative paths work.

- **Assets not found**
  - Ensure folders like `Images/`, `Background_Images/`, `poseImages/`, and `Fonts/` are present and keep the same relative paths as in the original project.

---

### License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

