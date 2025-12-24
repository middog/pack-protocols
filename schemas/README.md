---
title: Schemas
version: 1.0.0
tags:
  - json-schema
  - automation
  - api
  - machine-readable
---

# 📐 Schemas

**Machine-Readable Framework Definitions**

*~organizing for the robot pack members~* 🤖🐕

This directory contains JSON Schema definitions for key Pack Protocol frameworks. These enable:

- **Automation** — Build tools that work with our frameworks
- **Validation** — Ensure data conforms to expected structure
- **AI Integration** — LLMs can work with structured data
- **Interoperability** — Exchange data between systems

---

## Available Schemas

| Schema | Description | Use Case |
|--------|-------------|----------|
| [fire-triangle.schema.json](fire-triangle.schema.json) | Fire Triangle assessment | Organizational momentum diagnosis |
| [pack-dynamics.schema.json](pack-dynamics.schema.json) | Pack Dynamics assessment | Team state sensing |

---

## Usage

### Validation (JavaScript)

```javascript
import Ajv from 'ajv';
const ajv = new Ajv();

const schema = require('./fire-triangle.schema.json');
const validate = ajv.compile(schema);

const assessment = {
  assessment_id: "ft-2024-001",
  organization: "Example Corp",
  date: "2024-12-24",
  fuel: { score: 3, observations: "Good resources, some gaps" },
  oxygen: { score: 2, observations: "Process blockers identified" },
  heat: { score: 4, observations: "Team is engaged" }
};

if (validate(assessment)) {
  console.log("Valid assessment!");
} else {
  console.log("Invalid:", validate.errors);
}
```

### With LLMs

Include schema in prompts for structured output:

```
Conduct a Fire Triangle assessment for [organization].
Output as JSON conforming to this schema:
[include schema]
```

---

## Contributing Schemas

When adding new schemas:

1. Use JSON Schema draft-07
2. Include `$id` with mid.dog namespace
3. Add clear descriptions
4. Document in this README
5. Provide usage examples

---

## Future Schemas

Planned additions:
- `engagement.schema.json` — Client engagement tracking
- `growth-path.schema.json` — Project → Party → Practice assessment
- `compliance-control.schema.json` — NIST control status

---

*~structured data for structured thinking~* 📐🐕
