# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and this project adheres to [Semantic Versioning](https://semver.org/).
## [0.1.2] - 2026-01-30

### Added
- Documentation notes for Windows npm shim paths (double backslashes) across CLI backends and settings reference.
- OpenAI-compatible URL behavior documentation, including `/vN` base URL handling.

### Changed
- Gemini CLI default command updated to `gemini --output-format text --model gemini-2.5-flash`.
- OpenAI-compatible backend now respects versioned base URLs by appending `/chat/completions` instead of forcing `/v1`.
- MCP environment variables expanded for wider CLI discovery (`MCP_SERVER_URL`, `MCP_SERVER`, `MCP_TOKEN`).

### Fixed
- Toggle switches now animate to the correct side when state changes programmatically.
- CLI embedded mode no longer hangs on stdout reads; timeouts return with output tail for debugging.

## [0.1.1] - 2026-01-29

### Added
- Targeted tests submenu in request context menu for focused active scans (SQLi, XSS, SSRF, IDOR, etc.).
- Generic OpenAI-compatible HTTP backend with configurable base URL, model, API key, extra headers, and timeout.
- Optional API key and custom headers for Ollama and LM Studio HTTP backends.
- Open CLI buttons in backend settings for CLI backends (Codex, Gemini, OpenCode, Claude, Ollama CLI).
- Each chat session now remembers the context from previous messages.
- Default prompt templates now instruct the AI to always answer in English.

### Changed
- Context menu action renamed from "Quick recon" to "Analyze this request".
- Active issues now use class-based names (e.g., `[AI Active] SQLI`) and consolidate duplicates per base URL.
- Passive issues normalize to `[AI Passive] <VULN_CLASS>` when possible and consolidate duplicates per base URL.
- Issue details are sanitized to plain text (markdown removed) across passive/active scanners and MCP `issue_create`.

### Fixed
- Windows failures when OpenCode is installed via npm and the command is set to `opencode.exe`.

## [0.1.0] - 2026-01-28

### Added
- Initial public release.
- 6 AI backends: Ollama, LM Studio, Gemini CLI, Claude CLI, Codex CLI, OpenCode CLI.
- MCP server with 53+ tools (SSE and STDIO transports).
- Passive AI Scanner with background traffic analysis.
- Active AI Scanner with 62 vulnerability classes and 3 scan modes (BUG_BOUNTY, PENTEST, FULL).
- 3 privacy modes (STRICT, BALANCED, OFF) with cookie stripping, token redaction, and host anonymization.
- Agent Profiles system (pentester, bughunter, auditor) with section-based action mapping.
- 9 customizable prompt templates for context menu actions.
- JSONL audit logging with SHA-256 integrity hashing.
- Determinism mode for reproducible prompt bundles.
- Drop-in custom backend support via ServiceLoader.
- Burp Pro integration: native ScanCheck, Collaborator OAST, scanner issue actions.
- Full GitBook documentation.
