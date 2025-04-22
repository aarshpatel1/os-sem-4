# Assignment - 5 (I/O and Memory Management)

## Answer the short questions:

### 1. **What is Direct Memory Access (DMA)?**

- A technique where data is transferred directly between I/O devices and memory.
- CPU is bypassed during data transfer, improving performance.

---

### 2. **Define Device Driver and its Purpose**

- A software component that allows the OS to communicate with hardware devices.
- Acts as a translator between hardware and software applications.

---

### 3. **What is Seek Time and Latency in Disk Scheduling?**

- **Seek Time**: Time to move the read/write head to the correct track.
- **Latency (Rotational Delay)**: Time for the desired sector to rotate under the head.

---

### 4. **Explain the Purpose of Cache Memory in OS**

- Fast memory placed between CPU and RAM.
- Stores frequently accessed data to reduce access time and speed up processing.

---

### 5. **Define Thrashing in Virtual Memory**

- Condition where excessive paging occurs, leading to low CPU utilization.
- Caused when processes don't have enough frames, resulting in constant swapping.

---

### 6. **What is the Purpose of Page Replacement Algorithms?**

- To decide which memory page to replace when new pages need to be loaded.
- Aim to minimize page faults and improve system performance.

---

### 7. **Explain FCFS Disk Scheduling Algorithm**

- First Come, First Served: Requests are handled in the order they arrive.
- Simple but can result in long wait times and high seek time.

---

### 8. **What is the Difference Between SSTF and SCAN Scheduling?**

- **SSTF (Shortest Seek Time First)**: Chooses request closest to current head position.
- **SCAN**: Head moves in one direction servicing requests, then reverses like an elevator.
- **Key Difference**: SSTF may starve distant requests; SCAN is fairer.

---

### 9. **Define Spooling and its Role in OS**

- Spooling = Simultaneous Peripheral Operations Online.
- Buffers data for slow devices (e.g., printers), allowing multitasking and orderly execution.

---

### 10. **What is the Purpose of I/O Scheduling in OS?**

- Determines the order of I/O request execution.
- Aims to reduce wait time, improve device performance, and maximize throughput.

---

### ✅ Resources:

