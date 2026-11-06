# EYEAR System Integration

Eyes and Ears for Proactive Smart Home Orchestration through Spatial Awareness and Multi-Agent Collaboration

This is the shared integration entry point. It owns cross-module contracts, scenario fixtures, compatible component versions, and end-to-end verification. Perception, World Model, Orchestrator, and application source code remain in their owner repositories.

> Status: repository scaffold and implementation plan. This upload kit does not contain runnable services, approved new contracts, trained models, or measured results. Preserve existing implementation files when adding this scaffold.

> Independent academic prototype. EYEAR is not an official LG Electronics product. The course prototype does not modify ThinQ ON firmware, integrate with the production ThinQ application, or control physical LG appliances.

## Component map

| Repository | Owner | Responsibility |
| --- | --- | --- |
| [.github](https://github.com/HY-LG-EYEAR/.github) | Shared | Organization profile and repository navigation |
| [LG-EYEAR](https://github.com/HY-LG-EYEAR/LG-EYEAR) | Shared | Integration, shared contracts, scenario fixtures, and reproducible demo configuration |
| [eyear-node](https://github.com/HY-LG-EYEAR/eyear-node) | Banseok Shin | Local perception, sensor fusion, speech input/output, and semantic event publishing |
| [eyear-worldmodel](https://github.com/HY-LG-EYEAR/eyear-worldmodel) | Hyochang Lee | Whole-home state fusion, virtual appliances, and home simulation |
| [eyear-orchestrator](https://github.com/HY-LG-EYEAR/eyear-orchestrator) | Jungbin Song | Four agents, central arbitration, policy validation, dialogue, and agent experiments |
| [eyear-app](https://github.com/HY-LG-EYEAR/eyear-app) | Yewon Joung | Next.js frontend and Spring Boot application backend |
| [LG-EYEAR-docs](https://github.com/HY-LG-EYEAR/LG-EYEAR-docs) | Shared | CSE406 IEEE LaTeX sources and software engineering deliverables |
| [LG-EYEAR-blog](https://github.com/HY-LG-EYEAR/LG-EYEAR-blog) | Shared | ITE351 datasets, methodology, evaluation, and technical blog |

## Integration flow

```text
eyear-node -> World Model -> Orchestrator -> virtual appliance adapter
                 ^                              |
                 +------- execution feedback ---+
eyear-app (Next.js + Spring Boot) <-> Orchestrator
Orchestrator <-> Node voice I/O
```

Node-to-World messaging is planned over MQTT. World-to-Orchestrator transport is planned as a local HTTP interface. Exact routes, topics, coordinate conventions, and new contract versions require owner agreement. The previous WorldSnapshot 1.0 contract does not fully represent the new demonstration.

## Repository contents

| Path | Purpose |
| --- | --- |
| `contracts/` | Contract inventory, schema publication rules, and validation examples |
| `scenarios/` | The evening scenario and expected actions |
| `integration-tests/` | Cross-service acceptance cases |
| `scripts/` | Reserved for verified startup, shutdown, and health-check scripts |
| `deploy/` | Reserved for tested deployment configuration |
| `docs/` | Architecture and integration procedures |
| `components.lock.json` | Intended component URLs; exact versions are not yet selected |

## Getting started

1. Read [the architecture](docs/architecture.md) and [integration procedure](docs/integration-guide.md).
2. Agree on a contract release using [the contract inventory](contracts/README.md).
3. Check out compatible component revisions; null revisions in the manifest mean integration is not yet reproducible.
4. Follow each component's verified setup instructions, then add the tested integration commands here.
5. Run the evening scenario and record actual versus expected results.

No one-command launcher or container deployment is included yet. Do not present proposed paths as working commands. Integrate first with mocks and replace them one at a time; do not defer integration until the final presentation week.

## Demonstration and acceptance

The [evening scenario](scenarios/evening.json) covers the t0-t7 narrative. It is an authored fixture, not a Node event or WorldSnapshot payload. An adapter must translate it using approved contracts. See [acceptance cases](integration-tests/README.md).

## Contract and version policy

Publish reviewed JSON Schema and matching examples together. Python models may be the authoring source; Java and TypeScript consumers must validate the same contract and cases. Do not load schema files from a moving GitHub branch at runtime. Pin a contract release and component revision in each demonstrated build.

## Course materials

- [CSE406 sources and submissions](https://github.com/HY-LG-EYEAR/LG-EYEAR-docs)
- [ITE351 datasets, methods, and evaluation](https://github.com/HY-LG-EYEAR/LG-EYEAR-blog)
