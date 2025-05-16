# AI Prompt Evaluation Tool - Product Requirements Document

## 1. Product Overview

The AI Prompt Evaluation Tool is a lightweight Flask application designed to assess the performance of AI system prompts against synthetic documents. The tool allows users to create and test different prompt configurations to evaluate how well an AI model can accurately judge document quality, compliance, alignment, and requirement fulfillment.

## 2. Target Users

- AI Engineers
- Prompt Engineers 
- Product Managers
- Data Scientists
- Quality Assurance Specialists

## 3. Problem Statement

Currently available prompt evaluation tools don't offer the specific functionality needed to:
- Create modular prompt components that can be mixed and matched
- Run systematic evaluations against synthetic test documents
- Compare AI evaluations against ground truth metadata
- Export results with metadata for analysis

## 4. Core Functionality

### 4.1 Prompt Component Management
- Create, store, and manage reusable prompt components
- Component types include:
  - Personas (e.g., "You are an expert document reviewer...")
  - Scoring rubrics (e.g., criteria for rating document quality)
  - Task instructions (e.g., "Evaluate this document for compliance with...")
  - Other custom components
- Ability to create multiple versions of each component type
- Combine components to create complete system prompts
- Generate final prompts to be sent to Claude 3.7 on AWS Bedrock

### 4.2 Document Processing
- Retrieve synthetic test documents from a local directory
- Extract text content from documents
- Read document metadata from a companion Excel spreadsheet
- Metadata includes ground truth values for:
  - Document quality
  - Compliance status
  - Alignment metrics
  - Requirement fulfillment

### 4.3 Evaluation Engine
- For each document:
  - Combine the system prompt with the document text
  - Send the combined prompt to Claude 3.7 via AWS Bedrock API
  - Receive and parse the JSON payload response
  - Extract evaluation metrics from the JSON response
  - Compare against ground truth metadata from Excel

### 4.4 Results Management
- Export all results to Excel, including:
  - Document identifiers
  - System prompt configuration used
  - AI model evaluation results
  - Ground truth metadata values
  - Accuracy metrics (correct/incorrect judgments)
- Generate summary statistics on prompt performance

## 5. Technical Requirements

### 5.1 Technology Stack
- Backend: Python with Flask framework
- Frontend: Simple HTML/CSS/JavaScript
- Data Storage: Local file system, Excel files
- AI Model Integration: AWS Bedrock API calls to Claude 3.7
- Data Processing: Pandas for Excel handling
- Response Format: JSON payload parsing

### 5.2 System Architecture
- Lightweight local application
- No authentication/authorization required
- No need for scalability or distributed architecture
- Single-user operation

## 6. User Experience

### 6.1 UI Workflow
1. **Configure Prompt Components**
   - Select or create persona components
   - Select or create scoring rubric components
   - Select or create task instruction components
   - Configure additional components
   - Combine components into a complete system prompt

2. **Configure Document Source**
   - Specify local directory containing synthetic test documents
   - Specify Excel file containing document metadata

3. **Run Evaluation**
   - Execute the evaluation process
   - Monitor progress as documents are processed

4. **View Results**
   - View summary statistics on evaluation accuracy
   - Export detailed results to Excel

### 6.2 Key Screens
- Prompt Component Management
- Prompt Assembly
- Document Source Configuration
- Evaluation Progress
- Results Summary

## 7. Implementation Plan

### 7.1 File Structure
```
prompt_eval_tool/
│
├── app.py                 # Main Flask application
├── templates/             # HTML templates
│   ├── index.html
│   ├── components.html
│   ├── evaluation.html
│   └── results.html
│
├── static/                # CSS, JS, and other static files
│
├── modules/
│   ├── prompt_manager.py  # Handles prompt component management
│   ├── document_reader.py # Handles document and metadata reading
│   ├── evaluator.py       # Handles AI model integration and evaluation
│   └── results_exporter.py # Handles export to Excel
│
└── data/                  # Default location for input/output files
    ├── components/        # Stored prompt components
    ├── documents/         # Test documents
    ├── metadata/          # Excel files with document metadata
    └── results/           # Exported results
```

### 7.2 Key Implementation Details

#### Document Processing
- Support for common document formats (TXT, PDF, DOCX)
- Extraction of document text
- Reading metadata from Excel with pandas

#### AI Model Integration
- Integration with Claude 3.7 via AWS Bedrock API
- JSON payload as the expected response format
- Error handling for API failures

#### Results Analysis
- Calculate accuracy metrics
- Export comprehensive data for external analysis

## 8. Future Enhancements (Not in Initial Scope)

- Batch testing of multiple prompt configurations
- Visualization of evaluation results
- Integration with version control for prompt components
- Support for multiple AI models
- Automated optimization of prompt components

## 9. Success Metrics

- **Primary**: Accuracy of prompt evaluations compared to ground truth
- **Secondary**: Time saved in prompt development and testing process

## 10. Open Questions and Assumptions

1. ✓ Which AI model(s) will be used for evaluation? **Claude 3.7 on AWS Bedrock**
2. ✓ What is the expected format of the AI model's response? **JSON payload**
3. What specific metadata fields need to be tracked and compared?
4. Are there any performance requirements (e.g., documents processed per hour)?
5. Will the tool need to handle very large documents?
6. What document formats will the system need to support?
7. How will you define a "correct" evaluation by the AI?
8. Do you need any specific visualizations for result analysis?

## 11. Timeline

Given the straightforward nature of this application and its "quick and dirty" purpose:

- Development: 2-3 weeks
- Testing: 1 week
- Deployment: Minimal (local installation)