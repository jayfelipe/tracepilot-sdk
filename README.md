# TracePilot AI SDK 🚀

The official Node.js/TypeScript SDK for TracePilot AI.

Time-travel debugging, observability, and tracing for autonomous AI agents.

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
  await tp.startTrace('My Agent');

  const prompt = [
    {
      role: 'user',
      content: 'Hello!',
    },
  ];

  // Wrap your OpenAI calls to capture execution trees
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

# 💡 Get Your API Key

Visit https://tracepilotai.com to get your API Key and visualize your agent executions.

---

# 🚀 Publishing Your Package

1. Upload the code to your repository.
2. Publish it to npm.
3. Done — now your package has a public home.

---

# 🧪 End-to-End Testing (Clean Room Test)

Simulate exactly what a real developer would do when discovering your SDK from scratch.

## Step 1 — Get Your Real API Key

Go to https://tracepilotai.com, authenticate with GitHub or Google, and copy your real API Key from the dashboard.

Example:

```txt
tp_live_xxxxxxxxxxxxxxxxx
```

---

## Step 2 — Create a New Project

Navigate outside your existing project folders and create a fresh directory.

```bash
mkdir test-agent-user
```

---

## Step 3 — Initialize the Project

```bash
cd test-agent-user
npm init -y
npm install tracepilot-sdk openai
```

---

# 📚 API Reference

| Method | Description |
|---|---|
| `new TracePilot(apiKey)` | Initializes the SDK with your API Key |
| `tp.startTrace(name)` | Starts a new trace for your agent |
| `tp.wrapOpenAI(fn, prompt, parentSpanId?, depth?)` | Wraps an OpenAI call to capture the execution tree |

---

# 🔗 Links

- 🌐 Website: https://tracepilotai.com
- 📦 npm: https://www.npmjs.com/package/tracepilot-sdk
- 🐙 GitHub: https://github.com/TracePilotAI

---

# 📄 License

MIT © TracePilot AI
