# AI Assisted DevOps — Assignments & Lab Exercises

---

<details>
<summary><b>Day 0: Course Syllabus & Overview — Review Questions & Lab Exercises</b></summary>

## Day 0: Course Syllabus & Overview

### 📝 Review Questions

#### Beginner Level (0–1 Years Experience)

1. What is "AI Assisted DevOps" and how does it differ from traditional DevOps?
2. What is a Large Language Model (LLM)? Name two examples.
3. Why is prompt engineering considered the most important foundational skill for this course?
4. What does the instructor mean when he says "the medium to communicate with LLMs is prompt engineering"? Explain in your own words.
5. What are the three types of data DevOps engineers deal with in observability?
6. Why would a DevOps engineer run an LLM locally instead of using ChatGPT?
7. What is AIOps? Give a simple definition.
8. What is a CI/CD pipeline? Why would you want AI to assist with it?
9. What is the Capstone project for, and why is it important for your career?
10. What is the course schedule cadence (how many videos per week)?

#### Intermediate Level (1–3 Years Experience)

1. Describe the security and compliance concern with sending DevOps-related prompts to public LLMs like ChatGPT. What data might be at risk?
2. Explain the difference between zero-shot, few-shot, and N-shot prompting techniques with examples.
3. Why is AIOps particularly valuable for observability vs. traditional alerting? Explain the limitation of human-driven alert management.
4. What is the difference between an LLM and an AI Agent? How does an AI Agent add capabilities beyond an LLM?
5. Explain the concept of FinOps and why Generative AI is especially useful in this domain.
6. What is "chain-of-thought" prompting and when would you use it in a DevOps context?
7. Given a DevOps workflow that involves writing Dockerfiles, Kubernetes manifests, and shell scripts — which days of the course would be most directly applicable?
8. Why might open-source tools like Prometheus + Grafana be insufficient for a realistic AIOps demonstration?

#### Expert Level (3+ Years Experience)

1. Design a high-level architecture for a DevOps workflow that uses local LLMs to generate Kubernetes manifests without exposing data to public APIs. What components would you need?
2. Compare the security models of: (a) using ChatGPT with DevOps prompts, (b) using a local LLM via Ollama, and (c) using an enterprise-managed AI API. What are the trade-offs?
3. How could AI agents be integrated into a GitOps workflow? Describe the interaction model.
4. Evaluate the ROI of AIOps for a mid-size company running 100 microservices. What specific productivity gains would you expect?
5. What are the limitations of current Generative AI models in the context of DevOps automation? What types of tasks are they NOT well-suited for?

#### Cumulative / Cross-Day Questions (To revisit as course progresses)

1. After completing Days 1–3: How does your understanding of prompt engineering change after seeing it applied with a local LLM?
2. After completing Days 5–6: Describe a specific observability scenario from your own experience where AI-powered log analysis could have saved time or prevented an outage.
3. After completing Day 8: Design an AI agent that could automate the on-call escalation process for a DevOps team.
4. After the Capstone: What would you add or change in your capstone project if you had another week?

---

### 🔬 Lab Exercises

#### Foundation Labs (Complete Before Day 1)

**Lab 0.1 — Channel Exploration**
- Visit the Abhishekh Veeramalla YouTube channel
- Find and bookmark the DevOps Zero to Hero playlist
- List 5 technologies covered across the available course playlists
- **Goal:** Understand the breadth of the channel's content and where AI Assisted DevOps fits

**Lab 0.2 — AI Tools Inventory**
- Research and list 5 AI tools that a DevOps engineer could use today
- For each tool, note: (a) what DevOps task it helps with, (b) whether it runs locally or in the cloud, (c) whether it is free or paid
- Example categories to research: code generation, infrastructure-as-code, log analysis, CI/CD optimization
- **Goal:** Build awareness of the AI tool landscape before Day 1

**Lab 0.3 — Identify Your Security Risk**
- Review your current DevOps workflow
- List any scenarios where you might be tempted to paste sensitive data (infrastructure details, credentials, configs) into a public AI tool
- Think through what data should NEVER go to a public LLM
- **Goal:** Develop a personal security mindset for AI tool usage

**Lab 0.4 — Observability Data Awareness**
- In your current or a sample environment, identify:
  - What metrics are you collecting? (CPU, memory, etc.)
  - What logs are being generated? (application, system, audit)
  - Are distributed traces set up?
- **Goal:** Understand the data scale you'll be working with in Days 5 & 6

**Lab 0.5 — Prerequisite Self-Assessment**
- Rate yourself (1-5) on each of the following:
  - Docker fundamentals
  - Kubernetes basics
  - CI/CD pipeline experience
  - Python scripting
  - Shell scripting
  - Observability tools (Prometheus, Grafana, etc.)
- Identify your top 2 weakest areas and spend 1 hour refreshing before Day 1
- **Goal:** Identify knowledge gaps before the course starts

</details>

---

<details>
<summary><b>Day 1: Fundamentals of AI for DevOps Engineers — Review Questions & Lab Exercises</b></summary>

## Day 1: Fundamentals of AI for DevOps Engineers

### 📝 Review Questions

#### Beginner Level (0–1 Years Experience)

1. What is the fundamental difference between Traditional AI and Generative AI? Provide one concrete DevOps example for each.
2. What is a Large Language Model (LLM), and why is it considered a subcategory of Generative AI?
3. How do LLMs answer user prompts? Do they search the web in real-time, or do they retrieve answers from parameters encoded during training?
4. What are "parameters" in the context of an LLM, and how do they correlate to the model's capabilities and memory?
5. What is Prompt Engineering? Why is it considered the primary interface between human engineers and LLMs?
6. Name and describe the four categories of the AI landscape for DevOps engineers outlined in the lecture.
7. What is the difference between an AI Chatbot (e.g., ChatGPT) and an AI Coding Assistant (e.g., GitHub Copilot IDE plugin)?
8. What is an AI Agent (e.g., GitHub Copilot Workspace, Bolt.new), and how does its workflow differ from an AI Assistant?
9. In the health-check shell script demo (`health.sh`), what three operating system metrics were collected and evaluated?
10. What threshold value was used in the demo to classify a VM as "Healthy" vs. "Not Healthy"?

#### Intermediate Level (1–3 Years Experience)

1. Explain how **AWS Predictive Auto Scaling** functions as a Traditional AI system. What data does it train on, and how does its scaling trigger differ from reactive Target Tracking scaling?
2. Compare running a 7-billion parameter (7B) model vs. a 70-billion parameter (70B) or 400-billion parameter (405B) model for DevOps automation tasks. What are the trade-offs regarding RAM/VRAM, inference latency, compute cost, and reasoning capability?
3. In Linux systems diagnostics, why is parsing `free` memory often misunderstood by junior engineers? What is the difference between the `free` field and the `available` field, and why is `available` more critical for monitoring scripts?
4. When collecting CPU utilization using `top -bn1 | grep "Cpu(s)"`, what is the architectural significance of the `wa` (I/O Wait) and `st` (Steal Time) metrics in cloud environments (such as AWS EC2)?
5. Explain the concept of "hallucination" in LLMs. Why does it happen during text generation, and what prompt engineering strategies can a DevOps engineer use to prevent hallucinated CLI flags or configuration parameters?
6. How does GitHub Copilot Workspace bridge the gap between human intent and automated execution in Git-centric workflows (Issues → Specification → Plan → Implementation → Pull Request)?
7. Contrast zero-shot prompting with few-shot prompting in the context of writing an automated Ansible playbook or Terraform manifest.
8. How can a DevOps engineer programmatically integrate LLMs into existing CI/CD pipelines using Python (e.g., FastAPI, Flask, or direct SDK calls) to automate pull request code reviews or pipeline failure diagnoses?

#### Expert Level (3+ Years Experience)

1. **Autonomous Self-Healing Infrastructure**: Design the end-to-end architecture of an AI Agent designed to detect, diagnose, and remediate Kubernetes pod crash loops (`CrashLoopBackOff`). How do you architect the feedback loop, tool-calling interfaces (kubectl read/write), blast-radius limits, human-in-the-loop approvals, and rollback strategies?
2. **Proprietary vs. Self-Hosted Open-Weights LLMs**: Formulate an enterprise decision framework for evaluating whether to use commercial hosted models (e.g., Claude 3.5 Sonnet, GPT-4o) vs. self-hosted open-weights models (e.g., Llama 3 70B, DeepSeek) for analyzing internal CI/CD build logs containing proprietary source code and infrastructure topologies. Address data sovereignty, compliance (SOC2/HIPAA), cold-start latency, and TCO.
3. **Evaluating AI-Generated Infrastructure as Code (IaC)**: If an AI Agent generates Terraform code or Kubernetes manifests automatically, what automated validation gates and policy-as-code frameworks (e.g., OPA/Rego, Checkov, Trivy, `terraform validate`) must be placed in the automated CI pipeline to prevent catastrophic misconfigurations or security vulnerabilities?
4. **Context Window vs. Parameter Storage in Production**: LLM parameters store general knowledge learned during pre-training, while the context window provides runtime working memory. If you want an LLM to accurately debug a company's custom internal Helm chart syntax, would you fine-tune the model's parameters or use Retrieval-Augmented Generation (RAG) with the context window? Justify your architectural choice.
5. **Prompt Injection & Security Threat Modeling**: What security attack vectors emerge when allowing an AI Agent to execute shell scripts or interact with internal APIs based on external inputs (such as user-submitted pull requests or bug tickets)? How do you mitigate Indirect Prompt Injection?

#### Cumulative / Cross-Day Questions (To revisit as course progresses)

1. **Connecting Day 1 to Day 2**: In Day 1, prompt quality was highlighted as the defining factor for output quality ("garbage in, garbage out"). How will the formal prompting frameworks introduced in Day 2 (such as persona adoption, delimiting inputs, and chain-of-thought) directly address the script generation limitations experienced in Day 1?
2. **Connecting Day 1 to Day 3**: In Day 1, we learned that LLMs run in the cloud require sending prompts over the internet. When we cover local LLM hosting in Day 3, what specific security and compliance barriers identified in Day 1 will be resolved?
3. **Connecting Day 1 to Days 5 & 6 (AIOps)**: How does the convergence of Traditional AI (anomaly detection algorithms) and Generative AI (LLM log interpretation) form the foundation of modern AIOps platforms?
4. **Connecting Day 1 to Day 7 & 8 (AI Agents)**: Reflect on the Copilot Workspace demo from Day 1. When we build our own autonomous AI Agents from scratch in Days 7 and 8, what core agentic components (planner, memory, execution tools, reflection) will we need to construct programmatically?

---

### 🔬 Lab Exercises

#### Lab 1.1 — Traditional AI in Practice: AWS Predictive Auto Scaling Analysis
- **Objective**: Understand and analyze how Traditional AI operates using historical telemetry data in cloud environments.
- **Steps**:
  1. Review AWS Auto Scaling documentation on Predictive Scaling policies.
  2. Identify the minimum historical metric timeline required by AWS Predictive Auto Scaling (typically 24–48 hours of baseline data).
  3. Compare the behavior of a standard Target Tracking policy (reactive: CPU > 70% triggers scale-out after breach) against a Predictive Scaling policy (proactive: model forecasts traffic surge at 09:00 AM and triggers scale-out at 08:45 AM).
  4. Write a brief architectural comparison summarizing why Traditional AI (time-series forecasting) is superior to Generative AI for autoscaling decisions.
- **Verification**: Document the key distinction between predictive regression algorithms and generative text models.

#### Lab 1.2 — Generative AI Prompting Benchmark for DevOps Tasks
- **Objective**: Experience firsthand how Generative AI synthesizes new infrastructure code from zero, and test model responses across different prompt complexities.
- **Steps**:
  1. Open an AI Chatbot (ChatGPT, Claude, or DeepSeek).
  2. **Prompt 1 (Vague)**: `"Write a script to check server status."` — Observe the output format, assumptions, and lack of customization.
  3. **Prompt 2 (Specific & Constrained)**: `"Write a POSIX-compliant Bash script named health.sh that checks CPU, RAM, and root disk usage. If any metric exceeds 60%, print 'Not Healthy' with detailed explanations. If all metrics are below 60%, print 'Healthy'. Support an optional 'explain' argument and include appropriate Linux exit codes (0 for healthy, 1 for unhealthy)."`
  4. Compare the outputs: Observe how prompt detail directly dictates script quality, error handling, and production readiness.
- **Verification**: Note three specific differences between the vague prompt output and the constrained prompt output.

#### Lab 1.3 — Understanding LLM Knowledge Boundaries & Cutoffs
- **Objective**: Validate experimentally that LLMs synthesize answers from stored weights/parameters rather than live web queries (unless augmented with live browsing tools).
- **Steps**:
  1. Ask an LLM a question regarding core Linux fundamentals established decades ago (e.g., `"Explain how Linux calculates CPU idle time from /proc/stat"`).
  2. Ask the same LLM about an extremely recent internal infrastructure change or a newly released minor CLI version released this week (without web search enabled).
  3. Observe how the LLM seamlessly answers the first question from parameter weights, but either hallucinates, refuses, or states knowledge cutoff on the second question.
- **Verification**: Formulate a rule of thumb for your DevOps team specifying which queries are safe for offline LLM assistance vs. queries requiring up-to-date documentation ingestion.

#### Lab 1.4 — Building & Running the VM Health-Check Script (`health.sh`)
- **Objective**: Manually create, execute, and validate the reference shell script demonstrated in Day 1 on a Linux machine or WSL/container.
- **Steps**:
  1. Create a file named `health.sh` with the following implementation:
     ```bash
     #!/bin/bash
     THRESHOLD=60
     CPU_USAGE=$(top -bn1 | grep "Cpu(s)" | awk '{print $2 + $4}' | cut -d. -f1)
     MEMORY_USAGE=$(free | awk '/Mem:/ {printf "%.0f", $3/$2 * 100}')
     DISK_USAGE=$(df / | awk 'NR==2 {print $5}' | tr -d '%')

     STATUS="Healthy"
     REASONS=""

     if [ "$CPU_USAGE" -ge "$THRESHOLD" ]; then
         STATUS="Not Healthy"
         REASONS="${REASONS}\n  ⚠ CPU utilization is ${CPU_USAGE}% (threshold: ${THRESHOLD}%)"
     fi
     if [ "$MEMORY_USAGE" -ge "$THRESHOLD" ]; then
         STATUS="Not Healthy"
         REASONS="${REASONS}\n  ⚠ Memory utilization is ${MEMORY_USAGE}% (threshold: ${THRESHOLD}%)"
     fi
     if [ "$DISK_USAGE" -ge "$THRESHOLD" ]; then
         STATUS="Not Healthy"
         REASONS="${REASONS}\n  ⚠ Disk utilization is ${DISK_USAGE}% (threshold: ${THRESHOLD}%)"
     fi

     echo "VM Health Status: $STATUS"

     if [ "$1" == "explain" ]; then
         if [ "$STATUS" == "Healthy" ]; then
             echo -e "\n✅ All metrics are within acceptable limits:"
             echo "  CPU:    ${CPU_USAGE}%"
             echo "  Memory: ${MEMORY_USAGE}%"
             echo "  Disk:   ${DISK_USAGE}%"
         else
             echo -e "\n❌ The following metric(s) exceeded the ${THRESHOLD}% threshold:"
             echo -e "$REASONS"
         fi
     fi

     [ "$STATUS" == "Healthy" ] && exit 0 || exit 1
     ```
  2. Set executable permissions: `chmod +x health.sh`.
  3. Execute without arguments: `./health.sh`.
  4. Execute with explanation: `./health.sh explain`.
  5. Check the exit status in Bash: `echo $?`.
- **Verification**: Verify that the script executes cleanly, parses system outputs without syntax errors, and outputs the expected status.

#### Lab 1.5 — Deep Dive into Linux Diagnostic Commands (`top`, `free`, `df`)
- **Objective**: Master the diagnostic outputs and underlying filesystems used by automated monitoring scripts.
- **Steps**:
  1. Run `cat /proc/loadavg` and compare it to the load average displayed by `top -bn1 | head -n 5`.
  2. Inspect the CPU breakdown line in `top`: Identify `us` (user), `sy` (system), `id` (idle), `wa` (iowait), and `st` (steal).
  3. Run `free -m` and compute actual available memory percentage manually: `(available / total) * 100`. Compare this against the simplistic `(used / total)` calculation.
  4. Run `df -h /` and `df -i /`. Note the difference between 100% block capacity utilization and 100% inode exhaustion.
- **Verification**: Document why using `free` instead of `available` in automated health check scripts leads to false-positive alarms in production Linux servers.

#### Lab 1.6 — Hands-On with AI Agents: GitHub Copilot Workspace Simulation
- **Objective**: Understand the difference between an AI Assistant (code completion) and an AI Agent (autonomous planning, multi-file execution, Git PR workflow).
- **Steps**:
  1. Access GitHub Copilot Workspace (or an equivalent agentic tool such as GitHub Copilot agent mode / Bolt.new / Cursor Agent).
  2. Create a new repository: `devops-ai-health-monitor`.
  3. Submit a feature task issue: `"Create a bash health check utility that monitors CPU, RAM, and Disk, supports an explain mode, and includes a comprehensive README with installation and crontab scheduling instructions."`
  4. Inspect the agent's generated **Specification** and **Plan**.
  5. Review the proposed file diffs (script, README, test cases) before approving.
  6. Let the agent commit the changes to a new branch and open a Pull Request.
- **Verification**: Document how the agent handled the entire lifecycle autonomously compared to how you would prompt an inline code assistant in VS Code.

#### Lab 1.7 — Stress-Testing & Threshold Verification
- **Objective**: Simulate resource pressure to trigger and verify the health check alert mechanism.
- **Steps**:
  1. Run `./health.sh` to confirm the baseline healthy status.
  2. Temporarily lower the threshold in `health.sh` (e.g., `THRESHOLD=5`) or run a temporary stress test using `stress-ng` / `stress` or a background compute loop:
     ```bash
     # Optional temporary CPU burner (run for 5 seconds):
     sha256sum /dev/zero & PID=$!; sleep 5; kill $PID
     ```
  3. Run `./health.sh explain` while the threshold is breached.
  4. Confirm that the script returns `VM Health Status: Not Healthy`, lists the exact breaching metrics with warning emojis, and exits with code `1`.
- **Verification**: Confirm that the exit code `$?` evaluates to `1` when unhealthy, making it suitable for automated alerting pipelines.

</details>

---

<details>
<summary><b>Day 2: Prompt Engineering Explained — Review Questions & Lab Exercises</b></summary>

## Day 2: Prompt Engineering Explained

### 📝 Review Questions

#### Beginner Level (0–1 Years Experience)

1. What is a "prompt" in the context of Large Language Models? Provide a simple real-world analogy.
2. Define "Prompt Engineering." How does it transform a casual chat interaction into a reliable engineering tool?
3. What are the two primary business justifications for investing effort into prompt engineering?
4. What is a "token," and how does it relate to words in the English language? What is the rough word-to-token ratio in models like Google Gemini?
5. Why are API requests to cloud LLM providers (e.g., OpenAI, Google, DeepSeek) not free? What infrastructure costs do providers incur?
6. What is Zero-Shot Prompting? Under what circumstances is zero-shot prompting completely sufficient for DevOps tasks?
7. What is Few-Shot Prompting, and why is it considered the most recommended prompting technique for DevOps engineers?
8. Why does an LLM lack the context of your specific enterprise, even if it knows how to write ideal shell scripts or Kubernetes manifests?
9. What is Chain-of-Thought (CoT) prompting? What simple phrase triggers an LLM to engage in step-by-step reasoning?
10. Name and define each component of Abhishek's **4-Pillar Strategic Prompting Framework**.

#### Intermediate Level (1–3 Years Experience)

