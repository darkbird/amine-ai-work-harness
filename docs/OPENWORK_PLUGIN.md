# OpenWork Plugin Format

This repository uses the Agent Plugin manifest supported by current OpenWork GitHub discovery:

```text
plugin.json
skills/
```

The root `plugin.json` declares the Agent Plugin schema:

```json
{
  "$schema": "https://agent-plugins.org/schemas/1.0.0/plugin.schema.json"
}
```

There is deliberately no `.claude-plugin/` directory in this version.

The package is OpenWork-first while remaining based on the cross-agent Agent Plugin standard that OpenWork supports.
