# Cursor Workflow

This is a living note regarding my current Cursor workflow. Please feel free to raise an issue if you have a recommendation for improving it. 

## Step 1 - Scope the New Feature or Change.

Identify the discrete product, feature, or capability you want to develop. 
Explain what you are trying to accomplish to Claude 3.7 in Ask mode. At the same time, tag in your README.md and any other relevant documentation you have for your project.
Explore the idea with Claude. Ask Claude for ways to improve your idea. 
As you accept new ideas for different approaches or components, fold them into the plan. 
Keep asking questions. Explore the idea fully. Question your assumption. Explore the pros and cons of different libraries and programming approaches. Software development is all about tradeoffs. 
Finally, toggle to Agent mode and ask Claude to crete documentation for a step-by-step plan for implementing the change and save that plan to the /docs directory. Claude will create one if it does not already exist. 

## Step 2 - Peer review.

Change your model to Gemeni Pro 2.5 Pro

Tag in the Markdown files you created in Step 1. 
Ask Gemeni to review product documentation, the code base, and the plans creted in Step 1. 
Example Prompt: Determine if anything was missed when preparing the @[Plans]. Please list each issue identified separately in a numbered list. Beneath each issue propose at least two ways to resolve the issue. For each approach, explain briefly the pros and cons. These explanations should be 25-100 words. 

### Step 2.5

Evaluate your options. If you are not able to clearly determine an approach for each issue based on Gemeni's feedback, you should converse with Claude 3.7, ChatGPT 4o, or Gemeni Pro 2.5 to learn more about each option and elect an approach. 

## Step 3 - Provide the Feedback to Claude

Copy Gemeni's feedback and your selected approach to resolve each issue.
Instruct Claude 3.7 to edit the Plan to address the feedback. 

## Step 4 - Implement

Use Cluade 3.7 or Gemeni Pro 2.5 to implement the Plan

