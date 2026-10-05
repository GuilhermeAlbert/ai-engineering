# Module 2: How Generative AI Works


The goal here is technical *literacy*, not engineering depth: enough understanding of large language models (LLMs) to make good decisions about tools, budgets, and vendor claims: without needing to write code.

## What large language models are, explained without technical jargon

An LLM is a system trained on enormous amounts of text to predict "what word (technically, token) is most likely to come next," given everything written so far. Trained at large enough scale, this simple prediction task produces models that can hold conversations, summarize documents, write code, and reason through multi-step problems: not because they "understand" in a human sense, but because predicting plausible next text well requires capturing a huge amount of structure about language, facts, and reasoning patterns.

**Practical example:** When you type "The capital of France is," the model predicts "Paris" as the most probable continuation because that pattern appeared constantly in its training data: not because it looked up a fact in a database the way a search engine would.

## How inputs, outputs, and context windows shape model behavior

The **input** (your prompt, plus any documents you attach) and the **output** (the generated response) together must fit inside the model's **context window**: the maximum amount of text it can "see" at once, measured in tokens. Everything outside that window is invisible to the model for that request.

**Practical example:** A model with a 32,000-token context window (~24,000 words) can read an entire quarterly report and answer questions about it in one go. Feed it a 100,000-word annual report and it will either truncate the document, refuse, or need the document split into chunks: this is a real budgeting/tooling constraint, not a hypothetical.

## Why AI hallucinations occur and their impact on organizational use

A **hallucination** is when a model generates a confident, fluent, but factually wrong or fabricated answer: a citation that doesn't exist, a statistic invented, a policy detail misremembered. It happens because the model is optimizing for plausible-sounding text, not for verified truth; it has no built-in mechanism to say "I don't actually know this."

**Practical example:** A lawyer asks an LLM to find supporting case law and receives citations to real-sounding but nonexistent court cases, because the model generated text in the *style* of a citation without retrieving an actual verified source. This is precisely why organizations require human review of AI output in high-stakes contexts, and why techniques like RAG (see below) exist.

## How tokens, cost, and model size affect budget and deployment decisions

A **token** is roughly ¾ of a word (in English). Commercial LLM APIs charge per token, for both input and output. **Model size** (parameter count) roughly correlates with capability and cost: bigger models are usually smarter but slower and more expensive to run. This is why "just use the biggest model" is not automatically the right cost strategy.

**Practical example:** A company building an internal FAQ chatbot that answers simple, repetitive questions might deploy a small, cheap model for 90% of queries and route only complex escalations to a larger, pricier model: cutting API costs substantially without hurting the experience that matters.

## What multimodal AI enables in text, images, audio, and code

**Multimodal** models accept and/or generate more than one type of content: e.g., you can show a model a photo of a whiteboard and ask it to transcribe the diagram into text, or ask it to generate an image from a text description, or have it write and explain code.

**Practical example:** An insurance company uses a multimodal model to review photos submitted with car-damage claims alongside the claimant's written description, cross-checking whether the described damage is visually consistent: something a text-only model could never do.

## How leading models differ at a high level and what matters for leadership decisions

Models differ on: **capability** (reasoning quality, coding ability), **cost per token**, **context window size**, **latency**, **data/privacy terms** (does the vendor train on your inputs?), and **deployment options** (cloud API only, vs. options to run smaller "open-weight" versions locally). For a leader, the decision criteria are business-shaped, not benchmark-shaped: what does this cost at our volume, what are the data-handling terms, and can it integrate with our existing systems?

**Practical example:** A healthcare company might choose a vendor with a smaller context window but a contractual guarantee that patient data is never used for further model training: trading a technical capability for a compliance requirement.

## Key red flags to watch for when evaluating AI vendor claims

Watch for: benchmark numbers with no disclosed methodology; claims of "zero hallucinations" (technically not achievable with current LLM architectures); vague answers about where your data goes; demos on cherry-picked examples rather than your own data; and pricing that doesn't account for token costs at your actual usage volume.

**Practical example:** A vendor demo flawlessly answers three prepared questions about "your industry." Before signing, a smart buyer insists on testing the tool against five of *their own* messiest real documents: which is where hallucination rates and integration gaps actually show up.

## Extra terms from the course objectives: RAG and AI agents

The course objectives call out **LLMs, RAG, agents, and multimodal models** as the four capabilities leaders must be able to tell apart. LLMs and multimodal models are covered above; here are the other two.

**RAG (Retrieval-Augmented Generation)** connects an LLM to an external, up-to-date knowledge source (a document database, an internal wiki, a search index). Instead of relying only on what the model memorized during training, the system first *retrieves* relevant passages and feeds them into the prompt, so the model answers grounded in real, citable source material. This is the standard mitigation for hallucinations in enterprise settings.

**Practical example:** An HR chatbot built on a raw LLM might confidently invent a vacation-policy detail. An HR chatbot built with RAG first searches the company's actual HR handbook, retrieves the relevant paragraph, and answers based on that text: and can cite the exact policy section.

An **AI agent** is a system that uses an LLM not just to generate text, but to take multi-step actions toward a goal: deciding which tool to call, executing it, observing the result, and deciding the next step, often in a loop, with limited human intervention.

**Practical example:** A single-shot LLM prompt can *draft* a customer refund email. An agent can *handle the whole refund*: look up the order in the system, check the return policy, issue the refund via an API call, and then draft the confirmation email: chaining several tool calls autonomously instead of producing one static output.

---

[← Previous: Models and System Behavior](./README.md) · [Back to Models and System Behavior](./README.md) · [Next: Prompt Engineering →](../prompt-engineering/README.md)
