# news-rag
Get news updates on latest events 

### Repository Structure: 

news-rag/
│
├── cli/                              # Command-line interface
│   └── main.py                       # CLI for querying the system
│
├── data/                             # Storage for raw and processed data
│   ├── raw/                          # Scraped HTML/text
│   └── processed/                    # Cleaned and chunked documents
│
├── embeddings/                       # Embedding generation and Vector DB
│   ├── embedder.py                   # Create document embeddings
│   ├── vectordb.py                   # Store/query vectors
│   └── config.py                     # Configs for DB and embedding models
│
├── inference/                        # LLM Inference & Ray Serve
│   ├── model.py                      # LLM wrapper (e.g., TinyLlama, DistilGPT2)
│   ├── ray_serve_app.py              # Ray Serve deployment file
│   └── serve_utils.py                # Helper functions for answering queries
│
├── retriever/                        # Context retriever from vector DB
│   └── retrieve.py                   # Retrieves top-k documents per query
│
├── scraper/                          # Scraping & parsing logic
│   ├── scrape.py                     # Scrapes tech news
│   └── parser.py                     # Cleans and extracts relevant text
│
├── scripts/                          # Utility scripts
│   ├── ingest.py                     # Scrape → preprocess → embed → store
│   └── test_query.py                 # Manual test script for querying
│
├── k8s/                              # Kubernetes deployment (for Minikube)
│   ├── deployment.yaml               # Deployment spec for Ray Serve app
│   ├── service.yaml                  # NodePort service to expose API
│   ├── scraper-job.yaml              # K8s job to run scraper daily
│   └── configmap.yaml                # App-level configs
│
├── Dockerfile                        # Dockerfile for containerizing app
├── .dockerignore
├── requirements.txt                  # Python dependencies
├── minicube_run.sh                   # Shell script to build & deploy to Minikube
├── .env                              # Environment variables (not checked in)
└── README.md                         # Project overview, setup, and usage
