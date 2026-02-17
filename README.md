# CPU-IO Scheduler Simulator

<p><strong>The objective of this project is to simulate CPU and I/O scheduling procedures used by operating systems. The simulator implements multiple scheduling algorithms and allows users to analyze and compare their performance under different workloads. This project helps in understanding core operating system scheduling concepts and process lifecycle states.</strong></p>

---

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage Guide](#usage-guide)
- [Example](#example)

---

## Features

- Implementation of the following scheduling algorithms:
  - First-Come, First-Served (FCFS)
  - Shortest Job First (SJF)
  - Round Robin (RR)
  - Multilevel Feedback Queue (MLFQ)

- Generates detailed timeline logs showing process transitions during scheduling.
- Simulates the following process states:
  - NEW
  - READY
  - RUNNING
  - WAITING
  - TERMINATED

---

## Project Structure

  ## Project Structure

```
├── src/
│   └── data_structures/
│       ├── process.cpp
│       ├── process.h
│       ├── queue_node.h
│       ├── queue_util.h
│       └── queue.h
│   └── io/
│       └── reader/
│           ├── process_file_reader.cpp
│           └── process_file_reader.h
│       └── writer/
│           ├── file_writer.cpp
│           └── file_writer.h
│       ├── helper.cpp
│       └── helper.h
│   └── schedulers/
│       ├── fcfs.cpp
│       ├── fcfs.h
│       ├── mlfq.cpp
│       ├── mlfq.h
│       ├── rr.cpp
│       ├── rr.h
│       ├── scheduler.cpp
│       ├── scheduler.h
│       ├── sjf.cpp
│       └── sjf.h
│   └── timestamp/
│       ├── timestamp_interface.h
│       ├── timestamp_observer.cpp
│       ├── timestamp_observer.h
│       ├── timestamp_topic.cpp
│       ├── timestamp_topic.h
│       ├── timestamp.cpp
│       └── timestamp.h
│   └── main.cpp
├── .clang-format
├── .gitignore
├── example.csv
├── LICENSE
├── README.md
└── run.sh
```


---

## Requirements

- C++ compiler supporting C++17 (GCC / MinGW / Clang)
- Git CLI tool (or Git GUI client)

---

## Installation

1. Clone the repository:
git clone https://github.com/Manikantajagu11-hub/CPU-IO-Scheduler.git
2. Navigate to the project directory:
./run.sh example.csv
3. Or manually compile:
g++ -std=c++17 -o scheduler src/main.cpp src/data_structures/.cpp src/schedulers/.cpp src/io/.cpp src/timestamp/.cpp



---

## Usage Guide

1. Prepare a CSV file with the following format:
process_id,arrival_time,cpu_time1,cpu_time2,io_time

### Column Description

- **process_id**: Unique process identifier  
- **arrival_time**: Time when the process arrives  
- **cpu_time1**: First CPU burst duration  
- **cpu_time2**: Second CPU burst duration  
- **io_time**: I/O burst duration  

2. Run the program:
./scheduler example.csv
3. After the execution is completed, the following log files will be generated:
   ```
   ├── FCFS-Algorithm-Analysis.log
   ├── FCFS-Processes-Analysis.log
   ├── FCFS.log
   ├── MLFQ-Algorithm-Analysis.log
   ├── MLFQ-Processes-Analysis.log
   ├── MLFQ.log
   ├── RR-Algorithm-Analysis.log
   ├── RR-Processes-Analysis.log
   ├── RR.log
   ├── SJF-Algorithm-Analysis.log
   ├── SJF-Processes-Analysis.log
   └── SJF.log
   ```

## Example

**example.csv**

```
process_id,arrival_time,cpu_time1,cpu_time2,io_time
1,0,2,2,2
2,1,1,1,0
```


---

### Sample FCFS.log Output

**FCFS.log**
```
***First Come First Serve (FCFS) Scheduling Algorithm***

[Time]: 0 - 1
[Process ID]: 1, Moved from Job Queue to Ready Queue [NEW -> READY]
[Process ID]: 1, Moved from Ready Queue to Running State [READY -> RUNNING]
[Process ID]: 1, First CPU Burst Time was executed for 1 second, [Remaining First CPU Burst Time]: 1
[Time]: 1 - 2
[Process ID]: 2, Moved from Job Queue to Ready Queue [NEW -> READY]
[Process ID]: 1, First CPU Burst Time was executed for 1 second, [Remaining First CPU Burst Time]: 0
[Process ID]: 1, Moved from Running State to Waiting Queue to execute IO burst time [RUNNING -> WAITING]
[Time]: 2 - 3
[Process ID]: 2, Moved from Ready Queue to Running State [READY -> RUNNING]
[Process ID]: 1, Waited for IO resources for 1 second, [Remaining IO Burst Time]: 1
[Process ID]: 2, First CPU Burst Time was executed for 1 second, [Remaining First CPU Burst Time]: 0
[Time]: 3 - 4
[Process ID]: 1, Waited for IO resources for 1 second, [Remaining IO Burst Time]: 0
[Process ID]: 1, IO waiting time finished, Moved from Waiting Queue to Ready Queue [WAITING -> READY]
[Process ID]: 2, Second CPU Burst Time was executed for 1 second, [Remaining Second CPU Burst Time]: 0
[Process ID]: 2, was terminated [RUNNING - TERMINATED]
[Time]: 4 - 5
[Process ID]: 1, Moved from Ready Queue to Running State [READY -> RUNNING]
[Process ID]: 1, Second CPU Burst Time was executed for 1 second, [Remaining Second CPU Burst Time]: 1
[Time]: 5 - 6
[Process ID]: 1, Second CPU Burst Time was executed for 1 second, [Remaining Second CPU Burst Time]: 0
[Process ID]: 1, was terminated [RUNNING - TERMINATED]
```

**FCFS-Algorithm-Analysis.log**
```
***FCFS Algorithm Analysis***

[CPU Execution Time]: 6
[CPU Utilization Percentage]: 100
[CPU Idle Time]: 0
[Throughput]: 3
[Average Turnaround Time]: 4.5
[Average Wait Time]: 4.5
[Average Response Time]: 1

```

**FCFS-Processes-Analysis.log**

`***FCFS Process Analysis***`

| Process ID | Arrival Time | Termination Time | Response Time | Turnaround Time | Waiting Time |
|---|---|---|---|---|---|
| 2 | 1 | 4 | 2 | 3 | 3 |
| 1 | 0 | 6 | 0 | 6 | 6 |



---

## Author

**Manikanta Jagu**  
Computer Science Engineering Student  

---

## License

This project is licensed under the MIT License.