# Gemini CLI Tool Mapping

Skills speak in actions ("dispatch a subagent", "create a todo", "read a file"). On Gemini CLI these resolve to the tools below.

These mappings apply to actions already chosen by the workflow; they do not
require delegation or task tracking. Follow the current host's available tools.

| Action skills request | Gemini CLI equivalent |
|----------------------|----------------------|
| Read a file | `read_file` |
| Read multiple files at once | `read_many_files` |
| Create a new file | `write_file` |
| Edit a file | `replace` |
| Run a shell command | `run_shell_command` |
| Search file contents | `grep_search` |
| Find files by name | `glob` |
| List files and subdirectories | `list_directory` |
| Fetch a URL | `web_fetch` |
| Search the web | `google_web_search` |
| Invoke a skill | `activate_skill` |
| Dispatch a subagent (`Subagent (general-purpose):` template) | `invoke_agent` with `agent_name: "generalist"` (invocable via `@generalist` chat syntax — see [Subagent support](#subagent-support)) |
| Multiple parallel dispatches | Multiple `invoke_agent` calls in the same response |
| Task tracking ("create a todo", "mark complete") | `write_todos` (statuses: pending, in_progress, completed, cancelled, blocked) |

## Instructions file

When a skill mentions "your instructions file", on Gemini CLI this is **`GEMINI.md`**. Gemini CLI loads `GEMINI.md` hierarchically: global at `~/.gemini/GEMINI.md`, project-level files in workspace directories and their ancestors, and sub-directory `GEMINI.md` files when a tool accesses files in those directories.

## Personal skills directory

User-level skills live at **`~/.gemini/skills/`**, with **`~/.agents/skills/`** as a cross-runtime alias (shared with Codex and Copilot CLI). When both directories exist at the same scope, `.agents/skills/` takes precedence. Each skill is a subdirectory containing a `SKILL.md` (with `name` and `description` frontmatter).

## Subagent support

Gemini CLI dispatches subagents through the `invoke_agent` tool, which takes `agent_name` and `prompt` parameters. The same dispatch is also surfaced as a chat-syntax shortcut: typing `@generalist <prompt>` is equivalent to calling `invoke_agent` with `agent_name: "generalist"`. Built-in agent names include `generalist`, `cli_help`, `codebase_investigator`, and (with browser tooling enabled) `browser_agent`.

Pass a bounded brief to `invoke_agent`: the task, necessary context, acceptance
checks, and authorization limits. Skill prompt templates are optional aids, not
required forms. Do not add a report format or extra workflow just because a
template is available.

### Parallel dispatch

When delegation is useful and permitted, independent tasks can use multiple
`invoke_agent` calls in one response. Keep dependent tasks sequential; keep work
inline when delegation would add more coordination than value.

## Additional Gemini CLI tools

These tools are unique to Gemini CLI:

| Tool | Purpose |
|------|---------|
| `save_memory` (legacy) | Persist facts across sessions when `experimental.memoryV2 = false` |
| `get_internal_docs` | Look up Gemini CLI's bundled documentation |
| `ask_user` | Pose structured questions to the user (text / single-select / multi-select) |
| `enter_plan_mode` / `exit_plan_mode` | Switch into and out of read-only plan mode |
| `update_topic` | Update the current conversation's topic / strategic-intent metadata |
| `complete_task` | Signal that a Gemini subagent has completed and return its result to the parent agent |
| `tracker_create_task`, `tracker_update_task`, `tracker_get_task`, `tracker_list_tasks`, `tracker_add_dependency`, `tracker_visualize` | Rich task tracker with dependency and visualization support |
| `read_mcp_resource`, `list_mcp_resources` | MCP resource access |
