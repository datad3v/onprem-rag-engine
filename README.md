# Project Enclave: Private Document Search Engine

A local, containerized RAG (Retrieval-Augmented Generation) engine built to index and search sensitive documents completely offline. 

## 🧠 Why I Built This
If you work with regulated data (like healthcare records, legal docs, or enterprise financials), passing that data to a public cloud AI API is a non-starter. 

I wanted to see if I could build a secure alternative that brings the AI to the data, rather than sending the data to the cloud. This project is an on-premises blueprint for running document intelligence entirely inside a local, isolated environment—no data ever leaves the machine.

## 🛠️ The Stack
Instead of relying on cloud services, everything runs locally via Docker microservices:

* **OS & Environment:** Pop!_OS Linux
* **Compute:** Local AMD GPU acceleration using ROCm (because setting up local AI on AMD is a fun challenge)
* **Containers:** Docker & Docker Compose to keep services isolated and reproducible
* **Core Pipeline:** Python with LangChain for handling document ingestion and parsing
* **Vector Store:** ChromaDB running locally to handle embeddings and quick indexing
* **LLM Engine:** Ollama running open-source models (like Llama 3) entirely offline

## 🗺️ What's Built & What's Next
I'm building this out in practical phases. Here is where the project stands:

- [x] **Phase 1: Architecture & Specs:** Defining the infrastructure and data workflows (Done).
- [ ] **Phase 2: Environment & Hardware:** Configuring the Docker environment and testing AMD ROCm GPU passthrough.
- [ ] **Phase 3: The Parsing Pipeline:** Writing the Python scripts to chunk raw documents without losing context.
- [ ] **Phase 4: Vector Storage:** Mapping those chunks into local ChromaDB collections.
- [ ] **Phase 5: Search & Inference:** Connecting the local LLM to execute secure queries against the vector store.

## 🔒 A Note on Security
This engine is designed to operate completely air-gapped. Because there are no external API calls, there is zero risk of data leaks, usage-tracking, or privacy violations. It's just your hardware and your data.
