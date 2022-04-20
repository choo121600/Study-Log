```
from PyQt5.QtWidgets import QPushButton
from PyQt5.QtWidgets import *
from PyQt5.QtCore import Qt
from PyQt5.QtGui import *
from PyQt5 import uic
from PyQt5.QtCore import QTimer
from PyQt5.QtGui import QImage, QPixmap
from PyQt5.QtWidgets import QDialog, QApplication, QFileDialog
import cv2
import numpy as np
import sys
import mediapipe as mp
import csv

form_class = uic.loadUiType("./ui/new_gen.ui")[0] ###UI 경로 지정

class UIToolTab(QWidget,form_class):  ###########################화면구성
    def __init__(self, parent=None):
        super(UIToolTab, self).__init__(parent)
        self.setupUi(self)

class MainWindow(QMainWindow):
    def __init__(self, parent=None):
        super(MainWindow, self).__init__(parent)
        #self.setGeometry(0, 0, 661, 733)
        self.setFixedSize(680, 621)
        self.startUIToolTab()

    def startUIToolTab(self):  ####### 페이지 별 동작함수 구현
        self.ToolTab = UIToolTab(self)
        self.setWindowFlag(Qt.FramelessWindowHint)
        self.setWindowTitle("UIToolTab")
        self.setCentralWidget(self.ToolTab)
        self.show()

if __name__ == '__main__':
    app = QApplication(sys.argv)
    w = MainWindow()
    sys.exit(app.exec_())
```
