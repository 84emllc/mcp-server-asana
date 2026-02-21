# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-02-21

Initial public release. Fork of [roychri/mcp-server-asana](https://github.com/roychri/mcp-server-asana) v1.7.0.

### Added
- `asana_create_project` tool for creating projects in a workspace
- `asana_delete_task` tool for permanently deleting tasks
- `asana_add_project_to_task` and `asana_remove_project_from_task` for moving tasks between projects
- Positioning support when adding tasks to projects (section, insert_after, insert_before)
- Read-only mode via `READ_ONLY_MODE=true` environment variable
- HTML validation for `html_notes` fields when Asana API returns 400 errors
- HTML support for task comments via `html_text` parameter
- `html_notes`, `followers`, and `parent` parameters on `asana_update_task`

### Fixed
- Search task filters now correctly use dot-notation for Asana API
- `jsdom` moved from devDependencies to dependencies for HTML validation

### Upstream (v1.5.0 - v1.7.0)
- 33 tools covering workspaces, projects, tasks, stories, tags, and project status
- 3 prompts for task management workflows
- 2 resource types (workspaces and projects)
- Tag management and workspace tag operations
- Milestone and approval task support
- Custom fields support for task creation and updates
- Project status CRUD operations

[1.0.0]: https://github.com/84emllc/mcp-server-asana/releases/tag/v1.0.0
