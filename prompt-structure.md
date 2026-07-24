# Prompt Structure Reference Card

## The Four Parts

| Part | Question it answers | Example |
|------|-------------------|---------|
| **Task** | What should Copilot create or change? | "Add a method to TaskService..." |
| **Context** | Which files? What pattern to follow? | "...following the same style as getTasksByStatus" |
| **Constraint** | What must NOT change or break? | "Do not modify existing method signatures" |
| **Output** | What does done look like? | "Run mvn test and confirm the suite passes" |

## Quick Checklist

Before sending a prompt, ask yourself:

- [ ] Does it start with a verb? (Add, Create, Refactor, Fix, Update)
- [ ] Does it name the specific file or class to change?
- [ ] Does it say what existing behaviour must be preserved?
- [ ] Does it describe how to verify the result?

## Vague vs Precise Examples

| Vague | Precise |
|-------|---------|
| "Add validation" | "Add @Size(min=1, max=100) to Task.title using Jakarta Bean Validation" |
| "Fix the bug" | "Fix the NullPointerException in TaskService.updateTask when the task does not exist — return Optional.empty() instead of throwing" |
| "Write tests" | "Write JUnit 5 tests for TaskService.createTask covering: happy path, null title (expect exception), null status (expect exception)" |
| "Make it faster" | "Replace the ArrayList copy in TaskRepository.findAll with an unmodifiable view to avoid the allocation on every call" |