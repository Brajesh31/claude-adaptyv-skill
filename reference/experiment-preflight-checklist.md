# Adaptyv Experiment Preflight Checklist

Complete this checklist before submitting an experiment request. Confirm platform details against the current account and API contract.

## Experimental objective

- [ ] The scientific question is stated in one or two sentences.
- [ ] The measured outcome can answer the question.
- [ ] The assay type matches the objective.
- [ ] Success criteria and decision thresholds are defined.
- [ ] Required controls and replicates are planned.

## Candidate inputs

- [ ] Each candidate has a stable, unique identifier.
- [ ] Sequences use the accepted amino-acid alphabet.
- [ ] Sequence formatting matches the endpoint contract.
- [ ] Placeholder text, ellipses, and unintended whitespace are removed.
- [ ] Candidate metadata matches the sequence file.
- [ ] Input sequence records are saved in a versioned, read-only location.

## Assay configuration

- [ ] Target identifiers are validated where required.
- [ ] Method and experiment type are compatible.
- [ ] Concentrations and units are checked.
- [ ] Replicate count is valid for the selected experiment type.
- [ ] Controls are included where required.
- [ ] Optional parameters are supported by the current API schema.
- [ ] No unsupported fields are included.

## Account and authorization

- [ ] API token is set in an environment variable or secret manager.
- [ ] Token belongs to the intended organization.
- [ ] Token permissions are sufficient and no broader than needed.
- [ ] Request is being submitted under the correct account.
- [ ] Submission is explicitly approved.
- [ ] Cost estimate and budget are reviewed before proceeding.

## Request reliability

- [ ] Base URL and endpoint are current.
- [ ] Payload is validated before network submission.
- [ ] Timeout and error handling are configured.
- [ ] Request ID and experiment ID will be recorded.
- [ ] Retry behavior will not create duplicate experiments.
- [ ] Webhook or polling behavior is understood.

## Data management

- [ ] Raw inputs and submitted payload are archived.
- [ ] Experiment metadata and candidate mapping are recorded.
- [ ] Sensitive sequence and result data are stored appropriately.
- [ ] No token or secret is written to logs or reports.
- [ ] Result ownership and retention expectations are understood.

## Approval record

- Request owner:
- Experiment identifier, once returned:
- Approval reference:
- Estimated cost and currency:
- Submission date:
- Notes:
