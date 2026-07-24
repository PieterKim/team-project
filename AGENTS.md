# Repository Guidelines

## Project Structure & Module Organization

This repository is currently in the requirements and MVP-planning phase. The repository root contains contributor guidance, while `docs/requirements.md` defines the document-analysis and summarization service, its MVP scope, functional requirements, and acceptance scenarios. As implementation is added, keep runtime code under a clearly named source directory (for example, `src/`), tests under `tests/`, and reusable fixtures or sample documents under `tests/fixtures/`. Keep design notes and requirement updates in `docs/`.

## Build, Test, and Development Commands

No build system, package manifest, or test runner is configured yet. Before adding implementation, document the chosen toolchain and expose standard commands such as:

```text
npm install       # install dependencies
npm run dev       # start the local development server
npm test          # run the automated test suite
npm run lint      # check formatting and static analysis
```

Use the project's actual commands once the stack is selected, and update this guide whenever they change.

## Coding Style & Naming Conventions

Follow the formatter and linter selected for the implementation language; do not introduce competing style rules. Use two spaces for JSON/YAML and the language's standard indentation for source code. Prefer descriptive names: `camelCase` for JavaScript/TypeScript variables and functions, `PascalCase` for types and components, and `kebab-case` for document or route names. Keep file extraction, AI analysis, and result formatting as separate modules so each can be tested independently.

## Testing Guidelines

Tests should cover PDF/TXT validation, text extraction failures, AI/API failures, summary options, result rendering, copying, and Markdown/TXT downloads. Use descriptive names such as `document-upload.invalid-extension.test.*` and keep fixtures free of secrets or personal data. Every new feature should include a happy path and relevant error cases; record manual checks when automation is not yet available.

## Commit & Pull Request Guidelines

Use concise, imperative commit subjects with a clear scope, following the existing history's style (for example, `docs: add project requirements`). Pull requests should explain the user-facing or documentation change, list affected files, link the relevant requirement or issue, and include screenshots or manual verification steps for UI behavior. Keep unrelated refactors out of the same PR.

## Security & Configuration Tips

Never commit API keys, tokens, uploaded documents, or real personal information. Read secrets from environment variables and provide only placeholder names in `.env.example`. Do not log raw document contents or API credentials; sanitize errors and outputs before displaying them.
