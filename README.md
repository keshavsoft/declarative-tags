# declarative-tags

> **Canonical HTML tag dictionary, attribute taxonomy, and schema validation rules for declarative JSON-to-DOM compilers.**
---
[![LIVE DOCS](https://img.shields.io/badge/LIVE-DOCUMENTATION-blue?style=for-the-badge)](https://keshavsoft.github.io/declarative-tags/)

[![NPM](https://img.shields.io/badge/NPM-PACKAGE-CB3837?style=for-the-badge&logo=npm)](https://www.npmjs.com/package/declarative-tags)

[![GITHUB](https://img.shields.io/badge/GITHUB-REPOSITORY-181717?style=for-the-badge&logo=github)](https://github.com/keshavsoft/declarative-tags)

---
Part of the **KeshavSoft Declarative UI Architecture** (Tier 1: Ground Truth Dictionary).

---

## 📖 The Story

In declarative systems, UI components are built by compiling JSON specifications into DOM nodes. Without a strict ground truth dictionary:
* Compilers cannot validate whether an attribute (like `title`, `placeholder`, or `disabled`) is legally permitted on an element.
* Structural mismatches (like appending invalid children inside void tags like `<input>` or `<col>`) fail silently or produce broken markup.

`declarative-tags` solves this by serving as the authoritative **tag grammar rulebook**:
1. **Allowed Attributes**: Explicit whitelist of valid HTML attributes per element.
2. **Nesting Rules**: Enforces `allowsChildren`, `allowsTextContent`, and allowed `childTags`.
3. **JSON Schema Integrity**: Comes bundled with `tags.schema.json` for editor auto-complete and static validation.

---

## 📦 Installation

```bash
npm install declarative-tags
```

---

## 🚀 Usage

### 1. Import Tag Dictionary in ES Modules

```javascript
import tags, { tagsSchema } from "declarative-tags";

// Inspect tag rules
console.log(tags.input);
// Output:
// {
//   allowsTextContent: false,
//   allowsChildren: false,
//   allowedAttributes: ["type", "placeholder", "value", "name", "disabled", "readonly", "required", "list"]
// }
```

### 2. Import Specific Version

```javascript
import tags from "declarative-tags/v1";
```

### 3. Direct JSON Import

```javascript
import tags from "declarative-tags/tags.json" with { type: "json" };
import schema from "declarative-tags/tags.schema.json" with { type: "json" };
```

---

## 🏛️ Tag Schema Contract

Each tag entry adheres to the following declarative contract:

```json
{
  "table": {
    "allowsTextContent": false,
    "allowsChildren": true,
    "allowedAttributes": [
      "title",
      "role"
    ],
    "childTags": [
      "caption",
      "colgroup",
      "thead",
      "tbody",
      "tfoot",
      "tr"
    ]
  }
}
```

---

## 🌐 Interactive Monaco Studio & Documentation

Explore, search, and validate all tag schemas live directly in your browser:
* **Documentation & Story:** [https://keshavsoft.github.io/declarative-tags/](https://keshavsoft.github.io/declarative-tags/)
* **Monaco Schema Studio:** [https://keshavsoft.github.io/declarative-tags/monaco/v1/](https://keshavsoft.github.io/declarative-tags/monaco/v1/)

---

## 📄 License

MIT © [KeshavSoft](https://github.com/keshavsoft)
