# Minutes | AI Desktop Meeting Assistant

**A local-first desktop application for meeting transcription, AI-powered conversation management, and searchable meeting history.**

Minutes helps users capture meetings, calls, voice notes, and dictation. It converts speech into text, organizes conversation records, and enables AI assistants to access authorized meeting history through the Model Context Protocol (MCP).

The application focuses on local data storage, user-controlled sharing, and compatibility with AI development tools.

## 1. Project Overview

| Attribute | Details |
|---|---|
| Project Name | Minutes |
| Application Type | Desktop Application |
| Category | AI, Speech Processing, Productivity |
| Core Language | Rust |
| Desktop Framework | Tauri |
| Additional Technologies | TypeScript, Python, JavaScript |
| AI Integration | Model Context Protocol (MCP) |
| Storage | Local Markdown and YAML files |
| Primary Function | Meeting recording, transcription, and retrieval |
| Supported Interfaces | Desktop Application, CLI, MCP Server, SDK |

## 2. Key Features

| Feature | Description |
|---|---|
| Meeting Recording | Capture conversations, meetings, calls, and voice notes |
| Speech-to-Text | Convert recorded speech into text using local transcription |
| AI Summarization | Generate structured meeting summaries using supported AI providers |
| Action Item Extraction | Organize follow-up tasks and decisions from conversations |
| Meeting History | Maintain searchable records of past conversations |
| Voice Dictation | Convert spoken input into written text |
| MCP Integration | Allow compatible AI assistants to search authorized meeting records |
| Local Storage | Store conversation records in user-controlled Markdown files |
| Privacy Controls | Control what meeting information is shared with external services |
| Command-Line Interface | Manage recording and retrieval through terminal commands |
| Recovery | Support recovery workflows for interrupted audio processing |
| Structured Metadata | Store meeting details using YAML frontmatter |

## 3. Technology Stack

| Layer | Technology | Purpose |
|---|---|---|
| Core Backend | Rust | Application logic and processing |
| Desktop Framework | Tauri | Native desktop application |
| Application Logic | TypeScript | Integrations and client functionality |
| Supporting Scripts | Python | Processing, testing, and automation |
| UI Components | HTML, CSS, JavaScript | Desktop interface |
| AI Connectivity | MCP | AI assistant communication |
| Data Format | Markdown | Readable meeting records |
| Metadata | YAML | Structured information |
| Version Control | Git | Source code management |
| Repository Hosting | GitHub | Source code and documentation |

## 4. System Architecture

The application consists of several connected components.

| Component | Responsibility |
|---|---|
| Desktop Interface | Provides recording, transcription, and meeting management controls |
| Audio Capture | Collects input from supported audio sources |
| Transcription Engine | Converts recorded audio into text |
| Meeting Processor | Organizes transcript content and metadata |
| Summarization Integration | Sends authorized content to configured summarization providers |
| Local File Storage | Stores Markdown meeting records |
| Search and Retrieval | Finds relevant meeting information |
| MCP Server | Exposes supported meeting operations to AI assistants |
| CLI | Provides terminal-based application controls |
| SDK | Enables programmatic access to meeting information |

### High-Level Workflow

```text
              USER
               |
               v
      +-------------------+
      | Desktop Interface |
      +-------------------+
               |
               v
      +-------------------+
      |   Audio Capture   |
      +-------------------+
               |
               v
      +-------------------+
      | Local Transcription|
      +-------------------+
               |
               v
      +-------------------+
      | Meeting Processing|
      +-------------------+
               |
       +-------+--------+
       |                |
       v                v
+-------------+  +----------------+
| Local Files |  | AI Summarizer  |
| Markdown    |  | (Optional)     |
+-------------+  +----------------+
       |
       v
+---------------------+
| Search and Retrieval|
+---------------------+
       |
       v
+---------------------+
| MCP Server / CLI    |
+---------------------+
       |
       v
+---------------------+
| AI Assistant        |
+---------------------+
```

## 5. Supported Interfaces

| Interface | Function |
|---|---|
| Desktop App | Recording, dictation, viewing, and managing conversations |
| CLI | Recording controls, processing, searching, and automation |
| MCP Server | AI agent access to authorized meeting information |
| TypeScript SDK | Programmatic access to supported meeting data |
| Markdown Files | Direct access to locally stored meeting records |

## 6. AI Assistant Integration

Minutes supports integration with tools that can communicate through MCP.

| AI Tool | Integration Type |
|---|---|
| Claude Code | MCP |
| Codex | MCP |
| Cursor | MCP |
| OpenCode | MCP |
| Gemini CLI | MCP |
| Claude Desktop | MCP |
| Mistral Vibe | MCP |
| Other MCP Clients | MCP-compatible connection |

### Example MCP Setup

For Claude Code:

```bash
claude mcp add minutes -- npx -y minutes-mcp
```

The MCP server provides compatible assistants with access to permitted meeting operations.

### Example Query

A user can ask an AI assistant:

> What decisions were made in our previous project planning meeting?

The assistant can search available meeting records and return relevant information when the client and permissions are configured.

## 7. Meeting Record Format

Meeting records use Markdown files with structured YAML metadata.

### Example

```yaml
---
title: Project Planning Meeting
type: meeting
date: 2026-10-15T10:00:00
duration: 45m
context: Sprint planning and task allocation

action_items:
  - assignee: Developer A
    task: Complete API integration
    status: open

  - assignee: Developer B
    task: Prepare UI components
    status: open

decisions:
  - text: Complete the first development milestone
---
```

