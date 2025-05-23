# AI Interaction Strategy Framework

This document outlines a structured approach to designing effective AI prompts. It distinguishes between system-level prompts, user-level prompts, shared techniques, meta-techniques for self-improvement, and engineering considerations to ensure clarity, consistency, and high-quality outputs.

---

## System Prompt Layer

The system prompt sets the foundation for the AI's behavior. It defines how the AI should think, respond, and maintain context across interactions. Treat this like the model's "job description." You are able to adjust the system prompt when building your own AI applications, by using Projects for Claause, and by building custom GPTs on ChatGPT.

- **Define Persona**  
  Assign the AI a specific role or character to adopt. This shapes tone, perspective, and domain expertise.

- **Set Tone and Style**  
  Specify how responses should sound — formal, conversational, bullet-pointed, etc. 

- **Set Constraints and Limits**  
  Control response length, creativity level, and depth of explanation. Helps manage verbosity or conciseness. You can also address creativity via parameters.

- **Memory Management**  
  Define what context the model should remember within the session. Helps with continuity in longer workflows.

- **Handle Ambiguity**  
  Instruct the model to proactively ask clarifying questions if the prompt is unclear.

- **Fallback Behavior**  
  Provide guidance for uncertain situations. Encourage honesty like: "If unsure, say so."

- **Role Assignments**  
  Assign multiple roles for complex tasks, like combining technical and legal perspectives.

- **Audience Awareness**  
  Specify the target audience to adjust complexity, terminology, and tone accordingly.

### System Prompt Details

| Element | Description |
|---------|-------------|
| Persona | Defines the role the model should assume. |
| Tone and Style | Sets desired tone: formal, casual, etc. |
| Constraints and Limits | Sets boundaries on response length, creativity, and depth. |
| Memory Management | Determines what context persists across exchanges. |
| Handle Ambiguity | Directs the AI to seek clarification when needed. |
| Fallback Behavior | Provides instructions for uncertain or ambiguous scenarios. |
| Role Assignments | Assigns one or multiple roles to the AI. |
| Audience Awareness | Tailors responses to a specific audience. |

---

## User Prompt Layer

The user prompt defines the specific task or question at hand. It focuses the AI's attention and ensures alignment with the user's immediate goal.

- **Clear Task or Question**  
  Be explicit about what you want the AI to do. Avoid vague prompts.

- **Output Format**  
  Define the desired format: narrative, list, table, JSON, Markdown, etc.

- **Background and Context**  
  Provide enough information for the AI to understand your goals, even if it has no prior knowledge.

- **Clarify Questions**  
  Invite the AI to ask what it still needs to know to complete the task properly.

- **Iteration and Refinement**  
  Request drafts or revisions to progressively improve the output.

- **Parallel Alternatives**  
  Ask for multiple approaches to compare strategies or outputs.

- **Response Validation**  
  Direct the AI to check its response for accuracy and relevance before submitting.

- **Post-Processing Suggestions**  
  Ask the AI to recommend next steps after completing the response.

### User Prompt Details

| Element | Description |
|---------|-------------|
| Clear Task or Question | Defines exactly what you're asking the AI to do. |
| Output Format | Specifies output style or structure. |
| Background and Context | Provides essential context for the task. |
| Clarify Questions | Prompts AI to inquire about missing details. |
| Iteration and Refinement | Requests iterative drafts or improvements. |
| Parallel Alternatives | Asks for multiple solutions or viewpoints. |
| Response Validation | Instructs AI to double-check its answer. |
| Post-Processing Suggestions | Encourages next-step recommendations. |

---

## Shared Techniques

Shared techniques are reusable prompt enhancements that apply across both system and user prompts. They strengthen reasoning, improve accuracy, and introduce best practices.

- **Chain of Thought**  
  Request step-by-step reasoning to improve transparency and accuracy. This is less important when using reasoning models, such as Claude Sonnet 3.7 or OpenAI's ChatGPT o3.

- **Few-Shot Examples**  
  Provide examples of ideal inputs and outputs to set expectations.

- **Define Success**  
  Clarify what a successful answer looks like to guide the AI.

- **External Knowledge Use**  
  Instruct the model to access to external data or context as needed, if the model has access to tools.

- **Error Handling**  
  Prompt the AI to flag uncertainties or potential mistakes proactively.

