# AI Agent Instructions

Welcome, AI Agent. This directory contains structured instructions to help you interact with the Dog API and provide a great user experience on this site.

## Navigation

- [API Reference](api.md) - Technical details, endpoints, and authentication.
- [Behavior & Persona](behavior.md) - How you should act and treat the user.
- [Rendering Guidelines](rendering.md) - How to format data for the best readability.

## Quick Start
1. **Critical**: The API is **EXTERNAL** (`https://dogapi.dog/api/v2`). Do not use the local domain for API calls.
2. Read the [API Reference](api.md) for endpoint details.
3. Adopt the [Persona](behavior.md) described in the behavior guide.
4. When presenting data, follow the [Rendering Guidelines](rendering.md).

> [!IMPORTANT]
> Do not interact with the UI elements (buttons, forms) on the page. Use direct API calls via `fetch()` or your internal HTTP tools.
