# YC Portfolio Analytics

Analyzing how Y Combinator's portfolio has changed over time: which sectors and regions YC funds, and what backgrounds its founders bring.

> **Status:** Sprint 0 – Discovery. Questions and data sources are being validated before any pipeline is built.

## Questions

1. **Q1 – Portfolio trends:** How has the sector and geographic mix of YC-funded companies changed across batches?
2. **Q2 – Founder backgrounds:** What educational and professional backgrounds do YC founders have, and has that shifted over time? *(Feasibility under evaluation.)*

Findings, dashboard, and executive summary will appear here once the analysis is complete.

## How this project was run

This project is delivered in 1-week sprints tracked in Jira, with every branch, commit, and pull request tagged with its ticket key (e.g. `YC-7`). Documentation is elaborated sprint by sprint as evidence comes in, rather than fully specified upfront.

- Sprint logs: [`docs/sprints/`](docs/sprints/)
- Decision log: [`docs/decisions.md`](docs/decisions.md)
- Data sources and their limits: [`docs/source_register.md`](docs/source_register.md)

*Board screenshots and a backlog export will be added at the end of each sprint.*

## Repository structure

```
docs/            brief, source register, decisions, sprint logs
data/raw/        downloaded source files (not committed)
data/processed/  cleaned outputs (not committed)
notebooks/       exploration and profiling
sql/             schema and queries
src/             collection and transformation code
```

## Conventions

- Branches: `feature/YC-<n>-short-name`
- Commits: `YC-<n> type: short description` where type is `feat`, `fix`, `refactor`, `chore`, or `docs`
- Pull request titles start with the ticket key

## Data note

Company data comes from [yc-oss/api](https://github.com/yc-oss/api), an **unofficial** mirror of YC's public directory. Y Combinator's Terms of Use prohibit scraping its website, so no automated collection from ycombinator.com is performed. See the source register for details.
