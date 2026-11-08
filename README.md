# Adaptyv Skill

A practical skill for organizing protein-testing and experimental-validation workflows with the Adaptyv cloud laboratory platform. It covers request preparation, API authentication, supported assay workflows, experiment tracking, result retrieval, and protein-candidate review.

The skill connects computational protein design with experimental measurement. Predicted properties and measured experimental results must remain clearly separated.

## What This Skill Covers

- Preparing protein sequences and candidate metadata.
- Setting up API authentication safely.
- Understanding the experiment submission workflow.
- Working with binding, expression, thermostability, and enzyme-activity assays.
- Tracking experiment identifiers and status.
- Retrieving and reviewing experimental outputs.
- Comparing candidates and planning follow-up experiments.
- Using computational predictors to prioritize candidates before laboratory testing.

## When to Use It

Use this skill when preparing a protein-validation request, organizing experiments, submitting an authorized request through the platform API, checking experiment status, retrieving results, or planning a follow-up based on measured evidence.

It does not replace scientific review, experimental design review, or the platform's current API documentation.

## Installation

~~~bash
git clone https://github.com/Brajesh31/claude-adaptyv-skill.git ~/.claude/skills/adaptyv
~~~

The skill's Python examples use `requests` and `python-dotenv`. Install dependencies in an isolated project environment:

~~~bash
uv pip install requests python-dotenv
~~~

## Authentication Setup

The API requires an access token. Set it in the environment rather than placing secrets in source files.

Linux or macOS:

~~~bash
export ADAPTYV_API_KEY="your_api_key_here"
~~~

Windows PowerShell:

~~~powershell
$env:ADAPTYV_API_KEY = "your_api_key_here"
~~~

For local development, a `.env` file can be used if it is excluded from version control. Never commit real credentials, print them in logs, or include them in experiment reports.

## Invocation

~~~text
/adaptyv
~~~

Provide the experiment objective, sequence format, candidate identifiers, assay type, target information where applicable, replicate requirements, and any budget or timing constraints.

## Recommended Workflow

### 1. Define the scientific question

State what property or interaction is being evaluated and how the measurement will inform the next decision.

### 2. Validate candidate inputs

Check sequence formatting, identifiers, sequence alphabet, metadata, and candidate-to-result mapping. Keep an immutable copy of submitted inputs.

### 3. Confirm assay suitability

Select an assay that matches the question. Confirm required target information, controls, replicates, concentration settings, and any platform-specific constraints.

### 4. Prepare the request

Assemble the exact experiment payload. Review all candidate records and assay parameters before submitting.

### 5. Submit with explicit approval

Confirm the authenticated account, intended organization, experiment type, candidate list, and any potential costs. Do not automate submission or billing confirmation without explicit approval.

### 6. Track status

Store the returned experiment identifier. Track status and completion independently from local job state. Do not assume a submission is complete because the API accepted the request.

### 7. Retrieve and validate results

Check that results are complete, preserve raw outputs, and validate units and candidate identifiers. Missing or unresolved measurements must not be treated as zero or a negative result.

### 8. Interpret and plan follow-up

Compare results against the original hypothesis, assess replicate variation and uncertainty, and decide whether to iterate, redesign, or stop.

## Included Reference Files

The repository already includes the four reference files used by this skill:

| File | Purpose |
|---|---|
| [API reference](reference/api_reference.md) | Authentication, endpoint structure, requests, and responses |
| [Examples](reference/examples.md) | Example setup, submission, tracking, and retrieval workflows |
| [Experiment types](reference/experiments.md) | Assay overview and experiment planning |
| [Protein optimization](reference/protein_optimization.md) | Computational screening and sequence-quality considerations |
| [Preflight checklist](reference/experiment-preflight-checklist.md) | Additional request validation before submission |
| [Results review template](reference/results-review-template.md) | Structured review of returned experiment data |

## Data and Result Quality

- Keep candidate IDs consistent across input files, requests, and results.
- Preserve the submitted sequence and metadata.
- Record assay conditions and platform parameters.
- Distinguish predicted properties from measured values.
- Preserve raw outputs before transforming or normalizing data.
- Record units, replicate counts, and missing measurements.
- Review uncertainty and replicate variation before ranking candidates.
- Do not infer a failed experiment from a missing result without checking status.

## Security and Reliability

- Store API tokens in environment variables or a secret manager.
- Exclude local credential files from version control.
- Use least-privilege account access.
- Review experiment cost and request parameters before submission.
- Avoid automatic quote or payment confirmation unless the user explicitly approves it.
- Handle network timeouts without blindly repeating potentially non-idempotent submissions.
- Protect experiment data and sequence information according to the project's data policy.

## Limitations

Platform access, available assays, API behavior, pricing, and turnaround times can change. Confirm current details with the platform before submitting an experiment. Example requests are starting points and must be checked against the account's current API contract.

Experimental results are evidence for a specific construct, assay setup, and set of conditions. They are not universal guarantees of protein behavior. Review assay quality and scientific context before drawing conclusions.

## Repository Structure

~~~text
claude-adaptyv-skill/
├── SKILL.md
├── README.md
├── LICENSE
└── reference/
    ├── api_reference.md
    ├── examples.md
    ├── experiments.md
    ├── protein_optimization.md
    ├── experiment-preflight-checklist.md
    └── results-review-template.md
~~~

## License

Released under the MIT License. Copyright (c) 2026 Brajesh Kumar. See the root `LICENSE` file for the complete terms.
