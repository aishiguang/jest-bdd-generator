# jest-bdd-generator

A toolkit for bridging Jest unit tests and Gherkin feature files. The SDK provides parsers, generators, and React components that help teams apply behavior-driven development (BDD) without leaving the Jest ecosystem. This monorepo also contains a demo project and documentation website that show the workflows end to end.

## Monorepo layout
- [`packages/sdk`](packages/sdk/README.md) – publishes the `jest-bdd-generator` library and CLIs (`gen-comments`, `gen-test`, `gen-doc`, `gen-report`) used to convert between Jest and Gherkin assets. Includes reusable React UIs such as `TestOracle`, `TestGeneration`, and `TestStory`.
- `packages/demo` – runnable examples that exercise the CLI commands, HTML report generation, and UI widgets against real test suites.
- `packages/website` – Docusaurus documentation site that surfaces SDK docs, tutorials, and API references generated from the source in `packages/sdk/docs`.

Additional build and tooling configuration lives under `common/`, managed by Rush.

## Prerequisites
- Node.js `>=18.20.3 <19` or `>=20.14.0 <21` (matching `rush.json`).
- [PNPM](https://pnpm.io/) is managed automatically by Rush.
- Install Rush globally if you have not already:
  ```bash
  npm install -g @microsoft/rush
  ```

## Install and build
```bash
rush update    # install dependencies via pnpm
rush build     # compile packages respecting the dependency graph
```

Helpful follow-up commands:
- `rush test` – run package test suites (`jest` in the SDK and demo).
- `rush lint` – run ESLint across participating packages.

## Run the demo and docs
- Demo app: `cd packages/demo && pnpm start` to launch the example UI and generate reports with live data.
- Documentation site: `cd packages/website && pnpm start` to spin up the Docusaurus dev server that renders the authored guides.

Refer to the package-level READMEs for additional scenarios, including the `TestOracle` UI used to curate reusable example tables.

## Contributing
1. Create a topic branch and make your changes.
2. Use `rush lint` / `rush test` to validate before opening a PR.
3. Follow the existing conventions; generated API docs live in `packages/sdk/docs`.

This project is released under the MIT License. Contributions and feedback are welcome!
