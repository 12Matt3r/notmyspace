# Deep Dive: Supervisorai

## README Summary
# AI Supervisor & Orchestrator
### *A Submission for the Minimax Agent Hackathon*

---

## 1. Project Overview

This project is a sophisticated, AI-powered system designed to supervise, manage, and assist other AI agents. It has evolved from a simple monitoring script into a multi-layered platform with advanced capabilities for intelligent oversight and autonomous operation.

The system is built around three core concepts:
*   **Supervision:** A supervisor agent that uses a probabilistic model (Expectimax) to watch over a working agent, predict potential issues, and intervene when necessary.
*   **Orchestration:** An autonomous orchestrator that can manage a pool of specialized agents, decompose high-level goals into a dependency graph of tasks, and manage the entire execution workflow, including delegating complex tasks to sub-orchestrators.
*   **Assistance:** A proactive research assistant that can detect when an agent is stuck, perform web searches to find solutions for its errors, and provide intelligent suggestions to help it recover.

## 2. Core Features

This project includes a rich set of features, demonstrating a robust and intelligent architecture.

### **Supervision Engine**

*   **Intelligent Supervisor Agent:**
    *   Uses an **Expectimax algorithm** (`supervisor_agent/expectimax_agent.py`) to make nuanced decisions about whether to `ALLOW`, `WARN`, `CORRECT`, or `ESCALATE` an agent's output. This is not based on simple rules, but on a probabilistic model of future outcomes.
    *   The decision-making is based on a weighted evaluation of the agent's state, including output quality, task drift, error count, and resource usage.
    *   **Technical Deep Dive**: The utility function $U(s, a)$ calculates the expected value of a supervisor action $a$ in state $s$ by summing the probabilities of transition to future states $s'$ multiplied by their intrinsic reward. This allows the supervisor to allow minor errors if the probability of self-correction is high, optimizing for autonomy.

*   **Code-Aware Supervision:**
    *   The supervisor can now understand code quality. When an agent produces Python code, the system uses the **`pylint` static analysis tool** (`analysis/code_analyzer.py`) to check for errors, code smells, and style issues.
    *   The number of errors found is factored directly into the `AgentState` passed to the Expectimax agent, making its decisions about code much more intelligent.

*   **Multi-modal Supervision:**
    *   The supervisor now has a new sense: vision. It can evaluate image-based outputs from agents.
    *   When an agent's output is an image URL, the `LLMJudge` uses a vision-capable model (e.g., Claude 3 Opus) to evaluate the image against the task goals.

*   **Feedback-Driven Learning:**
    *   The supervisor can **learn from user feedback**. The dashboard allows a human to correct a bad decision, and this feedback is used to retrain the weights of the Expectimax agent's evaluation function via `supervisor_agent/feedback_trainer.py`.
    *   This creates a powerful self-improvement loop, allowing the supervisor's judgment to get better over time.

### **Orchestration Engine**

*   **Autonomous Orchestrator with Multi-LLM Support:**
    *   Manages a pool of specialized agents with different capabilities.
    *   Features an **LLM-powered task planner**. The system is architected to use multiple LLM providers concurrently (e.g., Anthropic, OpenAI), loading its configuration from `config/llm_config.json`.
    *   **Multi-LLM Management**: Seamlessly switches between providers (Anthropic, OpenAI, Groq) based on cost, latency, and context-window requirements. Fast models (e.g., GPT-4o-mini) are used for routine planning, while high-reasoning models (e.g., Claude 3.5 Sonnet) are reserved for auditing and complex task decomposition.

*   **Sub-Orchestration:**
    *   For extremely complex goals, the main orchestrator can now delegate tasks to **sub-projects**. The LLM planner is instructed to identify tasks that are themselves large projects and assign them a `sub_orchestration` capability.
    *   The orchestrator then creates a new, nested `ProjectGoal` and monitors it, allowing for hierarchical, recursive problem-solving.

*   **Resource-Aware Task Assignment:**
    *   The orchestrator is now aware of agent system resources. Agents can report their CPU and memory load via a new API endpoint.
    *   The `find_available_agent` logic has been enhanced to filter out agents with high resource usage (e.g., >90%) and to prioritize assigning tasks to the least-loaded agent available.

