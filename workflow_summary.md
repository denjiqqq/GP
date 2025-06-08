# Pinala Bot N8N Workflow

This repository includes the `pinala_workflow.json` file describing a Telegram bot implemented in N8N.

## Features
- User-specific long‑term memory stored in PostgreSQL/Supabase
- Task management commands (`/add`, `/edit`, `/delete`, `/done`, `/list`)
- Recurring tasks and deadlines with progressive reminders
- Statistics tracking per user
- AI-powered assistant using OpenAI with rate limiting
- Periodic meme delivery
- Admin broadcast feature via `/ads`

## Nodes Overview
1. **Telegram Trigger** – entry point for incoming messages.
2. **Find or Create User** – upserts user profiles in the database.
3. **Get User Memory** – loads previous interactions and stats.
4. **Parse Command** – detects commands vs. free-form chat.
5. **Switch Command** – routes to task nodes, meme node, or AI chat.
6. **Task Nodes** – handle creation, editing, deletion, completion, and listing of tasks.
7. **Stats Node** – returns stats to the user.
8. **Check Rate Limit** – ensures token usage stays within bounds.
9. **Prepare Prompt** – builds the OpenAI prompt using user memory.
10. **OpenAI Chat** – generates friendly responses with personality.
11. **Save Memory** – stores the new interaction.
12. **Send Telegram Reply** – sends messages back to the chat.
13. **Cron** nodes – handle reminders, recurring tasks, memes, and admin broadcasts.

## Optimization Suggestions
- Use indexes on `user_id` and `deadline` columns to speed up queries.
- Batch reminders to minimize Telegram API calls.
- Cache OpenAI responses where possible to reduce token usage.
- Monitor execution time with N8N analytics to scale workers when needed.

