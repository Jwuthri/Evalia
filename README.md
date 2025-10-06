# 🧠 Evalia — The Intelligence Layer for Prompt Evaluation

> **Where prompts meet proof.** Intelligent platform for evaluating, benchmarking, and improving large language model (LLM) prompts — automatically, continuously, and contextually.

Evalia empowers AI engineers, researchers, and product teams to understand how their prompts perform across tasks, domains, and models — with built-in analytics, adaptive datasets, and LLM-based evaluation.

[![FastAPI](https://img.shields.io/badge/FastAPI-0.104+-00a393?style=flat&logo=fastapi)](https://fastapi.tiangolo.com)
[![Next.js](https://img.shields.io/badge/Next.js-14+-black?style=flat&logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5+-3178c6?style=flat&logo=typescript)](https://www.typescriptlang.org)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-412991?style=flat&logo=openai)](https://openai.com)
[![Anthropic](https://img.shields.io/badge/Anthropic-Claude-orange?style=flat)](https://anthropic.com)
[![Docker](https://img.shields.io/badge/Docker-ready-2496ed?style=flat&logo=docker)](https://www.docker.com)

---

## 💡 **Why Evalia?**

Building great AI experiences requires **evidence-driven prompt design**. Evalia turns prompt engineering from trial-and-error into a measurable, scientific process — bridging the gap between intuition and performance.

---

## 🌟 **Core Features**

### 🧩 **Prompt Evaluation Engine**

- **Automated A/B Testing** of prompt variants across datasets, models, and criteria
- **Multi-Model Benchmarking** across GPT-4, Claude, Gemini, and more
- **Performance Metrics** including accuracy, tone, relevance, and custom criteria
- **Regression Detection** to catch prompt performance degradation

### 🧠 **LLM-as-Judge Scoring**

- **Advanced Model Evaluation** using GPT-4 or Claude for qualitative scoring
- **Reasoning & Explanations** for why outputs succeed or fail
- **Custom Evaluation Criteria** tailored to your specific use cases
- **Confidence Scoring** and uncertainty quantification

### 🏷️ **Domain-Aware Datasets**

- **Business-Specific Datasets** for legal, e-commerce, healthcare, and more
- **Adaptive Dataset Evolution** that improves with feedback
- **Realistic Example Generation** using LLMs when datasets don't exist
- **Version Control** for dataset changes and improvements

### 🔄 **Dynamic Dataset Builder**

- **On-the-Fly Generation** of realistic test cases using LLMs
- **Feedback Integration** to continuously improve dataset quality
- **Domain Expertise** injection for specialized use cases
- **Synthetic Data Pipeline** for privacy-sensitive applications

### 📊 **Insight Dashboard**

- **Performance Visualization** over time with interactive charts
- **Domain Comparison** to see which contexts perform best
- **Model Performance** side-by-side comparisons
- **Cost Analysis** and token usage optimization

### ⚡ **Continuous Evaluation Pipelines**

- **CI/CD Integration** for automatic prompt re-evaluation
- **Webhook Support** for real-time notifications
- **Scheduled Evaluations** for ongoing monitoring
- **Alert System** for performance degradation

### 🔍 **Hybrid Metrics**

- **LLM-Based Evaluation** for nuanced quality assessment
- **Rule-Based Metrics** for objective measurements
- **Human-in-the-Loop** validation and feedback
- **Custom Scoring Functions** for specialized requirements

### 🧬 **Model & Domain Comparison**

- **Cross-Model Benchmarking** (OpenAI, Anthropic, Google, etc.)
- **Domain-Specific Performance** analysis
- **Cost-Performance Trade-offs** visualization
- **Latency vs Quality** optimization insights

---

## 🚀 **Use Cases**

### 🎯 **Customer Support Optimization**

Evaluate customer-support prompts across different industries and optimize response quality, tone, and accuracy.

### 📊 **Content Generation Benchmarking**

Compare summarization, QA, and content generation prompts between models (GPT-4, Claude, Gemini) to find the best fit.

### 🔬 **Research & Development**

Fine-tuning validation, RAG system optimization, and prompt experimentation for AI labs and research teams.

### 🏢 **Enterprise AI Tooling**

Internal tooling for prompt experimentation, A/B testing, and performance monitoring at scale.

---

## 🏗️ **Architecture**

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Next.js       │────│   FastAPI       │────│  Evaluation     │
│   Dashboard     │    │   Backend       │    │   Engine        │
│                 │    │                 │    │                 │
│ • React Charts  │    │ • Python 3.11+ │    │ • Multi-Model   │
│ • Tailwind CSS  │    │ • Async/Await   │    │ • LLM-as-Judge  │
│ • TypeScript    │    │ • Pydantic      │    │ • Metrics       │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         └───────────────────────┼───────────────────────┘
                                 │
    ┌────────────────────────────┴────────────────────────────┐
    │                                                         │
┌───▼────┐ ┌────────┐ ┌────────┐ ┌─────────────┐ ┌──────────┐
│ Redis  │ │ Celery │ │ Qdrant │ │   Dataset   │ │PostgreSQL│
│ Cache  │ │ Queue  │ │Vector  │ │   Storage   │ │ Database │
└────────┘ └────────┘ └────────┘ └─────────────┘ └──────────┘
```

---

## 🚀 **Quick Start**

### 1. **Prerequisites**

```bash
# Install uv (ultra-fast Python package manager)
curl -LsSf https://astral.sh/uv/install.sh | sh

# Install Node.js 18+
# https://nodejs.org/

# Install Docker & Docker Compose
# https://docs.docker.com/get-docker/
```

### 2. **Environment Setup**

```bash
# Copy environment files
cp backend/.env.template backend/.env
cp frontend/.env.template frontend/.env

# Set your API keys in backend/.env
OPENAI_API_KEY=your_openai_key_here
ANTHROPIC_API_KEY=your_anthropic_key_here
GOOGLE_API_KEY=your_google_key_here  # Optional for Gemini

# Vector database for embeddings (choose one)
QDRANT_URL=http://localhost:6333
# OR
PINECONE_API_KEY=your_pinecone_key_here
```

### 3. **Start with Docker Compose** ⚡

```bash
# Start all services (recommended for first run)
docker-compose up -d

# Or use the development setup
docker-compose -f docker-compose.dev.yml up -d
```

### 4. **Manual Development Setup** 🛠️

```bash
# Backend
cd backend
uv venv
source .venv/bin/activate  # or `.venv\Scripts\activate` on Windows
uv pip install -e .
uv pip list
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

# Frontend (in another terminal)
cd frontend
npm install
npm run dev
```

### 5. **Access Evalia** 🎉

- **Dashboard**: <http://localhost:3000>
- **Backend API**: <http://localhost:8000>
- **API Docs**: <http://localhost:8000/docs>
- **Evaluation Results**: <http://localhost:3000/evaluations>

---

## 🔧 **Evaluation Configuration**

### **Supported Models**

Evalia supports evaluation across multiple LLM providers:

```python
# OpenAI Models
"gpt-4"                    # Best for complex reasoning
"gpt-4-turbo"             # Faster GPT-4 variant
"gpt-3.5-turbo"           # Cost-effective option

# Anthropic Models
"claude-3-opus"           # Most capable Claude model
"claude-3-sonnet"         # Balanced performance
"claude-3-haiku"          # Fast and efficient

# Google Models
"gemini-pro"              # Google's flagship model
"gemini-pro-vision"       # Multimodal capabilities

# Open Source (via Ollama)
"llama2"                  # Meta's Llama 2
"mistral"                 # Mistral 7B
"codellama"               # Code-specialized model
```

### **Evaluation Types**

**Quality Metrics**

- **Accuracy**: Correctness of responses
- **Relevance**: How well responses address the prompt
- **Coherence**: Logical flow and consistency
- **Completeness**: Coverage of required information

**LLM-as-Judge Evaluation**

- **GPT-4 Judge**: Use GPT-4 to evaluate response quality
- **Claude Judge**: Anthropic's Claude for nuanced assessment
- **Custom Criteria**: Define domain-specific evaluation criteria
- **Confidence Scoring**: Uncertainty quantification

### **Dataset Configuration**

**Built-in Domains**

- **Customer Support**: Service inquiries and responses
- **Content Generation**: Blog posts, summaries, descriptions
- **Code Generation**: Programming tasks and solutions
- **Legal**: Contract analysis and legal reasoning
- **Healthcare**: Medical information and advice
- **E-commerce**: Product descriptions and recommendations

**Custom Datasets**

- **CSV Import**: Upload your own evaluation datasets
- **API Integration**: Connect to existing data sources
- **Synthetic Generation**: AI-generated test cases
- **Version Control**: Track dataset changes over time

---

## 📚 **API Endpoints**

### **Prompt Evaluation**

```bash
# Create a new evaluation
POST /api/v1/evaluations
{
  "name": "Customer Support Prompt v2",
  "prompts": [
    {
      "id": "prompt_a",
      "content": "You are a helpful customer support agent..."
    },
    {
      "id": "prompt_b", 
      "content": "As a customer service representative..."
    }
  ],
  "dataset_id": "customer_support_v1",
  "models": ["gpt-4", "claude-3-sonnet"],
  "evaluation_criteria": ["accuracy", "tone", "helpfulness"]
}

# Get evaluation results
GET /api/v1/evaluations/{evaluation_id}/results

# List all evaluations
GET /api/v1/evaluations

# Compare prompt performance
GET /api/v1/evaluations/{evaluation_id}/compare
```

### **Dataset Management**

```bash
# Upload a new dataset
POST /api/v1/datasets
{
  "name": "Customer Support Q&A",
  "domain": "customer_support",
  "data": [
    {
      "input": "How do I return a product?",
      "expected_output": "You can return products within 30 days...",
      "metadata": {"category": "returns"}
    }
  ]
}

# Get dataset details
GET /api/v1/datasets/{dataset_id}

# Generate synthetic dataset
POST /api/v1/datasets/generate
{
  "domain": "e_commerce",
  "size": 100,
  "criteria": "product_descriptions"
}

# List available datasets
GET /api/v1/datasets
```

### **Model Management**

```bash
# Get available models
GET /api/v1/models

# Test model connectivity
POST /api/v1/models/{model_id}/test
{
  "prompt": "Hello, world!"
}

# Get model performance metrics
GET /api/v1/models/{model_id}/metrics

# Compare models
POST /api/v1/models/compare
{
  "models": ["gpt-4", "claude-3-sonnet"],
  "prompt": "Explain quantum computing",
  "evaluation_criteria": ["accuracy", "clarity"]
}
```

### **Analytics & Insights**

```bash
# Get evaluation analytics
GET /api/v1/analytics/evaluations/{evaluation_id}

# Performance trends over time
GET /api/v1/analytics/trends?timeframe=30d

# Cost analysis
GET /api/v1/analytics/costs?model=gpt-4&timeframe=7d

# Domain performance comparison
GET /api/v1/analytics/domains/compare
```

### **Background Tasks**

```bash
# Run evaluation asynchronously
POST /api/v1/tasks/evaluations
{
  "evaluation_id": "eval_123",
  "priority": "high"
}

# Get task status
GET /api/v1/tasks/{task_id}

# Schedule recurring evaluation
POST /api/v1/tasks/schedule
{
  "evaluation_id": "eval_123",
  "schedule": "0 9 * * 1"  # Every Monday at 9 AM
}
```

---

## 🔧 **Configuration**

### **Backend Settings** (`backend/.env`)

```bash
# LLM Provider API Keys
OPENAI_API_KEY=your_openai_key_here
ANTHROPIC_API_KEY=your_anthropic_key_here
GOOGLE_API_KEY=your_google_key_here

# Default Evaluation Settings
DEFAULT_EVALUATION_MODEL=gpt-4
DEFAULT_JUDGE_MODEL=gpt-4
ENABLE_COST_TRACKING=true
MAX_CONCURRENT_EVALUATIONS=5

# Vector Database (choose one)
VECTOR_DATABASE=qdrant
QDRANT_URL=http://localhost:6333
# OR
VECTOR_DATABASE=pinecone
PINECONE_API_KEY=your_pinecone_key
PINECONE_ENVIRONMENT=gcp-starter

# Database & Cache
DATABASE_URL=postgresql://user:pass@localhost:5432/evalia
REDIS_URL=redis://localhost:6379/0

# Background Tasks
CELERY_BROKER_URL=redis://localhost:6379/1
CELERY_RESULT_BACKEND=redis://localhost:6379/1
ENABLE_ASYNC_EVALUATIONS=true

# Monitoring & Analytics
ENABLE_METRICS=true
PROMETHEUS_PORT=9090
LOG_LEVEL=INFO
```

### **Frontend Settings** (`frontend/.env.local`)

```bash
NEXT_PUBLIC_API_URL=http://localhost:8000
NEXT_PUBLIC_APP_NAME=Evalia
NEXT_PUBLIC_ENABLE_ANALYTICS=true
```

---

## 🚢 **Deployment**

### **Using Docker** (Recommended)

```bash
# Production build
docker-compose -f docker-compose.prod.yml up -d

# Or use the deployment script
./backend/scripts/deploy.sh
```

### **Manual Deployment**

```bash
# Backend
cd backend
uv pip install -e .
gunicorn app.main:app -w 4 -k uvicorn.workers.UvicornWorker

# Start Celery workers for evaluation tasks
celery -A app.core.celery_app:celery_app worker --queues=evaluations --concurrency=4
celery -A app.core.celery_app:celery_app worker --queues=datasets --concurrency=2
celery -A app.core.celery_app:celery_app worker --queues=analytics --concurrency=2

# Optional: Start Celery Flower for monitoring
celery -A app.core.celery_app:celery_app flower --port=5555

# Frontend
cd frontend
npm run build
npm start
```

### **Environment Variables for Production**

- Set `ENVIRONMENT=production`
- Use strong `SECRET_KEY`
- Configure proper `CORS_ORIGINS`
- Set up SSL/TLS certificates
- Use managed database services (PostgreSQL, Redis)
- Configure production vector database (Qdrant Cloud or Pinecone)
- Set up monitoring and alerting
- Enable rate limiting and authentication

---

## 📁 **Project Structure**

```
evalia/
├── 📁 backend/                 # FastAPI Backend
│   ├── 📁 app/
│   │   ├── 📁 api/v1/         # API routes
│   │   │   ├── 📄 evaluations.py    # Evaluation endpoints
│   │   │   ├── 📄 datasets.py       # Dataset management
│   │   │   ├── 📄 models.py         # Model management
│   │   │   └── 📄 analytics.py      # Analytics & insights
│   │   ├── 📁 core/           # Core business logic
│   │   │   ├── 📁 evaluation/ # Evaluation engine
│   │   │   ├── 📁 llm/        # Multi-provider LLM integration
│   │   │   ├── 📁 datasets/   # Dataset management
│   │   │   └── 📁 analytics/  # Performance analytics
│   │   ├── 📁 models/         # Pydantic models
│   │   │   ├── 📄 evaluation.py     # Evaluation models
│   │   │   ├── 📄 dataset.py        # Dataset models
│   │   │   └── 📄 metrics.py        # Metrics models
│   │   ├── 📁 services/       # Business services
│   │   │   ├── 📄 evaluation_service.py  # Evaluation logic
│   │   │   ├── 📄 dataset_service.py     # Dataset operations
│   │   │   └── 📄 analytics_service.py   # Analytics processing
│   │   ├── 📁 tasks/          # Celery background tasks
│   │   │   ├── 📄 evaluation_tasks.py    # Async evaluations
│   │   │   └── 📄 dataset_tasks.py       # Dataset processing
│   │   └── 📁 utils/          # Utilities
│   ├── 📁 docker/             # Docker configurations
│   ├── 📁 scripts/            # Deployment scripts
│   └── 📄 pyproject.toml      # Python dependencies (uv)
│
├── 📁 frontend/               # Next.js Dashboard
│   ├── 📁 src/
│   │   ├── 📁 app/            # Next.js App Router
│   │   │   ├── 📁 evaluations/      # Evaluation pages
│   │   │   ├── 📁 datasets/         # Dataset management
│   │   │   ├── 📁 analytics/        # Analytics dashboard
│   │   │   └── 📁 models/           # Model comparison
│   │   ├── 📁 components/     # React components
│   │   │   ├── 📁 ui/         # Base UI components
│   │   │   ├── 📁 charts/     # Data visualization
│   │   │   ├── 📁 evaluation/ # Evaluation components
│   │   │   └── 📁 datasets/   # Dataset components
│   │   ├── 📁 hooks/          # Custom React hooks
│   │   │   ├── 📄 use-evaluations.ts # Evaluation hooks
│   │   │   └── 📄 use-analytics.ts   # Analytics hooks
│   │   ├── 📁 lib/            # Utilities & API client
│   │   └── 📁 types/          # TypeScript definitions
│   └── 📄 package.json       # Node.js dependencies
│
├── 📄 docker-compose.yml     # Development services
├── 📄 docker-compose.prod.yml # Production setup
└── 📄 README.md              # This file
```

---

## 🧪 **Development**

### **Running Tests**

```bash
# Backend tests
cd backend
uv run pytest

# Frontend tests
cd frontend
npm test
```

### **Code Quality**

```bash
# Backend linting & formatting
cd backend
uv run black .
uv run isort .
uv run ruff check .
uv run mypy .

# Frontend linting
cd frontend
npm run lint
npm run type-check
```

### **Database Migrations**

```bash
cd backend
uv run alembic revision --autogenerate -m "Description"
uv run alembic upgrade head
```

---

## 🔍 **Monitoring & Health Checks**

- **Health Check**: `GET /health`
- **Metrics**: `GET /metrics` (Prometheus format)
- **Evaluation Status**: `GET /api/v1/evaluations/status`
- **Model Health**: `GET /api/v1/models/health`
- **Vector DB Health**: `GET /api/v1/datasets/health`
- **Cost Tracking**: `GET /api/v1/analytics/costs`

---

## 🤝 **Contributing**

### 🔧 **Setup Pre-commit Hooks**

We use pre-commit hooks to ensure code quality. Set them up before making changes:

```bash
# Install and setup pre-commit hooks
./scripts/setup-pre-commit.sh

# Or manually:
pip install pre-commit
pre-commit install
pre-commit run --all-files
```

The hooks will automatically check:

- **Python**: Black formatting, autoflake unused import removal, isort import sorting, flake8 linting, mypy type checking
- **Frontend**: Prettier formatting, ESLint linting
- **Security**: Secret detection, private key scanning
- **General**: Trailing whitespace, file endings, YAML/JSON validation

### 🚀 **Contribution Steps**

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. **Setup pre-commit hooks**: `./scripts/setup-pre-commit.sh`
4. Make your changes
5. Run tests: `uv run pytest && npm test`
6. Commit: `git commit -m 'Add amazing feature'` (pre-commit hooks will run automatically)
7. Push: `git push origin feature/amazing-feature`
8. Open a Pull Request

---

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🧱 **Tech Stack**

### **Backend**

- **[FastAPI](https://fastapi.tiangolo.com)** - Modern Python web framework
- **[PostgreSQL](https://postgresql.org)** - Primary database for evaluations and results
- **[Redis](https://redis.io)** - Caching and task queue
- **[Celery](https://celeryproject.org)** - Background task processing
- **[uv](https://github.com/astral-sh/uv)** - Ultra-fast Python package manager

### **Frontend**

- **[Next.js](https://nextjs.org)** - React framework with App Router
- **[TypeScript](https://typescriptlang.org)** - Type-safe JavaScript
- **[Tailwind CSS](https://tailwindcss.com)** - Utility-first CSS framework
- **[Recharts](https://recharts.org)** - Data visualization library

### **LLM Integration**

- **[OpenAI](https://openai.com)** - GPT-4 and GPT-3.5 models
- **[Anthropic](https://anthropic.com)** - Claude models
- **[Google AI](https://ai.google.dev)** - Gemini models
- **[Ollama](https://ollama.ai)** - Local open-source models

### **Vector Database**

- **[Qdrant](https://qdrant.tech)** - High-performance vector database
- **[Pinecone](https://pinecone.io)** - Managed vector database service

### **Deployment**

- **[Docker](https://docker.com)** - Containerization
- **[Docker Compose](https://docs.docker.com/compose)** - Multi-container orchestration

---

## 🙏 **Acknowledgments**

- **[OpenAI](https://openai.com)** - GPT models for evaluation and LLM-as-Judge
- **[Anthropic](https://anthropic.com)** - Claude models for nuanced evaluation
- **[FastAPI](https://fastapi.tiangolo.com)** - Modern Python web framework
- **[Next.js](https://nextjs.org)** - React framework for production
- **[uv](https://github.com/astral-sh/uv)** - Ultra-fast Python package manager
- **[Qdrant](https://qdrant.tech)** - Vector database for semantic search

---

## 📞 **Support**

- 📧 **Email**: <julien.wut@gmail.com>
- 🐛 **Issues**: [GitHub Issues](<https://github.com/Julien> W./evalia/issues)
- 📖 **Documentation**: [Project Wiki](<https://github.com/Julien> W./evalia/wiki)

---

## ✨ **Taglines**

> **"Evalia — Where prompts meet proof."**

> **"Smarter prompt engineering through data."**

> **"Benchmark, optimize, and evolve your prompts."**

> **"The evaluation layer for AI systems."**

---

<div align="center">

**Built with ❤️ for the AI engineering community**

[🧠 OpenAI](https://openai.com) • [🤖 Anthropic](https://anthropic.com) • [⚡ FastAPI](https://fastapi.tiangolo.com) • [⚛️ Next.js](https://nextjs.org) • [🔍 Qdrant](https://qdrant.tech)

**Transform your prompt engineering from trial-and-error into a measurable, scientific process.**

</div>
