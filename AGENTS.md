# AGENTS.md – Best Practices for Using Opencode Agents

## 1. General Principles
- **Keep tasks atomic**: Break work into single, well‑defined steps.
- **Prefer explicit commands**: Use dedicated tools (`Read`, `Edit`, `Write`, `Bash`, etc.) instead of ad‑hoc scripts.
- **Respect security**: Never expose secrets or run unsafe commands.

## 2. Workflow Conventions
| Phase | Action |
|------|--------|
| **Planning** | Create a todo list (`task` tool) to outline steps. |
| **Execution** | Perform one operation at a time; update task status immediately. |
| **Verification** | Run lint/typecheck or relevant checks before committing. |
| **Commit** | Only commit when explicitly requested; use conventional messages. |
| **PR** | Use `gh pr create` with a clear title and multi‑bullet summary. |

## 3. Tool Usage
- **Read**: Retrieve file contents (use `offset/limit` for large files).  
- **Edit**: Modify files only after reading; preserve original indentation.  
- **Write**: Overwrite files; must read first if they already exist.  
- **Bash**: Execute shell commands via `workdir` for directory changes; include a short description.  
- **Glob/Grep**: Use for discovering files (`glob`) or content patterns (`grep`).  

## 4. Collaboration
- Ask clarifying questions with the `question` tool when requirements are ambiguous.  
- Resume paused tasks using their `task_id`.  
- Avoid interleaving unrelated actions; focus on a single objective per turn.

---  
*These practices aim to keep work reproducible, safe, and easy to review.*