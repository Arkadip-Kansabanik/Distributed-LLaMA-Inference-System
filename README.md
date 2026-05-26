# Distributed LLaMA Inference System

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Distributed-AI-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/LLaMA-2-orange?style=for-the-badge">
  <img src="https://img.shields.io/badge/Status-Research_Project-red?style=for-the-badge">
</p>

---

# 📌 Distributed LLaMA Inference System

A scalable distributed AI framework designed to run **LLaMA-based Large Language Models** across multiple machines using CPU parallelism.

This project enables low-cost local deployment of LLMs without requiring expensive GPU infrastructure.

---

# 📖 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Architecture](#️-architecture)
- [Execution Workflow](#️-execution-workflow)
- [Tools & Technologies](#️-tools--technologies)
- [Models Used](#-models-used)
- [Results](#-results)
- [Advantages](#-advantages)
- [Challenges Faced](#️-challenges-faced)
- [Future Scope](#-future-scope)
- [Applications](#-applications)
- [Installation](#️-installation)
- [Project Structure](#-project-structure)
- [Authors](#-authors)
- [Acknowledgement](#-acknowledgement)

---

# 📌 Overview

Large Language Models require high computational power and memory resources. Running modern LLMs on a single machine becomes difficult due to hardware limitations and expensive GPU requirements.

The Distributed LLaMA Inference System solves this problem by distributing inference workloads across multiple connected systems over a Local Area Network (LAN).

This enables:

- Faster inference
- Lower RAM usage
- CPU-based distributed computation
- Offline AI deployment
- Scalable architecture

---

# 📌 Problem Statement

## Existing Problem

Modern Large Language Models:

- Require large RAM capacity
- Depend heavily on GPU infrastructure
- Are expensive to deploy
- Have high inference latency
- Cannot efficiently run on low-resource systems

Running large-scale models on a single computer often causes:

❌ Memory bottlenecks  
❌ Slow response generation  
❌ High infrastructure cost  
❌ Limited scalability  

---

## Proposed Solution

The proposed system distributes the model inference process across multiple connected machines.

Instead of relying on one high-end GPU server, computation is shared among several worker nodes using CPU parallelism.

This creates:

✅ Low-cost distributed AI infrastructure  
✅ Faster inference performance  
✅ Better hardware utilization  
✅ Scalable local AI deployment  

---

# 🏗️ Architecture

The system follows a **Master–Worker Distributed Architecture**.

---

## 🔹 Master / Root Node

The Master Node is responsible for:

- Accepting user prompts
- Coordinating worker nodes
- Managing distributed communication
- Aggregating outputs
- Returning final responses

---

## 🔹 Worker Nodes

Worker Nodes are responsible for:

- Loading model partitions
- Processing assigned computations
- Performing inference tasks
- Returning intermediate outputs

---

# 🧠 System Architecture Diagram

```text
                           +----------------------+
                           |    MASTER NODE       |
                           |----------------------|
                           | Prompt Handling      |
                           | Task Distribution    |
                           | Synchronization      |
                           | Final Aggregation    |
                           +----------+-----------+
                                      |
          ---------------------------------------------------------
          |                         |                           |
+-------------------+   +-------------------+   +-------------------+
|   WORKER NODE 1   |   |   WORKER NODE 2   |   |   WORKER NODE 3   |
|-------------------|   |-------------------|   |-------------------|
| Model Layers      |   | Model Layers      |   | Model Layers      |
| CPU Computation   |   | CPU Computation   |   | CPU Computation   |
+-------------------+   +-------------------+   +-------------------+
```

---

# ⚙️ Execution Workflow

## Step-by-Step Workflow

### 1️⃣ Start Worker Nodes

Worker nodes are initialized on multiple machines connected over LAN.

```bash
python worker.py
```

---

### 2️⃣ Initialize Master Node

The master node establishes communication with all worker systems.

```bash
python master.py
```

---

### 3️⃣ Establish LAN Communication

The distributed network connection is initialized using TCP/IP socket communication.

```text
Listening on 0.0.0.0:9998
Root node connected successfully
```

---

### 4️⃣ Synchronize Distributed Nodes

All worker systems synchronize model layers and inference tasks.

```text
Network initialized
Synchronization complete
```

---

### 5️⃣ Load Model Weights

Distributed model weights are loaded across nodes.

```text
Weights loaded
CPU detected: AVX2
```

---

### 6️⃣ User Sends Prompt

The user submits prompts through a local API endpoint.

Example:

```text
"Explain distributed inference systems."
```

---

### 7️⃣ Distributed Inference Begins

Worker nodes collaboratively process model computations in parallel.

Tasks include:

- Token computation
- Layer execution
- Intermediate tensor processing

---

### 8️⃣ Aggregation by Master Node

The master node collects outputs from all workers and combines them into a final inference result.

---

### 9️⃣ Final Response Returned

The generated response is returned to the user.

Example:

```text
Distributed inference improves scalability by splitting workloads across multiple systems.
```

---

# 🛠️ Tools & Technologies

## 💻 Programming Languages

- Python
- Bash Scripting

---

## 🌐 Networking Technologies

- Socket Programming
- TCP/IP Communication
- LAN-based Synchronization

---

## 🤖 AI & Machine Learning

- LLaMA Models
- Local LLM Inference
- Distributed AI Systems
- CPU Parallelism

---

## ⚙️ System Technologies

- Multi-threading
- Parallel Processing
- Distributed Computing

---

## ☁️ Future Deployment Technologies

- Docker
- Kubernetes

---

# 🤖 Models Used

## LLaMA 2 7B

The system was benchmarked using the **LLaMA 2 7B** model.

---

## Features of the Model Deployment

✅ Offline inference  
✅ Distributed execution  
✅ Multi-node scalability  
✅ CPU-based deployment  
✅ Low-cost infrastructure  

---

# 📊 Results

## Benchmark Results

| Devices | Total Time | Inference Time |
|----------|-------------|----------------|
| 1 Node   | 1312 ms     | 1307 ms        |
| 2 Nodes  | 793 ms      | 739 ms         |
| 4 Nodes  | 494 ms      | 458 ms         |

---

## Performance Insights

- Increasing worker nodes significantly reduces latency
- Parallel CPU computation improves efficiency
- Lower memory load per machine
- Faster token generation achieved
- Improved scalability observed

---

# 🖥️ Real Deployment Logs

```bash
Listening on 0.0.0.0:9998
Root node connected successfully
Network initialized
Weights loaded
CPU detected: AVX2
```

---

# 🌐 LAN Connectivity

Observed network latency:

```text
≈ 0.1 ms
```

---

# ✅ Advantages

- Low-cost AI deployment
- Distributed CPU computation
- Offline AI systems
- Secure local infrastructure
- Faster inference speed
- Better resource utilization
- Scalable architecture
- Research-friendly implementation

---

# 🚀 Future Scope

Planned future improvements include:

- GPU + CPU hybrid clusters
- Automatic node discovery
- Multi-model support
- High-speed interconnect systems
- Kubernetes autoscaling
- Monitoring dashboards
- RAG integration
- AI Log Analyzer chatbot
- Production-scale deployment

---

# 💡 Applications

The system can be applied in:

- Enterprise AI Servers
- Offline AI Labs
- Research Clusters
- Educational Institutions
- Secure On-Premise AI
- Multi-user Chatbot Systems
- Edge AI Devices
- Distributed LLM Hosting

---

# ⚙️ Installation

## Clone Repository

```bash
git clone https://github.com/Arkadip-Kansabanik/Distributed-LLaMA-Inference-System.git
```

---

## Navigate to Project Directory

```bash
cd Distributed-LLaMA-Inference-System
```

---

## Start Worker Nodes

```bash
python worker.py
```

---

## Start Master Node

```bash
python master.py
```

---

# 📂 Project Structure

```text
Distributed-LLaMA-Inference/
│
├── master.py
├── worker.py
├── requirements.txt
├── config/
├── models/
├── logs/
├── screenshots/
├── docs/
└── README.md
```

