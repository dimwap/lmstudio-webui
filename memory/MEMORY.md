---
name: LM Studio Chat WebUI project overview
description: analysis of the LM Studio Chat WebUI project
type: project
---

Project name: LM Studio Chat WebUI (unofficial)

Overview: Browser-based chat interface for connecting to a locally hosted LM Studio server. Allows chatting from any device with a web browser including mobile phones.

Main files: index.html (single-file SPA, no build step required)

Technical approach: Vanilla JS + vanilla CSS in one file, uses Marked for markdown, MathJax for LaTeX rendering.

Key features:
- Dark mode interface with purple theme
- Connect to any LM Studio server (configurable URL)
- Model selection dropdown with auto-ejection of previous model
- Chat sidebar with collapsible design
- Multiple chat conversations with switch and delete functionality
- Context menu for deleting chats (right-click on chat title)
- Image upload support for vision model queries
- Markdown and LaTeX rendering in assistant responses
- Code highlighting via highlight.js with copy-to-clipboard buttons
- Mobile-friendly responsive design
- Streaming response support (assumed from partial read)

Backend requirements: LM Studio server with:
- CORS enabled
- Serve on Local Network enabled
- REST API endpoints: /v1/models

Architecture decisions:
- Single HTML file deployment simplifies sharing (email, cloud storage, file transfer)
- No dependencies on local filesystem — works from any URL
- Uses fetch API for all server communication

User flow:
1. Enter LM Studio server address in header
2. Click "Connect" to load available models
3. Select a model (optional: LLM,VLM)
4. Type message or upload image (if vision model)
5. Receive streamed response with markdown rendering

Known limitations:
- iOS Safari/Chrome require Edge or another browser (documented in README)
- Single-file design limits advanced features like persistent local storage
- No authentication layer — assumes trusted local network environment without API keys.