### Metadata Fields

| Field | Description |
|---|---|
| `title` | Meeting name |
| `type` | Record category |
| `date` | Meeting date and time |
| `duration` | Recording duration |
| `context` | Purpose of the meeting |
| `action_items` | Tasks assigned during the meeting |
| `assignee` | Person responsible for a task |
| `status` | Task completion status |
| `decisions` | Decisions recorded during the meeting |

## 8. Installation and Development

### Prerequisites

The development environment depends on the operating system and the components being built.

| Tool | Purpose |
|---|---|
| Git | Clone the repository |
| Rust and Cargo | Build Rust components |
| Tauri prerequisites | Build the desktop application |
| Node.js and npm | Support JavaScript-based tooling |
| Python | Run supporting Python scripts |
| C++ Build Tools | Native compilation where required |

### Clone the Repository

```bash
git clone https://github.com/DGSKOUSHIK/minutes-project.git
cd minutes-project
```

### Inspect the Rust Workspace

```bash
cargo metadata --no-deps
```

### Run the Rust Test Suite

```bash
cargo test --workspace
```

The commands above require the appropriate development dependencies. The full desktop application may need additional platform-specific configuration.

For detailed setup information, see `docs/install.md` in the repository.

## 9. Repository Structure

```text
minutes-project/
|
|-- .github/
|-- crates/
|-- tauri/
|-- sidecars/
|-- integrations/
|-- schema/
|-- scripts/
|-- tests/
|-- tooling/
|-- examples/
|-- docs/
|-- design/
|-- site/
|
|-- Cargo.toml
|-- Cargo.lock
|-- README.md
|-- LICENSE
|-- NOTICE
```

### Directory Details

| Directory | Purpose |
|---|---|
| `crates/` | Rust workspace components |
| `tauri/` | Desktop application source |
| `sidecars/` | Supporting processing services |
| `integrations/` | External integrations |
| `schema/` | Structured data definitions |
| `scripts/` | Development and automation scripts |
| `tests/` | Test suites and validation |
| `tooling/` | Developer tools |
| `examples/` | Usage examples |
| `docs/` | Technical documentation |
| `design/` | Application design information |
| `site/` | Website-related source files |
| `.github/` | GitHub configuration |

## 10. Privacy and Data Management

The application follows a local-first approach.

| Area | Implementation |
|---|---|
| Audio Processing | Local processing for supported transcription workflows |
| Meeting Records | User-controlled local files |
| Cloud Summarization | Optional and provider-dependent |
| AI Assistant Access | Authorized meeting context |
| File Format | Readable Markdown with YAML metadata |
| Data Portability | Records can be used with compatible text tools |
| Sensitive Information | Restricted handling for supported sensitive-record workflows |

When configured to use cloud AI services, authorized content may leave the local device. Users should review the selected provider and data-sharing settings.

## 11. Application Workflow

| Step | Process | Result |
|---|---|---|
| 1 | Start recording | Audio capture begins |
| 2 | Stop recording | Recorded audio is prepared for processing |
| 3 | Transcribe | Speech is converted into text |
| 4 | Organize | Meeting metadata is recorded |
| 5 | Summarize | Optional AI summary is generated |
| 6 | Store | Meeting record is saved locally |
| 7 | Search | Previous conversation content can be retrieved |
| 8 | Integrate | Authorized content becomes accessible to MCP clients |

## 12. Testing and Validation

The repository includes tests and supporting tools for application components.

| Test Area | Purpose |
|---|---|
| Rust Unit Tests | Validate core functionality |
| Integration Tests | Check interactions between components |
| Audio Processing Tests | Validate processing behavior |
| CLI Tests | Verify command-line operations |
| MCP Tests | Check supported agent integration contracts |
| Desktop Tests | Test application behavior on supported platforms |
| Privacy Tests | Validate relevant data-handling rules |

Test availability and results depend on the development environment. A successful repository upload does not by itself confirm that all tests pass.

## 13. Development Roadmap

The following are potential future enhancements, not claims of completed functionality.

| Planned Improvement | Objective |
|---|---|
| Transcription Improvements | Improve recognition quality for different accents and environments |
| Speaker Identification | Improve speaker separation in multi-person meetings |
| Semantic Search | Improve retrieval of relevant conversation details |
| Summary Customization | Provide flexible meeting-summary formats |
| Task Management | Improve action item organization |
| Export Options | Support additional report and document formats |
| Desktop Experience | Improve usability and workflow navigation |
| Integration Expansion | Support additional compatible AI tools |

## 14. Technical Documentation

| Document | Description |
|---|---|
| `docs/install.md` | Installation and development setup |
| `docs/features.md` | Application features and CLI commands |
| `docs/configuration.md` | Configuration options |
| `docs/architecture/README.md` | Architecture and application design |
| `docs/integration/clients.md` | AI client integrations |
| `docs/architecture/frontmatter-schema.md` | Meeting metadata format |
| `docs/security/` | Security documentation |
| `CONTRIBUTING.md` | Contribution guidance |
| `LICENSE` | Software license |
| `NOTICE` | Copyright and attribution notices |

## 15. License

Distributed under the MIT License. See the repository's `LICENSE` and `NOTICE` files for the applicable terms and copyright information.
