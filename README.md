# Hand Gesture Calculator

This project implements a hand gesture-based calculator using OpenCV and the cvzone library. The application detects hand gestures via a webcam and uses them to interact with a virtual calculator displayed on the screen.

## Requirements

Before running the project, ensure you have the following dependencies installed:

- Python 3.x
- OpenCV
- cvzone
- Mediapipe (required by cvzone)

You can install the necessary libraries using pip:

```bash
pip install opencv-python-headless cvzone mediapipe
```

## How It Works

### Hand Detection

The project uses the `HandDetector` module from the `cvzone` library to detect hands and track finger positions. The hand landmarks are used to determine the distance between specific fingers (index and middle) to detect clicks.

### Buttons

The calculator buttons are implemented using the `Button` class. Each button has a position, size, and value. The `draw` method displays the button on the screen, and the `checkClick` method checks if a button has been clicked based on finger positions.

### Calculator Logic

The calculator supports basic arithmetic operations: addition, subtraction, multiplication, and division. The equation is built incrementally as buttons are clicked and evaluated when the equals (`=`) button is pressed.

## Usage

1. **Running the Code**

   Run the script using Python:

   ```bash
   python hand_gesture_calculator.py
   ```

2. **Interacting with the Calculator**

   - Use your webcam to display your hand.
   - Move your index finger close to the middle finger to simulate a click.
   - The calculator will detect the click and perform the corresponding action.
   - Press 'c' on your keyboard to clear the current equation.

## Code Explanation

### `Button` Class

- `__init__(self, pos, width, height, value)`: Initializes the button with position, size, and value.
- `draw(self, img)`: Draws the button on the provided image.
- `checkClick(self, x, y)`: Checks if the button is clicked based on the provided x and y coordinates.

### Main Script

- **Button Initialization**: Creates a grid of buttons for the calculator.
- **Webcam Capture**: Captures frames from the webcam and flips them for a mirror effect.
- **Hand Detection**: Detects hands and tracks finger positions using `HandDetector`.
- **Button Interaction**: Checks for button clicks and updates the equation accordingly.
- **Equation Evaluation**: Evaluates the equation when the equals (`=`) button is clicked.
- **Display**: Displays the calculator interface and the result on the screen.

## Notes

- Ensure your webcam is working properly before running the script.
- The script uses `cv2.VideoCapture(0)` to access the default webcam. Modify the parameter if you have multiple cameras.

## License

This project is licensed under the MIT License. Feel free to use and modify it as per your requirements.

## Acknowledgements

- [OpenCV](https://opencv.org/)
- [cvzone](https://github.com/cvzone/cvzone)
- [Mediapipe](https://mediapipe.dev/)

---

This README provides an overview of the project, setup instructions, and a brief explanation of the code.
