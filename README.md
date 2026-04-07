<div align="center">

<br />

# ModelNorth

**Sovereign AI Infrastructure for Regulated Markets**

[![License](https://img.shields.io/badge/license-Apache%202.0-E8A020?style=flat-square)](LICENSE)
[![Status](https://img.shields.io/badge/status-production%20ready-00C896?style=flat-square)](#)
[![Deployment](https://img.shields.io/badge/deployment-air%20gapped%20capable-111111?style=flat-square)](#)
[![Region](https://img.shields.io/badge/headquarters-Pakistan-006600?style=flat-square)](#)

**[Website](https://modelnorth.com)** · **[Documentation](https://docs.modelnorth.ai)** · **[Contact](mailto:hello@modelnorth.com)**

</div>

---

## The Problem

Organizations in regulated markets face a structural disadvantage in AI adoption. Global cloud providers operate under foreign jurisdictions. Data residency requirements conflict with API architectures. Compliance frameworks demand audit trails that SaaS platforms cannot provide.

The result: **sovereignty gaps** that expose institutions to regulatory risk, data exfiltration, and operational dependency on infrastructure they do not control.

---

## Our Solution

ModelNorth designs, builds, and deploys **sovereign AI systems** that operate entirely within your perimeter. No foreign API dependencies. No shared infrastructure. No ambiguity about data ownership or residency.

We serve enterprises and government entities that treat data sovereignty as a hard requirement, not a preference.

### Core Capabilities

| Domain | Application | Compliance Focus |
|--------|-------------|------------------|
| **Security & Threat Intelligence** | Model-native threat detection, adversarial pattern recognition, automated incident response | SOC 2, ISO 27001, NIST CSF |
| **Talent & Workforce Intelligence** | Compliance-aware hiring pipelines, Emiratization/diversity mandate tracking, audit-ready HR workflows | GDPR, local labor regulations |
| **Market Intelligence** | Real-time signal extraction, competitive analysis, risk surface monitoring | Data residency, financial regulations |
| **Managed Infrastructure** | Self-hosted ERP, communications, document management with unified AI layer | Air-gapped deployment options |
| **Knowledge Management** | RAG-based enterprise search, secure AI workspaces, verifiable document lineage | Zero external telemetry |
| **Clinical AI** *(Research)* | Diagnostic support tools with differential privacy and federated learning capabilities | HIPAA, FDA 21 CFR Part 11 |

---

## Architecture Principles

### Zero-Trust by Design
- **No external API dependencies** in production deployments
- **Self-hosted inference** via Ollama, vLLM, or custom model serving
- **Zero telemetry** — no usage data leaves your perimeter
- **Air-gapped capable** — full functionality without internet connectivity

### Compliance-First Engineering
- **Data residency guarantees** — all processing within specified jurisdictions
- **Immutable audit trails** — complete prompt/response logging with cryptographic verification
- **Role-based access control (RBAC)** at the vector store level
- **Model versioning and rollback** capabilities for regulated environments

### Operational Sovereignty
- **Infrastructure as Code** — reproducible deployments on Hetzner, on-premise, or sovereign cloud
- **Self-healing systems** — automated failover without external orchestration dependencies
- **Vendor independence** — migrate between infrastructure providers without re-architecture

---

## Technology Stack

<table>
<tr>
<td width="33%">

**Frontend**
- Next.js 14 (App Router)
- React Server Components
- Tailwind CSS + shadcn/ui
- Radix UI primitives

</td>
<td width="33%">

**Backend & APIs**
- FastAPI (Python)
- Node.js (Express/NestJS)
- BullMQ (Redis-based queues)
- GraphQL federation

</td>
<td width="33%">

**AI & Orchestration**
- LangGraph (stateful agent workflows)
- CrewAI (multi-agent systems)
- Anthropic Claude API (optional)
- Ollama (local inference)

</td>
</tr>
<tr>
<td width="33%">

**Data Layer**
- Supabase (PostgreSQL)
- Redis (caching/sessions)
- Upstash (serverless Redis)
- Qdrant/Pinecone (vector stores)

</td>
<td width="33%">

**Infrastructure**
- Docker + Docker Compose
- Hetzner VPS (EU/Germany)
- Cloudflare Tunnel (optional)
- Dokploy (self-hosted PaaS)

</td>
<td width="33%">

**Observability**
- Self-hosted Langfuse
- Prometheus + Grafana
- Pino (structured logging)
- Zero external telemetry

</td>
</tr>
</table>

---

## Deployment Models

### Cloud Sovereign
Deployed on Hetzner Cloud (Germany) with GDPR-compliant infrastructure. Suitable for EU data residency requirements.

### On-Premise
Full stack deployment within your data center. Requires Kubernetes or Docker Swarm cluster. Includes hardware security module (HSM) integration for key management.

### Air-Gapped
Complete offline operation. No external network dependencies. Update packages delivered via secure physical media. Suitable for classified environments.

---

## Security & Compliance

- **Data Classification**: Automated PII detection and redaction at the prompt layer
- **Access Control**: Context-based access control (CBAC) for vector stores and knowledge bases
- **Audit Logging**: Immutable logs of all AI interactions with cryptographic verification
- **Red Teaming**: Quarterly adversarial testing for prompt injection and data exfiltration vectors
- **Model Governance**: SBOMs for all model dependencies, sunset criteria for model retirement

---

## Getting Started

### Prerequisites
- Docker 24.0+ and Docker Compose
- 16GB RAM minimum (32GB recommended for local LLM inference)
- Ubuntu 22.04 LTS or compatible Linux distribution

### Quick Start (Development)
```bash
# Clone the repository
git clone https://github.com/modelnorth/infrastructure.git
cd infrastructure

# Configure environment
cp .env.example .env
# Edit .env with your configuration

# Deploy stack
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d

# Initialize database
docker-compose exec api python scripts/init_db.py
