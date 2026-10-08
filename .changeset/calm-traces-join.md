---
'@mastra/mcp': minor
---

Linked MCP calls across traces. When an agent or workflow calls a tool through `MCPClient`, the request now carries the W3C `traceparent` of the tool call span. `MCPServer` keeps its own trace for the request and records a link to that span, so you can follow a tool call to the work the server did for it.

The server reads `traceparent` from the request `_meta`, or from the HTTP `traceparent` header that OpenTelemetry-instrumented callers send. Both traces keep their own root span and summary, so exporters show them as before.
