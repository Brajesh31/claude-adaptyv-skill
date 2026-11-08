# claude-adaptyv-skill

A Claude Code skill for managing protein testing and experimental validation workflows with the Adaptyv platform.

## Overview

This skill supports workflows that connect computational protein design with laboratory testing. It helps prepare protein sequences, configure experiments, submit requests, monitor experiment progress, retrieve results, and evaluate optimization opportunities.

## Main Capabilities

- Prepare protein sequence inputs for experimental testing.
- Organize experiment requests and required metadata.
- Work with supported assay types.
- Track experiment status and retrieve available results.
- Review expression, binding, stability, and activity measurements.
- Compare candidate sequences and experimental outcomes.
- Structure iterative protein optimization workflows.
- Use computational predictors to prioritize candidates before experimental submission.

## Experimental Workflows

Depending on platform access and available services, workflows may involve:

- Protein expression testing.
- Binding assays.
- Thermostability measurements.
- Enzyme activity assays.
- Sequence optimization and candidate comparison.
- Result review and follow-up experiment planning.

The exact assay options, accepted input formats, and turnaround times depend on the current platform configuration.

## Installation

Install the skill in your Claude Code skills directory:

```bash
git clone https://github.com/Brajesh31/claude-adaptyv-skill.git ~/.claude/skills/adaptyv
```

Review the Python dependencies required by the examples before running any scripts.

## Authentication and Setup

API access may require an account and an API token. Store credentials in environment variables or a secrets manager.

For a local shell session:

```bash
export ADAPTYV_API_KEY="your_api_key"
```

Do not place real credentials in source files, notebooks, issue reports, or version control.

## Usage

Invoke the skill when planning or managing a protein validation workflow:

```text
/adaptyv
```

Provide the sequence format, experiment objective, candidate identifiers, required assays, and any constraints on cost or turnaround time.

## Recommended Workflow

1. Define the experimental question and success criteria.
2. Validate sequence format and candidate metadata.
3. Review the available assay options.
4. Prepare the experiment request.
5. Submit only after confirming the input and account permissions.
6. Track the experiment using its returned identifier.
7. Retrieve and validate the results.
8. Compare results against the original hypothesis.
9. Decide whether to iterate, redesign, or stop.

## Reference Guide

| File | Purpose |
|---|---|
| `reference/api_reference.md` | API operations and data structures |
| `reference/examples.md` | Example request and response workflows |
| `reference/experiments.md` | Experiment planning and execution |
| `reference/protein_optimization.md` | Protein candidate optimization |

## Data Handling and Reliability

- Validate amino-acid sequences before submission.
- Keep candidate IDs consistent across analysis and experiment records.
- Record assay conditions and platform parameters.
- Distinguish predicted properties from measured results.
- Preserve raw experimental outputs.
- Do not interpret missing measurements as negative results.
- Review uncertainty and replicate variation before ranking candidates.

## Repository Contents

- `SKILL.md`: Main skill instructions.
- `reference/`: API, experiment, example, and optimization guides.
- `README.md`: Workflow overview and setup guidance.

## Important Note

This skill supports planning and handling experimental workflows. It does not guarantee assay availability, experimental success, or a specific turnaround time. Confirm current platform access and service details before scheduling work.