1. In the Google AI Studio demonstration, an unconstrained prompt produced 2,473 tokens while a constrained prompt produced 179 tokens. Calculate the percentage cost reduction. If an enterprise team executes 10,000 requests per month at $15 per million output tokens, how much money is wasted annually by unoptimized prompts?
2. Explain the difference between **System Prompts** (developer instructions) and **User Prompts** (runtime task inputs). How can system prompts be used to enforce corporate Few-Shot standards globally across an engineering organization?
3. When using LLMs to generate Infrastructure as Code (e.g., Terraform or CloudFormation), why can zero-shot prompting result in security regressions (e.g., world-open security groups `0.0.0.0/0` or unencrypted S3 buckets)? How does few-shot prompting mitigate this?
4. How does the choice of output format (e.g., requiring raw JSON or YAML vs. standard markdown text) affect downstream CI/CD automation? What prompt directives prevent the model from wrapping code in markdown code blocks (` ```yaml `)?
5. What are the trade-offs of Multi-Shot Prompting compared to Few-Shot Prompting in terms of prompt token overhead, context window utilization, and inference latency?
6. Describe the phenomenon of "context drift" or "instruction decay" when conversational prompts become excessively long. How do explicit delimiters (e.g., `### CONTEXT`, `### INSTRUCTION`, `### EXAMPLES`) maintain prompt integrity?
7. How does Chain-of-Thought prompting prevent hallucinated diagnostic conclusions when analyzing complex multi-container pod crash logs?
8. Explain how HTTP response code `429 (Too Many Requests)` relates to token rate limits (TPM - Tokens Per Minute) rather than request counts (RPM - Requests Per Minute).

#### Expert Level (3+ Years Experience)

1. **Dynamic Few-Shot Exemplar Selection**: When building an enterprise-scale DevOps AI assistant, hardcoding few-shot examples into prompts wastes tokens when tasks vary. Design an architecture using vector embeddings and semantic search (e.g., pgvector, ChromaDB) to dynamically retrieve the 2 most relevant company code exemplars based on the user's incoming query before passing them to the LLM.
2. **FinOps Token Governance Framework**: Architect a policy and monitoring system for an organization with 500 developers using internal LLM endpoints. Include: (a) automated prompt linter in CI to detect unconstrained prompts, (b) token quota tiers per environment (dev vs. prod), and (c) anomaly alerting on completion token spikes using Prometheus and OpenTelemetry.
3. **Prompt Injection & Security Threat Modeling**: If a developer builds a CI/CD pipeline that prompts an LLM with git commit messages or PR comments to generate release notes, how could an attacker use "Indirect Prompt Injection" to manipulate the pipeline? What prompt engineering boundaries and sandboxing controls are required to prevent command injection?
4. **Structured Outputs & Schema Guarantees**: Compare traditional prompt constraints (`"output strictly in JSON"`) with OpenAI/Gemini **JSON Schema / Structured Outputs** (enforced via context-free grammars during token decoding). Why is token-level grammar enforcement superior for production infrastructure automation?
5. **Chain-of-Thought vs. Fine-Tuning for Incident Response**: An enterprise wants an AI model to triage P1 production incidents based on proprietary runbooks. Evaluate whether they should: (a) fine-tune an open-source model (e.g., Llama 3) on past incident post-mortems, or (b) use a frontier model with Retrieval-Augmented Generation (RAG) and Chain-of-Thought prompting. Justify with respect to knowledge updates, maintenance costs, and hallucination rates.

#### Cumulative / Cross-Day Questions (To revisit as course progresses)

1. **Connecting Day 1 to Day 2**: In Day 1, we observed GitHub Copilot Workspace generating a `health.sh` script autonomously. How did Copilot Workspace implicitly use the 4-Pillar framework (Context from repo, Instructions from issue, Examples from codebase, Output format in Git diffs) under the hood?
2. **Connecting Day 2 to Day 3 (Local LLMs)**: Local LLMs (such as a 7B or 8B parameter model running via Ollama) have significantly less raw reasoning capability and smaller context windows than cloud giants like GPT-4o. Why does mastery of Few-Shot and 4-Pillar prompting become **even more critical** when deploying local models on your laptop or private cluster?
3. **Connecting Day 2 to Days 5 & 6 (AIOps)**: When parsing raw multi-gigabyte server logs in AIOps, passing entire raw logs directly into an LLM prompt is cost-prohibitive. How will prompt engineering and token budgeting dictate which log summaries are submitted for AI anomaly analysis?
4. **Connecting Day 2 to Days 7 & 8 (AI Agents)**: How does Chain-of-Thought prompting serve as the foundational internal loop (Thought → Action → Observation) for autonomous AI Agents?

---

### 🔬 Lab Exercises

#### Lab 2.1 — Live Token Benchmark & Cost Analysis in Google AI Studio
- **Objective**: Replicate Abhishek's live demonstration to observe token metrics and calculate real-world API cost differences.
- **Steps**:
  1. Navigate to Google AI Studio (or OpenAI Platform Playground).
  2. Select a current model (e.g., Gemini 1.5 Flash or GPT-4o-mini).
  3. Submit the unconstrained prompt:
     ```text
     generate a kubernetes manifest for deployment resource
     ```
     Record the output token count and observe the conversational boilerplate.
  4. Clear the session and submit the constrained prompt:
     ```text
     generate only kubernetes manifest for deployment resource
     ```
     Record the output token count.
  5. Calculate your token reduction ratio:
     $$\text{Token Savings \%} = \frac{\text{Tokens}_{\text{unconstrained}} - \text{Tokens}_{\text{constrained}}}{\text{Tokens}_{\text{unconstrained}}} \times 100$$
- **Verification**: Confirm a token reduction exceeding 85% while obtaining the exact same functional deployment manifest.

#### Lab 2.2 — Enforcing Corporate Bash Standards via Few-Shot Conditioning
- **Objective**: Train an LLM in-context to produce standardized enterprise Bash scripts without conversational filler.
- **Steps**:
  1. Open your preferred AI Chatbot or developer playground.
  2. Construct a Few-Shot prompt providing two exemplars:
     ```text
     Follow our enterprise DevOps scripting standard. Every script MUST include our exact header format (# Author, # Version, # Date, # Purpose) and set -euo pipefail.

     Example 1:
     Task: Fetch active listening ports.
     Answer:
     #!/bin/bash
     # Author: DevOps Platform Team
     # Version: 1.0.0
     # Date: 2026-10-12
     # Purpose: Audit active listening ports
     set -euo pipefail

     ss -tuln

     Example 2:
     Task: Check disk space for root partition.
     Answer:
     #!/bin/bash
     # Author: DevOps Platform Team
     # Version: 1.0.0
     # Date: 2026-10-12
     # Purpose: Check root filesystem capacity
     set -euo pipefail

     df -h /

     Now complete the following task:
     Task: Check memory utilization and trigger warning if available RAM is under 15%.
     Answer:
     ```
  3. Evaluate the output: Verify that the LLM copied the exact header structure, author, version format, `set -euo pipefail` flag, and wrote the logic cleanly.
- **Verification**: Verify that the model output contains zero conversational greetings and adheres strictly to the demonstrated syntax.

#### Lab 2.3 — Production Kubernetes Manifest Generation with the 4-Pillar Framework
- **Objective**: Implement the full 4-Pillar Framework to generate a production-ready, security-hardened Kubernetes manifest.
- **Steps**:
  1. Write a prompt that explicitly incorporates all four pillars:
     - **Context**: Enterprise FinTech environment on Kubernetes 1.30 with strict PCI-DSS and Pod Security Standards (Restricted profile).
     - **Instruction**: Create a Deployment for an Nginx reverse proxy with 3 replicas, read-only root filesystem, non-root user (UID 10001), dropped capabilities (`ALL`), explicit CPU/Memory requests, and a liveness probe on port 8080 (`/healthz`).
     - **Example**: Provide a brief 10-line YAML exemplar illustrating your team's standard metadata labels and annotations.
     - **Output Format**: `"Provide ONLY valid YAML. No markdown backticks, no comments, no explanations."`
  2. Run the prompt through an LLM.
  3. Save the resulting output to `nginx-deploy.yaml`.
  4. Validate the manifest locally using `kubectl` dry-run:
     ```bash
     kubectl apply --dry-run=client -f nginx-deploy.yaml
     ```
- **Verification**: Confirm that the generated YAML passes client-side validation with zero syntax errors.

#### Lab 2.4 — Deterministic JSON Output Enforcement & Validation with `jq`
- **Objective**: Enforce strict JSON output from an LLM and integrate it directly into a Bash pipeline using `jq`.
- **Steps**:
  1. Craft a prompt asking the LLM to inspect a simulated Linux server error log:
     ```text
     ### CONTEXT
     You are an automated CI/CD log triage agent.

     ### INSTRUCTION
     Analyze the following log snippet and extract:
     1. Error severity (CRITICAL, WARNING, INFO)
     2. Culprit process
     3. Recommended remediation command

     Log snippet:
     "Oct 12 10:14:02 prod-node-04 kernel: [12948.12] Out of memory: Kill process 8912 (mysqld) score 850 or sacrifice child"

     ### OUTPUT FORMAT
     Output strictly a single valid JSON object with keys: "severity", "process", "remediation". Do NOT use markdown code blocks or conversational text.
     ```
  2. Send the prompt via `curl` to an LLM API or test in playground and save the response to `triage.json`.
  3. Validate and parse the output using `jq`:
     ```bash
     cat triage.json | jq .
     cat triage.json | jq -r '.remediation'
     ```
- **Verification**: Ensure `jq` parses the file without syntax errors (`parse error: Invalid numeric literal...`).

#### Lab 2.5 — Chain-of-Thought (CoT) Incident Triage Simulation
- **Objective**: Compare direct zero-shot diagnosis against Chain-of-Thought prompting on a deceptive infrastructure failure.
- **Steps**:
  1. Prepare the deceptive scenario:
     *"A Kubernetes pod running a web service suddenly fails with `502 Bad Gateway` after a deployment update. Pod logs show no crashes, CPU is at 5%, RAM is at 10%, and the pod status is `Running (1/1)`. However, the readiness probe fails on `/health`."*
  2. **Query 1 (Zero-Shot Direct)**: `"What caused the 502 Bad Gateway and how do I fix it?"` — Observe if the model guesses generic answers (e.g., restart Nginx, scale up memory).
  3. **Query 2 (Chain-of-Thought Prompt)**:
     ```text
     Analyze this incident step by step:
     Step 1: Analyze why the pod status is Running but readiness is failing.
     Step 2: Trace the network path from Ingress/Service to the container port.
     Step 3: Hypothesize three configuration mismatches (e.g., targetPort vs. containerPort, health check path/port, environment variable database connection).
     Step 4: Propose specific kubectl commands to test each hypothesis.
     Step 5: Provide the most probable resolution.
     ```
  4. Compare the depth, accuracy, and troubleshooting utility of the two outputs.
- **Verification**: Document how Chain-of-Thought prevented jumping to an incorrect conclusion.

#### Lab 2.6 — Enterprise AI Token Cost Modeling in Python
- **Objective**: Build a Python script that calculates enterprise API token costs and simulates prompt engineering ROI.
- **Steps**:
  1. Create a script named `token_calculator.py`:
     ```python
     #!/usr/bin/env python3
     # Token FinOps Calculator for DevOps AI Integrations

     def calculate_cost(requests_per_day, unconstrained_tokens, engineered_tokens, cost_per_million=10.0):
         annual_requests = requests_per_day * 250
         
         annual_tokens_unconstrained = annual_requests * unconstrained_tokens
         annual_tokens_engineered = annual_requests * engineered_tokens
         
         cost_unconstrained = (annual_tokens_unconstrained / 1_000_000) * cost_per_million
         cost_engineered = (annual_tokens_engineered / 1_000_000) * cost_per_million
         savings = cost_unconstrained - cost_engineered
         
         print(f"=== Annual Enterprise Token Economics ===")
         print(f"Annual API Requests:        {annual_requests:,}")
         print(f"Unconstrained Cost:         ${cost_unconstrained:,.2f} ({annual_tokens_unconstrained:,} tokens)")
         print(f"Engineered Prompt Cost:     ${cost_engineered:,.2f} ({annual_tokens_engineered:,} tokens)")
         print(f"Net Annual FinOps Savings:  ${savings:,.2f} ({(savings/cost_unconstrained)*100:.1f}%)")

     if __name__ == "__main__":
         # Parameters from Day 2 demo: 500 req/day, 2,473 vs 179 tokens
         calculate_cost(requests_per_day=500, unconstrained_tokens=2473, engineered_tokens=179, cost_per_million=15.0)
     ```
  2. Execute the script: `python3 token_calculator.py`.
- **Verification**: Review the output and record the annual dollar savings achieved through prompt engineering.

#### Lab 2.7 — Multi-Shot Prompting for Multi-Cloud Terraform Tagging Standards
- **Objective**: Use Multi-Shot prompting to enforce uniform tagging policies across AWS, Azure, and Google Cloud Terraform resources.
- **Steps**:
  1. Formulate a prompt with 3 exemplars demonstrating required tags (`Environment`, `Owner`, `CostCenter`, `ManagedBy: Terraform`):
     - Exemplar 1: AWS S3 Bucket (`aws_s3_bucket`) with `tags = { ... }`.
     - Exemplar 2: Azure Resource Group (`azurerm_resource_group`) with `tags = { ... }`.
     - Exemplar 3: GCP Cloud Storage (`google_storage_bucket`) with `labels = { ... }` (noting GCP uses `labels` instead of `tags` and requires lowercase values).
  2. Task: Ask the model to generate a GCP Compute Engine instance (`google_compute_instance`) and an AWS EC2 instance (`aws_instance`).
  3. Validate that the LLM appropriately used `tags` for AWS and `labels` for GCP while preserving corporate tag values.
- **Verification**: Confirm that the generated Terraform complies with provider-specific syntax without tag omission.

#### Lab 2.8 — Testing API Error Codes and Throttling Simulation
- **Objective**: Understand API error handling for rate limits and tokens in automated scripts.
- **Steps**:
  1. Write a shell or Python script that inspects HTTP headers when invoking an LLM endpoint.
  2. Verify that your script checks for:
     - `HTTP 200`: Success.
     - `HTTP 429`: Rate limit exceeded (parse `Retry-After` header).
     - `HTTP 400`: Context length exceeded (prompt + max completion > model context window).
  3. Implement an exponential backoff loop (`sleep 2`, `sleep 4`, `sleep 8`) for handling transient `429` errors.
- **Verification**: Document how automated CI/CD runners should handle LLM rate throttling without failing pipeline jobs.

</details>

<details>
<summary><b>Day 3: GenAI Project For DevOps Engineers (G3CS46T)</b></summary>

### Review Questions

#### Beginner
1. **Explain the fundamental architectural difference between running an LLM locally via Ollama versus calling a hosted LLM API (such as Google Gemini or OpenAI). What are the primary trade-offs regarding data privacy and infrastructure maintenance?**
   - *Answer*: Local LLMs run inference directly on local hardware (CPU/GPU/RAM) via a daemon like Ollama (`localhost:11434`), ensuring that prompts and proprietary code never leave the local environment (100% data privacy, SOC2/compliance-ready, zero per-token cost). However, local execution requires local compute resources, can be slow on CPU-only machines, and demands infrastructure management. Hosted LLMs offload inference to cloud providers (e.g., Google AI Studio, OpenAI), providing instant responses and access to massive frontier models with zero infrastructure overhead, but require internet egress, expose prompts to third-party endpoints, and bill per token consumed.

2. **In the "Docker for LLMs" mental model, how do Ollama's core components (Ollama Library, CLI, model weights, and daemon) map to Docker's ecosystem?**
   - *Answer*:
     - **Ollama Library** (`ollama.com/library`) $\leftrightarrow$ **Docker Hub** (`hub.docker.com`): Public registries hosting downloadable artifacts.
     - **Ollama CLI** (`ollama pull`, `ollama run`) $\leftrightarrow$ **Docker CLI** (`docker pull`, `docker run`): Command-line tools for lifecycle management.
     - **Model Weights** (`llama3.2:1b`) $\leftrightarrow$ **Container Images** (`alpine:latest`): Pre-packaged binary payloads.
     - **Ollama Daemon** (`ollama serve` on port `11434`) $\leftrightarrow$ **Docker Daemon** (`dockerd`): Background services managing execution, memory, and API communication.

3. **Why did Abhishek choose Meta's Llama 3.2 1B model for the local hands-on demonstration instead of a 70B or 405B parameter model? What happens if you run a large model on a CPU-bound laptop?**
   - *Answer*: Llama 3.2 1B is an ultra-lightweight model requiring only ~1.3 GB of storage and minimal RAM, allowing it to run smoothly on standard laptops without dedicated GPUs. Attempting to run a 70B+ model on a standard CPU laptop leads to extreme memory swapping, thermal throttling, inference latencies exceeding 10–30 minutes per query, or system out-of-memory (OOM) crashes.

---

#### Intermediate
1. **Analyze the error message `Error: listen tcp 127.0.0.1:11434: bind: address already in use` when running `ollama serve`. What does this indicate, and how should a DevOps engineer verify the daemon's status?**
   - *Answer*: This message indicates that port `11434` is already bound by an existing process—meaning the Ollama background daemon is already running and operational (Ollama automatically installs and runs as an OS background service on macOS, Linux, and Windows). An engineer should verify daemon health by querying the REST endpoint via `curl -s http://localhost:11434/`, which returns `"Ollama is running"`.

2. **Why is multi-stage Docker build architecture mandatory when using Generative AI to generate container configurations for compiled or dependency-heavy languages (e.g., Groovy, Java, Go, Node.js)?**
   - *Answer*: Multi-stage builds separate the build environment (compilers, SDKs, package managers, development dependencies, build caches) from the final runtime container. In a single-stage build, SDKs like Maven, Gradle, or full Node build tools inflate the final image to 1 GB+ and expose build utilities as attack surfaces. Multi-stage builds (`AS builder` $\rightarrow$ lean runtime like `alpine` or `distroless`) ensure the production image contains only the compiled binary or minimal runtime dependencies, slashing image size by 80–90% and hardening the attack surface.

3. **In the Python script `generate_dockerfile.py`, why is it critical to extract `response['message']['content']` rather than returning the entire `response` object? What would happen downstream if raw `response` were returned?**
   - *Answer*: The `ollama.chat()` API returns a rich JSON payload containing metadata such as model name, timestamp, evaluation count, prompt eval duration, and total token latency alongside the nested `message` dictionary. Returning the entire object would output raw JSON metadata, breaking shell redirects (e.g., `python3 generate_dockerfile.py > Dockerfile`) and causing `docker build` to fail immediately with Dockerfile syntax errors.

---

#### Expert
1. **Design a production-grade Platform Engineering architecture that wraps `generate_dockerfile.py` into an automated self-service microservice for an enterprise of 1,000 developers. How would you handle caching, input sanitization, automated linting, and LLM fallback routing?**
   - *Answer*:
     ```mermaid
     flowchart LR
         Dev["Developer / PR"] --> Gateway["API Gateway / FastAPI"]
         Gateway --> Cache{"Redis Cache\n(Language + Framework Hash)"}
         Cache -->|Cache Hit| Return["Return Verified Dockerfile"]
         Cache -->|Cache Miss| Sanitize["Input Sanitization & Whitelisting"]
         Sanitize --> Router{"Router / Load Balancer"}
         Router -->|Primary: Air-Gapped| LocalPool["Private Ollama Cluster\n(Kube vLLM / Ollama on GPUs)"]
         Router -->|Fallback: Overflow| CloudLLM["Google Gemini / OpenAI API"]
         LocalPool --> Linter["Hadolint / Trivy Scanner Gate"]
         CloudLLM --> Linter
         Linter -->|Pass| CacheStore["Store in Redis"] --> Return
         Linter -->|Fail| SelfHeal["Refinement Prompt with Lint Errors"] --> Router
     ```
     - **Input Sanitization**: Whitelist permitted languages and frameworks; strip prompt injection attacks (e.g., `"ignore previous instructions"`).
     - **Redis Caching**: Cache generated Dockerfiles by runtime hash to avoid redundant LLM invocations for identical standard stacks.
     - **Automated Verification**: Pipe LLM output through `hadolint` (Dockerfile linter) and `trivy` (vulnerability scanner); if lint errors occur, trigger a self-correction loop passing lint errors back into the prompt.
     - **Fallback Routing**: Route primary traffic to on-prem GPU clusters (Ollama/vLLM) for compliance; fall back to cloud APIs (Gemini 1.5 Pro) with exponential backoff if on-prem queues saturate.

2. **Threat Model: Contrast a "Denial-of-Wallet" attack against a hosted LLM endpoint with a "Resource Starvation" attack against an on-prem Ollama server. Detail specific DevOps telemetry and mitigation strategies for both.**
   - *Answer*:
     - **Denial-of-Wallet (Hosted LLM)**:
       - *Threat*: Malicious actors or runaway CI/CD scripts invoke external APIs (OpenAI/Gemini) thousands of times in parallel, exhausting token quotas and generating astronomical cloud invoices.
       - *Telemetry*: Monitor `usage.total_tokens` metrics, track HTTP `429 Too Many Requests`, and integrate AWS/GCP Cost Anomaly Detection webhooks.
       - *Mitigation*: Enforce API gateway rate limits (Token Bucket algorithm per user/repo), configure strict hard daily spending caps in the cloud console, and implement ephemeral secret rotation.
     - **Resource Starvation (On-Premises Ollama)**:
       - *Threat*: Concurrent inference requests overwhelm on-prem GPU VRAM/CPU threads, causing daemon crashes, request queue timeouts, and starvation of other workloads on the host.
       - *Telemetry*: Prometheus scraping `container_cpu_usage_seconds_total`, GPU VRAM utilization via `nvidia-smi` / DCGM exporter, and Ollama request latency (`http_request_duration_seconds`).
       - *Mitigation*: Deploy behind an autoscaling queue (KEDA + RabbitMQ/Kafka), enforce concurrency limits (`OLLAMA_NUM_PARALLEL`), isolate GPU pods with Kubernetes ResourceQuotas, and configure aggressive HTTP read timeouts.

---

#### Cumulative
1. **Synthesize the foundational principles from Day 0 (Course Syllabus), Day 1 (Traditional vs. Generative AI, Parameters), Day 2 (Prompt Engineering & Token FinOps), and Day 3 (Local vs. Hosted Automation). Explain how an enterprise DevOps team should formulate an AI adoption roadmap that balances developer velocity against operational cost and corporate security.**
   - *Answer*:
     1. **Classification (Day 1)**: Distinguish between Traditional AI (deterministic metrics, predictive autoscaling) and Generative AI (unstructured text, code synthesis, configuration generation).
     2. **Governance & Privacy Triage (Day 0 & Day 3)**: Establish a data classification matrix. Workloads handling proprietary IP, customer PII, or regulated banking/health data must be routed exclusively to on-premises Local LLMs (Ollama / private vLLM clusters with models like Llama 3.2 or DeepSeek). Non-sensitive, general automation tasks can leverage Hosted Cloud LLMs (Gemini / OpenAI).
     3. **Prompt Standardization & FinOps (Day 2)**: Forbid ad-hoc, unconstrained prompts across enterprise tooling. Embed the 4-Pillar Prompting Framework (Context, Instruction, Few-Shot Examples, Output Format) into centralized, shared SDK libraries. Enforcing negative constraints (`"Only generate YAML/Dockerfile"`, `"Suppress commentary"`) guarantees both programmatic integration reliability and 90%+ token cost reductions.
     4. **Automated Tooling Integration (Day 3)**: Move from interactive AI chat web GUIs to CLI and pipeline integrations (Python automation scripts, CI/CD linting gates, Slackbot platform tools).
     5. **Continuous Telemetry & Hardening**: Implement centralized observability tracking token consumption, model response latency, linting pass rates, and cost attribution per development squad.

---

### Hands-on Labs

#### Lab 3.1 — Ollama CLI Setup, Daemon Verification, and Model Management
- **Objective**: Install and configure Ollama, inspect the background daemon, download model weights, and verify REST connectivity.
- **Environment**: Linux, macOS, or Windows WSL2 with Ollama installed.
- **Steps**:
  1. Verify the Ollama CLI version:
     ```bash
     ollama --version
     ```
  2. Test the loopback REST daemon directly using `curl`:
     ```bash
     curl -i http://localhost:11434/
     ```
     Ensure the HTTP response status is `200 OK` with body `Ollama is running`.
  3. Download the lightweight Meta Llama 3.2 1B parameter model:
     ```bash
     ollama pull llama3.2:1b
     ```
  4. Inspect the local model catalog to verify size and identifier:
     ```bash
     ollama list
     ```
  5. Run a quick interactive CLI test to verify model execution:
     ```bash
     ollama run llama3.2:1b "Explain Docker layer caching in one sentence."
     ```
- **Verification**: Record the model hash and ensure the CLI responds with a concise explanation.

---

#### Lab 3.2 — Python Virtual Environment (`venv`) & Ollama SDK Integration
- **Objective**: Establish an isolated Python environment and verify programmatic communication with the local Ollama daemon.
- **Steps**:
  1. Create a project directory and virtual environment:
     ```bash
     mkdir -p ~/devops-genai-project && cd ~/devops-genai-project
     python3 -m venv venv
     source venv/bin/activate
     ```
  2. Create a `requirements.txt` file:
     ```text
     ollama>=0.3.0
     ```
  3. Install dependencies using the correct flag:
     ```bash
     pip install -r requirements.txt
     ```
  4. Write a verification script `test_ollama_sdk.py`:
     ```python
     import ollama

     models = ollama.list()
     print("Available Local Models:")
     for model in models['models']:
         print(f" - {model['name']} (Size: {model['size'] / (1024**3):.2f} GB)")
     ```
  5. Execute: `python3 test_ollama_sdk.py`.
- **Verification**: Confirm that `llama3.2:1b` is listed in the output with its corresponding size.

---

#### Lab 3.3 — Building the Local CLI Multi-Language Dockerfile Generator
- **Objective**: Build and execute `generate_dockerfile.py` to generate Dockerfiles for multiple programming languages.
- **Steps**:
  1. Create `generate_dockerfile.py` in your project folder.
  2. Implement the full script matching Abhishek's lecture architecture (import `ollama`, define `generate_dockerfile(language)`, extract `response['message']['content']`, and wrap under `if __name__ == '__main__':`).
  3. Test with a Python target:
     ```bash
     python3 generate_dockerfile.py
     # Enter: Python
     ```
  4. Test with an Apache Groovy target:
     ```bash
     python3 generate_dockerfile.py
     # Enter: Groovy
     ```
  5. Test with a Ruby on Rails target:
     ```bash
     python3 generate_dockerfile.py
     # Enter: Ruby on Rails
     ```
- **Verification**: Confirm that each run emits a standalone Dockerfile without conversational markdown introductory text.

---

#### Lab 3.4 — Enforcing Enterprise Multi-Stage & Distroless Container Directives
- **Objective**: Enhance the system prompt to enforce multi-stage builds and Google Distroless runtime images.
- **Steps**:
  1. Edit the prompt in `generate_dockerfile.py` to add strict enterprise security directives:
     ```python
     prompt = f"""Only generate an ideal multi-stage Dockerfile for {language}.
     Do not provide any description or markdown commentary.
     Mandatory Constraints:
     1. Stage 1 (builder): Use standard official SDK to compile and build dependencies.
     2. Stage 2 (runtime): Use Google Distroless (e.g., gcr.io/distroless/static or gcr.io/distroless/base) or Alpine.
     3. Explicitly copy only build artifacts into Stage 2.
     4. Enforce non-root execution (USER 65532:65532).
     5. Expose default application port.
     """
     ```
  2. Run the script for `Go` (Golang):
     ```bash
     python3 generate_dockerfile.py
     # Enter: Golang
     ```
  3. Inspect the output to verify:
     - `FROM golang:... AS builder`
     - `FROM gcr.io/distroless/static-debian12`
     - `COPY --from=builder ...`
     - `USER nonroot:nonroot` or `USER 65532:65532`
- **Verification**: Verify that the generated Dockerfile builds a minimal binary container with zero package managers in the runtime layer.

---

#### Lab 3.5 — Hosted LLM Integration with Google AI Studio (Gemini 1.5 Pro)
- **Objective**: Configure Google AI Studio credentials, implement `generate_dockerfile_gemini.py`, and test cloud generation.
- **Steps**:
  1. Log in to [Google AI Studio](https://aistudio.google.com) and generate an API key.
  2. Export the key in your terminal:
     ```bash
     export GEMINI_API_KEY="AIzaSyYourActualKeyHere"
     ```
  3. Install the SDK:
     ```bash
     pip install google-generativeai
     ```
  4. Create `generate_dockerfile_gemini.py` using `genai.configure()` and `genai.GenerativeModel("gemini-1.5-pro")`.
  5. Execute for `Node.js`:
     ```bash
     python3 generate_dockerfile_gemini.py
     # Enter: Node.js
     ```
  6. **Security Cleanup**: Return to Google AI Studio and revoke/delete the API key once the test succeeds.
- **Verification**: Verify that the cloud API response returns within 2–3 seconds and uses `node:20-alpine` with multi-stage build layers.

---

#### Lab 3.6 — Multi-Model Benchmark: Comparing Llama 3.2, Gemini, and DeepSeek
- **Objective**: Compare the Dockerfile outputs produced by different foundation models for identical prompts.
- **Steps**:
  1. Pull a second local model in Ollama:
     ```bash
     ollama pull deepseek-r1:1.5b
     # Or pull deepseek-coder:1.3b
     ```
  2. Modify `generate_dockerfile.py` to accept the model name as a CLI flag (`sys.argv[1]`).
  3. Generate a Dockerfile for `Rust` using `llama3.2:1b`:
     ```bash
     python3 generate_dockerfile.py llama3.2:1b Rust > Dockerfile.llama
     ```
  4. Generate a Dockerfile for `Rust` using `deepseek-r1:1.5b`:
     ```bash
     python3 generate_dockerfile.py deepseek-r1:1.5b Rust > Dockerfile.deepseek
     ```
  5. Compare the files using `diff`:
     ```bash
     diff -u Dockerfile.llama Dockerfile.deepseek
     ```
- **Verification**: Document the differences in base image choice, cargo build flags, and caching mechanisms between models.

---

#### Lab 3.7 — Automated Syntax & Security Linting with `hadolint`
- **Objective**: Create an automated validation pipeline that validates LLM-generated Dockerfiles against Docker best practices.
- **Steps**:
  1. Install `hadolint` (Docker linter):
     - macOS: `brew install hadolint`
     - Linux: `wget -O /usr/local/bin/hadolint https://github.com/hadolint/hadolint/releases/download/v2.12.0/hadolint-Linux-x86_64 && chmod +x /usr/local/bin/hadolint`
     - Docker alternative: `docker run --rm -i hadolint/hadolint < Dockerfile`
  2. Write a shell script `validate_ai_dockerfile.sh`:
     ```bash
     #!/usr/bin/env bash
     set -e

     LANGUAGE="$1"
     echo "Generating Dockerfile for $LANGUAGE..."
     python3 generate_dockerfile.py "$LANGUAGE" > /tmp/GeneratedDockerfile

     echo "Linting with Hadolint..."
     hadolint /tmp/GeneratedDockerfile
     echo "✅ Dockerfile passed all Hadolint security checks!"
     ```
  3. Execute: `./validate_ai_dockerfile.sh Java`.
- **Verification**: Verify whether the LLM output triggers any warnings (e.g., `DL3008: Pin versions in apt-get install`) and refine your system prompt to eliminate flagged rules.

---

#### Lab 3.8 — Tokenomics, Cost Auditing, and Rate-Limiting Defense Simulation
- **Objective**: Implement client-side token counting and simulate rate-limiting backoff protection for cloud LLM pipelines.
- **Steps**:
  1. Create a script `token_guard.py` simulating automated pipeline calls:
     ```python
     import time
     import random

     class RateLimiter:
         def __init__(self, max_rpm=10):
             self.interval = 60.0 / max_rpm
             self.last_call = 0.0

         def wait(self):
             elapsed = time.time() - self.last_call
             if elapsed < self.interval:
                 sleep_time = self.interval - elapsed
                 print(f"⏳ RateLimiter: sleeping {sleep_time:.2f}s to respect RPM quota...")
                 time.sleep(sleep_time)
             self.last_call = time.time()

     def simulate_cloud_call(limiter, request_id):
         limiter.wait()
         # Simulate API response
         prompt_tokens = 185
         completion_tokens = 240
         total_tokens = prompt_tokens + completion_tokens
         cost = (total_tokens / 1_000_000) * 1.10  # o3-mini pricing
         print(f"[{request_id}] Success: {total_tokens} tokens | Cost: ${cost:.6f}")

     if __name__ == "__main__":
         limiter = RateLimiter(max_rpm=15)
         print("🚀 Simulating 5 Automated Pipeline Dockerfile Requests...")
         for i in range(1, 6):
             simulate_cloud_call(limiter, i)
     ```
  2. Execute: `python3 token_guard.py`.
- **Verification**: Confirm that the client sleeps between calls, preventing `429 Too Many Requests` API throttles during batch jobs.

</details>

<details>
<summary><b>Day 0: Course Syllabus & Overview — Assignments (CS46H)</b></summary>

## Interview Preparation Questions

### Beginner Level

1. What is "AI Assisted DevOps" and how does it differ from traditional DevOps practice?
2. What is a Large Language Model (LLM)? How is it different from traditional AI?
3. Why is prompt engineering important when working with LLMs?
4. Name three Zero-to-Hero course series available on Abhishek Veeramalla's YouTube channel.
5. What are the strict prerequisites for this AI Assisted DevOps course?
6. What is AIOps? Give one example of how AI can help with observability.
7. What is the difference between a "chatbot" and an "AI Agent"?
8. Why would a DevOps engineer run an LLM locally instead of using ChatGPT?
9. What is FinOps, and why is Generative AI useful for it?
10. What does "zero-shot prompting" mean?

### Intermediate Level

1. Explain the security and compliance risks of using public LLMs (e.g., ChatGPT) for DevOps tasks. How does running a local LLM mitigate these risks?
2. What are tokens in the context of LLMs, and why do they matter for DevOps organizations using AI APIs at scale?
3. Compare zero-shot, few-shot, and N-shot prompt engineering techniques. When would you use each?
4. Explain how Generative AI can help a DevOps engineer with CI/CD pipelines. Give two specific use cases.
5. What is Chain-of-Thought (CoT) prompting and when is it most useful in a DevOps context?
6. Describe the AIOps use case for CPU throttling prediction. Why is this something humans cannot reliably do manually at scale?
7. What is the role of AI Agents in DevOps automation? How do they differ from simple LLM queries?
8. A DevOps engineer needs to write a Kubernetes manifest for a microservice. What are the trade-offs between using ChatGPT vs. a local LLaMA model for this task?
9. Why does the instructor describe Day 2 (Prompt Engineering) as "super important for the entire series"?
10. What tools/models does the course introduce for running LLMs locally?

### Advanced Level

1. Design a security-compliant AI-assisted workflow for a DevOps team that has strict data residency requirements. Which days of this course address this requirement and how?
2. Explain the "Denial of Wallet" attack concept in the context of LLM API usage. How would you architect a defensive strategy?
3. You are implementing AIOps for a Kubernetes cluster generating 50 GB of logs per day. Describe the architectural components needed and explain why human-only analysis is insufficient.
4. How would you implement a "prompt engineering governance" standard for a team of 20 DevOps engineers all using LLMs? What key parameters would you standardize?
5. Compare enterprise AIOps tools (ManageEngine, Dynatrace) against open-source stacks (Prometheus + Grafana + custom AI integration) for production AIOps. What are the trade-offs?
6. Design an AI Agent architecture for a DevOps engineer that can autonomously monitor CI/CD pipelines, detect failures, analyze logs, and create GitHub issues with remediation steps.
7. How does the FinOps application of AI differ technically from the AIOps application, despite both dealing with large datasets? What ML/AI techniques are more applicable to each domain?

---

## Lab Exercises

### Foundation Labs (Day 0 Context)

**Lab 0.1 — Environment Survey**
- Inventory your current DevOps toolchain: list every tool you use for scripting, CI/CD, observability, and cloud cost management
- For each tool, identify one AI-assisted workflow that could improve your productivity in that area
- Document which tools have native AI integration and which would require a custom solution

**Lab 0.2 — Local LLM Setup (Preview)**
- Install Ollama on your machine: https://ollama.ai
- Pull the smallest available model: `ollama pull llama3.2:1b`
- Test it: `ollama run llama3.2:1b "Write a bash one-liner to check if port 443 is open on localhost"`
- Diagnostic check: verify the daemon is running with `curl http://localhost:11434/api/tags`
- Note the RAM usage before and after loading the model (`free -h` on Linux, Task Manager on Windows)

**Lab 0.3 — Prompt Quality Experiment**
- Pick any LLM chatbot (ChatGPT, Claude, Gemini)
- Ask it: `write a dockerfile` — note the output
- Ask it: `write a production-ready multi-stage dockerfile for a Python 3.11 FastAPI application, output only the Dockerfile with no explanation, use python:3.11-slim as base, non-root user, and expose port 8000`
- Compare the two outputs and document the quality differences
- This exercise previews Day 2 (Prompt Engineering) and Day 3 (Dockerfile generation)

**Lab 0.4 — AIOps Awareness Exercise**
- Access your cloud provider's cost management or observability dashboard
- Identify one metric that has been trending upward for the past 30 days
- Manually try to predict where that metric will be in 30 more days
- Note: this is the exact problem AIOps (Days 5-6) solves programmatically

**Lab 0.5 — CI/CD Log Analysis Baseline**
- Find a recent failed CI/CD pipeline run in your project (GitHub Actions, Jenkins, GitLab CI)
- Copy the failure log and paste it into ChatGPT with the prompt: `Analyze this CI/CD failure log and provide the root cause and remediation steps`
- Evaluate the quality of the response — this is the baseline for Day 7's AI + CI/CD module

</details>

<details>
<summary><b>Day 1 — Fundamentals of AI for DevOps Engineers (CS46H)</b></summary>

## Beginner Interview Questions

1. What is the difference between Traditional AI and Generative AI? Give one real-world example of each.
2. What is a Large Language Model (LLM)? Name three examples.
3. Why do LLMs require supercomputers for training?
4. What are "parameters" in the context of an LLM? What does LLaMA 3.1 405B's "405B" refer to?
5. How does an LLM answer a question — does it search the internet in real time?
6. What is prompt engineering and why does it matter?
7. List the four categories of AI tools for DevOps engineers.
8. What is the difference between an AI Chatbot and an AI Agent?
9. Name one free AI Chatbot, one free AI Agent, and one free AI Assistant for DevOps use.
10. What Linux commands are used to check CPU, memory, and disk usage in a shell script?

## Intermediate Interview Questions

1. How does AWS Predictive Autoscaling use Traditional AI? What data does it analyze?
2. Explain the "memory retrieval" model of how LLMs answer questions. What are the implications for DevOps engineers using LLMs for production infrastructure decisions?
3. What is zero-shot prompting? When would you use it vs. few-shot prompting?
4. Compare GitHub Copilot Workspace (AI Agent) and GitHub Copilot IDE plugin (AI Assistant). When would you use each?
5. A developer asks ChatGPT to generate a Kubernetes manifest for a new cloud service feature released last week. What risk does this introduce?
6. What is Common Crawl and why is it relevant to understanding LLM training data?
7. Explain the four-stage GitHub Copilot Workspace workflow used in the VM health-check demo.
8. Why does the instructor say "you still need DevOps fundamentals even with AI tools"? Give a concrete example of where AI-generated code could fail without domain expertise to review it.
9. What is the "4 categories" AI landscape framework for DevOps, and why is it structured by category rather than specific products?
10. If a VM health-check script reports "healthy" but the system is experiencing slowdowns, what metric might the script be missing that you would add?

## Advanced Interview Questions

1. **Architecture Decision:** Your organization needs to generate Kubernetes manifests for 50 microservices. Compare using: (a) an AI Chatbot (ChatGPT), (b) an AI Agent (GitHub Copilot Workspace), and (c) a Python script calling an LLM API. What are the trade-offs in control, speed, cost, and security?
2. **Security Analysis:** You are a DevOps engineer using GitHub Copilot Workspace to generate a VM health-check script. The script will run on production EC2 instances in a regulated environment (PCI-DSS). What risks must you evaluate before deploying the AI-generated script?
3. **Prompt Engineering:** Rewrite the zero-shot health-check prompt from the demo as a chain-of-thought prompt. What additional precision does CoT provide over zero-shot for this use case?
4. **Hallucination Mitigation:** An LLM generates a shell script that uses a `vmstat` flag that doesn't exist on the target Ubuntu version. Describe the debugging workflow you would follow and what safeguards you would build into a production AI-assisted scripting pipeline to prevent this.
5. **Scale Analysis:** LLaMA 3.1 405B has 405 billion parameters. A newer model has 1 trillion parameters trained on a larger dataset. What performance improvements would you expect, and what new infrastructure challenges does it create for running it locally vs. via API?
6. **AIOps vs. GenAI:** Describe a scenario where Traditional AI (AIOps) is the right tool and a scenario where Generative AI is the right tool for a DevOps incident. Why would combining both provide the best outcome?
7. **Organizational Rollout:** You are tasked with introducing AI tools to a 20-person DevOps team that has zero AI experience. Using the 4-category framework from this lesson, design a phased adoption plan (weeks 1–4) with one tool per category and specific tasks to practice each week.

## Lab Exercises

### Lab 1 — VM Health-Check Script (Replication)
**Objective:** Replicate the Day 1 demo using GitHub Copilot Workspace.
**Steps:**
1. Sign up for / access GitHub Copilot Workspace (free at copilot-workspace.githubnext.com)
2. Use the exact zero-shot prompt from the lesson (CPU/memory/disk, 60% threshold, `explain` argument, Ubuntu target)
3. Review the Brainstorm options — select "Basic" first, then compare with "Advanced"
4. Follow the Plan → Implement → Create Repo workflow
5. Clone the repository to a test Ubuntu VM (local VM, WSL2, or EC2 t2.micro)
6. Run `chmod +x vm_health_check.sh` then `./vm_health_check.sh` and `./vm_health_check.sh explain`
7. Verify output matches expected behavior (CPU/memory/disk percentages + healthy/not healthy status)

**Verification commands:**
```bash
# Test basic output
./vm_health_check.sh

# Test explain output (should show percentages)
./vm_health_check.sh explain

# Manually stress test CPU briefly (optional)
stress --cpu 4 --timeout 10 &
./vm_health_check.sh explain
```

### Lab 2 — AI Tool Category Exploration
**Objective:** Set up at least one tool from each of the 4 AI landscape categories and perform a DevOps task with each.
**Steps:**
1. **Chatbot:** Use ChatGPT or Claude to generate a Dockerfile for a Python Flask app. Observe the output quality with a vague vs. specific prompt.
2. **Agent:** Use GitHub Copilot Workspace to create a repository containing a `disk_cleanup.sh` script that removes files older than 30 days in `/tmp`.
3. **Assistant:** Install the GitHub Copilot VS Code extension (free). Open a shell script and observe inline suggestions as you type.
4. **Programming:** Write a 10-line Python script using the `requests` library to call a public LLM API (e.g., Ollama running locally with `llama3.2:1b`) and print its response to "What is DevOps in one sentence?"

### Lab 3 — Prompt Quality Comparison
**Objective:** Observe the impact of prompt quality on LLM output for a DevOps task.
**Steps:**
1. Open ChatGPT, Claude, or Google AI Studio
2. Submit the vague prompt: `"write a health check script"`
3. Record: number of lines, whether it includes comments/explanations, whether it addresses CPU/memory/disk
4. Submit the specific prompt: `"Write a bash shell script for Ubuntu that checks CPU utilization (vmstat), memory utilization (free), and disk usage (df). If all three are below 60%, print 'healthy'. If any exceeds 60%, print 'not healthy'. Support a command-line argument named 'explain' that prints each metric's current value alongside the status. Output ONLY the script, no explanations."`
5. Compare: lines of useful code, whether explanation was included, immediate usability

**Expected finding:** The specific prompt produces immediately usable, targeted output; the vague prompt produces a tutorial with explanations you must edit out.

### Lab 4 — Traditional AI vs. GenAI Classification
**Objective:** Reinforce the distinction between Traditional AI and Generative AI by classifying real tools.
**Task:** For each tool below, classify as Traditional AI, Generative AI (LLM), or Generative AI (non-LLM, e.g., image generation). Then describe one DevOps use case:
- AWS Predictive Autoscaling
- GitHub Copilot (code generation)
- Datadog Anomaly Detection
- DALL-E 3 image generation
- Prometheus alert prediction
- ChatGPT log explanation
- Google AI Studio Gemini for Kubernetes manifest generation
- Netflix recommendation engine

</details>

<details>
<summary><b>Day 2 — Prompt Engineering Explained (CS46H)</b></summary>

## Beginner Interview Questions

1. What is a "prompt" in the context of a Large Language Model?
2. Define prompt engineering in one sentence, in plain language.
3. What is zero-shot prompting? Give a one-line example.
4. What is few-shot prompting? Why is it called "few-shot"?
5. What are tokens in the context of LLM APIs? How do they relate to words?
6. Why does the number of tokens in an API response affect cost?
7. What was the token count difference in the instructor's Google AI Studio demo (bad vs. good prompt)?
8. Name the four prompt engineering techniques covered in Day 2.
9. What is the purpose of the "Output Format" pillar in Abhishek's 4-pillar strategy?
10. Name one tool you can use to count tokens in an LLM response for free.

## Intermediate Interview Questions

1. A DevOps engineer is building a Python automation that calls an LLM API 500 times per day, 365 days per year. Their current prompt generates 2,000 tokens per response. If they improve the prompt to 200 tokens per response, what percentage reduction in API billing would they achieve at scale?
2. What organizational problem does few-shot prompting solve that zero-shot prompting cannot? Give a DevOps-specific example.
3. Explain the key distinction: "providing examples to an LLM" vs. "training an LLM."
4. When would you choose multi-shot prompting over few-shot prompting?
5. The instructor says Chain-of-Thought "enhances the performance of the LLM." Explain mechanically why CoT improves output quality for complex reasoning tasks.
6. Describe the 4-pillar prompting strategy. Write a one-sentence description of each pillar.
7. Why does adding the word "ONLY" to a Kubernetes manifest generation prompt reduce token count by 92.7%?
8. What is the risk of using few-shot examples that are inconsistent with each other in format or style?
9. You are building a prompt for a Python script that will call the OpenAI API to generate Terraform modules. Design a prompt using all 4 pillars. Include a mock example for the examples pillar.
10. What is "prompt injection" in the context of a DevOps pipeline, and how does few-shot prompting interact with this risk?

## Advanced Interview Questions

1. **Cost Architecture:** Your team of 50 engineers uses an LLM API for automated PR review. Each review call currently uses an average of 8,000 tokens (3,000 input + 5,000 output). Design a prompt engineering strategy that reduces the output to under 1,000 tokens without losing actionable feedback quality. What pillar changes drive the most impact?
2. **Benchmark Design:** Design a repeatable token benchmarking process for a new LLM prompt used in CI/CD automation. What tool do you use, what metrics do you measure, and what threshold triggers a prompt revision?
3. **Few-Shot Template Library:** Design the structure of a team-wide prompt template library for a DevOps team of 20. What categories would it have, what format would each template follow (using the 4-pillar structure), and how would you manage versioning?
4. **CoT vs. Few-Shot Decision Tree:** For each of the following tasks, determine whether zero-shot, few-shot, multi-shot, or CoT is optimal and justify your answer: (a) Generate a Dockerfile for a Node.js app. (b) Explain why a Kubernetes pod is OOMKilled. (c) Generate a Helm values.yaml matching your org's naming conventions. (d) Design a rollback strategy for a failed canary deployment across 3 regions.
5. **API Cost FinOps:** You are the DevOps lead responsible for LLM API spending. Your monthly bill is $4,200 for OpenAI API calls from 8 internal automation scripts. Walk through how you would audit each script's prompt quality, what metrics you would report to leadership, and what engineering changes would reduce the bill by 60%.
6. **Prompt Security:** An internal DevOps tool lets engineers submit free-text "context" that is automatically interpolated into an LLM prompt to generate runbooks. A security engineer flags this as a prompt injection risk. Explain the attack vector, the specific harm it could cause in a DevOps context, and the technical mitigations.
7. **Output Determinism:** LLM outputs are probabilistic (temperature > 0). For a CI/CD automation that parses LLM-generated YAML, non-deterministic output will cause parsing failures. Design a prompting strategy (combining output format directives, temperature settings, and validation) that makes LLM YAML generation deterministic enough for automated pipeline use.

## Lab Exercises

### Lab 1 — Token Count Benchmark
**Objective:** Measure the token impact of prompt precision in Google AI Studio.
**Steps:**
1. Create a free account at aistudio.google.com
2. Enter the bad prompt: `generate a kubernetes manifest for deployment resource`
   - Record: token count (watch the counter at the bottom as it generates)
3. Enter the good prompt: `generate ONLY kubernetes manifest for deployment resource`
   - Record: token count
4. Calculate percentage reduction: `(bad - good) / bad × 100`
5. Repeat the experiment with your own DevOps task (e.g., "write a Dockerfile for a Python app" vs. "write ONLY a Dockerfile for a Python app, no explanation")
**Expected outcome:** The specific prompt uses 80–95% fewer tokens than the vague one.

### Lab 2 — Few-Shot Shell Script Demo Replication
**Objective:** Reproduce the few-shot demo from Day 2 and enforce your own org header standard.
**Steps:**
1. Open ChatGPT, Claude, or any LLM chatbot
2. Craft two examples with YOUR org header standard (replace Abhishek's name with your own)
3. Ask the LLM to generate a shell script to check if a list of required system packages are installed
4. Verify: does the generated script include your header exactly as shown in the examples?
5. Modify one example's header (e.g., add a `# Description:` line) and re-test — observe that the LLM adopts the new format

### Lab 3 — 4-Pillar Prompt Template
**Objective:** Write a professional, production-grade prompt using all 4 pillars for a real DevOps task.
**Task:** Write a prompt that generates a Bash script to automate AWS EC2 instance health reporting (CPU, memory, disk, running services) and sends a Slack notification if any metric exceeds a threshold.
**Deliverable:** A fully written prompt with:
- Context pillar (your role, OS, AWS environment)
- Instruction pillar (specific task with all requirements listed)
- Examples pillar (1–2 short example scripts in your org's format)
- Output Format pillar (raw bash only, no markdown, no explanations)

### Lab 4 — Prompt Library Bootstrap
**Objective:** Create the first 5 entries of your personal DevOps prompt library.
**Steps:**
1. Create a file `prompt-library.md` with 5 sections: Kubernetes, Docker, Shell Scripting, CI/CD, IaC
2. For each section, write one zero-shot prompt and one few-shot prompt template
3. Test each prompt against your preferred LLM and record: token count, output quality (1–5), usability without edits (yes/no)
4. Iterate on any prompt that scores below 4/5 or requires post-processing edits

</details>

<details>
<summary><b>Day 3 — GenAI Project For DevOps Engineers (CS46H)</b></summary>

## Beginner Interview Questions

1. What is the difference between a local LLM and a hosted LLM? Give one example of each.
2. What is Ollama and why is it compared to Docker?
3. What command do you run to download the Llama 3.2 1B model using Ollama?
4. What does "1B" mean in "llama3.2:1b"?
5. What is a Python virtual environment and why should you use one?
6. What is the command to activate a Python virtual environment on Linux/Mac?
7. What Python package do you install to talk to Ollama from a Python script?
8. What Python package do you install to use the Google Gemini API?
9. What is the Ollama API port that the Python script communicates with?
10. Why should you delete your Google AI Studio API key after completing a demo project?

## Intermediate Interview Questions

1. An organization has 500 developers who all need to generate Dockerfiles for their microservices. Compare the approach of using ChatGPT manually vs. building a Python script + LLM API. What are the key differences in automation, consistency, and enterprise access?
2. Explain the communication chain from a Python script to an Ollama-based LLM response. List every component in the chain.
3. A DevOps engineer wants to use a local LLM for Dockerfile generation. Their organization has 2,000 developers. What infrastructure challenges will they face at this scale?
4. Why does the Python script use `response["message"]["content"]` instead of just `response`? What would you see if you printed `response` directly?
5. What is the "Denial-of-Wallet" attack in the context of LLM APIs? How can a rate limit mitigate it?
6. Compare `ollama pull llama3.2:1b` vs. `ollama run llama3.2:1b`. When would you use each?
7. How does the Gemini version of `generate_dockerfile_gemini.py` differ from the Ollama version in terms of authentication, API call structure, and response parsing?
8. What is the `if __name__ == "__main__":` guard in Python for? What happens if you omit it when the script is imported as a module?
9. A developer has their `GOOGLE_API_KEY` hardcoded in `generate_dockerfile_gemini.py` and accidentally pushes it to a public GitHub repo. What is the risk, and what are the immediate remediation steps?
10. Why does the output from Gemini differ from the output from Llama 3.2 1B for the same programming language input?

## Advanced Interview Questions

1. **Production Architecture:** Design a production system where `generate_dockerfile.py` serves 500 developers in a regulated financial institution. Requirements: no data leaves the organization, the tool must be available as an internal API. Specify: LLM type (local/hosted), deployment pattern, how many instances, and what monitoring you add.
2. **Prompt Engineering for Consistency:** The current prompt produces varying Dockerfile structures across Llama and Gemini (e.g., one uses `COPY . .`, another uses `ADD`). Design a few-shot prompt that enforces your organization's Dockerfile standards across any model. Include two example Dockerfiles as the few-shot context.
3. **Security Threat Model:** A DevOps team builds a Python script that calls the OpenAI API and exposes it as an internal REST endpoint. Identify five security risks in this architecture and the mitigation for each.
4. **Cost Optimization:** Your team's `generate_dockerfile.py` script averages 1,600 tokens per request (400 input + 1,200 output). You have 200 developers each making 5 requests per day. Calculate: (a) monthly token volume, (b) monthly cost at OpenAI o1 pricing ($15/1M tokens), (c) monthly cost at o3 pricing ($1.10/1M tokens), (d) the cost reduction from adding the output constraint "Do not provide any description."
5. **Multi-Model Strategy:** Your organization deploys Llama 3.2 1B for Dockerfile generation (simple task) and OpenAI o1 for security policy review (complex task). Design the Python routing logic that sends requests to the appropriate model based on task type. What metadata in the request determines routing?
6. **Virtual Environment Best Practice:** A junior engineer runs `pip install ollama` globally (without a venv) and then tries to run your project's script. They encounter a version conflict. Walk through: (a) how to diagnose the conflict, (b) how to set up the correct venv, (c) how to prevent this in the future (requirements.txt pinning, Makefile target).
7. **Ollama at Scale:** You want to serve Ollama to 50 concurrent developers from a single GPU server. What Ollama configurations and Linux infrastructure (systemd, nginx, resource limits) would you set up to handle concurrent requests without one request blocking another?

## Lab Exercises

### Lab 1 — Local Dockerfile Generator (Full Replication)
**Objective:** Build and run `generate_dockerfile.py` using Ollama + Llama 3.2 1B.
**Steps:**
1. Install Ollama (download from ollama.com for your OS)
2. Verify Ollama is running: `ollama serve` or check system tray
3. Pull the model: `ollama pull llama3.2:1b`
4. Create a project folder, set up venv: `python3 -m venv venv && source venv/bin/activate`
5. Create `requirements.txt` with one line: `ollama`
6. Install: `pip install -r requirements.txt`
7. Write `generate_dockerfile.py` exactly as shown in the lesson
8. Run: `python3 generate_dockerfile.py`
9. Test with: Java, Python, Groovy, Ruby on Rails, Node.js
10. Add the multi-stage constraint to the prompt and re-test — observe the difference

### Lab 2 — Hosted Dockerfile Generator (Gemini)
**Objective:** Build and run `generate_dockerfile_gemini.py` using Google Gemini.
**Steps:**
1. Create a free Google AI Studio account at `aistudio.google.com`
2. Generate an API key (API key > Get API key > Create API key in current project)
3. Set the environment variable: `export GOOGLE_API_KEY="your-key"` (Linux/Mac) or `$env:GOOGLE_API_KEY = "your-key"` (Windows)
4. Install dependency: `pip install google-generativeai`
5. Write `generate_dockerfile_gemini.py` using the Gemini version shown in the lesson
6. Run: `python3 generate_dockerfile_gemini.py`
7. Test with Node.js — observe how output differs from the Llama version
8. Add the multi-stage constraint and re-test
9. **After completing:** Delete the API key from Google AI Studio

### Lab 3 — Output Comparison (Local vs. Hosted)
**Objective:** Compare LLM outputs for the same input to understand model differences.
**Steps:**
1. Run both scripts with the same input: "Ruby on Rails"
2. Save each output to a separate file: `local_ruby.dockerfile` and `gemini_ruby.dockerfile`
3. Compare the files using `diff local_ruby.dockerfile gemini_ruby.dockerfile`
4. Document: Which model added more constraints (non-root user, healthcheck, .dockerignore hint)? Which was closer to production-ready?
5. Modify the prompt with few-shot examples to make both outputs match your preferred standard

### Lab 4 — Security Audit and Hardening
**Objective:** Identify and fix the security issues in the raw scripts from the lesson.
**Issues to find and fix:**
1. API key in environment variable (good) vs. hardcoded (bad) — verify your script uses `os.environ`
2. No `max_tokens` limit on the API call — add `options={"num_predict": 600}` for Ollama or `generation_config=genai.types.GenerationConfig(max_output_tokens=600)` for Gemini
3. No error handling — wrap the API call in a `try/except` block that catches `ConnectionRefusedError` (Ollama not running) and `Exception` (API errors)
4. No input validation — add a check that the `language` input is not empty and not longer than 50 characters

</details>


<details>
<summary><b>Day 4 — AI Assisted Shell Scripting (CS46H)</b></summary>

## Beginner Interview Questions

1. What is AI pair programming? Describe it using the senior developer analogy.
2. Name two free AI pair programming tools for shell scripting.
3. Why is shell scripting considered the best DevOps use case for AI-generated code?
4. What is the first best practice for AI-assisted shell scripting, and why does it help?
5. What should a description block at the top of a shell script include?
6. How do you ask GitHub Copilot to explain a line of code you don't understand?
7. What Linux command is used to check if the AWS CLI is installed in a portable way?
8. What AWS CLI command verifies that credentials are configured and valid?
9. What is the difference between `chmod 777`, `chmod 755`, and `chmod 700`?
10. What was the error encountered during the first run of the demo script, and how was it fixed?

## Intermediate Interview Questions

1. Compare shell scripting, Python, Terraform, and Kubernetes YAML in terms of backward compatibility and AI-generation reliability. Which is safest to trust from AI and why?
2. A DevOps engineer uses GitHub Copilot to generate a shell script that checks disk usage on multiple servers. The description block says: "# Description: Check disk usage." What is wrong with this description, and how would you improve it to get better suggestions?
3. Explain the difference between `command -v aws` and `which aws`. Which is preferred for shell scripts and why?
4. The generated script uses `aws sts get-caller-identity` to verify configuration. What specific scenarios does this check catch that an AWS CLI installation check alone would miss?
5. Why does the generated script use `--query 'Vpc.VpcId' --output text` when creating the VPC? What would the output look like without these flags?
6. How does the file name `aws_vpc_create.sh` provide context to GitHub Copilot before a single comment is written?
7. Compare GitHub Copilot and Cursor AI. For which DevOps tasks would you use each? What is the key limitation of Cursor AI for daily DevOps use?
8. A junior engineer accepts every Copilot suggestion without reading it and deploys the script to production. The script deletes the wrong VPC. What engineering process controls would have prevented this?
9. Describe a scenario where `aws sts get-caller-identity` returns success but the subsequent `aws ec2 create-vpc` fails with an authorization error. What does this tell you about the IAM permissions of the configured role?
10. What is the `case "$1" in ... esac` pattern in Bash, and why is it preferred over a chain of `if/elif` statements for command-line argument handling?

## Advanced Interview Questions

1. **Enterprise AI Pair Programming Strategy:** Your organization wants to enable 200 DevOps engineers to write infrastructure scripts using GitHub Copilot. Design an enterprise adoption plan that includes: (a) a script template standard (file name convention, description block format, variable naming), (b) a code review checklist for AI-generated scripts before merging, (c) a training program for engineers who are new to AI-assisted development.
2. **Script Hardening:** The `aws_vpc_create.sh` script from the demo has several production gaps. Identify and fix at least five: (a) no `set -euo pipefail`, (b) no cleanup on failure (VPC created but subnet fails), (c) no idempotency check (running twice creates duplicate VPCs), (d) no logging, (e) CIDR block hardcoded rather than parameterized via argument flags.
3. **Teardown Implementation:** Implement the full `create/teardown` assignment script. The teardown function must: (a) find the VPC by tag name using `aws ec2 describe-vpcs`, (b) find all subnets in the VPC, (c) delete subnets before the VPC (AWS requirement), (d) handle the case where VPC doesn't exist gracefully.
4. **IAM Least Privilege:** List the minimum IAM permissions required for `aws_vpc_create.sh` to run. Write the IAM policy JSON. Why is running the script with `AdministratorAccess` a security anti-pattern even in a demo?
5. **Idempotency Design:** Rewrite `aws_vpc_create.sh` so that running it twice with the same parameters does not create a duplicate VPC. Use `aws ec2 describe-vpcs --filters "Name=tag:Name,Values=$VPC_NAME"` to check for existing resources before creating.
6. **Cross-Platform Compatibility:** The script uses `command -v aws` and Bash-specific features. Identify all the parts of the script that would break on: (a) a system with `sh` but not `bash`, (b) macOS with BSD `sed` vs. Linux GNU `sed`, (c) a Windows machine running Git Bash vs. WSL2.
7. **Dry Run Mode:** Add a `--dry-run` flag to `aws_vpc_create.sh`. When `--dry-run` is passed, the script should print every AWS CLI command it WOULD run (with actual variable values substituted) but not execute any of them. This is a standard production pattern for infrastructure scripts.

## Lab Exercises

### Lab 1 — GitHub Copilot Setup and First Script
**Objective:** Install GitHub Copilot and experience AI pair programming firsthand.
**Steps:**
1. Open VS Code → Extensions → Search "GitHub Copilot" → Install
2. Sign in with your GitHub account when prompted
3. Create a new folder called `ai-shell-scripts`
4. Create a new file: `aws_s3_list.sh`
5. Type `#!/bin/bash` and press Enter
6. Type `# Description: List all S3 buckets and their total size` and press Enter
7. Observe Copilot suggestions — accept with Tab, reject with Esc
8. Let Copilot generate the complete script without typing any logic yourself
9. Run the script (requires AWS CLI configured): `chmod +x aws_s3_list.sh && ./aws_s3_list.sh`

### Lab 2 — Reproduce the VPC Demo
**Objective:** Replicate the `aws_vpc_create.sh` demo from the lesson.
**Steps:**
1. Create `aws_vpc_create.sh` with the description block from the lesson
2. Accept Copilot suggestions for all variables, checks, and AWS commands
3. Before running, read every line — highlight any you don't understand and use Explain
4. Run `./aws_vpc_create.sh` — note any errors and fix the availability zone if needed
5. Verify in the AWS Console that the VPC and subnet were created with the correct names and CIDR blocks
6. Clean up: delete the subnet and VPC from the AWS Console (or write the teardown lab below)

### Lab 3 — Assignment: Create/Teardown Script
**Objective:** Complete the assignment from the Day 4 episode.
**Requirements:**
- `./aws_vpc_create.sh` → "Please provide input as 'create' or 'teardown'"
- `./aws_vpc_create.sh create` → Creates VPC and subnet (as in Lab 2)
- `./aws_vpc_create.sh teardown` → Finds VPC by tag name, deletes subnet, deletes VPC
- `./aws_vpc_create.sh anything_else` → "Invalid input parameter"
**Hint:** Use the `case "$1" in` pattern for argument handling. For teardown, query by tag: `aws ec2 describe-vpcs --filters "Name=tag:Name,Values=demo-vpc" --query 'Vpcs[0].VpcId' --output text`

### Lab 4 — Script Hardening
**Objective:** Add production-level safeguards to your VPC script.
**Add these improvements:**
1. Add `set -euo pipefail` after the shebang — makes the script exit on any error, undefined variable, or pipe failure
2. Add a cleanup trap: `trap 'echo "Script failed. Manual cleanup may be required." >&2' ERR`
3. Add an idempotency check: before creating, check if a VPC with the same `VPC_NAME` tag already exists
4. Add a `--dry-run` mode that prints commands without executing them
5. Add timestamps to output: `echo "[$(date '+%Y-%m-%d %H:%M:%S')] VPC created: $VPC_ID"`

</details>


<details>
<summary><b>Day 5 — AIOps Explained with Free Playgrounds (CS46H)</b></summary>

## Beginner Interview Questions

1. What does AIOps stand for, and what does it actually mean?
2. Give three examples of AI-related DevOps practices that are NOT considered AIOps.
3. What are the three pillars of observability that AIOps feeds on as input?
4. What is the difference between a reactive approach and a predictive approach in IT operations?
5. What is an "anomaly" in the context of AIOps?
6. Name two enterprise platforms that offer AIOps features and the name of each platform's AI engine.
7. Why are AIOps solutions generally not free?
8. In the Dynatrace Davis playground demo, what were the predicted order volumes for March 25th and 26th based on historical data?
9. In the ManageEngine Zia demo, how many monitors were set up total, and how many confirmed anomalies did Zia detect?
10. What specific anomaly was demonstrated in the ManageEngine Zia playground? Include the metric name, value, location, and time pattern.

## Intermediate Interview Questions

1. A DevOps engineer says "We're doing AIOps because we use GitHub Copilot to generate our Kubernetes deployment manifests." Is this correct? Explain the distinction.
2. Explain the memory leak scenario from the episode. Why does the reactive observability approach fail to prevent downtime in this case, even if alerts are configured properly?
3. Using the weather prediction analogy, explain how Traditional AI in AIOps works. What is the "historical data" equivalent in each domain?
4. Your organization monitors 150 microservices. Assuming 100 metrics per service, estimate the total number of metrics. Why does this create a business case for AIOps over human monitoring?
5. A Dynatrace Davis dashboard shows a flat disk utilization curve, and Davis predicts continued flat utilization. Does this mean AIOps found "nothing interesting"? Explain what this result actually tells you.
6. What is the role of Traditional AI versus GenAI in the emerging hybrid AIOps architecture? Which component predicts, and which component acts?
7. Explain why Karpenter is triggered at 80% memory in the current reactive model, and how an AI Agent changes the trigger point in the future hybrid model.
8. ManageEngine Zia reports a page load time surge of 15,609ms, 1.9x above threshold, between 12am–10am in Canberra. As a DevOps engineer, what is your next investigation step? What tools would you use?
9. Why does the instructor say open-source AIOps solutions are "not efficient" compared to commercial offerings? What makes AIOps computationally expensive to build and maintain?
10. Compare AIOps to the observability stack it sits on top of. Can you implement AIOps without first having a mature observability stack? Why or why not?

## Advanced Interview Questions

1. **AIOps Architecture Design:** Your organization runs 200 microservices on Kubernetes. Design an AIOps architecture that includes: (a) which observability data streams feed into the AIOps engine (metrics, logs, traces — which and why), (b) what Traditional AI algorithms are most appropriate for anomaly detection vs. forecasting (hint: time-series), (c) how you would handle false positives during the model's initial learning period, (d) the escalation path when AIOps detects an anomaly (alert → human vs. alert → AI Agent → auto-remediate).
2. **Build vs. Buy Analysis:** Your organization is deciding whether to build a custom AIOps ML model or subscribe to a commercial platform. Build a comparison matrix covering: (a) upfront and ongoing costs, (b) time-to-value, (c) required expertise (ML engineers vs. platform configuration), (d) customization depth, (e) maintenance burden (model drift, retraining), (f) your recommendation and reasoning.
3. **Anomaly Detection Deep Dive:** Explain the difference between anomaly detection and forecasting as AIOps capabilities. For each of the following situations, state whether anomaly detection, forecasting, or both would be most appropriate: (a) detecting that an API's error rate suddenly spiked at 2am; (b) predicting that disk space will run out in 14 days; (c) identifying that today's CPU usage is unusual given historical weekday patterns; (d) estimating next month's peak traffic for capacity planning.
4. **Traditional AI Model Evaluation:** An AIOps vendor claims their platform detected 66 anomalies out of 1,085 monitors (the ManageEngine Zia demo). (a) What is the false positive rate concern with this number? (b) How would you measure the precision and recall of the AIOps model? (c) What threshold would you set for "confirmed anomaly" vs. "likely anomaly" and why? (d) How does alert fatigue from AIOps false positives compare to alert fatigue from traditional threshold-based monitoring?
5. **GenAI Agent Integration Plan:** Design the AI Agent component of the future AIOps hybrid architecture. Given that Traditional AI has predicted "memory working set for service X will reach 85% in 10 days," specify: (a) the exact input the AI Agent receives (format, fields), (b) the reasoning chain the Agent follows to choose a remediation action, (c) the specific Kubernetes/cloud operations the Agent would execute (Karpenter node provisioning, HPA scaling, etc.), (d) the guardrails preventing the Agent from taking destructive actions, (e) the human escalation criteria (when should the Agent NOT auto-remediate and alert a human instead).
6. **Open-Source AIOps Research:** The instructor mentions open-source AIOps solutions exist on GitHub but are not production-efficient. Research (or reason through) what technical challenges make open-source AIOps difficult: (a) model training pipeline complexity, (b) infrastructure requirements for continuous retraining, (c) integration with diverse observability stacks (Prometheus, Grafana, Datadog, OpenTelemetry), (d) data volume and velocity challenges, (e) propose a realistic architecture for a small team that wants AIOps without commercial licensing costs.
7. **Production Implementation Plan:** You have been asked to implement AIOps for a medium-sized SaaS company (50 services, 5,000 metrics, currently using Prometheus + Grafana). Produce a 90-day implementation roadmap: (a) Days 1–30: observability data quality audit and AIOps platform selection, (b) Days 31–60: pilot deployment on 5 most critical services, baseline learning period, (c) Days 61–90: rollout to all 50 services, tuning false positive rate, defining escalation workflows. Include success criteria for each phase.

## Lab Exercises

### Lab 1 — Dynatrace Davis AIOps Playground Exploration
**Objective:** Get hands-on experience with a production AIOps engine.
**Steps:**
1. Sign up for the Dynatrace free playground (link in course description)
2. Navigate to the AIOps section and find the Davis anomaly detector
3. Open the "Orders Packed" e-commerce dashboard — record the historical data values and the Davis prediction values for the next 2–3 days
4. Open the "Predictive Disk Capacity" dashboard — record whether Davis predicts a flat curve or a spike, and explain why
5. Explore the "Kubernetes CPU Usage" and "Kubernetes Memory Working Sets" dashboards — describe what anomalies (if any) Davis surfaces
6. Reflection: For each dashboard, identify whether Davis is performing "anomaly detection," "forecasting," or both

### Lab 2 — ManageEngine Zia Anomaly Exploration
**Objective:** Understand what a real AIOps anomaly report looks like.
**Steps:**
1. Sign up for the ManageEngine playground (link in course description)
2. Navigate to the Zia anomaly dashboard
3. Find the total monitor count and confirmed anomaly count — do they match the values from the episode, or has the demo environment changed?
4. Click into at least 3 different confirmed anomalies and record: metric name, location, anomaly type, severity (e.g., Nx above threshold), time pattern
5. Compare the three anomalies: which is most severe? Which would you investigate first if you were the on-call engineer?
6. Reflection: Estimate how long it would take a human to find these same 3 anomalies by manually checking all monitors. What does this time saving demonstrate about AIOps value at scale?

### Lab 3 — AIOps vs. Observability Concept Map
**Objective:** Solidify the architectural distinction between observability and AIOps.
**Draw (on paper or in a diagramming tool like draw.io):**
1. The reactive observability flow: Application → Metrics/Logs/Traces → Monitor → Alert → Human → Fix
2. The predictive AIOps flow: Application → Metrics/Logs/Traces → AIOps Engine (Traditional AI) → Early Warning → Human fixes proactively
3. The future hybrid flow: Application → Metrics/Logs/Traces → AIOps Engine → AI Agent (GenAI) → Auto-remediation
4. For each flow, annotate: where does downtime risk exist? Where is human intervention required? What is the time-to-resolution?
5. Share your diagram in the course community or discuss with a peer

### Lab 4 — AIOps Platform Selection Exercise
**Objective:** Apply the enterprise AIOps platform comparison to a real decision.
**Scenario:** You are a DevOps architect at a company with 80 microservices currently using Grafana OSS + Prometheus for monitoring. Your manager has asked you to evaluate three AIOps options: Dynatrace, ManageEngine, and building a custom ML model.
**Deliverable:** Write a 1-page recommendation that includes:
1. A comparison table: each option rated on cost, ease of integration with Prometheus, time-to-value, customization, and vendor lock-in risk
2. Your recommendation with justification
3. One risk of your recommended option and how you would mitigate it
4. How you would present this recommendation to a non-technical manager who just wants to know "will it prevent 3am outages?"

</details>



<details>
<summary><b>Day 6 — AIOps for Log Analysis — First AIOps Project using Python (CS46H)</b></summary>

## Beginner Interview Questions

1. What are the three pillars of observability that AIOps feeds on? Which pillar does Day 6 focus on?
2. What is the ELK stack? Name each component and its role (Elasticsearch, Logstash, Kibana).
3. What is the key limitation of ELK-based log analysis compared to AIOps?
4. Name the four standard log levels used in the Day 6 project, ordered from least to most severe.
5. Why is it important to create a Python virtual environment before installing dependencies?
6. What command activates a Python virtual environment on Linux/macOS?
7. What two Python libraries are used in `simple_log_analysis.py`? What is each one used for?
8. What is the `contamination` parameter in Isolation Forest, and what value does the demo use?
9. In the demo output, what specific anomalies did the Isolation Forest detect that the simple script missed?
10. Why does the instructor say the developer-assigned log level is "unreliable" for AIOps purposes?

## Intermediate Interview Questions

1. Explain the memory leak scenario from the episode. How does a WARNING-level memory log eventually cause a CRITICAL outage, and why does the simple script fail to detect it?
2. Describe the regex pattern used to parse the log file. What types of log content does it intentionally filter out, and why?
3. Compare the `simple_log_analysis.py` and `aiops_log_analysis.py` approaches: for each, describe the detection method, what log levels are examined, how the threshold/sensitivity is set, and what the output looks like.
4. What is label encoding in the context of `aiops_log_analysis.py`? Why must log level values be converted to numbers before feeding to Isolation Forest?
5. The Isolation Forest flagged "Multiple failed login attempts" logged as WARNING — not ERROR. How does the algorithm detect this as anomalous even though its log level is low?
6. Explain the response time degradation scenario (10ms → 60ms → 1s → 5s → 25s) from INFO logs. Why would a traditional script miss this, and what would the ELK Kibana dashboard show?
7. What is the difference between supervised and unsupervised machine learning? Why is Isolation Forest (unsupervised) more appropriate for log anomaly detection than a supervised algorithm?
8. If you set `contamination=0.5` in the Isolation Forest model, what would happen to the anomaly detection results? What is the risk?
9. The instructor says "Enterprise platforms use the same algorithm but with much more training data." What specifically would a better-trained model detect that this script might miss?
10. Why does the course recommend a virtual environment (`venv`) rather than installing packages globally with `pip install`?

## Advanced Interview Questions

1. **Production Deployment Design:** You are deploying `aiops_log_analysis.py` as a production service. Design a complete architecture: (a) how the script ingests real-time logs instead of a static file (Kafka stream, CloudWatch Logs, or ELK Logstash output), (b) how the Isolation Forest model is trained once per week on the last 30 days of logs and serialized to disk (`joblib.dump`), (c) how the script loads the pre-trained model on each run (`joblib.load`) instead of retraining, (d) how anomaly detections trigger Slack/PagerDuty alerts instead of `print` statements, (e) how the service runs on a schedule (Kubernetes CronJob or AWS Lambda + CloudWatch Events).
2. **Feature Engineering for Better Accuracy:** The current model only uses `level_numeric` (one feature). Propose three additional numeric features extracted from the log DataFrame that would improve anomaly detection accuracy. For each feature, describe: (a) how to extract it from the log text, (b) why it provides signal for anomaly detection, (c) an example of an anomaly it would catch that `level_numeric` alone would miss.
3. **Contamination Tuning Experiment:** Run `aiops_log_analysis.py` three times with `contamination=0.05`, `contamination=0.1`, and `contamination=0.2`. For each run: (a) count the total anomalies detected, (b) identify which anomalies appear in all three runs (likely true positives), (c) identify which anomalies appear only in the high-contamination run (likely false positives), (d) recommend the best contamination value for a production security-focused system and explain your reasoning.
4. **Log Level Mislabeling Audit:** The episode highlights that developers frequently assign incorrect log levels. Design an automated audit process: (a) a regex-based classifier that scans log messages for security keywords ("password", "unauthorized", "failed login") and flags any logged below ERROR level, (b) a frequency analysis that identifies log messages repeating more than X times per hour at WARNING/INFO level, (c) a report format that recommends log level corrections to the development team, (d) how this audit integrates with a CI/CD pipeline to prevent new log misclassifications from being merged.
5. **Isolation Forest vs. Alternative Algorithms:** Research and compare Isolation Forest to two alternative unsupervised anomaly detection algorithms (e.g., Local Outlier Factor (LOF) and One-Class SVM): (a) how each algorithm defines "anomalous" differently, (b) time complexity for training (relevant when logs have millions of lines), (c) performance on sequential time-series data (log timestamps), (d) which algorithm you would choose for a production log analysis system handling 100GB of logs per day, and why.
6. **Multi-Service AIOps Pipeline:** Your organization runs 50 microservices, each producing separate log files. Extend `aiops_log_analysis.py` into a pipeline that: (a) reads all 50 log files from a directory, (b) trains a separate Isolation Forest model per service (because each service has different normal behavior), (c) aggregates anomalies from all services into a single report ranked by severity, (d) correlates anomalies across services by timestamp (if Service A and Service B both show anomalies within 30 seconds, that's a higher-priority cross-service incident), (e) outputs a JSON report suitable for ingestion by a SIEM (Security Information and Event Management) tool.
7. **Model Drift and Retraining Strategy:** Isolation Forest trained on last month's logs will degrade in accuracy as application behavior changes (new features deployed, user traffic patterns shift, seasonal effects). Design a model drift detection and retraining strategy: (a) define what "model drift" means for an anomaly detection model (hint: false positive rate changes), (b) how to measure drift using a sliding window of recent anomaly rates, (c) what triggers an automatic retraining (threshold: if false positive rate exceeds X%), (d) how to A/B test the new model vs. the old model before fully replacing it, (e) how to prevent the retraining process itself from running during a real incident (when anomaly rate spikes legitimately).

## Lab Exercises

### Lab 1 — Run Both Scripts Against the Course Log File
**Objective:** Experience the difference between traditional and AIOps log analysis firsthand.
**Steps:**
1. Clone the course GitHub repository and navigate to `day6/`
2. Create a virtual environment: `python3 -m venv venv && source venv/bin/activate`
3. Install dependencies: `pip install pandas scikit-learn`
4. Run `python3 simple_log_analysis.py` — record every line of output
5. Run `python3 aiops_log_analysis.py` — record every anomaly line (❌ markers)
6. Create a comparison table: for each anomaly detected by the AIOps script, note (a) its log level, (b) whether the simple script would have detected it, (c) its business significance
7. Reflection: How many anomalies were only found by AIOps? What would happen in production if only the simple script was deployed?

### Lab 2 — Tune the Contamination Parameter
**Objective:** Understand the effect of the `contamination` parameter on detection sensitivity.
**Steps:**
1. Make a copy of `aiops_log_analysis.py`: `aiops_log_analysis_tuning.py`
2. Run the script three times with different values:
   - `contamination=0.05` → record anomaly count
   - `contamination=0.10` → record anomaly count (baseline from episode)
   - `contamination=0.20` → record anomaly count
3. For each value, list which specific log lines are flagged as anomalies
4. Identify the "stable anomalies" (flagged at all three contamination values) — these are your highest-confidence detections
5. Identify the "edge case anomalies" (only flagged at 0.20) — these are potential false positives
6. Write a one-paragraph recommendation for what contamination value to use in production, justifying your choice

### Lab 3 — Add a Third Feature to the Model
**Objective:** Improve anomaly detection accuracy by engineering additional features.
**Steps:**
1. Copy `aiops_log_analysis.py` as `aiops_enhanced.py`
2. Add a second feature: message length (number of characters in the log message)
   ```python
   df["message_length"] = df["message"].str.len()
   ```
3. Train the model on both `level_numeric` AND `message_length`:
   ```python
   df["anomaly"] = model.fit_predict(df[["level_numeric", "message_length"]])
   ```
4. Compare the output to the original script — did adding message length change which lines are flagged?
5. Reflection: Why might very long log messages (e.g., stack traces that slipped through the regex) be anomaly indicators? What does a very short log message indicate?

### Lab 4 — Build a Production-Style Alert Integration
**Objective:** Evolve the script from a demo to a production-deployable tool.
**Steps:**
1. Replace the `print` statements in `aiops_log_analysis.py` with structured output:
   ```python
   import json
   anomalies = []
   for _, row in df.iterrows():
       if row["anomaly"] == -1:
           anomalies.append({
               "timestamp": row["timestamp"],
               "log_level": row["log_level"],
               "message": row["message"],
               "severity_score": row["level_numeric"]
           })
   print(json.dumps({"anomaly_count": len(anomalies), "anomalies": anomalies}, indent=2))
   ```
2. Run the script and save the output to a JSON file: `python3 aiops_log_analysis.py > anomaly_report.json`
3. Inspect `anomaly_report.json` — verify the structure is correct
4. Optional challenge: send the JSON to a Slack webhook using the `requests` library:
   ```python
   import requests
   webhook_url = "https://hooks.slack.com/services/YOUR/WEBHOOK/URL"
   requests.post(webhook_url, json={"text": f"AIOps detected {len(anomalies)} anomalies"})
   ```
5. Reflection: What would you need to change to run this script on a schedule (every 5 minutes against fresh logs)?

</details>



<details>
<summary><b>Day 7 — Create your First AI Agent with Zero Coding and Zero Cost (CS46H)</b></summary>

## Beginner Interview Questions

1. What is the fundamental difference between an AI assistant (e.g., ChatGPT) and an AI agent?
2. Give two real-world examples of AI agents that can implement complex DevOps tasks end-to-end (from the episode).
3. Name three open-source AI agent frameworks mentioned in the episode.
4. Why does the instructor prefer local LLMs over OpenAI APIs for this project? Give two reasons.
5. What Python version range does CrewAI require, and what happens if you use an unsupported version?
6. What command creates a new CrewAI project with the full scaffolded folder structure?
7. In the auto-generated project, which two YAML files do you configure, and what does each one define?
8. In `main.py`, what is the only change you need to make to research a different topic?
9. What are the two agents created by default in a new CrewAI project, and what is each one's role?
10. Why does the generated report contain outdated Kubernetes information when using Llama 3.1?

## Intermediate Interview Questions

1. Explain the "stitching problem" with AI assistants. How do AI agents solve it? Use a web application build scenario as an example.
2. A developer says "I use ChatGPT to generate all my Terraform code, so I'm already using AI agents." Is this correct? Explain the distinction.
3. What is the relationship between an AI agent and an LLM? Why can an agent not function without an LLM?
4. Compare the three open-source frameworks mentioned (AutoGen, LangGraph, CrewAI): what is the key differentiator for each, and when would you choose one over another?
5. Explain the role of the `backstory` field in `agents.yaml`. How does it influence the LLM's output, and what happens if you provide a very generic vs. very specific backstory?
6. In the two-agent architecture, why does Agent 1 produce "10 bullet points" rather than the full report? What would happen if you asked Agent 1 to produce the full report directly?
7. What is `Process.sequential` in `crew.py`? How does it differ from `Process.hierarchical`, and when would you use each?
8. Why does CrewAI use `uv` instead of `pip` for dependency management? What advantage does `uv.lock` provide that a plain `pip install` does not?
9. The demo shows that Llama 3.1 produces outdated Kubernetes version information. What specific technical reason causes this, and what are two solutions the instructor proposes?
10. What Python concept do the `@agent`, `@task`, and `@crew` decorators use in `crew.py`? Why is it important NOT to modify this file?

## Advanced Interview Questions

1. **Production Agent Architecture Design:** You are building a production CrewAI agent that assists your SRE team by: (a) monitoring a Prometheus metrics endpoint every 5 minutes, (b) detecting anomalies in the metrics, (c) drafting a plain-English incident report, (d) posting the report to a Slack channel. Design the full multi-agent architecture: number of agents, role/goal/backstory for each, task sequence, and which tools each agent needs (e.g., HTTP client for Prometheus, Slack webhook for posting). Justify why you need more than one agent.
2. **Local vs. Hosted LLM Decision Matrix:** Your organization wants to deploy CrewAI agents in production. Build a decision matrix for choosing between Ollama (local), OpenAI API, and Anthropic API as the LLM backend. Include: (a) data sensitivity requirements (PII in prompts?), (b) cost model (volume of requests/day), (c) latency requirements (seconds vs. minutes acceptable?), (d) inference hardware availability (GPU vs. CPU), (e) knowledge freshness requirements (real-time vs. training-cutoff), (f) your final recommendation for a healthcare SRE team with strict HIPAA requirements.
3. **Extending to a Three-Agent System:** The current system has Researcher → Reporting Analyst. Add a third agent: a Fact Checker that validates each claim in the researcher's 10 bullet points before they are passed to the Reporting Analyst. (a) Write the `agents.yaml` entry for the Fact Checker (role, goal, backstory), (b) write the `tasks.yaml` entry for the fact-checking task (description, expected_output), (c) update `crew.py` to include the new agent and task in `Process.sequential` order, (d) explain what the Fact Checker's expected output should look like so it is useful input for the Reporting Analyst.
4. **Tool Integration:** By default, CrewAI agents using a local LLM cannot access the internet. The CrewAI framework supports "tools" — Python functions agents can call to gather external data. (a) Research the `SerperDevTool` (Google search) and `WebsiteSearchTool` — describe how they work and what API key they require, (b) modify `agents.yaml` to assign the `SerperDevTool` to the researcher agent, (c) explain how adding web search changes the data flow and why it would fix the "outdated knowledge" problem, (d) what new security consideration does internet-accessible tool use introduce compared to a purely local LLM?
5. **CrewAI for DevOps Automation:** Design a three-agent CrewAI system that automates a security audit of a Kubernetes cluster: Agent 1 (Scanner) reads the output of `kubectl get pods --all-namespaces -o json` and extracts security-relevant fields; Agent 2 (Analyst) checks each finding against CIS Kubernetes Benchmark controls; Agent 3 (Reporter) generates a prioritized remediation report. (a) Define role/goal/backstory for each agent, (b) define the task sequence and expected outputs, (c) which tool would the Scanner agent need to call `kubectl`? (d) what are the security implications of an agent that can execute `kubectl` commands?
6. **Model Parameter Trade-offs:** The instructor mentions that Llama 3.1 has 4.7 billion parameters vs. newer models with more. (a) Explain what "parameters" represent in an LLM and how they relate to model capability, (b) compare Llama 3.1 (4.7B), Llama 3.3 (70B), and GPT-4 (~1T estimated) in terms of RAM requirements and inference speed on CPU, (c) for a DevOps organization with a 32GB RAM server (no GPU), which local model would you recommend and why? (d) when does the "more parameters = better" rule break down?
7. **Agent Failure and Recovery:** The instructor briefly mentions agents can "unblock themselves" by creating sub-agents. (a) Describe what CrewAI's `Process.hierarchical` mode does when an agent fails mid-task, (b) design a retry-with-escalation pattern: if the researcher agent returns fewer than 10 bullet points (incomplete output), a retry agent re-invokes the researcher with a more specific prompt, (c) how would you detect "fewer than 10 bullet points" programmatically in `crew.py`? (d) at what point should the system give up and alert a human instead of retrying?

## Lab Exercises

### Lab 1 — Run the Kubernetes Research Demo
**Objective:** Complete the exact project from the episode and observe multi-agent execution.
**Steps:**
1. Verify prerequisites: `python3 --version` (must be 3.10–3.13) and `ollama list` (Llama 3.1 present)
2. Create `crew_example/` directory and virtual environment, activate it
3. `pip install crewai`
4. `crewai create crew devops_ai_project` — select Ollama + llama3.1
5. `cd devops_ai_project && crewai install`
6. Open `src/devops_ai_project/main.py` — change topic to `'kubernetes'` if not already set
7. `crewai run` — observe the terminal output, noting when Agent 1 completes and Agent 2 starts
8. Open `report.md` in a Markdown viewer — read the generated report
9. Reflection: (a) How long did each agent take? (b) What was the quality of the Kubernetes information? (c) Was anything outdated? Note the Kubernetes version mentioned in the report.

### Lab 2 — Research a Different Topic
**Objective:** Understand how easily CrewAI agents generalize to new domains.
**Steps:**
1. Using the same project from Lab 1, open `main.py`
2. Change `'topic': 'kubernetes'` to a topic relevant to your own work (e.g., `'docker'`, `'GitOps'`, `'OpenTelemetry'`, `'Argo CD'`)
3. `crewai run` — wait for the new report to generate
4. Compare `report.md` to the Kubernetes report:
   - Is the structure the same? (Should be — same task definition)
   - Is the quality comparable?
   - What limitations do you observe from the local LLM's knowledge cutoff?
5. Optional: edit `agents.yaml` to give the researcher a more specific backstory for your chosen topic — re-run and compare

### Lab 3 — Customize the Output Format
**Objective:** Modify `tasks.yaml` to produce a different report format.
**Steps:**
1. Open `src/devops_ai_project/config/tasks.yaml`
2. Change the `reporting_task.expected_output` to request a table format:
   ```
   A markdown table with columns: Trend | Description | Impact (High/Medium/Low) | Action Required
   Each of the 10 research points as a row in the table.
   ```
3. Run `crewai run` again
4. Inspect `report.md` — did the agent produce a table? If not, what did it produce instead?
5. Experiment: change `output_file: report.md` to `output_file: kubernetes_report.md` — verify the file is created with the new name
6. Reflection: What does this experiment reveal about how precisely agents follow formatting instructions?

### Lab 4 — Add a Third Agent (Summarizer)
**Objective:** Extend the default two-agent system to a three-agent pipeline.
**Steps:**
1. Open `src/devops_ai_project/config/agents.yaml` and add a third agent:
   ```yaml
   executive_summarizer:
     role: >
       {topic} Executive Summarizer
     goal: >
       Distill the detailed {topic} report into a 3-sentence executive summary
     backstory: >
       You are a CTO-level communicator who specializes in translating
       technical research into clear, action-oriented summaries for
       non-technical leadership.
   ```
2. Open `tasks.yaml` and add a third task:
   ```yaml
   summary_task:
     description: >
       Read the full {topic} report and write a 3-sentence executive summary
       suitable for a non-technical VP or CTO. Focus on business impact.
     expected_output: >
       Exactly 3 sentences. First sentence: what is changing in {topic}.
       Second sentence: what the business risk is if ignored.
       Third sentence: the single most important action to take.
     output_file: executive_summary.md
     agent: executive_summarizer
   ```
3. Open `crew.py` and add the new `@agent` method and `@task` method following the existing pattern
4. `crewai run` — verify both `report.md` and `executive_summary.md` are generated
5. Reflection: Read the executive summary — is it actually 3 sentences? Did the agent follow the format precisely? What does this tell you about LLM instruction-following at smaller parameter counts?

</details>



<details>
<summary><b>Day 8 — AI Agent for Internal Documentation in 30 Minutes (CS46H)</b></summary>

## Beginner Interview Questions

1. Why can't an organization upload its internal documentation to ChatGPT to help employees?
2. What fictional internal tool does the Day 8 demo use, and what type of platform is it?
3. What two AI/ML tools are combined to build the internal documentation agent? (framework + LLM runtime)
4. What prompt engineering technique was used to generate the fake Viraala documentation PDF?
5. Why is the virtual environment folder named `.ai_sandbox` (with a dot prefix)?
6. What is the purpose of the `.env` file in this project? What two values does it contain?
7. Which existing CrewAI example was cloned and adapted instead of building from scratch?
8. In `main.py`, what Python function replaces the hardcoded question to allow dynamic user input?
9. What error occurs if you update the agent key in `agents.yaml` but forget to update `tasks.yaml`?
10. What does the `train()` function in `main.py` do, and when is it most valuable to add training examples?

## Intermediate Interview Questions

1. Explain the key architectural difference between the Day 7 project (Kubernetes research) and the Day 8 project (internal documentation). Why does Day 8 only need one agent?
2. A security officer asks: "How do we know the internal documentation isn't being sent to OpenAI?" Walk through the architecture to explain exactly where the data flows and where it stays local.
3. What is CrewAI's `knowledge` feature? How does it differ from simply putting the document content in the agent's prompt (context stuffing)?
4. The instructor notes that a `KeyError` occurred during the demo. Explain the exact cause of this error and the specific change needed to fix it.
5. Why does `crewai run` fail with an "OpenAI API key" error when Ollama was selected during `crewai create crew`? What mechanism in the project overrides the default LLM provider?
6. Describe the `pyproject.toml` bug the instructor encountered during `crewai install`. What is the root cause, and how is it fixed?
7. Compare the Day 8 approach (CrewAI knowledge + local LLM) to a traditional ELK stack search for navigating internal documentation. What can the AI agent do that ELK cannot?
8. The instructor says "more training = more accurate answers." What exactly happens during training in CrewAI? Is this fine-tuning the LLM weights, or something else?
9. The Viraala PDF is 30 pages. If the documentation were 500 pages, what technical challenges would arise, and how might you address them?
10. What prompt engineering techniques did the instructor apply when generating the Viraala documentation with ChatGPT? Identify at least three techniques by name.

## Advanced Interview Questions

1. **Production Deployment Architecture:** Your organization wants to deploy the internal documentation agent as a service used by 500 employees. Design the production architecture: (a) How do you expose the `crewai run` functionality as an HTTP API (hint: Flask or FastAPI wrapper), (b) how do you handle concurrent requests from multiple users simultaneously, (c) how do you update the documentation when the PDF changes without redeploying the entire service, (d) how do you add authentication so only employees (not external users) can query the agent, (e) what logging/monitoring would you add to track agent usage and detect hallucinations at scale?
2. **Multi-Document Knowledge Base:** Your organization has 20 internal tools, each with their own documentation PDF (totaling 800 pages across all documents). Extend the Day 8 architecture to handle this: (a) how does CrewAI's `PDFKnowledgeSource` handle multiple files? Show the `crew.py` modification, (b) what routing problem arises when 20 documents are loaded — how does the agent know which document to search? (c) propose a multi-agent architecture where a "router" agent selects the relevant document before the "expert" agent answers, (d) at what document volume does a vector database (Chroma, Qdrant, Pinecone) become necessary instead of CrewAI's built-in knowledge?
3. **RAG Architecture Deep Dive:** CrewAI's knowledge feature implements Retrieval Augmented Generation (RAG) internally. (a) Explain the three phases of RAG: document chunking, embedding, and retrieval. What happens during each phase when the PDF is loaded? (b) What embedding model does CrewAI use by default, and how can it be overridden? (c) What chunk size and overlap settings affect retrieval quality, and how would you tune them for a 30-page technical specification? (d) How does the retrieved context get assembled into the LLM prompt? (e) What is the "lost in the middle" problem in RAG, and how does it affect long-document retrieval?
4. **Hallucination Detection and Mitigation:** The instructor acknowledges that local models will hallucinate. Design a hallucination detection system: (a) define what hallucination means in the context of document-grounded Q&A (the answer contains information NOT in the PDF), (b) propose a "grounding check" second agent that verifies each answer against the PDF source and marks it as "verified" or "unverified," (c) implement a confidence scoring approach where the agent appends a citation ("This answer is based on page X of the documentation"), (d) how would you build a test suite of 50 known Q&A pairs to measure the agent's accuracy before deploying to employees?
5. **Security and Privacy Hardening:** You are deploying this agent for a healthcare organization handling HIPAA-protected internal documentation. (a) What specific threats does the local LLM architecture protect against compared to OpenAI API? (b) What residual security risks remain even with a local LLM (e.g., the PDF on disk, the agent's training data, the server running Ollama)? (c) How would you encrypt the PDF at rest and ensure the agent can only access it during query time? (d) Should training data (questions asked by employees) be retained? What are the privacy implications? (e) Design an audit log that records every query without storing the actual question text (hint: use hashing).
6. **Model Selection for Production:** The demo uses Llama 3.1 (4.7B parameters). For a production deployment answering technical questions from a 500-page architecture document, evaluate three local model options: (a) Llama 3.1 8B, (b) Llama 3.3 70B, (c) Mistral 7B. For each: required RAM, inference latency per question (estimate), suitability for technical Q&A, and recommended hardware specs. Which would you choose for a server with 64GB RAM and 4× A100 GPUs?
7. **Continuous Documentation Updates:** Internal documentation changes frequently. Design a CI/CD pipeline for documentation updates: (a) trigger: documentation team pushes a new PDF version to a Git repository, (b) automated test: run 10 golden-path Q&A pairs against the new PDF and verify the agent answers correctly, (c) deployment: if tests pass, update the production agent's knowledge source with the new PDF, (d) rollback: if the new PDF causes accuracy regression (>20% of golden-path tests fail), automatically revert to the previous PDF version, (e) notification: alert the documentation team with a report showing which questions degraded and which improved.

## Lab Exercises

### Lab 1 — Build the Viraala Documentation Agent
**Objective:** Complete the exact project from the episode.
**Steps:**
1. Use ChatGPT to generate the Viraala PDF using the few-shot prompt from the episode (or download it from the Day 8 course folder)
2. Clone `crewai-examples` and navigate to `MetaQuest_knowledge/`
3. Follow all 10 steps from the episode:
   - Swap the PDF, update agents.yaml, tasks.yaml, main.py, crew.py, create .env
4. Run `crewai install` (fix any pyproject.toml name errors if they arise)
5. Run `crewai run` and ask: "What is Viraala tool?"
6. Ask a second question: "How does Viraala compare to Prometheus?"
7. Record both answers and note any hallucinations (claims not in the PDF)
8. Reflection: How accurate were the answers? What would you add to the training examples to improve quality?

### Lab 2 — Generate Documentation for a Real Internal Tool
**Objective:** Apply the same pattern to a tool your organization actually uses.
**Steps:**
1. Choose an internal tool from your work or an open-source tool you know well (e.g., your company's CI/CD pipeline, a custom API, a monitoring setup)
2. Use ChatGPT to generate a fake but realistic 20-page documentation PDF for this tool using the few-shot prompting technique from the episode
3. Swap the Viraala PDF for your new tool's PDF in the `knowledge/` folder
4. Update `agents.yaml` with a role and backstory specific to your tool
5. Run `crewai run` and ask 5 questions you would realistically ask about this tool
6. For each answer: (a) is it accurate? (b) is it grounded in the PDF? (c) what training example would you add?

### Lab 3 — Add Dynamic Multi-Turn Conversation
**Objective:** Allow the user to ask multiple questions in a single session instead of restarting the agent each time.
**Steps:**
1. Modify `main.py`'s `run()` function to loop:
   ```python
   def run():
       print("Viraala Documentation Agent — type 'quit' to exit")
       while True:
           question = input("Your question: ")
           if question.lower() == 'quit':
               break
           inputs = {'question': question}
           MetaquestKnowledgeCrew().crew().kickoff(inputs=inputs)
   ```
2. Run `crewai run` and ask 3 consecutive questions in one session
3. Observe: Does the agent remember previous questions in the conversation? (It should not — each `kickoff()` is stateless)
4. Reflection: What would need to change architecturally to give the agent conversation memory? (Hint: look at CrewAI's memory features)

### Lab 4 — Build the Agent for Your Organization
**Objective:** Prototype a real internal documentation agent for a documentation set you have access to.
**Steps:**
1. Identify a publicly available PDF document that represents the kind of internal documentation your organization might have (e.g., a tool's architecture design document, an open-source project's contributor guide, a compliance framework document like NIST or CIS Benchmarks)
2. Replace the Viraala PDF with this real document
3. Update `agents.yaml` backstory to match the document's domain
4. Define 10 representative questions your team would actually ask about this document
5. Run the agent against all 10 questions and record answers
6. Score each answer: Accurate / Partially Accurate / Hallucinated
7. Add training examples for the "Partially Accurate" and "Hallucinated" cases
8. Re-run and compare the scores — did training improve accuracy?
9. Write a one-page proposal for deploying this to your organization, covering: benefit, risk, data privacy approach, and recommended LLM model

</details>



<details>
<summary><b>Capstone — AI DevSecOps Workflow on Pull Requests (CS46H)</b></summary>

## Beginner Interview Questions

1. What is a DevSecOps workflow, and why is it needed when developers use AI to write code?
2. What is Sim.ai, and what two methods does it offer for building AI workflows?
3. What is the "Mothership" feature in Sim.ai? What input does it require?
4. Name the five blocks in the DevSecOps AI workflow built in this session, in order.
5. What role does the GitHub webhook play in this workflow? When is it triggered?
6. What three types of security vulnerabilities does the default security agent check for?
7. Where should you store your GitHub Personal Access Token in Sim.ai, and why?
8. After deploying the workflow, what URL do you configure in GitHub repository settings?
9. In the demo, what vulnerability was detected in the test PR? What severity was assigned?
10. What was the AI's overall recommendation after detecting the vulnerability — approve or block?

## Intermediate Interview Questions

1. Explain why a natural language prompt-based security workflow is more flexible than a traditional SAST tool. Give a concrete example of adding or removing a security check.
2. A developer argues: "Our SAST tool already catches hardcoded secrets — why do we need this AI workflow?" Provide three reasons the AI approach is superior or complementary.
3. The Capstone workflow uses a "bring your own model" approach. What are the trade-offs between using GPT-4o (OpenAI hosted) vs. Llama 3.3 (local via Ollama) for the security analysis agent?
4. Describe the complete data flow from "developer opens PR" to "security report posted." Name each system involved and what data passes between them.
5. How would you configure this workflow to cover all 50 repositories in your GitHub organization without creating 50 separate workflows?
6. The instructor says you can add a Mailchimp block or a Slack block to the workflow. What architectural pattern does this represent — and what does it tell you about Sim.ai's design philosophy?
7. What is the difference between Mothership and the traditional drag-and-drop Workflow Builder? When would you use each?
8. The prompt stored in `DevSecOps.md` specifies the output format of the security report. Why is defining the output format in the prompt important for the downstream "Post PR Comment" block?
9. What GitHub token scopes are required for the workflow to post comments on pull requests? Why is a read-only token insufficient?
10. The workflow currently has no secret validation on the webhook. What security risk does this create, and how would you mitigate it?

## Advanced Interview Questions

1. **Production Hardening:** You are deploying this AI DevSecOps workflow for a Fortune 500 company with 500 engineers and 2,000 repositories. Design the production architecture: (a) how do you apply a single webhook to all repositories at the organization level (not repo level) in GitHub, (b) how do you rate-limit the workflow to prevent credit exhaustion during a mass PR event (e.g., a company-wide refactoring sprint), (c) how do you handle false positives at scale — if 10% of PRs are incorrectly blocked, what escalation path exists?, (d) what SLA do you offer engineers ("your PR will be reviewed within N seconds"), and what determines that N?
2. **Multi-Language Security Rules:** The current prompt checks for generic vulnerabilities. Design language-specific prompts: (a) write a Python-specific security prompt section covering: eval() usage, pickle deserialization, SQL string concatenation (not parameterized queries), and subprocess shell=True, (b) write a JavaScript-specific section covering: prototype pollution, innerHTML XSS, eval(), and unvalidated redirects, (c) how would you auto-detect the programming language of changed files and route to the appropriate prompt section? (d) What is the risk of a "catch-all" vs. language-specific security prompt?
3. **Feedback Loop and Continuous Improvement:** The AI will produce false positives and false negatives. Design a feedback system: (a) when a developer disagrees with a "BLOCK MERGE" verdict, how do they appeal it — what workflow block do you add to capture the appeal?, (b) how do you use accumulated false positive data to refine the prompt?, (c) define a precision/recall framework for measuring the security agent's accuracy over 1,000 PRs — what constitutes a "good" security agent metric?, (d) at what false positive rate would you recommend disabling the "auto-block" feature and switching to "advisory only"?
4. **OWASP Integration:** Extend the workflow to check against the OWASP Top 10 (2021). (a) Write the prompt section that maps each OWASP Top 10 category to specific code patterns the AI should look for, (b) for OWASP A02:2021 (Cryptographic Failures), define 5 specific patterns the AI should detect in source code, (c) how would you map AI findings to OWASP category IDs in the output report for compliance reporting?, (d) what is the limitation of using an LLM for OWASP compliance verification vs. a dedicated tool like OWASP ZAP?
5. **Infrastructure-as-Code Security:** Extend the workflow beyond application code to IaC files. (a) Write a Terraform-specific security check prompt covering: S3 bucket public access, security groups with 0.0.0.0/0, unencrypted EBS volumes, IAM roles with wildcard permissions, (b) write a Kubernetes manifest check covering: containers running as root, missing resource limits, privileged containers, hostPath volumes, (c) how would you route Terraform files vs. Kubernetes manifests vs. application code to different AI agents in the same workflow?, (d) what risk does checking IaC in PRs (before apply) miss vs. checking deployed infrastructure state?
6. **Cost Optimization:** The pro plan charges per credit. Design a cost-efficient workflow: (a) estimate the cost of analyzing a PR with 10 changed files, each averaging 200 lines of diff, using GPT-4o at standard pricing, (b) which files should be excluded from security analysis (e.g., test files, auto-generated files, documentation), and how do you implement that filter in the workflow?, (c) at what organization size does running a local Ollama instance for the security agent become cheaper than using the OpenAI API?, (d) propose a tiered approach: fast/cheap model for initial triage, expensive model only for high-severity findings.
7. **Compliance and Audit Trail:** Your organization requires an immutable audit log of all security reviews for SOC 2 compliance. (a) What data from each workflow execution must be logged (PR number, files analyzed, findings, recommendation, timestamp, model used)?, (b) design a workflow extension that writes each execution result to an append-only database or S3 bucket, (c) how do you ensure the audit log cannot be tampered with (hint: cryptographic hash of each record), (d) what is the data retention requirement, and how do you implement automated purging of records older than the compliance window?

## Lab Exercises

### Lab 1 — Build the DevSecOps AI Workflow
**Objective:** Complete the exact workflow from the episode using Sim.ai.
**Steps:**
1. Create a free Sim.ai account (you receive 1,000 credits)
2. Go to Workspace → Files → New File → name it `DevSecOps.md`
3. Paste the DevSecOps workflow requirements prompt (from the episode description or course folder)
4. Go to Mothership and type: "Build an AI workflow according to the requirement that is in the file DevSecOps.md from the workspace"
5. Wait 30–60 seconds for the workflow to be generated
6. Review all 5 blocks — verify they match the architecture from the study guide
7. Go to Settings → Secrets → add your GitHub Personal Access Token
8. Click Deploy → copy the webhook URL
9. Add the webhook to a test GitHub repository (Settings → Webhooks → Pull requests event)
10. Create a test PR with an intentional vulnerability (e.g., a hardcoded API key string in any file)
11. Wait 60 seconds → check the PR for the AI security report comment
12. Reflection: Was the vulnerability detected? What severity was assigned? Was the recommendation accurate?

### Lab 2 — Customize the Security Checks
**Objective:** Modify the security agent's check list and observe the behavior change.
**Steps:**
1. Open your `DevSecOps.md` prompt file in Sim.ai Workspace
2. Add two new security checks to the prompt:
   - "Check for use of `eval()` in JavaScript/Python files"
   - "Check for API endpoints with no authentication decorators/middleware"
3. Ask Mothership to regenerate/update the workflow: "Update the security analysis block in my workflow to use the revised DevSecOps.md prompt"
4. Create a test PR with `eval("user_input")` in a JavaScript file
5. Verify the new check appears in the security report
6. Remove the "unsafe deserialization" check from the prompt and regenerate
7. Create a PR with a deserialization pattern — verify it is no longer flagged
8. Reflection: What does this exercise demonstrate about the prompt-as-configuration philosophy?

### Lab 3 — Add a Slack Notification Block
**Objective:** Extend the workflow to notify a Slack channel when a CRITICAL vulnerability is found.
**Steps:**
1. In Sim.ai, open your deployed DevSecOps workflow
2. Create a Slack webhook URL for a test channel in your Slack workspace
3. Add a Slack notification block after "Post PR Comment"
4. Configure the block: only send a notification if the overall recommendation is "BLOCK MERGE"
5. Message format: "🚨 CRITICAL security finding in PR #{{pr_number}} in {{repo_name}} — review immediately"
6. Store the Slack webhook URL in Sim.ai Secrets
7. Deploy the updated workflow
8. Create a PR with a critical vulnerability → verify both the PR comment AND the Slack message are sent
9. Create a PR with only a LOW severity finding → verify Slack is NOT notified (only PR comment)

### Lab 4 — Multi-Repo Deployment
**Objective:** Configure the workflow to cover 3 separate GitHub repositories with a single deployment.
**Steps:**
1. Using the same Sim.ai webhook URL from Lab 1
2. Add the webhook to 2 additional GitHub repositories (you can fork any public repos)
3. Create PRs in each of the 3 repositories with different vulnerability types:
   - Repo 1: hardcoded password
   - Repo 2: SQL injection pattern
   - Repo 3: command injection (`subprocess.call(user_input, shell=True)`)
4. Verify all 3 PRs receive AI security report comments from the same workflow
5. Check Sim.ai Logs → verify all 3 executions appear with their repo names
6. Reflection: How does this "one workflow, many repos" architecture compare to installing a SAST tool on each repository individually?

</details>



<details>
<summary><b>Bonus 1 — kubectl Pod Topology AI Plugin (CS46H)</b></summary>

## Beginner Interview Questions

1. What is a kubectl plugin? How does kubectl discover and execute plugins installed on the system?
2. What does the `kubectl pod-topology` command do? What three parameters does it require?
3. Why are two different AI APIs used in this project instead of one? What does each API do?
4. What is Luma AI, and why was it chosen over OpenAI for image generation in this project?
5. Where must an API key file never be stored, and what file contains the API keys in this project?
6. What Kubernetes resources does the plugin analyze to build the traffic flow relationship?
7. In the demo, what was the TLS status of the nginx ingress, and how was it shown in the generated image?
8. What visual indicator in the generated image shows that a pod is in a healthy `Running` state?
9. What command verifies that kubectl has recognized and registered your plugin correctly?
10. What does `install.sh` do, and why is it necessary after writing the Python script?

## Intermediate Interview Questions

1. Explain the two-step API call architecture in detail. What prompt does OpenAI generate, and how does Luma AI use it?
2. A team member says "We can just use `kubectl describe pod` — why do we need this plugin?" Provide three concrete scenarios where the visual topology image is more useful than raw text output.
3. What is the `kubectl-` prefix convention? Explain exactly how kubectl discovers, validates, and executes a plugin binary.
4. The plugin currently saves images to local directories only. Design the code change needed to save to an S3 bucket instead — what AWS SDK functions would you call, and what IAM permissions would the script need?
5. Why is the OpenAI API call made first before the Luma AI call? Could you reverse the order? Explain what would fail.
6. How does the plugin determine which Service and Ingress are associated with the given pod? What Kubernetes label selector mechanism is involved?
7. The instructor mentions that pod status icons change color (green for Running, red for CrashLoopBackOff). How does the plugin communicate pod status to Luma AI — through the text prompt? What specific words in the prompt would produce a red icon vs. a green icon?
8. Compare this kubectl plugin approach (Python + AI) to using tools like Lens or k9s for Kubernetes visualization. What unique capability does the AI-generated image provide that these tools cannot?
9. What happens when the plugin runs against a pod that has no associated Ingress? Design the error handling behavior.
10. The plugin uses `.env.local` for API keys. What is the security risk of this approach in a shared CI/CD environment, and what is the secure alternative?

## Advanced Interview Questions

1. **Production Plugin Architecture:** Design a production-grade kubectl plugin distribution system for a 200-person engineering organization: (a) how do you distribute plugin updates — centralized package registry, Homebrew tap, or OS package manager? (b) how do you enforce that all engineers use the same plugin version? (c) how do you rotate the API keys used by the plugin across all engineer machines without requiring manual `.env.local` updates? (d) what happens when a new engineer joins — what is their installation experience?
2. **Multi-Pod Topology:** The current plugin visualizes one pod. Extend it to visualize an entire application's topology: (a) given a Kubernetes Deployment name, enumerate all pods in that Deployment, (b) show all replicas with their individual health states, (c) show load balancing across pods from the Service, (d) how does the complexity of the OpenAI prompt change as the number of pods increases? At what scale would you switch to a different visualization approach?
3. **Gateway API Support:** Kubernetes is migrating from Ingress to Gateway API (HTTPRoute, Gateway, GatewayClass). (a) Describe the resource hierarchy in Gateway API vs. classic Ingress, (b) what changes are needed in the "gather cluster resources" function to query HTTPRoutes instead of Ingress objects, (c) how does the prompt to OpenAI change to describe a Gateway API topology vs. a classic Ingress topology? (d) what kubectl API groups must the plugin query for Gateway API resources?
4. **Real-Time Topology Monitoring:** Design a `--watch` mode that continuously regenerates the topology image during incidents: (a) implement a polling loop that re-runs the plugin every 30 seconds and saves images as `topology_<timestamp>.png`, (b) design a diff mechanism that compares consecutive images and alerts when topology changes, (c) what Kubernetes event to watch (instead of polling) would give near-real-time topology updates? (d) how would you stream topology changes to a Slack channel as an incident unfolds?
5. **Cost Analysis:** The plugin makes two paid API calls per invocation. Calculate the total cost per week for a 50-engineer team where each engineer runs the plugin an average of 10 times per day: (a) estimate OpenAI API cost (GPT-4o pricing per token, assume 500 tokens in + 500 tokens out), (b) estimate Luma AI image generation cost (research current pricing), (c) identify which optimization reduces cost the most: caching (avoiding duplicate calls for the same pod), cheaper models, or batching requests, (d) at what usage level is a self-hosted image generation model (Stable Diffusion) cheaper than Luma AI?

## Lab Exercises

### Lab 1 — Set Up and Run the kubectl Pod Topology Plugin
**Objective:** Complete the exact project from the episode and generate a topology image.
**Steps:**
1. Get an OpenAI API key (platform.openai.com → API Keys)
2. Get a Luma AI API key (platform.lumalabs.ai → API section)
3. Clone the repository: `git clone https://github.com/abhishekveeramalla/kubectl-pod-topology`
4. Create `.env.local` with both API keys
5. Run `./install.sh` to install the plugin
6. Verify with `kubectl plugin list` — confirm `kubectl-pod-topology` appears
7. Create a test namespace and deploy a workload with Deployment + Service + Ingress
8. Run `kubectl pod-topology <pod-name> <namespace> /tmp/topology/`
9. Open the generated image — verify the topology is accurate
10. Reflection: Does the image correctly show the Ingress → Service → Pod flow? Is the pod status shown?

### Lab 2 — Test with Multiple Pod States
**Objective:** Verify that the image changes when pod health changes.
**Steps:**
1. Using the setup from Lab 1, deliberately crash the pod:
   ```bash
   # Edit the deployment to use an invalid image
   kubectl set image deployment/<name> <container>=invalid-image:broken
   ```
2. Wait for the pod to enter `CrashLoopBackOff` state (`kubectl get pods`)
3. Re-run `kubectl pod-topology` — generate a new image
4. Compare the two images: (a) Did the pod icon change color? (b) What changed in the image?
5. Fix the deployment: `kubectl rollout undo deployment/<name>`
6. Generate a third image — verify the pod returns to green
7. Reflection: How would this visual workflow help during a production incident vs. reading `kubectl describe pod`?

### Lab 3 — Extend the Output to S3
**Objective:** Modify the plugin to save the topology image to an S3 bucket.
**Steps:**
1. Install boto3: `pip install boto3`
2. Add AWS credentials to `.env.local`
3. Modify the image-saving function:
   ```python
   import boto3
   s3 = boto3.client('s3')
   s3.upload_file(local_image_path, 'your-bucket-name', f'topology/{pod_name}_{timestamp}.png')
   print(f"Uploaded to s3://your-bucket-name/topology/{pod_name}_{timestamp}.png")
   ```
4. Run the plugin — verify the image appears in your S3 bucket
5. Generate a pre-signed URL (expires in 24h) and share with a teammate
6. Reflection: What IAM permissions does the script need? Is `s3:PutObject` alone sufficient?

</details>



<details>
<summary><b>Bonus 2 — Enterprise AI Agent for Internal Documentation with Retool (CS46H)</b></summary>

## Beginner Interview Questions

1. Why do most organizations block ChatGPT for internal use? Give two specific reasons.
2. What is Retool, and how does it differ from other AI builder platforms?
3. What is a "Retool Vector," and why is it needed to give an AI agent access to your documents?
4. What are the two trigger types available in Retool, and when would you use each?
5. What is the Configuration Assistant in Retool, and how does it help you write agent instructions?
6. What does BYOM (Bring Your Own Model) mean in the context of Retool?
7. In the demo, what was the name of the fictional internal platform used? What was its documentation about?
8. How does the Retool agent know to search the internal documentation when asked "What is Superbility?"
9. What three SSO providers does Retool support for enterprise authentication?
10. What is the "retrieve tool" in the demo, and what two parameters were set as defaults?

## Intermediate Interview Questions

1. Compare Retool's approach to internal documentation (Retool Vectors + agent) vs. a traditional Elasticsearch/ELK setup. What can the AI agent do that Elasticsearch cannot?
2. A security officer asks: "How do we know our internal documentation isn't being sent to OpenAI for training?" How would you answer, given how Retool vectors work?
3. Explain the vector database concept in plain terms. Why does converting a PDF to vector embeddings make it accessible to an LLM, when storing it as raw text would not work as well?
4. The instructor sets "demo" as the default vector name and "superbility_documentation.pdf" as the default document name. What goes wrong if you skip this step in a multi-vector setup?
5. Describe the email trigger use case for CI/CD integration. Walk through the complete data flow from "CI/CD build fails" to "developer receives diagnosis."
6. Compare Retool (this session) to CrewAI + Ollama (Day 8) across five dimensions. When would you choose each?
7. What is RBAC in the context of a Retool deployment? Give an example of a realistic access control rule an organization might set.
8. The Configuration Assistant turns a plain English description into formal agent instructions. Why is this important for teams that don't have prompt engineering expertise?
9. What happens when you upload multiple documents to the same vector? Can the agent search across all of them simultaneously?
10. The instructor mentions adding a "Calendar event" tool after execution. What use case does this enable, and how does it demonstrate the composability of Retool agents?

## Advanced Interview Questions

1. **Enterprise-Scale Deployment:** Design a Retool deployment for a 2,000-employee engineering organization with 50 internal tools, each having its own documentation PDF: (a) how do you structure the vectors — one per tool or one combined?, (b) how do you implement access control so the DevOps team can only query DevOps tool docs, not HR/Legal docs?, (c) how do you keep the documentation up-to-date when PDFs are updated — is there a webhook or CI/CD integration for vector updates?, (d) how do you measure adoption and ROI — what metrics would you track?
2. **CI/CD Integration Design:** Design the complete email trigger integration for a production CI/CD system: (a) what information should the CI/CD pipeline include in the email to the Retool agent (build logs, failure stage, error message, affected service)?, (b) write the agent instruction that tells it to parse a CI/CD failure email and query the relevant runbook, (c) how does the agent determine which internal tool's documentation to query based on the failure context?, (d) what is the escalation path if the agent cannot find an answer in the documentation?
3. **RAG Quality Improvement:** The agent answers from documents, but answers may be incomplete or inaccurate. Design a quality improvement program: (a) define a test set of 50 golden-path Q&A pairs for each internal tool documentation, (b) run these tests weekly and measure precision@1 (is the top answer correct?), (c) when a question fails, trace whether the failure is in retrieval (wrong document section returned) or in generation (wrong reasoning from correct section), (d) what changes to the document structure (headings, formatting, chunking) would improve retrieval accuracy?
4. **Multi-Agent Architecture:** For complex queries that span multiple internal tools, design a multi-agent Retool setup: (a) a "router agent" that reads the question and determines which tool documentation is relevant, (b) one "specialist agent" per tool category (DevOps, Security, Finance), (c) an "aggregator agent" that combines answers from multiple specialists into a single response, (d) how does Retool support agent chaining — can one agent invoke another?
5. **Compliance and Data Residency:** Your organization is in the EU and must comply with GDPR. The internal documentation contains personal data: (a) what data residency options does Retool offer for EU organizations?, (b) when an employee asks a question and the agent returns an answer citing a document section that contains personal data, what is the compliance exposure?, (c) how would you redact or mask personal data before uploading documents to Retool Vectors?, (d) what audit trail does Retool provide for tracking who asked which questions?

## Lab Exercises

### Lab 1 — Build the Internal Documentation Agent
**Objective:** Complete the exact project from the episode using Retool.
**Steps:**
1. Create a free Retool account (link in episode description)
2. Go to Agents → + New Agent → Start from scratch → name it `documentation-agent-one`
3. Use the Configuration Assistant to generate basic instructions
4. Select a model (GPT-4o mini recommended for cost efficiency)
5. Create a PDF document for a fictional internal tool (use ChatGPT to generate 5–10 pages of realistic documentation)
6. Resources → Retool Vectors → New Vector → upload your PDF
7. In the agent: Tools → + Add Tool → Retool Vector → configure with your vector name and document name as defaults
8. Use the Configuration Assistant to add: "Use [your-vector] as the default vector, [your-doc].pdf as the default document name"
9. Go to the Chat section → ask "What is [your tool name]?"
10. Ask a follow-up question that requires comparing your tool to a known public tool
11. Reflection: Did the agent retrieve accurate information? Did it hallucinate anything not in the PDF?

### Lab 2 — Enable the Email Trigger
**Objective:** Configure the email trigger and test it from an external system.
**Steps:**
1. In your documentation agent → Triggers → enable Email trigger
2. Copy the generated email address for the agent
3. From your personal email, send a message to the agent's email address with a question about your internal tool
4. Wait 30–60 seconds → check the agent's response (via Retool Chat or email reply, depending on configuration)
5. Try sending a question that is NOT in the documentation — observe the fallback behavior
6. Reflection: How would you wire this email address into a GitHub Actions or Jenkins pipeline notification step?

### Lab 3 — Upload Multiple Documents
**Objective:** Test the agent's ability to search across multiple documents.
**Steps:**
1. Using the same vector from Lab 1, upload a second PDF (a different internal tool's documentation)
2. Remove the "default document name" from the tool configuration — leave it blank
3. Ask a question that is only in Document 1 → verify the agent finds it
4. Ask a question that is only in Document 2 → verify the agent finds it
5. Ask a question that spans both documents (e.g., "compare Tool 1 and Tool 2") → observe
6. Re-add the default document name (Document 1 only) → re-ask the Document 2 question
7. Observation: When the default is set, does the agent still search Document 2?
8. Reflection: What is the trade-off between setting a default (efficiency) vs. no default (flexibility)?

</details>



<details>
<summary><b>Bonus 3 — AI Deploys to All Four Environments with Windsurf Cascade (CS46H)</b></summary>

## Beginner Interview Questions

1. What is Windsurf, and what two ways can it be used?
2. What is the Cascade feature in Windsurf? How do you activate it?
3. What are the four deployment environments tested in this session?
4. What application was generated by Cascade as the test subject, and in what language?
5. What is a user data script in the context of AWS EC2? What does the one generated by Cascade do?
6. How many containers were in the Docker Compose file Cascade generated? Name each one.
7. What error occurred during the Kubernetes deployment, and what caused it?
8. How did Cascade resolve the CrashLoopBackOff error — did it require human intervention?
9. Why did Cascade use `kubectl port-forward` instead of Ingress for the kind cluster?
10. What two AWS services were used for the serverless deployment? What role does each serve?

## Intermediate Interview Questions

1. Compare the Cascade agent's behavior on the Kubernetes deployment to what a developer without AI would have done. What specific steps did the agent automate that would have taken significant manual time?
2. Explain why the Docker Compose file Cascade generated included Redis and Prometheus containers that weren't requested. Is this behavior desirable in production? What risk does it introduce?
3. What is the difference between Cascade's "auto access" and "manual approval" modes? For which of the four deployments would you NOT use auto access, and why?
4. Lambda is designed for functions, not static website hosting. What is the technically correct AWS serverless architecture for hosting a static HTML/CSS/JavaScript application? Compare it to what Cascade generated.
5. The instructor has multiple kubectl installations and specifies the path in the prompt. What problem does this solve, and what best practice does this suggest for enterprise Cascade usage?
6. Cascade generated all manifests, Dockerfiles, and deployment scripts within the project folder. How would you adapt this for a real GitOps workflow where manifests live in a separate infrastructure repository?
7. The EC2 deployment used a user data script that installs nginx and copies files. What is the limitation of this approach for production? What would you use instead (hint: AMI baking, container-on-EC2, Auto Scaling Group)?
8. Cascade recognized that it was deploying to a kind cluster and made a different decision than it would for EKS. What does this demonstrate about Cascade's contextual awareness, and what is its limit?
9. The Docker Compose deployment ran 4 containers (app + nginx + Redis + Prometheus). For a production Docker Compose equivalent, what additional concerns are NOT addressed by the generated files?
10. The instructor estimates 7–8 hours for manual completion vs. 20–30 minutes with Cascade. Break down where most of the manual time would be spent. Which environment would take longest, and why?

## Advanced Interview Questions

1. **Production Hardening of All Four Environments:** The Cascade-generated artifacts are functional but not production-ready. For each environment, identify the single most critical missing element: (a) EC2: missing secrets management (the app has no env vars, but what if it needed DB credentials?), (b) Docker Compose: missing secrets management for Redis and Prometheus, (c) Kubernetes: missing resource requests/limits and PodDisruptionBudget, (d) Lambda: missing VPC configuration (Lambda in default VPC has no access to private RDS). For each, write the specific YAML or CLI change needed.
2. **CI/CD Pipeline for All Four Environments:** Design a GitHub Actions workflow that uses Cascade's generated artifacts to deploy the application across all four environments on every push to main: (a) which environment should be deployed to first (which has the fastest feedback loop?), (b) how do you run integration tests after each environment's deployment before proceeding to the next?, (c) what is the rollback strategy for each environment?, (d) how do you manage environment-specific secrets (EC2 key pair, Kubeconfig, AWS Lambda credentials) securely in GitHub Actions?
3. **Kubernetes Production Readiness:** The kind cluster deployment was a proof of concept. Design the changes needed to move to EKS production: (a) replace port-forward with a LoadBalancer service or ALB Ingress Controller — write the Service and Ingress manifest changes, (b) add resource requests and limits to the Deployment, (c) add a HorizontalPodAutoscaler for the deployment, (d) add pod anti-affinity to spread replicas across AZs, (e) add a NetworkPolicy restricting ingress to the Service only.
4. **Cascade Security Model:** Cascade in auto-access mode executed commands on the local machine and created real AWS resources. Design a security model for safe enterprise Cascade usage: (a) what is the blast radius if Cascade misinterprets a prompt and runs a destructive command (e.g., `kubectl delete namespace`)?, (b) what principle of least privilege means for AWS credentials used with Cascade?, (c) how would you sandbox Cascade in a dedicated AWS account with budget limits and SCPs?, (d) what logging and approval workflow would you add for production Cascade usage?
5. **Comparing AI Coding Agents:** Cascade (Windsurf) competed with GitHub Copilot Workspace (Day 1) and similar tools. Design a structured evaluation framework for choosing between AI coding agents for a DevOps team: (a) define 5 evaluation criteria beyond "can it deploy to X", (b) how would you score each agent on multi-file refactoring, error self-healing, infrastructure-awareness, and security hygiene?, (c) what is the cost model difference between Windsurf, GitHub Copilot, and Cursor?, (d) for a team of 50 DevOps engineers, calculate the annual cost of each option.

## Lab Exercises

### Lab 1 — Generate and Test the Application
**Objective:** Use Windsurf Cascade to generate a web application from a natural language prompt.
**Steps:**
1. Download Windsurf IDE (windsurf.com) and create a free account
2. Open Windsurf → press Cmd+L / Ctrl+L to open Cascade
3. Prompt: `"Generate a sample tic-tac-toe application. Project name: my-tic-tac-toe. Language: JavaScript."`
4. Watch Cascade generate the folder structure, HTML, CSS, and JS files
5. Verify the application opens in a browser (Cascade should do this automatically)
6. Play a game to verify it works
7. Reflection: How long did it take? How many files were created? Is the code readable?

### Lab 2 — Deploy to Docker Compose
**Objective:** Use Cascade to generate and run a Docker Compose deployment.
**Steps:**
1. In the same Cascade session from Lab 1, prompt: `"Generate a docker compose file to deploy this application as containers on localhost."`
2. Examine the generated Dockerfile — note the base image (nginx) and what files are copied
3. Examine the docker-compose.yml — how many containers? What are they?
4. Run: `docker compose up -d` (or let Cascade do it)
5. Access `localhost:8080` — verify the application is running
6. Run: `docker compose ps` — verify all containers are healthy
7. Run: `docker compose logs tic-tac-toe` — view the application container logs
8. Reflection: Did Cascade add any containers you didn't ask for? Are they useful or unnecessary for this use case?

### Lab 3 — Deploy to Kubernetes (kind)
**Objective:** Deploy to a local Kubernetes cluster and observe autonomous error recovery.
**Steps:**
1. Install kind: `brew install kind` (macOS) or appropriate for your OS
2. Create cluster: `kind create cluster --name cascade`
3. Verify: `kubectl get nodes`
4. Prompt to Cascade: `"Generate Kubernetes manifests for this application and deploy to the cluster configured with kubectl."`
5. Examine each generated manifest file (namespace, configmap, deployment, service)
6. If pods enter CrashLoopBackOff: run `kubectl logs <pod-name> -n <namespace>` — observe the error
7. Watch if Cascade self-heals the issue without prompting
8. Once pods are Running: `kubectl port-forward -n <namespace> svc/<service> 8081:80`
9. Access `localhost:8081`
10. Reflection: Did Cascade self-heal any errors? What was the error? What change did it make?

### Lab 4 — Parallel Deployments
**Objective:** Use multiple Cascade windows to deploy to EC2 and Docker simultaneously.
**Steps:**
1. In Windsurf, open a second Cascade conversation window (new chat)
2. Window 1: prompt for Docker Compose deployment
3. Window 2: prompt for EC2 deployment (requires AWS CLI configured)
4. Run both simultaneously — observe that they execute in parallel
5. Once both are complete, compare completion times
6. Reflection: What are the benefits of parallel deployment? What coordination risk exists (e.g., if both modify the same file)?

</details>



<details>
<summary><b>Bonus 4 — Docker Model Runner: Local LLMs Without Ollama (CS46H)</b></summary>

## Beginner Interview Questions

1. What is Docker Model Runner, and in which Docker Desktop version was it introduced?
2. What are the four main `docker model` CLI commands and what does each do?
3. Where are Docker Model Runner models hosted? What is the URL, and how is it similar to Docker Hub?
4. What model was used in the demo, and how many parameters does it have? Compare it to the smallest Llama model.
5. What two modes can you run a model in? How do you enter interactive chat mode?
6. What is the main advantage of Docker Model Runner for engineers who already use Docker?
7. How do you download a model with Docker Model Runner? How do you verify it downloaded?
8. What file in the official example repository specifies which model the Python assistant uses?
9. On what port does the Python AI assistant from the official example run?
10. What future capability did the instructor mention for Docker Model Runner that was not demonstrated?

## Intermediate Interview Questions

1. Compare Docker Model Runner and Ollama across five dimensions. In what specific scenario would you choose Ollama over Docker Model Runner?
2. SmolLM2 has 135 million parameters while Llama 3 starts at ~4.7 billion. What concrete differences in response quality would you expect? Give an example question where SmolLM2 would fail but Llama 3 would succeed.
3. The official repository runs Python, Node.js, and Go containers from a single `run.sh`. What design pattern does this represent, and what production concern does it raise (hint: all three do the same thing — is that right for a real deployment)?
4. How does Docker Model Runner differ technically from Ollama in terms of how it exposes the model to applications? Does it use the same OpenAI-compatible API endpoint (`/v1/chat/completions`)?
5. The `.env` file approach for specifying the model has a drawback: if the model is not available locally, the application auto-pulls it. What is the production risk of this auto-pull behavior, and how would you prevent it?
6. The instructor mentions Docker Model Runner has "great integration with the MCP server." What is the MCP (Model Context Protocol) server, and why would its integration with Docker Model Runner be significant for AI agent development?
7. Docker Model Runner is only available in Docker Desktop (GUI version). It is NOT available in Docker Engine (server/headless version). What does this limitation mean for using Docker Model Runner in a CI/CD pipeline or a headless Linux server?
8. The Python assistant connects from a container to the Docker Model Runner service. How does a Docker container reach a service running on the host machine (hint: `host.docker.internal`)?

## Advanced Interview Questions

1. **Production AI Service with Docker Model Runner:** Design a production microservice architecture where multiple application services share a single local LLM via Docker Model Runner: (a) expose Docker Model Runner as a shared OpenAI-compatible HTTP endpoint on the host, (b) configure multiple Docker containers (Python API, Node.js API, Go worker) to all call the same model endpoint, (c) add an nginx reverse proxy container that load-balances across multiple model instances if Docker adds multi-instance support, (d) add authentication to the model endpoint so not all containers can access all models.
2. **Model Selection Framework:** Your team needs to choose a local model for an internal DevOps Q&A assistant. Design a structured model evaluation: (a) define a test set of 20 DevOps-specific questions ranging from simple (what is a pod) to complex (design a Kubernetes HA architecture), (b) run SmolLM2, Llama 3 (4.7B), and Phi against the test set and score each answer 0-3, (c) measure inference time per question for each model on the same hardware, (d) plot quality vs. latency — where is the Pareto frontier? (e) what model would you recommend for interactive Q&A (latency-sensitive) vs. background report generation (latency-insensitive)?
3. **Docker Compose + Model Runner Integration:** Design a docker-compose.yml that includes the LLM as a service alongside the application: (a) define a `model` service that starts Docker Model Runner with SmolLM2, (b) define the Python API service with a depends_on: model so the LLM is ready before the API starts, (c) add a health check for the model service that verifies the API endpoint is responsive before marking it healthy, (d) what challenges exist with this approach given that Docker Model Runner is currently a Desktop-only feature?

## Lab Exercises

### Lab 1 — Install and Use Docker Model Runner
**Objective:** Set up Docker Model Runner and run your first local LLM query.
**Steps:**
1. Open Docker Desktop → check the version (bottom right) — must be 4.40+; update if needed
2. Open a terminal: `docker model --help` — verify the subcommands appear
3. Go to `hub.docker.com/u/ai` — browse available models
4. Pull SmolLM2: `docker model pull ai/smollm2` (256 MB download)
5. Verify: `docker model list`
6. Single-prompt test: `docker model run ai/smollm2 "What is Kubernetes?"`
7. Interactive mode: `docker model run ai/smollm2` → ask 3 follow-up questions
8. Remove and verify: `docker model rm ai/smollm2` → `docker model list`
9. Re-pull: `docker model pull ai/smollm2` → note it is served from cache (fast)

### Lab 2 — Build the Python AI Assistant
**Objective:** Deploy the official Docker AI assistant example with a local model.
**Steps:**
1. Clone the official repository (link in episode description)
2. Edit the `.env` file — change the model to `ai/smollm2` (or whichever you downloaded)
3. Run `./run.sh` — observe which containers start successfully
4. Check running containers: `docker ps`
5. Open `localhost:8081` in a browser
6. Ask: "What is Kubernetes?"
7. Ask: "How does it differ from Docker Compose?"
8. Observe response speed — compare to your experience with ChatGPT
9. Check `docker logs <container>` for the Python assistant container
10. Reflection: Is SmolLM2's quality sufficient for technical DevOps questions? What would you swap it for?

### Lab 3 — Compare SmolLM2 vs. Llama 3
**Objective:** Empirically compare model quality at different parameter scales.
**Steps:**
1. Pull Llama 3: `docker model pull ai/llama3` (note the size vs. SmolLM2's 256 MB)
2. Run the same 5 questions to both models and record answers:
   - Q1: "What is Kubernetes?" (simple)
   - Q2: "What is the difference between a Deployment and a StatefulSet?" (intermediate)
   - Q3: "Design a Kubernetes HA architecture for a stateful database." (advanced)
   - Q4: "Write a bash script that checks pod health in all namespaces." (code generation)
   - Q5: "What is the CAP theorem?" (conceptual)
3. Score each answer 1-3 (1=wrong/incomplete, 2=partial, 3=correct and detailed)
4. Measure time per response for each model
5. Plot: SmolLM2 vs. Llama3 — quality vs. speed
6. Conclusion: For which question types is SmolLM2 adequate vs. where does Llama3 add value?

</details>



<details>
<summary><b>Bonus 5 — Run DeepSeek AI Locally in 2 Steps (CS46H)</b></summary>

## Beginner Interview Questions

1. What is DeepSeek R1, and which company released it?
2. What benchmark was used to compare DeepSeek R1 to OpenAI o3? What did the comparison show?
3. What is the reported training cost of DeepSeek R1, and why did this cause a reaction in the AI industry?
4. Why is DeepSeek R1 being "open source" significant for DevOps engineers?
5. What are the two steps to run DeepSeek locally?
6. Which DeepSeek R1 model size is recommended for local use on a standard laptop, and how large is the download?
7. What tool is used to run DeepSeek locally (same tool used in Day 7 and Day 8)?
8. What are two options for getting a ChatGPT-like UI over a locally running DeepSeek model?
9. How do you configure Chatbox AI to use a local Ollama model? What URL does Chatbox AI connect to?
10. What is the API cost comparison between OpenAI o3 and DeepSeek per 1 million tokens?

## Intermediate Interview Questions

1. DeepSeek R1 matches OpenAI o3 on SWE-bench at 98% lower API cost. Why would a startup still choose OpenAI API over DeepSeek API for a production chatbot?
2. Explain the data privacy difference between: (a) using the DeepSeek cloud API at api.deepseek.com, and (b) running DeepSeek R1 locally via Ollama. Which is appropriate for HIPAA-compliant healthcare applications?
3. The instructor demonstrates DeepSeek via Ollama, not via DeepSeek's own cloud API. What are the trade-offs of each approach for a DevOps team building an internal tool?
4. How does the Nvidia stock drop relate to DeepSeek's low training cost? Explain the market reasoning.
5. Compare Chatbox AI vs. Open WebUI as interfaces for local Ollama models. What would make you choose one over the other?
6. DeepSeek R1 is available in sizes from 1.5B to 671B parameters. A developer has a 16 GB RAM MacBook Pro (M2). Which size would you recommend, and why? What happens if they try to run the 671B model?
7. The SWE-bench benchmark measures software engineering task performance. What types of tasks does it include? What DevOps-specific tasks would it NOT cover?
8. "The higher the billion parameters, the model is trained on more data." Is this statement accurate? Explain the relationship between parameter count and training data size.

## Advanced Interview Questions

1. **Production Migration from OpenAI to DeepSeek:** Your startup spends $3,000/month on OpenAI API for a customer-facing chatbot. Design a migration plan to DeepSeek: (a) how do you test DeepSeek quality against your specific use case before migrating?, (b) what is the risk of changing models mid-production, and how do you mitigate it with A/B testing?, (c) should you use DeepSeek's cloud API or self-host via Ollama? Calculate the break-even point where self-hosting becomes cheaper, (d) what specific OpenAI API parameters (temperature, max_tokens, system prompt) need re-tuning for DeepSeek?
2. **DeepSeek in an Enterprise Air-Gapped Environment:** Your organization's security policy prohibits all outbound API calls. Design the full architecture to run DeepSeek R1 for an internal documentation Q&A system: (a) which model size would serve 500 concurrent engineers?, (b) what GPU server hardware is needed? (c) how do you expose the model as a shared OpenAI-compatible API endpoint that all engineers can call?, (d) how do you version control and deploy model updates without disrupting users?
3. **SWE-bench Evaluation:** The transcript claims DeepSeek R1 matches OpenAI o3 on SWE-bench. Design your own benchmark for DevOps-specific AI tasks: (a) define 20 DevOps-specific test cases (Terraform writing, Kubernetes debugging, CI/CD pipeline generation, log analysis), (b) score rubric for each test case (0-3), (c) run both models against your benchmark, (d) what would a 10% quality gap at 98% cost reduction mean for your organization's specific use case?

## Lab Exercises

### Lab 1 — Run DeepSeek R1 Locally
**Objective:** Run DeepSeek R1 in 2 steps and test it.
**Steps:**
1. If you don't have Ollama: download from ollama.ai, install, verify with `ollama --help`
2. Run DeepSeek 1.5B: `ollama run deepseek-r1:1.5b` (first run downloads ~1.1 GB)
3. Test with simple prompt: "Write a Python function to calculate factorial"
4. Test with DevOps prompt: "Write a Kubernetes deployment manifest for an nginx pod with resource limits"
5. Test with reasoning prompt: "Design a CI/CD pipeline for a microservices application"
6. Verify model is cached: exit and re-run `ollama run deepseek-r1:1.5b` — should start instantly
7. Check `ollama list` — note the model size and when it was last used
8. Reflection: How does the code quality compare to your experience with ChatGPT?

### Lab 2 — Set Up Chatbox AI
**Objective:** Get a ChatGPT-like interface over DeepSeek via Chatbox AI.
**Steps:**
1. Download Chatbox AI for your OS (Windows/macOS/Linux — find the official site)
2. Install and launch
3. Go to Settings → AI Model → choose Ollama as provider
4. Set API URL: `http://localhost:11434` (default)
5. In the model dropdown: select `deepseek-r1:1.5b`
6. Save settings and start a new conversation
7. Ask: "Why is Pluto a dwarf planet?" (from the demo)
8. Ask: "Compare Prometheus and Grafana" (DevOps-relevant)
9. Compare the experience: CLI (`ollama run`) vs. Chatbox UI
10. Optional: change the model to Llama 3 (if you have it) and compare response quality

### Lab 3 — Cost Calculation Exercise
**Objective:** Calculate real API cost savings from switching to DeepSeek.
**Steps:**
1. Use the token counter at platform.openai.com/tokenizer
2. Paste a typical prompt you send to ChatGPT (e.g., a Kubernetes manifest generation request)
3. Note the input token count
4. Estimate the response token count (add ~50-200 tokens for a typical manifest response)
5. Calculate: total tokens / 1,000,000 × $7.50 = OpenAI o3 cost for that prompt
6. Calculate: total tokens / 1,000,000 × $0.15 = DeepSeek API cost for that prompt
7. If your team sends 100 such prompts per day: calculate monthly cost for each
8. Identify the break-even for self-hosting DeepSeek 7B on a cloud GPU server (assume ~$200/month for a small GPU instance)

</details>


