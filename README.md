# MCP Server for Asana

> Fork of [roychri/mcp-server-asana](https://github.com/roychri/mcp-server-asana) with additional tools, read-only mode, and project management capabilities.

A Model Context Protocol (MCP) server that connects AI assistants to the Asana API for task, project, and workspace management.

## Installation

### Claude Desktop

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "asana": {
      "command": "npx",
      "args": ["-y", "mcp-server-asana"],
      "env": {
        "ASANA_ACCESS_TOKEN": "your-asana-access-token"
      }
    }
  }
}
```

### Cursor

Add to your Cursor MCP settings:

```json
{
  "mcpServers": {
    "asana": {
      "command": "npx",
      "args": ["-y", "mcp-server-asana"],
      "env": {
        "ASANA_ACCESS_TOKEN": "your-asana-access-token"
      }
    }
  }
}
```

## Configuration

| Variable | Required | Description |
|----------|----------|-------------|
| `ASANA_ACCESS_TOKEN` | Yes | Your Asana personal access token ([generate one here](https://app.asana.com/0/my-apps)) |
| `READ_ONLY_MODE` | No | Set to `true` to disable all write operations |

## Tools (33)

### Workspaces

| Tool | Description |
|------|-------------|
| `asana_list_workspaces` | List all available workspaces |

### Projects

| Tool | Description |
|------|-------------|
| `asana_search_projects` | Search projects by name pattern |
| `asana_get_project` | Get project details |
| `asana_get_project_task_counts` | Get task counts for a project |
| `asana_get_project_sections` | Get sections in a project |
| `asana_create_project` | Create a new project |

### Project Status

| Tool | Description |
|------|-------------|
| `asana_get_project_status` | Get a project status update |
| `asana_get_project_statuses` | List all status updates for a project |
| `asana_create_project_status` | Create a status update |
| `asana_delete_project_status` | Delete a status update |

### Tasks

| Tool | Description |
|------|-------------|
| `asana_search_tasks` | Search tasks with advanced filtering |
| `asana_get_task` | Get task details |
| `asana_create_task` | Create a new task |
| `asana_update_task` | Update a task |
| `asana_delete_task` | Delete a task permanently |
| `asana_create_subtask` | Create a subtask |
| `asana_get_multiple_tasks_by_gid` | Get multiple tasks by GID (max 25) |
| `asana_get_task_stories` | Get comments and stories for a task |
| `asana_create_task_story` | Add a comment to a task |

### Task Relationships

| Tool | Description |
|------|-------------|
| `asana_add_task_dependencies` | Set task dependencies |
| `asana_add_task_dependents` | Set task dependents |
| `asana_set_parent_for_task` | Set or change a task's parent |
| `asana_add_project_to_task` | Add a task to a project |
| `asana_remove_project_from_task` | Remove a task from a project |

### Tags

| Tool | Description |
|------|-------------|
| `asana_get_tag` | Get tag details |
| `asana_get_tags_for_task` | Get tags on a task |
| `asana_get_tasks_for_tag` | Get tasks with a specific tag |
| `asana_get_tags_for_workspace` | List tags in a workspace |
| `asana_create_tag_for_workspace` | Create a tag |
| `asana_update_tag` | Update a tag |
| `asana_delete_tag` | Delete a tag |
| `asana_add_tag_to_task` | Add a tag to a task |
| `asana_remove_tag_from_task` | Remove a tag from a task |

## Prompts

| Prompt | Description |
|--------|-------------|
| `task-summary` | Generate a summary and status update for a task |
| `task-completeness` | Analyze if a task has sufficient details for completion |
| `create-task` | Create a task with guided details |

## Resources

| Resource | URI Pattern | Description |
|----------|-------------|-------------|
| Workspaces | `asana://workspace/{gid}` | Workspace details as JSON |
| Projects | `asana://project/{gid}` | Project details with sections and custom fields |

## Read-Only Mode

Set `READ_ONLY_MODE=true` to disable all write operations. Only read tools remain available, and the `create-task` prompt is hidden. Useful for testing or restricting access.

## Contributing

Pull requests welcome. See the [upstream project](https://github.com/roychri/mcp-server-asana) for the original implementation.

## License

MIT License. See [LICENSE](LICENSE) for details.

## Credits

- Original implementation by [Christian Roy](https://github.com/roychri)
- Fork maintained by [84em.io](https://84em.io)
