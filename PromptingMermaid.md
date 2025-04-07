# Prompting Foundation Models

```mermaid

graph TD
    A[AI Interaction Strategy Framework]

    %% Main Split
    A --> SP[System Prompt Layer]
    A --> UP[User Prompt Layer]
    A --> S[Shared Techniques]
    A --> M[Meta-Layer: Self-Improvement]
    A --> EC[Engineering Considerations]

    %% System Prompt Layer
    SP --> SP1[Define Persona]
    SP --> SP2[Define Tone and Style]
    SP --> SP3[Set Constraints and Limits]
    SP3 --> SP3a[Token limits and creativity level]
    SP --> SP4[Memory Management]
    SP4 --> SP4a[Define persistent context]
    SP4 --> SP4b[Define when to clear/reset memory]
    SP --> SP5[Clarify Ambiguity Protocols]
    SP5 --> SP5a[Ask clarifying questions if unclear]
    SP5 --> SP5b[Flag uncertainties and provide best guesses]
    SP --> SP6[Fallback Behavior]
    SP6 --> SP6a[Define response when unsure]
    SP --> SP7[Role Assignments]
    SP --> SP8[Audience Awareness]
    SP8 --> SP8a[Define target audience]
    SP8 --> SP8b[Adjust complexity]

    %% User Prompt Layer
    UP --> UP1[Define Clear Task or Question]
    UP --> UP2[Specify Output Format]
    UP --> UP3[Provide Background and Context]
    UP3 --> UP3a[Ensure understanding without prior knowledge]
    UP --> UP4[Ask Clarifying Questions]
    UP4 --> UP4a[What additional info is needed?]
    UP4 --> UP4b[What question have I not asked?]
    UP4 --> UP4c[What are alternative approaches?]
    UP --> UP5[Iteration and Refinement]
    UP5 --> UP5a[Request drafts before final output]
    UP5 --> UP5b[Loop feedback and iterate]
    UP --> UP6[Parallel Alternatives]
    UP6 --> UP6a[Request multiple approaches]
    UP6 --> UP6b[Compare methods]
    UP --> UP7[Response Validation]
    UP7 --> UP7a[Cross-check answer against prompt]
    UP7 --> UP7b[Request logical consistency]
    UP --> UP8[Post-Processing Suggestions]
    UP8 --> UP8a[Recommend next steps]
    UP8 --> UP8b[Offer optional formats such as Markdown, JSON]

    %% Shared Techniques
    S --> S1[Chain of Thought Prompting]
    S1 --> S1a[Request step-by-step reasoning]
    S --> S2[Few-Shot Learning]
    S2 --> S2a[Provide examples of good/bad outputs]
    S --> S3[Define Success Criteria]
    S3 --> S3a[Define success for the answer]
    S3 --> S3b[Specify evaluation metrics]
    S --> S4[External Knowledge Use]
    S4 --> S4a[Assume access to external data]
    S4 --> S4b[Reference RAG systems]
    S --> S5[Error Anticipation and Handling]
    S5 --> S5a[Predict potential errors]
    S5 --> S5b[Request confidence estimates]
    S --> S6[Multi-Modal Considerations]
    S6 --> S6a[Define input/output formats]
    S6 --> S6b[Clarify handling of non-text data]

    %% Meta-Layer: Self-Improvement
    M --> M1[Log what worked and what didn’t]
    M --> M2[Maintain a prompt library]
    M --> M3[Track versions of prompts]
    M --> M4[Super Meta-Technique: Ask AI to improve or critique the prompt]

    %% Engineering Considerations
    EC --> EC1[Execution Context]
    EC1 --> EC1a[Specify environment assumptions such as Python, Markdown, etc.]
    EC1 --> EC1b[Define system capabilities or access]
    EC --> EC2[Risk Management]
    EC2 --> EC2a[Flag high-risk areas]
    EC2 --> EC2b[Provide risk notes]
    EC --> EC3[Stylistic Preferences]
    EC3 --> EC3a[Define tone such as formal, casual, etc.]
    EC3 --> EC3b[Specify output formatting]
    EC --> EC4[Model Self-Reflection]
    EC4 --> EC4a[Request confidence score]
    EC4 --> EC4b[Explain confidence level]\

```
