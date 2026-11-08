# EYEAR

Shared documents and system integration for [EYEAR](https://github.com/HY-LG-EYEAR).

## System

```text
Sensor Nodes -> World Model -> Role-Based Agents -> Home Orchestrator
                    ^                                    |
                    +---- Simulated Appliances <---------+
```

The application provides resident preferences, controls, and decision views. Voice requests and replies connect the Orchestrator to the Nodes.

## Components

- [Node](https://github.com/HY-LG-EYEAR/eyear-node) — Banseok Shin
- [World Model and simulation](https://github.com/HY-LG-EYEAR/eyear-worldmodel) — Hyochang Lee
- [Agents and Orchestrator](https://github.com/HY-LG-EYEAR/eyear-orchestrator) — Jungbin Song
- [Application](https://github.com/HY-LG-EYEAR/eyear-app) — Yewon Joung

## Documents

- [Software Engineering Specification — Submission B](docs/SE_G05_EYEAR_B.pdf)
- [LaTeX source](docs/main.tex)

## Team coordination

Cross-component requests and updates are shared in [eyear-team](https://github.com/HY-LG-EYEAR/eyear-team).
