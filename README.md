This is created by Harsh Kumar. Sap ID : 590015264 Batch : 01
About this code: 
This is a web-based visual tool (pure HTML, CSS, JavaScript) that lets students or learners: Create processes and resources. Simulate allocation and resource requests. Detect deadlocks using a wait-for graph. Run Banker’s Algorithm to check if the system is in a safe/unsafe state. Apply deadlock recovery strategies like aborting a process or preempting resources. Visualize everything with interactive graphs and logs. 👉 In short: It’s a teaching tool to demonstrate how deadlocks happen, how to detect them, and how recovery works.

⚙️ What the Code Does (Step by Step)

User Interface (HTML & CSS) Header → Title and a Reset button. Left panel (Configuration & Controls): Add processes (P1, P2, …). Add resources (R1, R2, …). Select a process → allocate/request/release resources. Run Banker’s Algorithm or Detect Deadlock. Recovery section: abort process or preempt resource. Shows system state matrices (allocation and request). Right panel (Visualization): SVG graph → process nodes (circles) and resource nodes (rectangles). Edges for allocations and requests. Logs of all actions. Notes for learners. Footer → Hints on how to create a deadlock cycle.

Adding Processes & Resources User types process name (e.g., P1) → added to list. User types resource name (e.g., R1) → added to list. Code prevents duplicates. UI is refreshed with new dropdowns.

Simulating Operations Allocate → Give a resource to a process. Request → A process asks for a resource. Release All → Clears a process’s allocations and requests.

System State Matrices The code renders two tables: Allocation Matrix → shows which process holds which resources. Request Matrix → shows pending requests. This mirrors how OS textbooks explain deadlocks.

Graph Visualization (SVG) Processes = circles on the left. Resources = rectangles on the right.

Edges: Process → Resource (allocation). Resource → Process (request). If a deadlock cycle is detected, the involved processes are highlighted in red.

Deadlock Detection (Wait-for Graph) Builds a graph of process → process dependencies: If P1 is waiting for a resource held by P2 → edge P1 → P2. Runs a DFS cycle-detection algorithm. If a cycle exists → deadlock is reported and highlighted.

Banker’s Algorithm Implements a simplified Banker’s algorithm (single-unit resources). Steps: Tracks available resources. Computes if there exists a safe sequence of processes. If yes → system is SAFE, shows sequence. If no → UNSAFE, potential deadlock.

Deadlock Recovery Two strategies are simulated: Abort process → Kills a process, releases all its resources back. Preempt resource → Takes one resource away from a victim process. Logs show what happened.

Logging Every action (adding process, allocating, detecting deadlock, running Banker, recovery, etc.) is logged with timestamps.

Seed Example When the page loads, it auto-creates a classic deadlock scenario: P1 holds R1 and requests R2. P2 holds R2 and requests R1. This creates a cycle → deadlock. This helps learners immediately see how deadlocks occur.

Why This Was Generated: This project was made as an educational visualizer for Operating Systems concepts: Students often struggle with abstract concepts like deadlock, safe states, and Banker’s algorithm. Teachers need a simple, browser-based tool with no installation required. This code helps learners see: How processes and resources interact. How deadlocks form (cycles). How to detect and recover from them. It’s a teaching demo tool → can be used in class or assignments.

How It Works Internally: Input: User adds processes/resources, simulates allocations/requests. State Tracking: Code updates allocation/request matrices. Graph Drawing: SVG shows process-resource graph dynamically.

Detection: Wait-for graph cycle detection → deadlock check. Banker’s Algorithm → safety check. Recovery: Aborts or preempts resources. Output: Updates graph, matrices, and logs.

Summary: What it is: A browser-based Deadlock & Recovery Visualizer for OS. What it does: Lets you simulate process-resource allocation, detect deadlocks, run Banker’s algorithm, and apply recovery. Why made: For teaching/learning OS concepts without complex setups. How it works: Uses JS arrays for system state, cycle detection for deadlock, Banker’s for safety, SVG for visualization, and logs for tracking.
