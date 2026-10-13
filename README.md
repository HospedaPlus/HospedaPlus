# HospedaPlus

HospedaPlus is a team project for building a data platform and analytics solution. The repository is organized to keep application code, data pipelines, infrastructure, reporting assets, tests, and project documentation in clearly defined locations.

## Project components

- **Frontend** — user-facing application in `apps/frontend/`.
- **Backend** — API and application services in `apps/backend/`.
- **Airflow** — workflow orchestration and scheduling in `data-pipeline/airflow/`.
- **Spark** — distributed data processing jobs in `data-pipeline/spark/`.
- **AWS infrastructure** — infrastructure configuration and deployment-related assets in `infrastructure/aws/`.
- **Power BI** — reports, dashboards, and related assets in `power-bi/`.
- **Documentation** — architecture and technical decisions in `docs/architecture/` and `docs/decisions/`.
- **Tests** — automated and supporting tests in `tests/`.
- **Scripts** — reusable development and maintenance scripts in `scripts/`.

The folders are initial placeholders. Add component-specific instructions, dependencies, environment variables, and run commands as those components are implemented.

## Repository structure

```text
.
├── apps/
│   ├── frontend/
│   └── backend/
├── data-pipeline/
│   ├── airflow/
│   └── spark/
├── infrastructure/
│   └── aws/
├── power-bi/
├── docs/
│   ├── architecture/
│   └── decisions/
├── tests/
├── scripts/
└── README.md
```

## Getting started

1. Clone the repository.
2. Check out the branch for the task you are working on.
3. Read the relevant component documentation before adding code.
4. Keep credentials and secrets out of Git. Use local environment variables or an approved secrets manager.
5. Create a pull request and request review before merging changes into `main`.

There is not yet a single project-wide install or run command because the application and data-pipeline components are still being established. Add the appropriate commands to the relevant component README as implementation progresses.

## Branching and pull-request guidelines

See [Branching Guidelines](docs/branching-guidelines.md) for branch naming, commit messages, pull-request expectations, and the merge process.

## Team workflow

- Keep changes focused on one task.
- Link pull requests to the relevant Jira issue.
- Do not commit secrets, credentials, local environment files, generated data, or large temporary artifacts.
- Update documentation when project structure, setup, or behavior changes.
