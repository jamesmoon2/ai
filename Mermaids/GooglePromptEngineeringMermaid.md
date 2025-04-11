graph TD
    PE[Prompt Engineering] --> CONFIG[LLM Output Configuration]
    PE --> TECHNIQUES[Prompting Techniques]
    PE --> BP[Best Practices]
    PE --> CP[Code Prompting]
    PE --> APE[Automatic Prompt Engineering]
    
    %% Main concept explanations
    PE --- PE_EXP["• Process of crafting inputs to guide LLM outputs
    • Iterative approach requiring experimentation
    • Combines art and science of communication with AI"]
    
    APE --- APE_EXP["• Using LLMs to generate and evaluate prompts
    • Automates testing of multiple prompt variations
    • Uses models to optimize their own inputs"]
    
    %% LLM Output Configuration branch
    CONFIG --> OL[Output Length]
    CONFIG --> SC[Sampling Controls]
    SC --> TEMP[Temperature]
    SC --> TOPK[Top-K]
    SC --> TOPP[Top-P]
    
    CONFIG --- CONFIG_EXP["• Settings that control response generation
    • Parameters affecting creativity vs precision
    • Technical controls for token selection"]
    
    OL --- OL_EXP["• Controls token count in responses
    • Affects computation cost and time
    • Limits response size but not style"]
    
    TEMP --- TEMP_EXP["• Controls randomness (0-1 scale)
    • Low: deterministic, predictable responses
    • High: creative but potentially inconsistent"]
    
    TOPK --- TOPK_EXP["• Limits selection to K most probable tokens
    • Higher values: more diverse responses
    • Lower values: more focused outputs"]
    
    TOPP --- TOPP_EXP["• Nucleus sampling until probability threshold met
    • Values from 0 (deterministic) to 1 (all tokens)
    • Balances diversity and relevance"]
    
    %% Prompting Techniques branch
    TECHNIQUES --> BASIC[Basic Techniques]
    TECHNIQUES --> CONTEXT[Context-Based]
    TECHNIQUES --> ADVANCED[Advanced Reasoning]
    
    TECHNIQUES --- TECH_EXP["• Methods to structure effective prompts
    • Strategies for different task types
    • Approaches that leverage model training"]
    
    %% Basic Techniques
    BASIC --> ZERO[Zero-Shot]
    BASIC --> ONE[One-Shot]
    BASIC --> FEW[Few-Shot]
    
    ZERO --- ZERO_EXP["• No examples provided
    • Direct instructions only
    • Relies on model's pre-training"]
    
    ONE --- ONE_EXP["• Single example in prompt
    • Demonstrates desired pattern
    • Shows format through illustration"]
    
    FEW --- FEW_EXP["• Multiple examples (3-6 typically)
    • Establishes patterns through demonstration
    • Most effective with varied examples"]
    
    %% Context-Based Techniques
    CONTEXT --> SYSTEM[System Prompting]
    CONTEXT --> ROLE[Role Prompting]
    CONTEXT --> CONTEXTUAL[Contextual Prompting]
    
    SYSTEM --- SYSTEM_EXP["• Sets overall context and objectives
    • Specifies output format requirements
    • Defines constraints and parameters"]
    
    ROLE --- ROLE_EXP["• Assigns identity to the model
    • 'Act as a travel guide/professor/etc.'
    • Controls voice, expertise and perspective"]
    
    CONTEXTUAL --- CONTEXTUAL_EXP["• Provides relevant background information
    • Focuses model attention on specific aspects
    • Improves relevance of responses"]
    
    %% Advanced Reasoning Techniques
    ADVANCED --> COT[Chain of Thought]
    ADVANCED --> STEP[Step-Back Prompting]
    ADVANCED --> SELF[Self-Consistency]
    ADVANCED --> TOT[Tree of Thoughts]
    ADVANCED --> REACT[ReAct]
    
    COT --- COT_EXP["• Shows reasoning steps: 'Let's think step by step'
    • Improves complex problem-solving
    • Makes reasoning explicit and traceable"]
    
    STEP --- STEP_EXP["• Considers broader principles first
    • Steps back to general concepts before specifics
    • Activates relevant background knowledge"]
    
    SELF --- SELF_EXP["• Generates multiple reasoning paths
    • Takes majority vote from different attempts
    • Improves accuracy through consensus"]
    
    TOT --- TOT_EXP["• Explores multiple reasoning branches
    • Evaluates different paths systematically
    • More structured than linear reasoning"]
    
    REACT --- REACT_EXP["• Combines reasoning with actions
    • Alternates thinking with external tools
    • Enables tool use (search, computation)"]
    
    %% Code Prompting branch
    CP --> CW[Writing Code]
    CP --> CE[Explaining Code]
    CP --> CT[Translating Code]
    CP --> CD[Debugging Code]
    
    CP --- CP_EXP["• Specialized techniques for code tasks
    • Methods for generation and analysis
    • Programming-specific prompt strategies"]
    
    CW --- CW_EXP["• Generating code in various languages
    • Creating functions and applications
    • Implementing algorithms from descriptions"]
    
    CE --- CE_EXP["• Breaking down code functionality
    • Explaining complex logic step-by-step
    • Making technical concepts accessible"]
    
    CT --- CT_EXP["• Converting between programming languages
    • Preserving functionality across syntax
    • Maintaining logic with different libraries"]
    
    CD --- CD_EXP["• Finding and fixing errors
    • Suggesting improvements and optimizations
    • Explaining bugs and their solutions"]
    
    %% Best Practices branch
    BP --> BP1[Provide Examples]
    BP --> BP2[Design with Simplicity]
    BP --> BP3[Be Specific About Output]
    BP --> BP4[Use Instructions over Constraints]
    BP --> BP5[Control Token Length]
    BP --> BP6[Use Variables in Prompts]
    BP --> BP7[Experiment with Formats]
    BP --> BP8[Document Prompt Attempts]
    BP --> BP9[Use Structured Output/JSON]
    
    BP --- BP_EXP["• Guidelines for effective prompts
    • Practical recommendations from experience
    • Strategies to improve prompt performance"]
    
    BP1 --- BP1_EXP["• Include desired output examples
    • Show patterns through demonstration
    • More effective than abstract instructions"]
    
    BP2 --- BP2_EXP["• Use clear, concise language
    • Avoid unnecessary complexity
    • Employ direct, action-oriented verbs"]
    
    BP3 --- BP3_EXP["• Define expected response format
    • Specify length, style and content
    • Provide detailed output requirements"]
    
    BP4 --- BP4_EXP["• Focus on what model should do
    • Positive instructions over prohibitions
    • Specify desired behavior not restrictions"]
    
    BP9 --- BP9_EXP["• Request structured formats (JSON/XML)
    • Reduces hallucinations through constraints
    • Makes responses programmatically usable"]
    
    %% Relationships between techniques
    COT -- improves --> SELF
    SELF -- extends --> TOT
    STEP -- combines with --> COT
    ZERO -- leads to --> ONE
    ONE -- extends to --> FEW
    
    %% Special notation
    classDef advanced fill:#f9f,stroke:#333,stroke-width:2px;
    class ADVANCED,COT,STEP,SELF,TOT,REACT advanced;
    
    classDef config fill:#bbf,stroke:#333,stroke-width:1px;
    class CONFIG,OL,SC,TEMP,TOPK,TOPP config;
    
    classDef practice fill:#bfb,stroke:#333,stroke-width:1px;
    class BP,BP1,BP2,BP3,BP4,BP5,BP6,BP7,BP8,BP9 practice;
    
    classDef explanation fill:#fffce8,stroke:#ccc,stroke-width:1px;
    class PE_EXP,APE_EXP,CONFIG_EXP,OL_EXP,TEMP_EXP,TOPK_EXP,TOPP_EXP,TECH_EXP,ZERO_EXP,ONE_EXP,FEW_EXP,SYSTEM_EXP,ROLE_EXP,CONTEXTUAL_EXP,COT_EXP,STEP_EXP,SELF_EXP,TOT_EXP,REACT_EXP,CP_EXP,CW_EXP,CE_EXP,CT_EXP,CD_EXP,BP_EXP,BP1_EXP,BP2_EXP,BP3_EXP,BP4_EXP,BP9_EXP explanation;