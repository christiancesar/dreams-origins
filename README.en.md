# Dreams Origins

This repository gathers the original project from my Bachelor's thesis (Information Systems, UFR, 2022), **"Microservices Architecture: Projects, Patterns and Principles"** (originally in Portuguese).

The thesis builds the same travel-package booking application twice, once as a monolith and once as microservices, and compares both using DDD, hexagonal architecture, SOLID principles and design patterns.

The full thesis (in Portuguese) is available as a PDF: [docs/TCC-Christian-Cesar-2022-Arquitetura-de-Microsservicos.pdf](docs/TCC-Christian-Cesar-2022-Arquitetura-de-Microsservicos.pdf)

Portuguese version: [README.md](README.md)

## What this repository contains

This is a central repository that points, through `git submodule`, to the independent repositories of the project. Each submodule has its own history, README and run instructions.

| Repository | Role in the thesis | Architecture |
|---|---|---|
| [dreams-project-monolith](dreams-project-monolith) | Monolithic implementation of the application, with hexagonal architecture | Monolith (REST API) |
| [dreams-project-microservices](dreams-project-microservices) | Same application split into microservices with an API Gateway and gRPC | Microservices |
| [dreams-proto-sharing](dreams-proto-sharing) | Shared `.proto` contracts used by the microservices, published to npm | Contract library |

## Suggested reading order

1. Read the thesis PDF, especially sections 2 (literature review) and 3 (methodology and development).
2. Look at the monolith in `dreams-project-monolith` to see the domain and the module layout.
3. Look at the microservices in `dreams-project-microservices`, together with the contracts in `dreams-proto-sharing`.

## How to clone

```bash
git clone --recurse-submodules git@github.com:christiancesar/dreams-origins.git
```

If you cloned without the flag, run:

```bash
git submodule update --init --recursive
```

## Note on running the projects

The projects depend on:

- **MongoDB Atlas** for persistence (Prisma with MongoDB).
- **Amadeus API credentials** (`AMADEUS_CLIENT_ID` and `AMADEUS_CLIENT_SECRET`) for flight and hotel offer search.

The Amadeus Self-Service program, used during the thesis, was shut down in July 2026. Without Enterprise access, the external offer search routes do not work. The rest, such as user registration, persistence and inter-service communication, still runs on the project's own data. Each project README gives the details.

These projects were written in 2022 as an academic proof of concept and are not production-ready.

## Author

Christian Cesar Rodrigues Santos.
Advisor: Prof. Dr. Maikon Adiles Fernandez Bueno. Co-advisor: Prof. Dr. Mara Andréa Dota.