## Project Structure
```
temp_repos/Supervisorai
temp_repos/Supervisorai/requirements.txt
temp_repos/Supervisorai/config
temp_repos/Supervisorai/config/weights.json
temp_repos/Supervisorai/config.json
temp_repos/Supervisorai/docs
temp_repos/Supervisorai/docs/README_INTEGRATED.md
temp_repos/Supervisorai/docs/README.md
temp_repos/Supervisorai/docs/README_HYBRID_INTEGRATION.md
temp_repos/Supervisorai/docs/PROJECT_COMPLETE.pdf
temp_repos/Supervisorai/docs/README.pdf
temp_repos/Supervisorai/docs/README.docx
temp_repos/Supervisorai/docs/DEPLOYMENT.md
temp_repos/Supervisorai/docs/LICENSE
temp_repos/Supervisorai/docs/INTEGRATION_COMPLETE.md
temp_repos/Supervisorai/docs/comprehensive_README.md
temp_repos/Supervisorai/knowledge_base.json
temp_repos/Supervisorai/frontend
temp_repos/Supervisorai/frontend/interactive-dashboard
temp_repos/Supervisorai/README.md
temp_repos/Supervisorai/pyproject.toml
temp_repos/Supervisorai/AGENTS.md
temp_repos/Supervisorai/supervisor_data
temp_repos/Supervisorai/supervisor_data/supervisor.log
temp_repos/Supervisorai/examples
temp_repos/Supervisorai/examples/dashboard.html
temp_repos/Supervisorai/supervisor.log
temp_repos/Supervisorai/scripts
temp_repos/Supervisorai/scripts/generate_icons.py
temp_repos/Supervisorai/scripts/run.sh
temp_repos/Supervisorai/hybrid_config.json
temp_repos/Supervisorai/audit.jsonl
temp_repos/Supervisorai/tests
temp_repos/Supervisorai/tests/test_feedback_trainer.py
temp_repos/Supervisorai/tests/test_assistance_integration.py
temp_repos/Supervisorai/tests/test_hybrid_integration.js
temp_repos/Supervisorai/tests/test_llm_judge.py
temp_repos/Supervisorai/tests/test_orchestrator.py
temp_repos/Supervisorai/tests/test_task_coherence.py
temp_repos/Supervisorai/tests/test_idea_validation.py
temp_repos/Supervisorai/tests/test_researcher.py
temp_repos/Supervisorai/tests/test_interactive_editing.py
temp_repos/Supervisorai/tests/test_expectimax_agent.py
temp_repos/Supervisorai/uv.lock
temp_repos/Supervisorai/browser_extension
temp_repos/Supervisorai/browser_extension/icon-48.png
temp_repos/Supervisorai/browser_extension/injector.js
temp_repos/Supervisorai/browser_extension/icon-16.png
temp_repos/Supervisorai/browser_extension/content.js
temp_repos/Supervisorai/browser_extension/icon-128.svg
temp_repos/Supervisorai/browser_extension/manifest.json
temp_repos/Supervisorai/browser_extension/popup.html
temp_repos/Supervisorai/browser_extension/activity-log.html
temp_repos/Supervisorai/browser_extension/popup.js
temp_repos/Supervisorai/browser_extension/icon-128.png
temp_repos/Supervisorai/browser_extension/background.js
temp_repos/Supervisorai/mcp-server.json
temp_repos/Supervisorai/src
temp_repos/Supervisorai/src/llm
temp_repos/Supervisorai/src/idea_validation
temp_repos/Supervisorai/src/reporting
temp_repos/Supervisorai/src/monitoring
temp_repos/Supervisorai/src/supervisor_agent
temp_repos/Supervisorai/src/researcher
temp_repos/Supervisorai/src/server
temp_repos/Supervisorai/src/task_coherence
temp_repos/Supervisorai/src/error_handling
temp_repos/Supervisorai/src/orchestrator
temp_repos/Supervisorai/src/main_reporting_system.py
```

## Python Dependencies
```
aiofiles==24.1.0
fastmcp==2.11.3
Flask==3.1.2
flask_socketio==5.5.1
httpx==0.28.1
Jinja2==3.1.6
matplotlib==3.10.5
numpy==2.3.2
pandas==2.3.1
plotly==6.3.0
psutil==7.0.0
Requests==2.32.5
scikit_learn==1.7.1
seaborn==0.13.2
aiohttp==3.9.5
```


## Unique Code Findings

### 🛡️ Expectimax Supervision (src/supervisor_agent/expectimax_agent.py)
- **Probabilistic Oversight**: Instead of simple IF/THEN rules, it uses a game-theory approach (Expectimax) to evaluate the best action for a supervisor based on the predicted future state of a working agent.
- **State Evaluation**: Factors in `quality_score`, `task_drift`, `error_rate`, and `resource_usage` to calculate utility values for different intervention levels.

### 🕸️ Dependency-Graph Orchestration (src/orchestrator/planner.py)
- **Autonomous Planning**: Takes a complex goal and uses an LLM to decompose it into a JSON-based dependency graph.
- **Dynamic Task Assignment**: Assigns tasks to the best-suited agent based on capabilities and current system load.

### 🔍 Proactive Researcher (src/researcher/search_tool.py)
- **Error Recovery**: Automatically triggers Google searches when an agent encounters a persistent error, synthesizing the results into a helpful suggestion for the agent to try.

### 🔌 Multi-LLM Management (src/llm/manager.py)
- **Provider Agnostic**: Seamlessly switches between Anthropic, OpenAI, and Groq based on configuration and cost-efficiency.
