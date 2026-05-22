# TracePilot AI SDK 🚀
## AI Agent Observability, Debugging, Tracing & Time-Travel Replay for OpenAI Agents

The official Node.js and TypeScript SDK for TracePilot AI.

TracePilot helps developers debug autonomous AI agents like software engineers debug production systems.

Monitor, trace, replay, inspect, and fix AI workflows in real time with advanced observability tools for:
- OpenAI agents
- AI copilots
- Autonomous workflows
- LangChain apps
- CrewAI systems
- Multi-agent architectures
- LLM applications
- AI orchestration pipelines

Perfect for developers searching for:
- How to debug AI agents
- AI agent observability
- OpenAI debugging tools
- LLM tracing platforms
- AI workflow monitoring
- AI execution replay
- Prompt debugging
- AI runtime inspection
- AI stack traces
- AI error tracing
- AI debugging SDK
- Autonomous agent debugging
- Time-travel debugging for AI
- AI infrastructure tools

---

# 🔥 Why TracePilot?

Modern AI agents fail silently.

Traditional logs are not enough for autonomous AI systems, multi-step reasoning pipelines, or tool-calling workflows.

TracePilot gives you:
- Full execution tracing
- Runtime observability
- Prompt inspection
- Execution tree visualization
- AI replay debugging
- Span-based tracing
- OpenAI call instrumentation
- Agent execution history
- Time-travel debugging
- Real-time monitoring

Debug AI agents the same way developers debug backend systems.

---

# 📦 Installation

```bash
npm install tracepilot-sdk
```

---

# ⚡ Quick Start

```ts
import { TracePilot } from 'tracepilot-sdk';
import OpenAI from 'openai';

const tp = new TracePilot('YOUR_API_KEY');

const openai = new OpenAI({
  apiKey: 'YOUR_OPENAI_KEY',
});

async function runAgent() {
  await tp.startTrace('Customer Support AI Agent');

  const prompt = [
    {
      role: 'user',
      content: 'How do I reset my password?',
    },
  ];

  const { result } = await tp.wrapOpenAI(
    async () => {
      return await openai.chat.completions.create({
        model: 'gpt-4o-mini',
        messages: prompt,
      });
    },
    prompt,
    undefined,
    1
  );

  console.log(result.choices[0]?.message?.content);
}

runAgent();
```

---

# 🧠 What Can You Debug With TracePilot?

TracePilot is designed for:
- AI SaaS applications
- AI startups
- Autonomous AI agents
- Multi-agent systems
- LLM infrastructure
- AI copilots
- AI automation tools
- AI customer support systems
- AI coding assistants
- Retrieval-Augmented Generation (RAG) systems
- LangChain workflows
- CrewAI agents
- OpenAI SDK integrations

Use TracePilot to:
- Detect hallucinations
- Debug failed prompts
- Analyze token flows
- Trace agent decisions
- Monitor OpenAI API calls
- Replay execution paths
- Inspect AI reasoning chains
- Understand tool-calling failures
- Visualize agent execution trees

---

# 💡 Get Your API Key

Visit https://tracepilotai.com to get your API Key and visualize your AI agent executions in real time.

---

# 🚀 Features

## ✅ AI Agent Tracing
Track every AI execution step across your workflow.

## ✅ OpenAI Instrumentation
Wrap OpenAI calls automatically and capture execution data.

## ✅ Time-Travel Debugging
Replay autonomous AI workflows frame by frame.

## ✅ AI Observability Dashboard
Visualize prompts, responses, spans, errors, and execution trees.

## ✅ Production Monitoring
Monitor live AI systems in production environments.

## ✅ Developer-Friendly SDK
Simple TypeScript and Node.js integration.

---

# 🧪 End-to-End Testing (Clean Room Test)

Simulate exactly what a real developer would do when discovering your SDK from scratch.

## Step 1 — Get Your Real API Key

Go to https://tracepilotai.com, authenticate with GitHub or Google, and copy your real API Key from the dashboard.

Example:

```txt
tp_live_xxxxxxxxxxxxxxxxx
```

## Step 2 — Create a New Project

```bash
mkdir test-agent-user
```

## Step 3 — Initialize the Project

```bash
cd test-agent-user
npm init -y
npm install tracepilot-sdk openai
```

## Step 4 — Create index.ts

```ts
import { TracePilot } from 'tracepilot-sdk';
import OpenAI from 'openai';

const tp = new TracePilot('YOUR_API_KEY');

const openai = new OpenAI({
  apiKey: 'YOUR_OPENAI_KEY',
});

async function main() {
  await tp.startTrace('AI Debug Test');

  const messages = [
    {
      role: 'user',
      content: 'Explain recursion simply.',
    },
  ];

  const { result } = await tp.wrapOpenAI(
    async () => {
      return await openai.chat.completions.create({
        model: 'gpt-4o-mini',
        messages,
      });
    },
    messages
  );

  console.log(result.choices[0]?.message?.content);
}

main();
```

---

# 📚 API Reference

| Method | Description |
|---|---|
| `new TracePilot(apiKey)` | Initializes the SDK with your API Key |
| `tp.startTrace(name)` | Starts a new trace for your AI agent |
| `tp.wrapOpenAI(fn, prompt, parentSpanId?, depth?)` | Wraps an OpenAI call and captures the execution tree |

---

# 🌍 SEO Keywords

AI debugging tool, AI observability platform, OpenAI debugging SDK, AI tracing software, LLM observability, AI execution replay, autonomous agent monitoring, prompt debugging tool, AI infrastructure platform, AI developer tools, AI tracing SDK, AI runtime debugging, LangChain observability, CrewAI debugging, AI execution tracing, AI monitoring SaaS.

---

# 🔗 Links

- 🌐 Website: https://tracepilotai.com
- 📦 npm: https://www.npmjs.com/package/tracepilot-sdk
- 🐙 GitHub: https://github.com/TracePilotAI

---

# 📄 License

MIT © TracePilot AI

