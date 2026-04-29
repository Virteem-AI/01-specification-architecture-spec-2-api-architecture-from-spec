# Exercise Guide - SPEC-2

## Goal

Create a technical design from the TaskFlow API specification.

## Steps

1. Open Copilot Chat in Plan Mode.
2. Attach or paste `repo/spec-reference.md`.
3. Ask Copilot:

```text
Based on this spec, propose the module structure, route definitions and validation approach.
Do not generate code yet. Produce a design document.
```

4. Ask Copilot to write an ADR for the decision: "single-file Flask application with in-memory storage".
5. Ask Copilot to generate a Mermaid sequence diagram for `POST /tasks`.
6. Review the design and ask for production limitations.
7. Save the result in `repo/design.md`.

## Expected Output

`repo/design.md` should include:

- File structure.
- Endpoint table.
- Validation approach.
- Error strategy.
- At least one ADR.
- One Mermaid sequence diagram.

## Completion Criteria

The design should be clear enough for a developer or agent to implement the API without additional specification questions.
