---
type: permanent
stage: permanent
created: 2026-02-10
updated: 2026-08-19
context: [career]
tags: [ai, agents, mcp, tool-use]
distilled: false
publish: true
---

## Introduction

You've raised a very insightful question about the future of AI development, particularly regarding the roles of MCP servers, tools, and agent creation methodologies. Your intuition that the focus is shifting towards more structured and tool-centric approaches is indeed aligned with the current trends in the AI industry. This document aims to provide a comprehensive overview of the modern AI infrastructure, clarify how its various components interact, and offer a nuanced perspective on your theory.

## The Core Components of Modern AI Infrastructure

To understand the bigger picture, it's helpful to break down the AI infrastructure into its core components. Think of it as a layered system where each component builds upon the others to create increasingly capable AI systems.

| Component                        | Analogy            | Function                                                                             | Key Characteristics                                                                                                                           |
| :------------------------------- | :----------------- | :----------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------- |
| **AI Models (LLMs)**             | The Brain          | Provides reasoning, language understanding, and knowledge.                           | Based on architectures like Transformers; trained on vast datasets; examples include GPT-4, Claude 3, and Llama 3.                            |
| **AI Agents**                    | The Actor          | Autonomous systems that use the "brain" to perform tasks.                            | Can plan, reason, and execute multi-step workflows; they are goal-oriented and can operate independently.                                     |
| **Tools & Function Calling**     | The Hands          | Enables agents to interact with the external world.                                  | Allows access to APIs, databases, web search, and other external functionalities; function calling is the mechanism for invoking these tools. |
| **MCP (Model Context Protocol)** | The Nervous System | A universal standard for communication between AI applications and external systems. | Acts as a universal connector, standardizing how AI agents access tools and data, making the ecosystem more modular and scalable.             |

### AI Models: The Foundation

At the heart of modern AI are the foundational models, particularly Large Language Models (LLMs). These models are trained on massive amounts of text and data, enabling them to understand and generate human-like language, reason about complex problems, and serve as the cognitive engine for more advanced AI systems [4].

### AI Agents: The Autonomous Actors

AI agents are a step beyond simple models. They are autonomous systems that can perceive their environment, make decisions, and take actions to achieve specific goals [2]. An agent uses an LLM as its core reasoning engine but extends its capabilities by being able to plan, decompose complex tasks, and utilize external tools [2].

### Tools and Function Calling: Interacting with the World

This is where the AI system gains the ability to affect the real world. Function calling (or tool use) is the mechanism that allows an LLM to invoke external functions or APIs [6]. For example, an agent can use a tool to search the web, access a database, send an email, or even execute code. This ability is what transforms a passive language model into an active participant in a workflow [6].

### MCP: The Universal Connector

The Model Context Protocol (MCP) is an open-source standard designed to solve a critical problem: how to seamlessly and securely connect AI applications with a diverse and ever-growing set of external tools and data sources [1]. Instead of building custom integrations for every new tool, developers can create MCP-compliant servers that expose tools and resources in a standardized way. This is analogous to how USB-C provides a universal standard for connecting peripherals to a computer [1]. MCP is designed to be the foundational communication layer for an “AI-native web,” where agents can act on behalf of users in complex scenarios [1].

## How the Components Feed into Each Other: An End-to-End Workflow

Let's walk through a simplified example to see how these components work together:

1.  **User Prompt:** You ask an AI assistant, "What was the closing price of GOOG yesterday, and can you email it to me?"
2.  **Agent & LLM Reasoning:** The AI agent, powered by an LLM, receives your request. The LLM understands that it needs two pieces of information it doesn't have internally (the stock price) and needs to perform an action (send an email).
3.  **Tool Selection (via MCP):** The agent, through its MCP client, discovers the available tools. It identifies a `stock_price_tool` and an `email_tool` exposed by one or more MCP servers.
4.  **Function Calling:** The LLM generates a "tool call" to the `stock_price_tool` with the argument "GOOG".
5.  **Execution:** The application executes this function, which calls a financial data API and gets the closing price.
6.  **Response to LLM:** The stock price is sent back to the LLM.
7.  **Second Tool Call:** The LLM now generates another tool call, this time to the `email_tool`, with the recipient's address and the body of the email containing the stock price.
8.  **Final Response:** The email is sent, and the agent informs you that the task is complete.

