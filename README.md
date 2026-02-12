# Dormitory Management System (IoT Dormitories)

A console-based C++ application for managing student dormitory assignments. Developed as a group project for the Department of Computer Science, Hawassa University.

---

## 📋 Overview

The Dormitory Management System allows administrators to:

- Store student records (name, ID, gender, department, CGPA)
- Assign dorm rooms automatically either by name or by CGPA
- Display, update, find, and delete student information
- View dormitory occupancy and summary statistics
- Display information about the development team

All data is persistently stored in a binary file (`newstuds.txt`).

---

## ✨ Features

| #  | Feature              | Description                                                                         |
|----|----------------------|-------------------------------------------------------------------------------------|
| 1  | Display Students     | List all registered students with their current dorm assignment status               |
| 2  | Update Student       | Modify any field (name, ID, gender, department, CGPA) of a student                  |
| 3  | Insert Student       | Add one or more new students to the system                                          |
| 4  | Find Student         | Search for a student by name or ID                                                  |
| 5  | Assign by Name       | Sort students alphabetically and assign room numbers (2 per room) by gender         |
| 6  | Assign by CGPA       | Sort students by CGPA (ascending) and assign room numbers (2 per room) by gender    |
| 7  | Display Dorms        | Show which students are assigned to which rooms in male and female blocks           |
| 8  | Delete Student       | Remove a student record after confirmation                                          |
| 9  | Summary              | Show total student count and gender distribution                                    |
| 10 | About                | Display development team information                                                |

---

## 🛠 Technologies Used

- Language: C++ (C++11/14)
- I/O: Console input/output, binary file handling (`fstream`)
- Platform: Windows (`conio.h` for `getch()`)
- Compiler: Tested with MinGW GCC and Visual Studio

---

## 🚀 Installation and Compilation

### Prerequisites

- A C++ compiler (e.g., GCC, MinGW, MSVC)
- Windows OS (due to `conio.h` and `system("cls")`)

### Steps

1. Clone or download the source file `dormitory_management_group4.cpp`.
2. Compile the program.  
   Example with MinGW:
   ```bash
   g++ dormitory_management_group4.cpp -o dormitory.exe
   ```
3. Run the executable:
   ```bash
   ./dormitory.exe
   ```

The program will automatically create `newstuds.txt` in the same directory upon first use.

---

## 📖 Usage

1. Launch the program. Press any key (except `x`) to enter the main menu.
2. Navigate the menu by entering the corresponding number.
3. Follow on-screen prompts to perform actions.
4. Use getch() – press any key to continue after most operations.
5. To exit, press any key other than 1–10 at the main menu.

### Important Notes

- Gender must be entered as `male` or `female` (case-insensitive; first letter capitalized automatically).
- Room assignment:
  - Students with `roomnum = 0` are unassigned.
  - Assignment fills rooms in order (room 1, 2, 3, …) with two students per room.
  - Assignments are destructive – they overwrite previous room assignments.
- Binary file: `newstuds.txt` is not human-readable; always use the program to view or modify data.

---

## 📁 File Structure

```text
project-folder/
├── dormitory_management_group4.cpp   # Main source code
├── newstuds.txt                      # Binary student database (auto-generated)
└── README.md                         # This file
```

Note: `newstuds.txt` is created/overwritten by the program.  
It is recommended to keep backups before performing assignments.

---

## ⚠️ Known Limitations

- String comparison: Uses `==` on `char[]` vs `string` – may fail to find records. Prefer `strcmp()` or store as `std::string`.
- File I/O: Binary reading/writing of plain structs is non-portable across compilers/platforms (due to padding, endianness).
- Input validation: Minimal; entering wrong data types may cause infinite loops.
- Windows only: Relies on `conio.h` and `system("cls")`.
- Assignment logic: Does not check room capacity when reassigning; always resets all assignments.
- CGPA sorting: Compares CGPA as strings, not numerically (e.g., "9.5" > "10.0" as string).

> These limitations are noted as part of the educational scope of the project.

---

## 📄 License

This project is developed for academic purposes and is not intended for production use. No formal license is applied.

---

## 🙏 Acknowledgments

Special thanks to course instructors and Hawassa University for providing the opportunity to work on this project.

---

Thank you for using IoT Dormitories Management System!

> Note:  
> Never use `#` at the beginning of a line unless you intend to start a Markdown heading!
