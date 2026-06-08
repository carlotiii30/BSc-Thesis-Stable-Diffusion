# Custom Stable Diffusion via DreamBooth (FastAPI Backend)

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![Poetry](https://img.shields.io/badge/Poetry-Dependency%20Manager-60A5FA?style=flat-square&logo=poetry&logoColor=white)](https://python-poetry.org/)

This repository contains the core AI implementation and backend architecture of my Bachelor's Thesis in Computer Engineering. It focuses on custom text-to-image generation through modern generative deep learning techniques.

---

## Model Architecture & Core Implementation

### 🔹 Model Fine-Tuning (DreamBooth)
The system leverages **Stable Diffusion** as its foundational text-to-image generative framework. To achieve specialized domain adaptation, the base model was fine-tuned using **DreamBooth** to personalize image generation for specific dog breeds. 

*   **Dataset:** A filtered subset of the **Stanford Dogs Dataset** was curated, selecting specific breeds and balancing class distributions.
*   **Hardware Optimization:** Implemented advanced training configurations to handle large-scale weights adjustment under strict hardware constraints, including **mixed precision (fp16)**, **gradient checkpointing**, and dynamic batch-size reduction for optimal GPU memory management.
*   **Custom Pipeline:** Built a dedicated Python inference pipeline for serving the custom-tuned weights efficiently.

### 🔹 Backend Architecture (FastAPI)
The fine-tuned models and inference pipelines are fully exposed through a high-performance **FastAPI** application, enabling synchronous and asynchronous HTTP requests for model management and image generation tasks.

---

## Quickstart: Installation & Usage

### 1. Dependency Management
This project uses **Poetry** for package isolation and deterministic environment replication.

Install Poetry if you don't have it yet:
```bash
pip install poetry
```

Install project dependencies:
```bash
poetry install
```

### 2. Running the FastAPI Server
To spin up the development server with hot-reloading:
```bash
poetry run uvicorn api.main:app --reload
```

### 3. API Consumption & Interactive Docs
You can explore and test the available endpoints via the Swagger interactive UI at: `http://localhost:8000/docs`

---

## Related Repositories
This project is part of a modular ecosystem. Check out the other components:
* **Java Desktop Interface:** [BSc-Thesis-Java-Client](https://github.com/carlotiii30/BSc-Thesis-Java-Client) – The graphical client designed to interact with this API.
* **Official Thesis Report:** [BSc-Thesis-LaTeX](https://github.com/carlotiii30/BSc-Thesis-LaTeX) – Full LaTeX documentation and academic dissertation.
* **JMR Descriptor:** [Bsc-JMR](https://github.com/carlotiii30/BSc-JMR) – Specific operational configuration schemas.
