# ⚙️ Cursor Setup Guide

This document outlines how to set up and manage your project efficiently using [Cursor](https://www.cursor.so).

---
1) .cursorrules
The .cursorrules file contains project-specific instructions that are always in the AI's context. Adding custom rules helps AI provide better, more relevant suggestions.
- Example: "Always use strict types instead of any in TypeScript."
- More examples: cursor.directory

2) Pre-prompt
In Cursor settings, under "Rules for AI," you can define custom instructions to refine AI responses:
- Keep answers concise and direct
- Suggest alternative solutions
- Avoid unnecessary explanations
- Prioritize technical details over generic advice

3) Code Index
AI relies on your code index to understand your project. If you're frequently adding or deleting files, outdated indexing can lead to incorrect suggestions.
- AI might reference old files and produce incorrect code
- Manual resyncing keeps AI aware of your latest changes
- Go to Cursor Settings > Resync Index to update it

4: Reference Open Editors
For AI to stay focused, only relevant files should be added to the context.
- Close unnecessary tabs
- Open only the files you need
- Use / Reference Open Editors to quickly add them to context

5) Notepads
Notepads let you save frequently used prompts, file references, and explanations for quick reuse. Instead of manually re-explaining things, simply call a Notepad.
- Document feature setups (e.g., "How to Add a New API Route")
- Store common prompts like code reviews or security checks

## 💡 Tips & Best Practices

- Use [Awesome Cursor Rules](https://github.com/cursor-dev/awesome-cursor-rules) to enhance your `.cursorrules` file.
- Reindex the codebase from:
  > **Settings → Cursor settings → Features**
- Keep tasks small and incremental. Ask Cursor:
  > _“Let’s work on the next feature.”_
- Update `Project_milestones.md` and `Documentation.md` regularly.

---

##  📺 Helpful Video Guides

- [Cursor Workflow Part 1](https://www.youtube.com/watch?v=1L509JK8p1I)
- [Cursor Deep Dive Part 2](https://www.youtube.com/watch?v=2PjmPU07KNs)

