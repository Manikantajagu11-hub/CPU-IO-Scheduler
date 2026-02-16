# CPU-IO Scheduling Simulator

## 📌 Project Overview
CPU-IO Scheduling Simulator is a C++ project that simulates how an operating system schedules processes with CPU and I/O bursts.  
The simulator implements multiple scheduling algorithms and generates detailed execution logs and performance analysis reports.

This project helps in understanding real-world OS scheduling concepts such as process arrival, CPU bursts, I/O waiting, and queue management.

---

## ⚙️ Supported Scheduling Algorithms

The simulator supports the following CPU scheduling algorithms:

- **FCFS (First Come First Serve)**
- **SJF (Shortest Job First)**
- **Round Robin (RR)**
- **Multi-Level Feedback Queue (MLFQ)**

---

## 📂 Input File Format

The program takes a CSV file as input with **5 columns**:
process_id,arrival_time,cpu_time1,cpu_time2,io_time
1,0,2,2,2
2,1,1,1,0


### Column Explanation

| Column Name   | Description |
|--------------|-------------|
| process_id   | Unique ID of the process |
| arrival_time | Time when process enters the system |
| cpu_time1    | First CPU burst time |
| cpu_time2    | Second CPU burst time |
| io_time      | I/O burst time |

---

## ▶️ How to Compile and Run

### 1️⃣ Compile the Source Code

```bash
g++ -std=c++17 -o scheduler src/main.cpp src/data_structures/*.cpp src/schedulers/*.cpp src/io/*.cpp src/timestamp/*.cpp

Run the Program

./scheduler example.csv

You can also use your own CSV file:

./scheduler test1.csv

📄 Output Files Generated

After execution, the simulator generates the following files:


Scheduling Logs

FCFS.log

SJF.log

RR.log

MLFQ.log

Performance Analysis Reports

FCFS-Algorithm-Analysis.log

SJF-Algorithm-Analysis.log

RR-Algorithm-Analysis.log

MLFQ-Algorithm-Analysis.log

These files contain scheduling timelines, CPU execution details, and performance metrics

🛠 Technologies Used

C++ (GCC Compiler)

STL (Standard Template Library)

Git & GitHub

CSV File Processing

Features

Simulates real operating system CPU scheduling behavior

Handles multiple CPU and I/O burst cycles

Modular scheduler implementation using object-oriented programming

Automatically generates execution logs and algorithm analysis reports

Easy CSV-based process input

Future Enhancements

Add Priority Scheduling Algorithm

Gantt Chart Visualization

GUI Interface for Scheduling Simulation

Calculation of Average Waiting Time and Turnaround Time

Support for more CPU burst cycles

Author

Manikanta Jagu
Computer Science Student
https://github.com/Manikantajagu11-hub/CPU-IO-Scheduler


