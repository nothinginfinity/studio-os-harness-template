# Example Automation: Multi-Step Workflow Template

## Purpose

Automations define multi-step sequences the model should follow for a specific task class. They are procedural — each step has a clear input, action, and output.

## Trigger

Describe what initiates this automation (user message pattern, webhook event, schedule, etc.).

## Steps

### Step 1: Gather Context
- **Input**: User request
- **Action**: Call `read_file` or `search` to collect relevant context
- **Output**: Populated context block

### Step 2: Plan
- **Input**: Context block
- **Action**: Think through the task, identify dependencies, list actions
- **Output**: Ordered action plan

### Step 3: Execute
- **Input**: Action plan
- **Action**: Execute each action in order, confirm before irreversible steps
- **Output**: Result per action

### Step 4: Verify
- **Input**: Results
- **Action**: Check each result against acceptance criteria
- **Output**: Pass/fail per action

### Step 5: Report
- **Input**: Verification results
- **Action**: Summarize what was done, what succeeded, what failed, and next steps
- **Output**: Summary message to user

## Error Handling

- On tool failure: retry once, then ask user for guidance
- On ambiguity: stop and ask rather than guess
- On irreversible action: always confirm first
