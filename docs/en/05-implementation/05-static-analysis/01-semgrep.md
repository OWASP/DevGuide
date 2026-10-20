# Semgrep

## What is Semgrep?

- Semgrep CE is an open source tool that performs static analysis on source code.
- It uses rules that detect patterns that represent insecure code.
- It can use community rules or custom rules.
- You can execute it locally through CLI commands and Semgrep can be part of the development workflow.

## Why use Semgrep?

- It provides an accessible way to start using SAST.
- Semgrep can run fast scans during development stages.
- It has community-provided rules.
- You can create your own rules for specific needs.
- Semgrep can be integrated with your IDE, CI/CD and other workflows.
- It helps to find problems early before they reach production.

## Getting started

### Step 1 - Install Semgrep Community Edition.

On macOS, Semgrep CE can be installed using Homebrew:

```bash
brew install semgrep
```

On Linux or Windows environments with Python:

```bash
python3 -m pip install semgrep
```

### Step 2 - Run a scan from the command line.

To scan the current project using community rules:

```bash
semgrep --config=auto
```

Semgrep can also scan a specific file:

```bash
semgrep --config=auto VulnerableExample.java
```

To use a specific local rule, you can create a `semgrep.yml` file in the root of your project:

```bash
semgrep --config=semgrep.yml VulnerableExample.java
```

### Step 3 - Review the findings.
Semgrep reports matches found by the configured rules. Each finding should be reviewed to determine whether it represents a real security issue.

## Rules and patterns

- A rule defines what Semgrep should look for in the code.
- A rule can contain one or more patterns.
- A pattern represents a code structure or behavior that Semgrep attempts to identify.
- Rules can detect dangerous function calls, insecure patterns, or specific data flows.
- You can use community-contributed rules or create your own.
- When code matches a rule, Semgrep generates a finding.
- A match—or finding—does not automatically mean that an actual vulnerability exists; it must be reviewed.

### Example

```yaml
rules:
  - id: java-runtime-exec
    languages:
      - java
    message: Potential command execution using Runtime.exec
    severity: WARNING
    pattern: Runtime.getRuntime().exec($COMMAND)
```

- `id` identifies the rule.
- `languages` limits the language analyzed.
- `pattern` defines the structure to be searched for.
- `$COMMAND` acts as a metavariable and can represent an expression.
- If Semgrep finds a match, it generates a `finding`.

## Taint analysis

- Taint analysis tracks the flow of untrusted data through code.
- This flow is typically modeled as: source → propagation → sink.
- A `source` is the point where untrusted data enters—for example, an HTTP parameter.
- `propagation` represents how that data moves through variables, methods, or expressions.
- A `sink` is a sensitive or dangerous operation, such as executing a command or constructing an insecure query.
- Semgrep can use rules in "taint mode" to detect when untrusted data reaches a sink.
- A `sanitizer` is something that the rule recognizes as a validation or transformation that makes the data safe for this context.
- The result is a `finding` that requires review; it is not an automatically confirmed vulnerability.

### Example

```text
request.getParameter(...)
      ↓
    command
      ↓
Runtime.getRuntime().exec(...)
```

## Development workflow integration

- It can be integrated into events such as pushes or pull requests.
- It can also be executed within CI/CD pipelines.
- Running it early helps detect findings before later stages.
- Teams can define policies to determine which findings require review and which should block the pipeline.
- Not all findings should automatically block the workflow.
- This integration helps provide faster feedback to developers.

## Limitations

- Semgrep relies on configured rules; if a rule does not cover a specific pattern, it may fail to detect it.
- It may produce false positives.
- It may produce false negatives.
- Complex data flows, frameworks, reflection, generated code, or dynamic behavior can complicate analysis.
- A finding requires human review and context.
- Semgrep CE is not a substitute for manual review, DAST, SCA, or other security practices.

## References

- [Semgrep Community Edition](https://semgrep.dev/products/community-edition/)
- [Semgrep - Demystifying Taint Mode](https://semgrep.dev/blog/2022/demystifying-taint-mode/)
- [Semgrep - Writing Semgrep Rules](https://semgrep.dev/blog/2020/writing-semgrep-rules-a-methodology/)
- [Semgrep - Important updates to Semgrep OSS](https://semgrep.dev/blog/2024/important-updates-to-semgrep-oss/)
