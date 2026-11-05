# ChronoStar Wave Program Issue Plan

ChronoStar participates in The Wave Program by breaking roadmap milestones into well-scoped, self-contained issues for contributors during sprint cycles. Maintainers define clear acceptance criteria, provide setup guides, and review PRs within 48 hours to ensure fast feedback.

## 1. Planned Work Categories

### A. Bug Fixes & Stability
Hardening existing primitives across the protocol:
- **Keeper Resiliency**: Add exponential backoff and retry handling for failed Soroban RPC submissions.
- **Frontend Wallet Disconnect**: Gracefully handle unexpected Freighter session drops and RPC timeouts.
- **Contract Boundary Checks**: Guard against overflow and negative intervals in recurring stream deposits.

### B. New Features
Expanding core protocol functionality:
- **Multi-Asset DCA Policies**: Extend `DCAPolicy` to support arbitrary token pairs via Soroswap AMM pools.
- **Stream Top-Up & Extension**: Allow deposit top-ups and duration extensions on active recurring streams without cancellation.
- **Interactive Stream Visualizer**: Real-time rate-of-flow and remaining balance animation in the frontend dashboard.
- **Webhook Notifications**: Add webhook dispatcher to the backend for stream withdrawals and vault unlocks.

### C. Testing & Quality Assurance
Deepening verification across Rust contracts and services:
- **Contract Property-Based Testing**: Expand `proptest` suites for stream cancellation states and vault unlocking edge cases.
- **End-to-End Test Suite**: Build Playwright automation testing full flows (connect wallet -> deposit -> release).
- **Keeper Mock Simulation**: Sandbox test suite simulating high network congestion and nonce desyncs.

### D. Documentation & Developer Experience
Empowering external developers and integrators:
- **Astro Docs Overhaul**: Add interactive code sandboxes and sequence diagrams for vault and DCA lifecycles.
- **Soroban Integration Guide**: Step-by-step tutorial on triggering ChronoStar contracts from custom contracts.
- **TypeScript SDK Package**: Extract client bindings and type definitions into `@chronostar/sdk`.

### E. Infrastructure & Dev Tooling
Improving developer iteration and CI speed:
- **Local Dev Sandbox Script**: One-line docker-compose / script spinning up local Soroban network and deployed contracts.
- **CI Benchmarks**: Automated gas and WASM size regression tracking on pull requests.

## 2. Sprint Scoping & Contributor Workflow

Issues in The Wave Program follow a standardized lifecycle:
1. **Scoping**: Each issue includes background context, target files/modules, explicit acceptance criteria, and difficulty rating (`Wave: Starter`, `Wave: Intermediate`, `Wave: Advanced`).
2. **Tagging**: Labeled with `wave-program`, `help-wanted`, and domain tags (`contract`, `frontend`, `backend`, `keeper`, `docs`).
3. **Sprint Cycles**: Tasks are assigned during sprint kickoffs with dedicated Discord/GitHub mentorship and office hours.
4. **Review & Merge**: Review turnaround under 48 hours with automated CI checks (linting, tests, WASM build).