- [GeeksforGeeks – Operating System](https://www.geeksforgeeks.org/operating-system/)
- [TutorialsPoint – OS Basics](https://www.tutorialspoint.com/operating_system/index.htm)
- [Javatpoint – OS Concepts](https://www.javatpoint.com/os-tutorial)

---

## Answer the long questions:

### 1. **Functions of Device Management in an OS**

- **Device Communication**: Manages communication between hardware devices and the system.
- **Device Allocation**: Allocates devices to processes as needed.
- **Monitoring**: Tracks the status of all devices to avoid conflicts.
- **Buffering and Caching**: Uses temporary storage to improve performance.
- **Drivers Management**: Loads and manages device drivers.
- **Error Detection and Recovery**: Detects hardware faults and attempts recovery.

---

### 2. **Device Characteristics and Their Impact on OS**

- **Speed**:
  - Fast (RAM) vs. slow (hard disk); affects scheduling and buffering needs.
- **Shared vs. Dedicated**:
  - Printers (shared) vs. keyboard (dedicated); affects access control.
- **Sequential vs. Random Access**:
  - Tape (sequential), Disk (random); affects read/write methods.
- **Transfer Mode**:
  - Character-based (keyboard) vs. block-based (disk); impacts driver design.
- **Volatility**:
  - Volatile (RAM) vs. non-volatile (Disk); impacts data persistence handling.

---

### 3. **Disk Space Management in OS**

- **Free Space Tracking**:
  - Bitmap or linked list to manage free disk blocks.
- **Allocation Strategies**:
  - Allocates space using methods like contiguous, linked, or indexed.
- **Directory Management**:
  - Maintains file directories and paths.
- **Garbage Collection**:
  - Frees unused or deleted file blocks.
- **Quota Management**:
  - Controls disk usage per user.

---

### 4. **Disk Allocation Methods in OS**

- **Contiguous Allocation**:
  - Stores file blocks in continuous memory.
  - _Pros_: Fast access; _Cons_: Fragmentation.
- **Linked Allocation**:
  - Each block contains a pointer to the next.
  - _Pros_: No fragmentation; _Cons_: Slow access.
- **Indexed Allocation**:
  - Uses an index block to store all block addresses.
  - _Pros_: Direct access; _Cons_: Overhead for index block.

---

### 5. **Disk Scheduling Algorithms in OS**

- **FCFS (First Come First Serve)**:
  - Simple but inefficient for heavy loads.
- **SSTF (Shortest Seek Time First)**:
  - Picks the nearest request; risk of starvation.
- **SCAN (Elevator Algorithm)**:
  - Moves back and forth across disk like an elevator.
- **C-SCAN (Circular SCAN)**:
  - Services in one direction and jumps back.
- **LOOK/C-LOOK**:
  - Like SCAN but only goes as far as needed.

---

### 6. **Interrupt Handling in Device Management**

- **Interrupt Request (IRQ)**:
  - Devices send IRQs to the CPU when they need attention.
- **Interrupt Handler**:
  - A routine that processes interrupts.
- **Interrupt Vector Table**:
  - Stores addresses of all handlers.
- **Context Switching**:
  - Saves the current process state to handle the interrupt.
- **Prioritization**:
  - Critical devices (e.g., disk I/O) may have higher priority.

---

### 7. **I/O Buffering in OS**

- **Purpose**:
  - Temporarily stores data to match speed between devices and CPU.
- **Types**:
  - **Single Buffering**: One buffer used at a time.
  - **Double Buffering**: Two buffers alternate, reducing wait time.
  - **Circular Buffering**: Multiple buffers in a queue-like structure.
- **Benefits**:
  - Increases throughput, reduces idle time, smoothens data flow.

---

### 8. **Spooling in Device Management**

- **Definition**:
  - Simultaneous Peripheral Operations On-Line.
- **How it Works**:
  - Data from multiple jobs is queued in a buffer (usually on disk) before being sent to the device.
- **Use Case**:
  - Printing — allows multiple users to send print jobs without waiting.
- **Benefits**:
  - Increases efficiency, supports multi-user systems, avoids device idling.

---

### 9. **Virtual Memory in Device Management**

- **Definition**:
  - A memory management technique that gives an illusion of large memory using disk space.
- **Paging**:
  - Divides memory into fixed-size pages and swaps between RAM and disk.
- **Benefits**:
  - Allows more processes to run, handles larger applications.
- **Impact on Devices**:
  - Uses disk (secondary storage) to extend RAM, affecting disk I/O performance.

---

### 10. **Deadlock in Device Management**

- **How it Occurs**:
  - When multiple processes wait indefinitely for resources held by each other.
- **Conditions for Deadlock**:
  - Mutual exclusion, hold and wait, no preemption, circular wait.
- **Prevention Techniques**:
  - **Deadlock Prevention**: Break one of the four conditions.
  - **Deadlock Avoidance**: Use algorithms like Banker’s.
  - **Deadlock Detection and Recovery**: Periodically check and recover by terminating/restarting processes.
  - **Resource Allocation Graphs**: Visual tool to prevent circular wait.

---

### ✅ Resources:

- [Operating System Concepts – Silberschatz, Galvin, Gagne](https://www.os-book.com/)
- [GeeksforGeeks – OS Topics](https://www.geeksforgeeks.org/operating-system/)
- [TutorialsPoint – OS Study Material](https://www.tutorialspoint.com/operating_system/index.htm)
- [Javatpoint – OS Basics](https://www.javatpoint.com/os-tutorial)

---

<p align="right"><strong>- Aarsh Patel</strong></p>
