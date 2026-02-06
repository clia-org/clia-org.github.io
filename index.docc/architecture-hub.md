# CLIA Org

@Metadata {
  @PageKind(article)
  @PageColor(blue)
  @TitleHeading("Agentic Frameworks")
  @PageImage(purpose: icon, source: "index-icon", alt: "CLIA Icon")
  @PageImage(purpose: card, source: "index-card", alt: "CLIA Card")
}

@Options {
  @TopicsVisualStyle(detailedGrid)
  @AutomaticSeeAlso(disabled)
}

Human-centered automation and agent orchestration.

## Overview

CLIA (Command Line Interface Agent) is a platform for building, managing, and collaborating with AI agents in a local-first engineering environment.

## Topics

### Ecosystem

- **CLIA Agent**: The core agentic engine.
- **Workflow**: Automated build and deployment pipelines.

### Guides

- <doc:triads>
- <doc:s-type-system>

### CLIA Architecture

CLIA is designed as a layered, local-first system.

- **Surface / Entry points**
  - **`clia` executable**: the user-facing CLI that parses intent and orchestrates operations.
- **Command sets** (reusable CLI behaviors)
  - **CLIAAgentCoreCLICommands**: agent operations (run, inspect, manage).
  - **CLIAIncidentCoreCommands**: incident creation and triage.
  - **CLIAIncidentResolutionCommands**: incident resolution workflows.
- **Core domain libraries** (portable + testable)
  - **CLIACoreModels**: shared data models.
  - **CLIACore**: core CLIA domain logic and utilities.
  - **CLIAAgentCore**: agent runtime core.
  - **CLIAAgentAudit**: auditing/trace helpers.
- **Runtime + tooling ecosystem**
  - process, shell, logging, filesystem, and formatting libraries from the broader ecosystem.

Mental model:

**User intent → `clia` CLI → command set → core libs → runtime/tooling deps → output + audit trail**

### CLIA Org Libraries

- **CLIACoreModels**: Shared data models used across CLIA tools.
- **CLIACore**: Core CLIA domain logic and utilities.
- **CLIAAgentCore**: Core agent runtime components.
- **CLIAAgentCoreCLICommands**: Reusable CLI subcommand implementations for agent operations.
- **CLIAIncidentCoreCommands**: Incident creation/triage command set.
- **CLIAIncidentResolutionCommands**: Incident resolution workflows.
- **CLIAAgentAudit**: Auditing/trace helpers for agent runs.

### OpenClaw

- [openclaw-swift](../../local/openclaw-swift.docc/index.md)
- [openclaw-runtime](../../local/openclaw-runtime.docc/index.md)
- [CLIA 2025 Wrapped](/documentation/clia-2025-wrapped/)