- **Multi-Modal Considerations**  
  Specify formats for tasks involving images, text, or other media.

### Shared Techniques Details

| Technique | Description |
|-----------|-------------|
| Chain of Thought | Encourages step-by-step reasoning. |
| Few-Shot Examples | Provides reference examples for clarity. |
| Define Success | Describes success criteria for the response. |
| External Knowledge Use | Assumes access to relevant external data. |
| Error Handling | AI should flag uncertainties or risks. |
| Multi-Modal Considerations | Clarifies expectations for non-text data. |

---

## Meta-Layer: Self-Improvement

Meta-layer techniques turn the AI into a co-designer of its own prompts. They promote continuous improvement and learning over time.

- **Log Successes and Failures**  
  Keep track of what works and what doesn't for future reference.

- **Maintain Prompt Library**  
  Build a library of successful prompts to reuse.

- **Track Versions**  
  Version control prompts to track improvements and iterations.

- **Ask AI to Improve Prompt (Super Meta-Technique)**  
  After initial drafts, have the AI critique and refine the prompt itself.

### Meta-Layer Details

| Technique | Description |
|-----------|-------------|
| Log Successes and Failures | Record effective and ineffective prompts. |
| Maintain Prompt Library | Curate reusable prompt examples. |
| Track Versions | Maintain version history for prompts. |
| Ask AI to Improve Prompt | Have the AI critique and enhance the prompt. |

---

## Engineering Considerations

Engineering considerations ensure your prompts work reliably at scale, in production environments, or across different systems.

- **Execution Context**  
  Specify the environment (Python, Markdown parser, etc.) assumed by the AI.

- **Risk Management**  
  Request the AI to flag high-risk assumptions or uncertainties.

- **Stylistic Preferences**  
  Define preferred formats, like using headings or bullet points.

- **Model Self-Reflection**  
  Ask the AI to rate its confidence and explain its reasoning.

### Engineering Considerations Details

| Consideration | Description |
|---------------|-------------|
| Execution Context | Defines environmental assumptions (e.g., Python version). |
| Risk Management | Prompts AI to flag risks or uncertainties. |
| Stylistic Preferences | Guides formatting and style. |
| Model Self-Reflection | Requests confidence scores and reasoning. |

---

## Prompt Structure and Organization

Effective prompts benefit from consistent formatting and logical organization. This section addresses how to physically structure prompts and where to position different components.

- **Formatting Options**  
  Choose a consistent formatting approach that makes your prompt readable and parsable:
  - **Markdown**: Use headings, lists, and code blocks for organization
  - **XML Tags**: Enclose sections in custom tags like `<instructions>...</instructions>`
  - **JSON**: Structure complex prompts as parsable JSON objects
  - **Delimiters**: Use triple backticks, triple dashes, or other clear separators

- **Component Placement**  
  Position elements strategically within your prompt:
  - **Context First**: Begin with background information and key context
  - **Instructions Second**: Place clear action items after establishing context
  - **Examples Last**: End with demonstrations or few-shot examples
  - **Hierarchical Structure**: Organize from general instructions to specific details

- **Visual Hierarchy**  
  Use formatting to create visual emphasis:
  - **Bold/Italic**: Highlight critical instructions or constraints
  - **Indentation**: Group related concepts and create parent-child relationships
  - **Line Breaks**: Separate distinct instructions for clarity
  - **Numbered Steps**: Order sequential instructions explicitly

- **Semantic Sections**  
  Group related instructions into labeled sections:
  - **Required vs. Optional**: Clearly distinguish must-have elements
  - **Input vs. Output**: Separate what you're providing from what you expect
  - **Guidelines vs. Examples**: Differentiate rules from demonstrations

### Prompt Structure Details

| Element | Description |
|---------|-------------|
| Formatting Options | Selects a consistent syntax approach (Markdown, XML, JSON, etc.) |
| Component Placement | Determines logical ordering of prompt elements |
| Visual Hierarchy | Uses formatting to establish importance and relationships |
| Semantic Sections | Groups related instructions into meaningful clusters |

---

# ✅ Usage Notes

- Use this document as a working reference for designing high-quality AI prompts.
- Copy individual sections into your prompt design workflows or GitHub issues.
- Iterate and refine this framework as your projects evolve.
- For best results, combine system and user prompts with shared techniques.

---
