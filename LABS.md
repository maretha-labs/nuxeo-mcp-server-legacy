# Maretha Labs / Hyland collaboration

Maretha partnered with Hyland on Nuxeo MCP. Hyland maintains the canonical repository:
https://github.com/nuxeo/nuxeo-mcp-server.

This Labs fork uses upstream commit `9fca70859deaa45c61465ce7a5ef95baa27e5311` as its
reference implementation.
The `labs` default branch carries the canonical Hyland source and this documentation;
the inherited `main` branch is historical and is not the recommended starting point.

Use Hyland upstream for canonical development and current release information. This fork
is for Maretha examples and collaboration; it is not a competing supported distribution.
Original author history and attribution are preserved. No runtime code changes were made
for the initial Labs release.

## Get started

```bash
git clone --branch labs https://github.com/maretha-labs/nuxeo-mcp-server.git
cd nuxeo-mcp-server
uv sync --frozen --extra dev
uv run nuxeo-mcp --help
```

Configure a least-privilege Nuxeo account and the required transport/authentication before
connecting a client. The upstream README explains the account and tool permissions. Do not
use local-development defaults against production. An exposed HTTP server needs an appropriate
network and client-authentication boundary; a tool being available does not authorize every
user to execute it. No credentials or production data are included in this Labs preparation.

## Validation and maintenance

The source passed 107 tests; 19 integration tests were skipped. The source distribution and wheel built successfully. Upstream static checks remain failing: mypy reports 149 errors in 13 source files; Black would reformat 47 files, and isort reports import-order differences. These baseline findings were not changed as part of the documentation-only Labs preparation. No live Nuxeo or hosted-model
integration was certified. The default-branch workflow triggers are manual only; image-publishing
jobs are disabled in this fork so they cannot publish to Hyland infrastructure. Upstream setup
instructions and scripts remain reference material, not an instruction to deploy to its accounts.

Future upstream changes should be reviewed before integration. See SECURITY.md for reporting.
