# 🏦 Advanced Multithreaded Banking System Simulator

## 🌟 Overview

A **real-time, multithreaded banking system simulator** developed in **C++** using **POSIX threads**.  
The simulator emulates OS-level resource allocation, transaction scheduling, synchronization, error detection, and **secure event logging**.

Key system features include:
- Token-based security
- VIP customer prioritization
- Simulated business hours
- Dynamic resource management
- Mutex- and semaphore-based synchronization

---

## 👥 Team Members

| Name            | Contact                                      |
|------------------|----------------------------------------------|
| **Ghulam Qadir** | 📧 gqitspecialist@gmail.com <br> 🔗 [LinkedIn](https://www.linkedin.com/in/ghulam-qadir-07a982365) |
| **Noor Malik**   | 🔗 [LinkedIn](https://www.linkedin.com/in/noormalik56500) |
| **Ishrat Ali**   | —                                            |
| **Muqeem Ahmed** | —                                            |

---

## 🧠 Project Goals

The system simulates a working banking environment where:

- Multiple transactions are executed **concurrently**
- Resources such as **ATMs**, **tellers**, and **tokens** are allocated **dynamically**
- **Customer types** (e.g., VIP, clearance-needed) affect execution priority
- **External disruptions** like fraud, overload, or network delays impact flow
- **Thread synchronization** is managed via `mutex` and `semaphore` mechanisms

---

## 🔧 Technologies Used

| Feature                  | Implementation Details                            |
|--------------------------|----------------------------------------------------|
| **Language**             | C++ with `pthread.h`, `semaphore.h`               |
| **Threads**              | POSIX Threads (`pthreads`)                        |
| **Synchronization**      | `pthread_mutex_t` and semaphores                 |
| **Dynamic Resources**    | ATMs, Tellers, Tokens using LRU strategy         |
| **Transaction Priorities** | 4 Levels — Critical → High → Medium → Low       |
| **Security Logging**     | With Unix timestamp-based log entries             |
| **Error Handling**       | Custom enum `ErrorCode`                           |
| **Simulated Business Hours** | Automatically ends after 10 seconds runtime  |

---

## 🚀 Features

### 🔐 Token-Based Security
- Required for **critical** and **high-priority** transactions  
- Managed via **Least Recently Used (LRU)** allocation strategy  

### ⏱️ Business Hours Simulation
- The system operates for **10 seconds**, simulating real-time banking hours  
- Transactions after closure are **automatically rejected**

### 🧵 Multithreaded Transaction Handling

#### Background Threads:
- `scheduler` – Executes priority queues
- `resource_replenishment` – Refills system funds and teller/ATM capacity
- `io_simulator` – Simulates I/O delays, regulations, and network effects

### 🧑‍💼 Customer Differentiation
- **VIP Customers**: Assigned higher priority by default  
- **Clearance-Required Customers**: Have stricter processing and error checking  

### 📊 Priority Queues
- **Four queues**: Critical, High, Medium, Low  
- Ordered by **submission time** → FIFO within priority levels

### ⚠️ Error Detection
Handles runtime errors including:
- ❌ Insufficient funds  
- ⚠️ Suspicious/fraudulent activity  
- 🔁 System overload  
- 🌐 Network interruptions  
- 🚫 Maximum customer threshold exceeded  

### 📜 Event Logging
- All transactions (success/failure) are **timestamped and logged**
- Supports review of **fraud detection**, **fund transfers**, **transaction failures**

---

## 📜 License

This project is open-source and available for **educational and academic use** under the **MIT License**.

---

## 📧 Contact

For inquiries or feedback:

- **Ghulam Qadir** — 📧 gqitspecialist@gmail.com  
- **Noor Malik** — 🔗 [LinkedIn](https://www.linkedin.com/in/noormalik56500)


## 📂 File Structure

```bash

├── banking_simulator.cpp     # Main project file
├── README.md                 # Project documentation

🧪 Sample Output

Transaction ID: 5 escalated for clearance
Transaction ID: 3 flagged for fraud
Peak time: High volume!
Transaction ID: 7 failed: Outside business hours
Resources replenished. Funds: 56200, Capacity: 10

Security Log:
Time: 1720318512  Fraud suspected
Time: 1720318513  Fund transfer of 2300 received
🏁 How to Compile & Run
🔧 Compile

g++ -pthread banking_simulator.cpp -o bank_sim
▶️ Run

./bank_sim
🔄 Thread Overview
Thread Name	Responsibility
scheduler	Executes transactions by priority
resource_replenishment	Refills system funds and teller/ATM capacity
io_simulator	Simulates I/O maintenance and network delays

📦 Resource Configuration

MAX_ATMS       = 2
MAX_TELLERS    = 3
MAX_TOKENS     = 5
MAX_CUSTOMERS  = 5
INITIAL_FUNDS  = 50000
BUSINESS_HOURS = 10  // in seconds



