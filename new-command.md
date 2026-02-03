---
description: Create a new slash command file
---

Help me create a new slash command. Guide me through this step by step.

**Step 1: Ask me for the command name**
- Lowercase, hyphens for spaces (e.g., `review-code`, `deploy-staging`)

**Step 2: Ask me what I want this command to accomplish**
- Let me describe it in plain language
- Ask clarifying questions if my description is vague

**Step 3: Structure my idea into an effective prompt**

Apply these prompt engineering best practices from Anthropic:

<best-practices>
- **Be clear and direct**: Write instructions as if for a brilliant new employee with no context
- **Provide context**: What is this task for? What does success look like?
- **Use sequential steps**: Numbered lists ensure Claude follows the exact process
- **Be specific about output**: If you want a specific format, say so explicitly
- **Use XML tags if helpful**: Tags like `<instructions>`, `<example>`, `<output>` help Claude parse complex prompts
</best-practices>

**Step 4: Write the command file**

Create the `.md` file in this folder with:
```
---
description: [Brief description for the command menu]
---

[The structured prompt instructions]
```

Use the other `.md` files in this folder as reference for tone and format.