## Tool-Based vs. Document-Based AI Development

This brings us to your core question. You are right to distinguish between these two approaches:

*   **Document-Based Approach:** This often refers to prompt engineering, where developers write detailed natural language instructions (often in Markdown files) to guide an agent's behavior. These documents can define the agent's persona, goals, constraints, and even the steps to take for certain tasks.
*   **Tool-Based Approach:** This focuses on creating a rich ecosystem of tools that an agent can use. The development effort is concentrated on building robust, well-documented functions and exposing them through a standardized interface like MCP.

You are correct that the industry is moving more towards a **tool-based approach**, but it's not a replacement for the document-based approach. Rather, they are complementary. The markdown documents are evolving from simple prompts to more structured definitions of an agent's capabilities, including which tools it has access to and how it should use them. The future is not about choosing one over the other, but about the synergy between them.

## Evaluating Your Theory: The Future of AI Development

Your theory is largely correct. The future of AI development will be less about writing lengthy, unstructured prose to coax a model into performing a task, and more about building a robust and standardized ecosystem of tools. The focus will be on:

*   **Creating Tools:** As you predicted, a significant part of AI development will involve creating specialized tools that can be used by AI agents. These tools will be the building blocks of complex AI applications.
*   **Standardization with MCP:** MCP is poised to become a critical standard for how these tools are exposed and consumed [7]. This will lead to a more modular and interoperable AI ecosystem, where developers can easily mix and match tools from different providers.
*   **Agentic Workflows:** The emphasis will be on designing and orchestrating agentic workflows, where autonomous agents use these tools to achieve complex goals [7].

However, the role of descriptive documents will not disappear. Instead, it will evolve. These documents will become more like configuration files or blueprints for agents, defining their core logic, the tools they can use, and the rules of engagement. So, while the focus is shifting to tools, the need to describe and orchestrate how those tools are used remains crucial.

## Conclusion

Your intuition is sharp. The future of AI development is indeed moving towards a more structured, tool-centric paradigm, with MCP playing a pivotal role in standardizing the communication layer. This shift will enable the creation of more powerful, reliable, and interoperable AI systems. However, this doesn't mean that descriptive documents will become obsolete. Instead, they will evolve to work in concert with this new tool-based ecosystem, providing the high-level guidance and orchestration that agents need to perform complex tasks. The synergy between well-defined tools and well-crafted agentic instructions will be the engine of the next generation of AI applications.

## References

[1] Model Context Protocol. (n.d.). *Model Context Protocol*. Retrieved from https://modelcontextprotocol.io/

[2] IBM. (n.d.). *What are AI Agents?*. IBM. Retrieved from https://www.ibm.com/think/topics/ai-agents

[3] IBM. (n.d.). *What is Tool-based AI Development?*. IBM. Retrieved from https://www.ibm.com/think/topics/ai-in-software-development

[4] Epical Group. (n.d.). *Generative AI Fundamentals: Exploring the 6-Layer Architecture*. Retrieved from https://www.epicalgroup.com/blogs/generative-ai-fundamentals-exploring-6-layer-architecture

[5] IBM. (n.d.). *What is LLM Orchestration?*. IBM. Retrieved from https://www.ibm.com/think/topics/llm-orchestration

[6] OpenAI. (n.d.). *Function Calling*. OpenAI. Retrieved from https://platform.openai.com/docs/guides/function-calling

[7] Splunk. (2024). *Top 10 AI Trends for 2025: How Agentic AI and MCP Changed IT*. Retrieved from 
```