# crdc-datahub-static-content

A repository to hold static content for the CRDC Submission Portal (CRDC-DH) project.

## Publishing Process

1. Draft your changes in a feature branch based on the `dev` branch.
2. Submit a pull request targeting the `dev` branch for review and approval.
3. Once approved, merge the pull request to publish the changes to the `dev` environment.
4. Promote changes through LINEAR MERGING PROCESS, ensuring that each environment is updated in sequence (e.g., `dev` → `qa` → `stage` → `prod`).

> [!DANGER]
> Do **not** merge changes directly to higher environments without following the linear merging process.

## Content

- [Release notes](./content/release-notes.md): the complete release history, rendered
  as Markdown by the application's Release Notes page.
- Place future content in separately named files or directories under `content/`.

## Environments

Each application tier reads the same file path from its corresponding GitHub
branch: `dev2` reads `dev2`, `prod` reads `prod`, and so on.

The browser fetches public content directly from:

```text
https://raw.githubusercontent.com/CBIIT/crdc-datahub-static-content/refs/heads/{tier}/content/release-notes.md
```

## Markdown and annotations

Use standard Markdown; the application does not execute raw HTML or MDX.
Front matter and HTML comments are not currently supported as hidden annotations
and can appear as visible text.
