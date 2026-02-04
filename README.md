🕒 Digital Clock using PyQt5

A simple Digital Clock desktop application built using Python and PyQt5.
The clock displays the current system time in HH:MM:SS AM/PM format, updates every second, and uses a modern UI with a black background and green digital-style text.

📌 Features

Real-time digital clock

Updates every second using a timer

Clean and minimal GUI

Uses PyQt5 framework

Center-aligned large digital font

AM/PM time format

🛠️ Technologies & Tools Used

Python 3

PyQt5 (GUI Framework)

Qt Core & Widgets

VS Code / PyCharm (any Python IDE)

Git & GitHub

📂 Project Structure
DigitalClock/
│
├── digital_clock.py
├── README.md
└── requirements.txt

📦 Required Libraries

Install PyQt5 before running the application:

pip install PyQt5


(Optional) requirements.txt

PyQt5

📥 Imports Explained
import sys


Provides access to system-specific parameters and functions.

Required for QApplication execution and exiting the app safely.

from PyQt5.QtWidgets import QApplication, QWidget, QLabel, QVBoxLayout


QApplication: Manages the GUI application

QWidget: Base class for GUI windows

QLabel: Displays text (used for time display)

QVBoxLayout: Aligns widgets vertically

from PyQt5.QtCore import QTimer, QTime, Qt


QTimer: Triggers time updates every second

QTime: Fetches current system time

Qt: Used for alignment and UI constants

from PyQt5.QtGui import QFont, QFontDatabase


Used for font customization (can be extended for digital fonts)

🧠 Code Explanation
1️⃣ DigitalClock Class
class DigitalClock(QWidget):


Inherits from QWidget

Represents the main clock window

2️⃣ Constructor (__init__)
def __init__(self):
    super().__init__()
    self.time_label = QLabel(self)
    self.timer = QTimer(self)
    self.initUI()


Initializes the label for displaying time

Creates a timer to update time every second

Calls initUI() to set up the interface

3️⃣ UI Setup (initUI)
self.setWindowTitle('Digital Clock')
self.setGeometry(100, 100, 200, 100)


Sets window title and size

self.time_label.setAlignment(Qt.AlignCenter)


Centers the time text

self.time_label.setStyleSheet(
    "font-size: 150px; color: hsl(111, 100%, 50%);"
)


Large font size

Bright green digital color

self.setStyleSheet("background-color: black;")


Black background for digital clock effect

4️⃣ Timer Configuration
self.timer.timeout.connect(self.update_time)
self.timer.start(1000)


Timer triggers every 1000 ms (1 second)

Calls update_time() method

5️⃣ Time Update Method
def update_time(self):
    current_time = QTime.currentTime().toString("hh:mm:ss AP")
    self.time_label.setText(current_time)


Fetches system time

Formats time as HH:MM:SS AM/PM

Updates the label

6️⃣ Application Entry Point
if __name__ == "__main__":
    app = QApplication(sys.argv)
    clock = DigitalClock()
    clock.show()
    sys.exit(app.exec_())


Creates the Qt application

Displays the digital clock window

Ensures clean exit

▶️ How to Run the Project

Clone the repository:

git clone https://github.com/your-username/digital-clock-pyqt5.git


Navigate to the project folder:

cd digital-clock-pyqt5


Install dependencies:

pip install PyQt5


Run the application:

python digital_clock.py

🚀 Future Enhancements

Custom digital font support

Date display

12/24-hour toggle

Full-screen clock mode

Alarm functionality
