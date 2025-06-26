import sys
from PyQt5.QtWidgets import QApplication
from ui.login_window import LoginWindow
from ui.main_window import MainWindow

def main():
    app = QApplication(sys.argv)

    main_win = None  # объявляем переменную в области функции

    def start_main():
        nonlocal main_win
        main_win = MainWindow()
        main_win.show()

    login_win = LoginWindow(on_success=start_main)
    login_win.show()

    sys.exit(app.exec_())

if __name__ == "__main__":
    main()
