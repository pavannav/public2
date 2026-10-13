# AI Assisted DevOps — Zero to Hero | Course Summary

**Channel:** Abhishekh Veeramalla (ytb-AbhishekhV)
**Playlist:** AI Assisted DevOps Zero to Hero
**Target Location:** `Z:\sharefolder\Transcripts\StudyGuides\AI-Assisted-DevOps-ytb-AbhishekhV\`

---

## Progress Tracker

| Day | Topic | Status | Study Guide |
|-----|-------|--------|-------------|
| **Day 0** | Course Syllabus & Overview | ✅ Completed (G3CS46T + CS46H) | [day-00-course_syllabus_and_overview.md](./day-00-course_syllabus_and_overview.md) |
| **Day 1** | Fundamentals of AI for DevOps Engineers | ✅ Completed (G3CS46T + CS46H) | [day-01-fundamentals_of_ai_for_devops.md](./day-01-fundamentals_of_ai_for_devops.md) |
| **Day 2** | Prompt Engineering Explained | ✅ Completed (G3CS46T + CS46H) | [day-02-prompt_engineering_explained.md](./day-02-prompt_engineering_explained.md) |
| **Day 3** | GenAI Project For DevOps Engineers | ✅ Completed (G3CS46T + CS46H) | [day-03-genai_project_for_devops.md](./day-03-genai_project_for_devops.md) |
| **Day 4** | AI Assisted Shell Scripting | ✅ Completed (CS46H) | [day-04-ai_assisted_shell_scripting.md](./day-04-ai_assisted_shell_scripting.md) |
| **Day 5** | AIOps Explained with Free Playgrounds | ✅ Completed (CS46H) | [day-05-aiops_explained.md](./day-05-aiops_explained.md) |
| **Day 6** | AIOps for Log Analysis — First AIOps Project | ✅ Completed (CS46H) | [day-06-aiops_for_log_analysis.md](./day-06-aiops_for_log_analysis.md) |
| **Day 7** | Create Your First AI Agent | ✅ Completed (CS46H) | [day-07-first_ai_agent_with_crewai.md](./day-07-first_ai_agent_with_crewai.md) |
| **Day 8** | AI Agent for Internal Documentation | ✅ Completed (CS46H) | [day-08-ai_agent_for_internal_docs.md](./day-08-ai_agent_for_internal_docs.md) |
| **Capstone** | AI DevSecOps Workflow on Pull Requests | ✅ Completed (CS46H) | [capstone-ai_devsecops_on_pull_request.md](./capstone-ai_devsecops_on_pull_request.md) |
| **Bonus 1** | kubectl Pod Topology AI Plugin | ✅ Completed (CS46H) | [bonus-01-kubectl_pod_topology_ai_plugin.md](./bonus-01-kubectl_pod_topology_ai_plugin.md) |
| **Bonus 2** | Enterprise AI Agent for Internal Docs — Retool | ✅ Completed (CS46H) | [bonus-02-enterprise_ai_agent_retool.md](./bonus-02-enterprise_ai_agent_retool.md) |
| **Bonus 3** | AI Deploys to VM + Container + K8s + Serverless | ✅ Completed (CS46H) | [bonus-03-ai_deploy_four_environments_windsurf.md](./bonus-03-ai_deploy_four_environments_windsurf.md) |
| **Bonus 4** | Docker Model Runner — Local LLMs Without Ollama | ✅ Completed (CS46H) | [bonus-04-docker_model_runner.md](./bonus-04-docker_model_runner.md) |
| **Bonus 5** | Run DeepSeek AI Locally in 2 Steps | ✅ Completed (CS46H) | [bonus-05-deepseek_ai_local_setup.md](./bonus-05-deepseek_ai_local_setup.md) |

---

## Stats

- **Total Days in Course:** 10 days + Capstone + 5 Bonus sessions = 16 total
- **Days Completed:** 16 (Day 0–8, Capstone, Bonus 1–5)
- **Last Updated:** 2026-10-12 (CS46H pass on all bonus sessions)
- **Model Used:** G3CS46T, CS46H

---

## Section Summaries

### Day 0: Course Syllabus & Overview ✅

**File:** [day-00-course_syllabus_and_overview.md](./day-00-course_syllabus_and_overview.md)

**Topics Covered:**
- Introduction to the AI Assisted DevOps course concept
- Channel background and available Zero-to-Hero courses
- Prerequisites (no strict requirements; DevOps fundamentals recommended)
- Full 10-day course syllabus breakdown

**Key Concepts:**
- **Generative AI for DevOps** — how DevOps engineers can use GenAI to enhance productivity
- **Prompt Engineering** — the foundational skill for all AI interactions (Day 2 highlighted as most critical)
- **Local LLMs** — running models on-premises for security/compliance
- **AIOps** — AI-powered observability for metrics, logs, and traces
- **AI Agents** — autonomous task execution for DevOps workflows
- **FinOps + AI** — cloud cost optimization with generative AI

**Day-by-Day Syllabus Summary:**
- Day 1: Intro to GenAI for DevOps, LLMs, AI tools landscape
- Day 2: Prompt Engineering (zero-shot, few-shot, N-shot, chain-of-thought)
- Day 3: Running LLMs locally — security/compliance use case, API calls
- Day 4: AI-assisted shell scripting and Python scripting
- Days 5 & 6: AIOps — observability + AI-powered log analysis project
- Day 7: AI + CI/CD — pipeline generation and log analysis
- Day 8: Building AI Agents for DevOps
- Day N: FinOps — AI-powered cloud cost optimization
- Capstone: End-to-end GenAI + DevOps showcase project

**Transcript Corrections:**
- "insns/inare/inger/inet/inire" → "engineers" (garbled audio)
- "metrix" → "metrics"
- "phobs" → "FinOps"
- "compains" → "compliance"
- "nsh prompt engineering" → "N-shot prompt engineering"

---

### Day 1: Fundamentals of AI for DevOps Engineers ✅

**File:** [day-01-fundamentals_of_ai_for_devops.md](./day-01-fundamentals_of_ai_for_devops.md)

**Topics Covered:**
- Traditional AI vs. Generative AI — definitions, use cases, differences
- Large Language Models (LLMs) — what they are and how they work
- How LLMs are trained (supercomputers, GPUs/TPUs, billions of parameters)
- Prompt Engineering introduction — why prompt quality matters
- The AI Landscape for DevOps Engineers (4 categories)
- Demo: VM health-check shell script via GitHub Copilot Workspace (AI Agent)

**Key Concepts:**
- **Traditional AI** — Prediction from historical data (e.g., AWS Predictive Autoscaling)
- **Generative AI** — Creates NEW content (text, images, code)
- **LLMs** — Sub-category of GenAI focused on text generation; answer from memory (parameters)
- **Parameters** — Numerical weights representing the model's learned knowledge (e.g., Llama 407B)
- **Prompt Engineering** — Crafting effective inputs to maximize LLM output quality
- **AI Chatbots** — ChatGPT, Claude, Llama, DeepSeek (category 1)
- **AI Agents** — GitHub Copilot Workspace, Bolt.new — autonomously plan AND execute (category 2)
- **AI Assistants** — GitHub Copilot IDE plugin, Pieces for Developers (category 3)
- **Python + FastAPI/Flask** — Programmatic LLM interaction (category 4)

**Demo Task:**
- Shell script `health.sh` monitors CPU, Memory, Disk (< 60% = Healthy)
- Supports `./health.sh` (status only) and `./health.sh explain` (with reasons)
- Created by GitHub Copilot Workspace in ~2–5 minutes (vs. 2–3 hours manually)

**Transcript Corrections:**
- "deop enges / devop sner / enger" → "DevOps engineers" (audio garbling, very frequent)
- "gpta Transformers" → "GPT-based Transformers"
- "genkins" → "Jenkins"
- "anible" → "Ansible"
- "Puli" → "Pulumi"
- "bold. new" → "Bolt.new"
- "Jango" → "Django"
- "zero short / few short / n short" → "zero-shot / few-shot / N-shot"
- "bid bucket" → "Bitbucket"
- "gilot workspace" → "GitHub Copilot Workspace"

---

### Day 2: Prompt Engineering Explained ✅

**File:** [day-02-prompt_engineering_explained.md](./day-02-prompt_engineering_explained.md)

**Topics Covered:**
- What is Prompt Engineering? — Layman's definition, inputs, and output conditioning
- The Dual Business Justifications: Output Precision (eliminating fluff) & Token Cost Optimization (FinOps for AI)
- Live Google AI Studio Token Benchmark — Bad prompt (2,473 tokens) vs. Good prompt (179 tokens, 92.7% reduction)
- Prompt Engineering Taxonomy: Zero-Shot, Few-Shot, Multi-Shot, and Chain-of-Thought (CoT)
- Hands-on Few-Shot Demo: Forcing corporate Bash script headers (`Author`, `Version`, `Date`) on virtual machine service auditing
- Abhishek's 4-Pillar Strategic Prompting Framework (Context, Instruction, Examples, Output Format)

**Key Concepts:**
- **Prompt vs. Prompt Engineering** — User input vs. systematic refinement to yield deterministic, high-quality technical assets
- **Token Economics** — API pricing model based on input + completion tokens (~100 words ≈ 60–80 tokens); scaling impact on 100+ developers
- **Zero-Shot (Direct) Prompting** — No reference examples; best for standard, widely documented syntax
- **Few-Shot Prompting** — Providing 2–3 reference examples; the primary technique for bridging enterprise context voids
- **Multi-Shot Prompting** — Scaling examples for complex domain rules and multi-cloud conditional branches
- **Chain-of-Thought (CoT)** — Cognitive step-by-step reasoning for deep architectural analysis and incident root cause isolation
- **4-Pillar Framework** — `Context` (persona/environment) + `Instruction` (task criteria) + `Examples` (few-shot exemplars) + `Output Format` (raw YAML/JSON schema)

**Demo Tasks:**
1. **Google AI Studio Token Count**:
   - `generate a kubernetes manifest for deployment resource` → 2,473 tokens (verbose tutorials, explanations)
   - `generate only kubernetes manifest for deployment resource` → 179 tokens (pure YAML, zero filler)
2. **Enterprise Shell Script Few-Shot Conditioning**:
   - Exemplar 1: Docker version with corporate header
   - Exemplar 2: Terraform version with corporate header
   - Query: Enumerate VM service/process versions → Produced standard script with identical author, version, and date headers

**Transcript Corrections:**
- "prompt ins saring" → "Prompt Engineering"
- "Equus deployment" → "Kubernetes deployment"
- "deployment yl file" → "deployment YAML file"
- "wordss" → "words"
- "deeps / deep seek" → "DeepSeek"
- "open aai" → "OpenAI"
- "AA model" → "AI model"
- "zero short / few short / n short" → "zero-shot / few-shot / N-shot"
- "chain off thoughts" → "chain-of-thought (CoT)"
- "mirala" → "Veeramalla"
- "close the comms" → "close the comments"
- "concised" → "concise"

---

### Day 3: GenAI Project For DevOps Engineers ✅

**File:** [day-03-genai_project_for_devops.md](./day-03-genai_project_for_devops.md)

**Topics Covered:**
- Polyglot DevOps challenge: automated multi-language Dockerfile generation (Java, Node.js, Python, Ruby on Rails, Groovy)
- Architectural trade-off analysis: Local LLMs (Ollama) vs. Hosted LLMs (Google AI Studio / OpenAI)
- Demystifying Ollama via the "Docker for LLMs" mental model (library, CLI, weights, daemon)
- Setting up Python virtual environments (`venv`) and installing client packages (`ollama`, `google-generativeai`)
- Building `generate_dockerfile.py` with programmatic Ollama chat calls and structural few-shot constraints
- Live multi-language testing: Groovy, Python, and Ruby on Rails
- Building `generate_dockerfile_gemini.py` with Google AI Studio free API keys and environment variables
- Live multi-stage build testing for Node.js (`AS builder`, alpine runtime, non-root user)
- Tokenomics, hyperscaler API pricing comparison, and DoS / Denial-of-Wallet threat modeling

**Key Concepts:**
- **Local LLMs** — Zero data leakage, strict compliance/privacy, zero token cost; requires local compute/RAM
- **Hosted LLMs** — Zero infra overhead, frontier model performance, instant execution; token billing and potential data exposure
- **Ollama Ecosystem** — Library = Docker Hub, CLI = docker CLI, weights = container images, daemon = dockerd (`localhost:11434`)
- **Meta Llama 3.2 1B** — Ultra-lightweight open-source model (~1.3 GB) capable of laptop-level execution
- **Constraint Enforcement** — Directing LLM to emit *only* pure Dockerfiles, eliminating markdown chatter
- **Multi-Stage Build Pattern** — Separating dependency build layers from minimal runtime containers (alpine/slim)
- **API Key Security & Hygiene** — Strict environment variable injection and immediate key revocation post-experimentation

**Demo Tasks:**
1. **Local Ollama Generator**:
   - Pulled `llama3.2:1b`, setup `venv`, installed `ollama`
   - Generated Dockerfiles for Groovy, Python, and Ruby on Rails
   - Added multi-stage constraint (`AS builder` -> runtime image)
2. **Hosted Google Gemini Generator**:
   - Acquired Google AI Studio API key, installed `google-generativeai`
   - Generated optimized multi-stage Node.js Dockerfile with `npm ci --only=production` and `USER node`

**Transcript Corrections:**
- "VNV / virtual machine" → "virtual environment (`venv`)"
- "Ollama h" → "`ollama --help`"
- "Ollama serve address already in use" → "Daemon already listening on port 11434"
- "open aai" → "OpenAI"
- "Lama / Lama 3.2 1b" → "Meta Llama 3.2 1B"
- "pip3 install requirements.txt" → "`pip install -r requirements.txt`"
- "Google generative AI" → "`google-generativeai`"
- "disto less" → "distroless"
- "gemini pro 1.5" → "Gemini 1.5 Pro"
- "Deep seek" → "DeepSeek"
- "DOS attack" → "Denial of Service (DoS / Denial of Wallet)"

---

### Day 4: AI Assisted Shell Scripting ✅

**File:** [day-04-ai_assisted_shell_scripting.md](./day-04-ai_assisted_shell_scripting.md)

**Topics Covered:**
- Why shell scripting is the best AI use case in DevOps (commands are stable/backward-compatible)
- AI pair programming concept — the senior developer analogy
- GitHub Copilot installation and usage as a free AI pair programmer
- 4 best practices: meaningful file name, description block, variable names, ask for explanations
- Demo: ws_vpc_create.sh — VPC + public subnet via Copilot (zero lines of code typed)
- Assignment: extend script to accept create / 	eardown command-line arguments

**Key Concepts:**
- **AI Pair Programming** — AI watches you type and suggests the next line in real time
- **Shell Stability** — Shell commands almost never change; AI-generated shell scripts are reliable long-term
- **Description Block** — Multi-line comment at file top acts as the prompt to Copilot
- **command -v aws** — POSIX-portable way to check if AWS CLI is in PATH
- **aws sts get-caller-identity** — Validates that AWS credentials are configured and valid
- **chmod 777 vs 755 vs 700** — Permission levels for shell scripts

**Transcript Corrections:**
- "abishek" → "Abhishek"
- "fur Loop" → "for loop"
- "grip" → "grep"
- "cadr" → "CIDR"
- "bpc / bpcreate / Tri 7" → "VPC / aws_vpc_create.sh / chmod 777"
- "taay down / pair down" → "teardown"
- "CVS" → "CVEs (Common Vulnerabilities and Exposures)"
- "Dosh" → ".sh (shell extension)"

---

---

### Day 5 — AIOps Explained with Free Playgrounds (CS46H)

**Core concept:** AIOps = Traditional AI applied to observability data for a predictive approach to IT operations — NOT GenAI for code generation.

**Key distinction:** Using GenAI to generate Dockerfiles, Kubernetes manifests, shell scripts, or CI/CD pipelines is "AI-Assisted DevOps," not AIOps. AIOps specifically refers to Traditional AI (ML models) trained on metrics/logs/traces to detect anomalies and predict incidents before they cause downtime.

**The business problem:** Reactive observability (monitor → alert → human reacts) still allows downtime. By the time an engineer responds to a memory alert at 80%, the application may already be at 100%. AIOps adds a predictive layer that identifies patterns days or weeks before thresholds are breached.

**Scale driver:** At 100 services × 100 metrics each = 10,000 metrics, human monitoring is not viable. AIOps platforms monitor all metrics simultaneously, continuously.

**Weather analogy:** Traditional AI in AIOps works like weather prediction — feeding months of historical observability data into an ML model that recognizes patterns and forecasts future states (e.g., "memory will hit 80% in 10 days").

**GenAI's emerging role:** Traditional AI predicts → GenAI Agent auto-remediates (e.g., instructs Karpenter to provision a node before memory exhaustion). This hybrid is not yet mature as of recording.

**Enterprise demos:**
- **Dynatrace Davis:** E-commerce order forecasting (predicted 63 orders on March 25), disk capacity prediction (flat curve → flat prediction = no anomalies)
- **ManageEngine Zia:** 1,085 monitors → 66 confirmed anomalies; homepage load time surged 15,609ms in Canberra, 1.9x above threshold, 12am–10am pattern

**Platforms:** Dynatrace (Davis), ManageEngine (Zia), Datadog, Grafana Cloud — all commercial; free playgrounds available for Dynatrace and ManageEngine.

**File:** `day-05-aiops_explained.md` | **Model:** CS46H | **Status:** ✅ Completed


---

### Day 6 — AIOps for Log Analysis — First AIOps Project using Python (CS46H)

**Core concept:** Applies AIOps to the second observability pillar — logs. Demonstrates why traditional log analysis (ELK + threshold scripts) is reactive and limited to known ERROR patterns, while AIOps (Isolation Forest ML) detects unknown anomalies across ALL log levels.

**The critical insight:** Developers assign log levels incorrectly. Critical security and performance events are often logged as WARNING or INFO. A traditional script counting ERROR logs misses these entirely. Isolation Forest detects the anomalous PATTERN regardless of the developer-assigned level.

**Two scripts built:**
- `simple_log_analysis.py` — traditional: pandas + regex + Counter; counts ERROR logs per 30-second window; human-defined threshold; detected only 2 error bursts
- `aiops_log_analysis.py` — AIOps: pandas + scikit-learn Isolation Forest; label encoding (INFO=1, WARNING=2, ERROR=3, CRITICAL=4); contamination=0.1; detected 6 anomalies including failed logins, slow SQL queries, and unauthorized attempts — all logged as WARNING

**Key Isolation Forest parameters:** `contamination=0.1` (expect 10% anomalies; lower = stricter), label encoding for log levels, `fit_predict` returns -1 (anomaly) or +1 (normal).

**Setup:** `python3 -m venv venv` → `source venv/bin/activate` → `pip install pandas scikit-learn`

**DIY vs. Enterprise:** Same algorithm (Isolation Forest), vastly different accuracy — enterprise platforms train on millions of lines continuously; this script uses ~1,000 lines.

**File:** `day-06-aiops_for_log_analysis.md` | **Model:** CS46H | **Status:** ✅ Completed


---

### Day 7 — Create Your First AI Agent with Zero Coding and Zero Cost (CS46H)

**Core concept:** AI agents implement tasks autonomously end-to-end; AI assistants (ChatGPT) only respond conversationally and require the user to manually stitch outputs together. CrewAI is an open-source framework that enables multi-agent workflows using local LLMs (Ollama) — zero cost, zero data exposure.

**Key distinction:** Agent = autonomous task executor. Assistant = conversational responder. Both need LLMs, but agents orchestrate LLM calls across multiple steps automatically.

**Frameworks covered:** AutoGen (Microsoft), LangGraph (LangChain), CrewAI (used today).

**Project built:** Two-agent Kubernetes research pipeline. Agent 1 (Researcher) queries Llama 3.1 via Ollama and returns 10 bullet points of trends. Agent 2 (Reporting Analyst) expands them into a complete eport.md blog post.

**Setup:** pip install crewai → crewai create crew <name> (scaffolds project) → select Ollama + llama3.1 → edit main.py topic → crewai install → crewai run

**File architecture:** gents.yaml (role/goal/backstory) + 	asks.yaml (description/expected_output) + main.py (topic input only) + crew.py (orchestration decorators — do not modify).

**Accuracy trade-off:** Llama 3.1 (4.7B parameters) has older training data; Llama 3.3 or OpenAI API gives more current information at the cost of money (~.20/request) and data exposure.

**File:** day-07-first_ai_agent_with_crewai.md | **Model:** CS46H | **Status:** ✅ Completed

---

### Day 8 — AI Agent for Internal Documentation in 30 Minutes (CS46H)

**Core concept:** Build a single-agent CrewAI system that reads confidential internal documentation (PDF) and answers employee questions using a local LLM — zero data exposure, zero cost.

**Problem solved:** Internal docs are confidential (can't use ChatGPT); hundreds of pages are hard to navigate; search returns documents, not answers. The agent synthesizes direct answers from the PDF.

**Architecture:** Single agent + CrewAI knowledge source (PDF) + Ollama/Llama 3.1 (local). No data leaves the machine. One agent is sufficient because the task is pure retrieval + synthesis.

**Shortcut used:** Instead of building from scratch, clone the crewai-examples repository and adapt the MetaQuest Knowledge example — swap the PDF, update 4 files (agents.yaml, tasks.yaml, main.py, crew.py).

**Key setup steps:** .env file required to override CrewAI's default OpenAI to Ollama (MODEL=ollama/llama3.1, API_BASE=http://localhost:11434). Agent key in agents.yaml must exactly match tasks.yaml gent: field — mismatch = KeyError.

**Demo:** Viraala observability platform (fictional) — agent correctly answered "What is Viraala?" and "How does Viraala compare to Prometheus?" using only PDF content.

**Training:** Add representative Q&A examples to main.py train() section for improved accuracy on edge cases; more examples = better enterprise-grade answers.

**File:** day-08-ai_agent_for_internal_docs.md | **Model:** CS46H | **Status:** ✅ Completed


---

### Capstone — AI DevSecOps Workflow on Pull Requests (CS46H)

**File:** [capstone-ai_devsecops_on_pull_request.md](./capstone-ai_devsecops_on_pull_request.md)

**Topics Covered:**
- Why AI-generated code introduces security vulnerabilities that need automated review
- Sim.ai platform: Mothership (prompt-to-workflow) vs. drag-and-drop Workflow Builder
- 5-block DevSecOps workflow: GitHub PR Trigger → Extract Data → Fetch Files → Security Agent → Post PR Comment
- GitHub webhook configuration for single-URL coverage of unlimited repositories
- Natural language security checks: hardcoded secrets, injection vulnerabilities, unsafe deserialization
- Demo: Hardcoded password detected in `backend/src/db.js` — CRITICAL severity, merge blocked
- Workflow extension: adding Slack notifications, email, labels, auto-close via additional blocks

**Key Concepts:**
- **Sim.ai** — No-code AI workflow platform; Mothership generates workflows from natural language prompts
- **Mothership** — AI that reads a prompt file from the workspace and builds the full workflow automatically
- **Prompt-as-configuration** — Security rules defined in natural language; add/remove checks by editing the prompt
- **BYOM (Bring Your Own Model)** — Connect any LLM (OpenAI, Anthropic, local) to the security agent
- **GitHub Webhook** — One URL configured on any number of repositories triggers the workflow on every PR
- **Sim.ai Secrets** — Secure storage for GitHub tokens, API keys, database credentials (never hardcoded)
- **5-block architecture** — Trigger → Extract → Fetch → Analyze → Comment; each block independently replaceable
- **1,000 free credits** — Sim.ai free tier; Pro/Max plans for production usage (coupon: `abi20` = 20% off)

**Demo Results:**
- PR with hardcoded password in `backend/src/db.js` → CRITICAL severity → BLOCK MERGE recommendation
- Complete security report posted as PR comment in under 60 seconds

**Transcript Corrections:**
- "Sim.ai" referred to as just "sim" or "sim AI" in places → Sim.ai (the platform name)
- "mothership" mentioned multiple times → Mothership (capitalized as a feature name)




---

### Bonus 1 — kubectl Pod Topology AI Plugin (CS46H)

**File:** [bonus-01-kubectl_pod_topology_ai_plugin.md](./bonus-01-kubectl_pod_topology_ai_plugin.md)

**Topics Covered:**
- Building a kubectl plugin in Python that generates visual Kubernetes topology images
- Two-API architecture: OpenAI (cluster analysis + prompt) + Luma AI (image generation)
- kubectl plugin discovery mechanism (executable with `kubectl-` prefix in PATH)
- Three input parameters: pod name, namespace, output path
- Installation via `install.sh` (bundles Python package, adds to PATH)
- Demo: nginx-topology pod → visual image showing internet → ingress (no TLS) → service → pod (Running/green)
- Extensions: S3/Google Drive output, Gateway API support, `--watch` mode

**Key Concepts:**
- **kubectl plugin** — Any executable in PATH with the `kubectl-` prefix is recognized as a sub-command
- **Luma AI** — Purpose-built image generation API (platform.lumalabs.ai); more cost-effective than OpenAI for images
- **Two-model pattern** — OpenAI handles analysis/text reasoning; Luma AI handles image generation
- **Status icons** — Running = green, CrashLoopBackOff = red, Pending = yellow
- **`.env.local`** — Never commit API keys; use `.env.local` excluded from `.gitignore`

---

### Bonus 2 — Enterprise AI Agent for Internal Documentation with Retool (CS46H)

**File:** [bonus-02-enterprise_ai_agent_retool.md](./bonus-02-enterprise_ai_agent_retool.md)

**Topics Covered:**
- Why organizations block ChatGPT (security, compliance, data training risk)
- Retool platform: enterprise-grade AI agent/workflow/app builder with SSO, RBAC, BYOM
- Creating agents: triggers (Chat + Email), Configuration Assistant, model selection
- Retool Vectors: built-in vector database for unstructured document storage (PDFs)
- Adding tools: retrieve tool connected to a Retool Vector with default vector/document names
- Email trigger for CI/CD integration (agent invoked from pipeline failures)
- Demo: "Superbility" observability platform agent — correctly answered questions from PDF

**Key Concepts:**
- **Retool Vectors** — Managed vector database; upload PDFs for LLM retrieval without external Pinecone/Chroma
- **Configuration Assistant** — Plain English → formal agent instructions
- **Email trigger** — CI/CD pipeline can invoke the agent by emailing it (zero-code integration)
- **RBAC** — Role-Based Access Control; defines who can access which agents, apps, and data
- **SSO** — Okta, Auth0, OneLogin supported; no manual user onboarding

---

### Bonus 3 — AI Deploys to All Four Environments with Windsurf Cascade (CS46H)

**File:** [bonus-03-ai_deploy_four_environments_windsurf.md](./bonus-03-ai_deploy_four_environments_windsurf.md)

**Topics Covered:**
- Windsurf IDE: Cascade agent (Cmd/Ctrl+L), Deep Wiki, Code Lenses
- Ultimate DevOps test: deploy one app to VM + Containers + Kubernetes + Serverless
- App generation: tic-tac-toe (HTML/CSS/JS) from single natural language prompt
- EC2 deployment: AWS CLI + security group + user data script (nginx install + file copy)
- Docker Compose: 4-container setup (app + nginx LB + Redis + Prometheus) with health checks
- Kubernetes (kind): namespace + configmap + deployment + service + ingress; CrashLoopBackOff self-healed
- Lambda: IAM role + Lambda function + API Gateway + deploy.sh — all via AWS CLI
- Cascade autonomously fixed nginx permission error during K8s deployment without human input

**Key Concepts:**
- **Cascade** — Windsurf's AI coding agent; generates code AND executes commands AND deploys
- **Auto access** — Cascade runs shell commands without approval per command (use carefully)
- **Autonomous error recovery** — Cascade detected CrashLoopBackOff, read logs, fixed manifest, redeployed
- **Environment-aware decisions** — Cascade recognized kind cluster → used port-forward instead of Ingress
- **7–8 hours → 20–30 minutes** — estimated productivity gain from manual vs. AI-assisted deployment

---

### Bonus 4 — Docker Model Runner: Local LLMs Without Ollama (CS46H)

**File:** [bonus-04-docker_model_runner.md](./bonus-04-docker_model_runner.md)

**Topics Covered:**
- Docker Model Runner: feature in Docker Desktop 4.40+ for running local LLMs
- CLI commands mirror Docker container commands (pull/run/rm/list)
- Docker AI Hub (hub.docker.com/u/ai): model registry equivalent to Docker Hub
- SmolLM2: 135M parameters, 256 MB — fastest local model; vs. Llama 3 (4.7B+)
- Single-prompt mode vs. interactive chat mode
- Official Docker example repository: Python/Node.js/Go AI assistants
- Integration via `.env` file specifying model name
- Comparison: Docker Model Runner vs. Ollama — consolidation benefit for Docker users

**Key Concepts:**
- **Docker Model Runner** — Requires Docker Desktop 4.40+; not available in Docker Engine headless
- **SmolLM2** — 135M parameters, 256 MB, fastest inference; trade-off: lower quality than Llama
- **hub.docker.com/u/ai** — Docker's model registry; pull models same as container images
- **`docker model pull/run/rm/list`** — Direct parallel to `docker pull/run/rm/images`
- **One tool**: containers AND models managed in Docker Desktop (vs. Docker + Ollama separately)

---

### Bonus 5 — Run DeepSeek AI Locally in 2 Steps (CS46H)

**File:** [bonus-05-deepseek_ai_local_setup.md](./bonus-05-deepseek_ai_local_setup.md)

**Topics Covered:**
- DeepSeek R1: Chinese open-source LLM matching OpenAI o3 on SWE-bench benchmarks
- Training cost: $5.5M reported vs. billions for comparable US models — industry disruption
- API cost: $0.15 per 1M tokens (DeepSeek) vs. $7.50 (OpenAI o3) — 98% cheaper
- Open source: download, run locally, use in commercial products
- 2-step local setup: install Ollama → `ollama run deepseek-r1:1.5b`
- Model sizes: 1.5B (1.1 GB, recommended local) to 671B (enterprise)
- Chat UI options: Open WebUI (browser) or Chatbox AI (native desktop app)
- Chatbox AI: Settings → Ollama → `localhost:11434` → select model

**Key Concepts:**
- **SWE-bench** — Software Engineering Benchmark; DeepSeek R1 matches OpenAI o3
- **Open source** — Weights are downloadable; inference is free when self-hosted
- **Data privacy**: local Ollama = no data leaves machine; DeepSeek cloud API = data to China
- **Cost comparison**: DeepSeek API 98% cheaper than OpenAI o3 per million tokens
- **Chatbox AI** — Native desktop Ollama client; alternative to Open WebUI for local model chat


