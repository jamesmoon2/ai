# AI Interaction Strategy Framework (Compact Version)

```mermaid
graph TB
    A[AI Interaction Strategy Framework]

    %% Subgraphs for clarity
    subgraph System Prompt Layer
        SP1[Define Persona]
        SP2[Set Tone and Style]
        SP3[Set Constraints and Limits]
        SP4[Memory Management]
        SP5[Handle Ambiguity]
        SP6[Fallback Behavior]
        SP7[Role Assignments]
        SP8[Audience Awareness]
    end

    subgraph User Prompt Layer
        UP1[Clear Task or Question]
        UP2[Output Format]
        UP3[Background and Context]
        UP4[Clarify Questions]
        UP5[Iteration and Refinement]
        UP6[Parallel Alternatives]
        UP7[Response Validation]
        UP8[Post-Processing Suggestions]
    end

    subgraph Shared Techniques
        S1[Chain of Thought]
        S2[Few-Shot Examples]
        S3[Define Success]
        S4[External Knowledge Use]
        S5[Error Handling]
        S6[Multi-Modal Considerations]
    end

    subgraph Meta-Layer
        M1[Log Successes and Failures]
        M2[Prompt Library]
        M3[Track Versions]
        M4[Ask AI to Improve Prompt]
    end

    subgraph Engineering Considerations
        EC1[Execution Context]
        EC2[Risk Management]
        EC3[Stylistic Preferences]
        EC4[Model Self-Reflection]
    end

    %% Connect main node to subgraphs
    A --> System Prompt Layer
    A --> User Prompt Layer
    A --> Shared Techniques
    A --> Meta-Layer
    A --> Engineering Considerations

    %% Internal connections for better flow (optional)
    SP3 --> SP4
    UP1 --> UP3
    UP3 --> UP4
    UP4 --> UP5
    UP5 --> UP6
    UP6 --> UP7
    UP7 --> UP8
    M1 --> M4
    EC1 --> EC2
    EC2 --> EC3
    EC3 --> EC4
