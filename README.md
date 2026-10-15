# POPA Recon

Research public web3 projects, protocols, tokens, wallets, transactions and market events, with factual answers and cited sources. No investment advice, price predictions, trades or transfers.

This standalone Cursor-format plugin connects to the public MCP endpoint at https://poparecon.com/mcp. No account, API key, secret, local executable or installation dependency is required. Do not submit secrets or sensitive personal information.

## Tools and review steps

1. Connect using the root `mcp.json`. Initialize MCP with protocol `2025-03-26` and list tools. The server exposes `research` and `answer`, both without authentication.
2. For a functional review, call `research` once with a factual question such as `What is Hyperliquid?`. Questions must contain 1–1000 characters. This starts research and may consume service resources.
3. If the result is pending, call `answer` with the returned 43-character `request_id` receipt until it is done or failed. Do not start another research request to retrieve a pending answer. `answer` reads the saved request without starting research.
4. A finished result contains the answer and source links. A failed result is not a completed answer; report the failure without claiming success.

Package validation reused existing live initialization and tool-list evidence; it did not start a research request. End-to-end research completion and marketplace installation were not tested for this release.

- Website: https://poparecon.com
- Privacy: https://poparecon.com/policy
- Terms: https://poparecon.com/terms
- Support: https://poparecon.com/support

## Package format

The manifest is `.cursor-plugin/plugin.json`; Cursor discovers `mcp.json` at the package root and infers remote transport from `url`. The logo is the existing POPA Recon artwork composited onto a solid dark purple backplate, saved as an opaque 512 × 512 RGB PNG.

Format reference: https://cursor.com/docs/reference/plugins
