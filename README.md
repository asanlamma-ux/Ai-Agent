# Flask API Service Starter

This is a minimal Flask API service starter based on [Google Cloud Run Quickstart](https://cloud.google.com/run/docs/quickstarts/build-and-deploy/deploy-python-service).

## Getting Started

Server should run automatically when starting a workspace. To run manually, run:
```sh
./devserver.sh
```
Master Prompt Here:
''' ‎
‎
‎
‎---
‎
‎Master Prompt — Local AI English Assistant IDE (Termux / Android CPU)
‎
‎Project Overview
‎
‎Create a local AI-powered English Assistant IDE that runs on Android through Termux using only CPU inference. The system must be optimized for a Unisoc T606 CPU and limited RAM environment.
‎
‎The assistant should function as a smart English language tool and IDE-style interface where the user can:
‎
‎query English words
‎
‎perform pattern searches
‎
‎receive contextual assistance
‎
‎train small datasets
‎
‎interact through a clean terminal or lightweight UI
‎
‎
‎The system must support local inference only with no cloud dependencies.
‎
‎
‎---
‎
‎Hardware Constraints
‎
‎Target device:
‎
‎CPU: Unisoc T606 Architecture: ARM64 Environment: Termux
‎
‎Constraints:
‎
‎CPU-only inference
‎
‎No GPU usage
‎
‎RAM usage under 2GB
‎
‎Model size between 500MB and 1GB maximum
‎
‎Must run efficiently on mobile CPU
‎
‎
‎Optimization requirements:
‎
‎quantized models
‎
‎low memory usage
‎
‎streaming inference
‎
‎minimal dependencies
‎
‎
‎
‎---
‎
‎Core System Components
‎
‎The application must consist of the following modules:
‎
‎1. AI Model Engine
‎
‎Local language model for understanding natural language queries.
‎
‎Requirements:
‎
‎model size between 500MB – 1GB
‎
‎CPU optimized
‎
‎quantized weights
‎
‎transformer-based architecture
‎
‎context memory support
‎
‎
‎Capabilities:
‎
‎understand natural language queries
‎
‎assist with English language tasks
‎
‎provide explanations
‎
‎interpret commands
‎
‎
‎Example queries:
‎
‎words that start with B and end with D
‎define "beyond"
‎generate a sentence using "abandon"
‎what words rhyme with cold
‎
‎
‎---
‎
‎2. English Knowledge Database
‎
‎A large English word dataset stored locally.
‎
‎Must include:
‎
‎full English dictionary
‎
‎word meanings
‎
‎synonyms
‎
‎word forms
‎
‎phonetics if available
‎
‎
‎Recommended storage format:
‎
‎SQLite database
‎
‎indexed search tables
‎
‎fast query lookup
‎
‎
‎Capabilities:
‎
‎prefix search
‎suffix search
‎pattern matching
‎dictionary lookup
‎synonym search
‎
‎Example queries:
‎
‎words starting with b
‎words ending with d
‎6-letter words starting with br
‎
‎
‎---
‎
‎3. Query Interpreter
‎
‎A command parser that interprets user instructions.
‎
‎Responsibilities:
‎
‎detect user intent
‎
‎route queries to the correct system
‎
‎combine AI reasoning + database results
‎
‎
‎Example flow:
‎
‎User Query
‎      ↓
‎Query Parser
‎      ↓
‎Database Search OR AI Model
‎      ↓
‎Formatted Response
‎
‎
‎---
‎
‎4. Training System
‎
‎Provide a lightweight system to train or fine-tune the model.
‎
‎Capabilities:
‎
‎add new datasets
‎
‎train small embeddings
‎
‎incremental learning
‎
‎store new knowledge
‎
‎
‎Training must:
‎
‎run on CPU
‎
‎support batching
‎
‎prevent memory overflow
‎
‎
‎
‎---
‎
‎5. Context Memory
‎
‎Maintain conversation context so the assistant remembers previous queries.
‎
‎Example:
‎
‎User: words starting with b
‎Assistant: list...
‎
‎User: only 6 letters
‎Assistant: filtered results
‎
‎Implement using:
‎
‎session memory
‎
‎conversation buffer
‎
‎
‎
‎---
‎
‎IDE-Style User Interface
‎
‎The UI should resemble a developer console or lightweight IDE.
‎
‎Design goals:
‎
‎minimal CPU usage
‎
‎clean layout
‎
‎keyboard friendly
‎
‎mobile-friendly terminal UI
‎
‎
‎Possible frameworks:
‎
‎Textual (Python terminal UI)
‎
‎curses
‎
‎lightweight web UI served locally
‎
‎
‎
‎---
‎
‎UI Features
‎
‎Main Console
‎
‎Primary command interface where users type queries.
‎
‎Example:
‎
‎> words starting with b ending with d
‎> define brave
‎> generate sentence using "beyond"
‎
‎
‎---
‎
‎Dataset Manager
‎
‎Allows users to:
‎
‎import datasets
‎
‎view dictionary entries
‎
‎manage training data
‎
‎
‎
‎---
‎
‎Training Panel
‎
‎Displays:
‎
‎training status
‎
‎dataset size
‎
‎epochs
‎
‎progress
‎
‎
‎
‎---
‎
‎Model Monitor
‎
‎Shows:
‎
‎RAM usage
‎
‎model size
‎
‎inference speed
‎
‎CPU load
‎
‎
‎
‎---
‎
‎AI Capabilities
‎
‎The assistant should support:
‎
‎Language Assistance
‎
‎definitions
‎synonyms
‎grammar explanation
‎sentence generation
‎spelling correction
‎
‎
‎---
‎
‎Word Pattern Queries
‎
‎Examples:
‎
‎words starting with b ending with d
‎words containing "ight"
‎7-letter words starting with un
‎
‎
‎---
‎
‎Contextual Assistance
‎
‎Example interaction:
‎
‎User: words starting with b
‎Assistant: list...
‎
‎User: only 5 letters
‎Assistant: filtered results
‎
‎
‎---
‎
‎Performance Requirements
‎
‎Must meet these performance goals on Unisoc T606 CPU:
‎
‎Inference latency:
‎
‎simple query < 2 seconds
‎complex query < 5 seconds
‎
‎Memory usage:
‎
‎< 1.5GB RAM
‎
‎Model loading:
‎
‎< 10 seconds
‎
‎
‎---
‎
‎Software Stack
‎
‎Recommended technologies:
‎
‎Language:
‎
‎Python
‎
‎Libraries:
‎
‎PyTorch CPU
‎SQLite
‎NumPy
‎Textual (UI)
‎SentenceTransformers or small transformer model
‎
‎Optional optimization:
‎
‎ONNX Runtime
‎GGUF quantized models
‎
‎
‎---
‎
‎File Structure
‎
‎The generated project should use a clean structure:
‎
‎ai_assistant/
‎    model/
‎    database/
‎    training/
‎    ui/
‎    parser/
‎    core/
‎    datasets/
‎    main.py
‎
‎
‎---
‎
‎Security & Offline Operation
‎
‎Requirements:
‎
‎fully offline
‎
‎no telemetry
‎
‎no external API calls
‎
‎user data stored locally
‎
‎
‎
‎---
‎
‎Expected Final Result
‎
‎A local AI English Assistant IDE that:
‎
‎runs fully on phone CPU
‎
‎loads a 500MB–1GB AI model
‎
‎supports natural language queries
‎
‎allows dataset training
‎
‎performs advanced word searches
‎
‎maintains conversation context
‎
‎provides an IDE-style interface
‎
‎
‎
‎
'''