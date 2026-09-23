# Contributing Guide

Welcome! Thank you for taking the time to contribute. This repository is a multi-workspace project encompassing four core technology layers:

1. **Frontend** (Web Interface / UI)
2. **Backend** (API & Services)
3. **Soroban Contracts** (Stellar Smart Contracts)
4. **Noir Circuits** (Zero-Knowledge Proof Circuits)

To keep contributions consistent and high quality, please follow the guidelines below.

---

## 1. Prerequisites & Environment Setup

Ensure you have the following toolchains installed locally before working in any workspace:

| Layer | Dependency | Recommended Version | Verification Command |
| :--- | :--- | :--- | :--- |
| **Frontend & Backend** | Node.js / npm | Node v20.x+ | `node -v` |
| **Soroban Contracts** | Rust & Cargo | Rust 1.78+ | `rustup --version` |
| **Soroban Contracts** | WASM Target | `wasm32-unknown-unknown` | `rustup target list \| grep installed` |
| **Soroban Contracts** | Stellar CLI | Latest | `stellar --version` |
| **Noir Circuits** | Nargo (Noir CLI) | v0.25.0+ | `nargo --version` |

### Installing Toolchain Components

```bash
# Install WASM compilation target for Rust
rustup target add wasm32-unknown-unknown

# Install Stellar CLI for Soroban contract compilation
cargo install --locked stellar-cli

# Install Nargo for Noir ZK circuit compilation
noirup
```


## 2. Workspace Setup, Build, and Test Commands

### 2.1 Workspace Installation
Install root and workspace dependencies:

```bash
npm install
```

## 2.2 Frontend Workspace

```bash
# Build frontend
npm run build --workspace=frontend

# Run linter
npm run lint --workspace=frontend

# Run component/unit tests
npm run test --workspace=frontend

```

## 2.3 Backend Workspace

```bash
# Build backend
npm run build --workspace=backend

# Run unit/integration tests
npm run test --workspace=backend
```

## 2.4 Soroban Smart Contracts (/contracts)

```bash
# Compile contracts to WASM targets
stellar contract build

# Run Rust smart contract unit & integration tests
cargo test

# Check formatting
cargo fmt --check
```

## 2.5 Noir ZK Circuits (/circuits)
```bash
# Compile Noir circuits
nargo compile

# Execute Noir circuit test suite
nargo test
```

## 3. Contributor Workflow Guidelines

### ​3.1 Branch Naming Convention
​Branches must use one of the following standard prefixes:

```bash
​feat/<short-description> — New features or functional enhancements

​fix/<short-description> — Bug fixes or security patches

​docs/<short-description> — Documentation updates and guides

​refactor/<short-description> — Code restructuring without logic changes

​test/<short-description> — Adding or updating unit/integration tests
```

### 3.2 Conventional Commits
​All commit messages must strictly adhere to the Conventional Commits format:
```bash
<type>(<scope>): <short description>

[optional body]
```

## 4. Pull Request Requirements

```bash
Every Pull Request must satisfy the following checklist before being merged:

✅ Closes #N Requirement: The PR description MUST contain Closes #N or Fixes #N (where N is the issue number) to enable automatic issue closing upon merge.

✅ Screenshots Required: If your PR modifies UI layouts, CSS, or component rendering on the Frontend, you MUST attach before/after screenshots or a short GIF.

✅ Security Notes Required: If your PR modifies authentication logic, cryptography/key handling, Soroban contract storage/permissions, or Noir ZK circuit constraints, you MUST include a Security Notes section in your PR description explaining the safety implications.

✅ Test Evidence: Include terminal execution logs or test output showing that all impacted workspace tests pass.
```

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold these standards. 

Please report unacceptable behavior to `conduct@<your-organization-domain>.com`.
# Contributor Covenant Code of Conduct

## Our Pledge

We as members, contributors, and leaders pledge to make participation in our community a harassment-free experience for everyone, regardless of age, body size, visible or invisible disability, ethnicity, sex characteristics, gender identity and expression, level of experience, education, socio-economic status, nationality, personal appearance, race, caste, color, religion, or sexual identity and orientation.

We pledge to act and interact in ways that contribute to an open, welcoming, diverse, inclusive, and healthy community.

## Our Standards

Examples of behavior that contributes to a positive environment for our community include:

* Demonstrating empathy and kindness toward other people
* Being respectful of differing opinions, viewpoints, and experiences
* Giving and gracefully accepting constructive feedback
* Accepting responsibility and apologizing to those affected by our mistakes, and learning from the experience
* Focusing on what is best not just for us as individuals, but for the overall community

Examples of unacceptable behavior include:

* The use of sexualized language or imagery, and sexual attention or advances of any kind
* Trolling, insulting or derogatory comments, and personal or political attacks
* Public or private harassment
* Publishing others' private information, such as a physical or email address, without their explicit permission
* Other conduct which could reasonably be considered inappropriate in a professional setting

## Enforcement Responsibilities

Community leaders are responsible for clarifying and enforcing our standards of acceptable behavior and will take appropriate and fair corrective action in response to any behavior that they deem inappropriate, threatening, offensive, or harmful.

Community leaders have the right and responsibility to remove, edit, or reject comments, commits, code, wiki edits, issues, and other contributions that are not aligned to this Code of Conduct, and will communicate reasons for moderation decisions when appropriate.

## Scope

This Code of Conduct applies within all community spaces, and also applies when an individual is officially representing the community in public spaces. Examples of representing our community include using an official e-mail address, posting via an official social media account, or acting as an appointed representative at an online or offline event.

## Enforcement & Reporting

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported to the project maintainers responsible for enforcement at:

* **Primary Contact:** `conduct@<your-organization-domain>.com`
* **Escalation Contact:** `security@<your-organization-domain>.com`

All complaints will be reviewed and investigated promptly and fairly. All community leaders are obligated to respect the privacy and security of the reporter of any incident.

## Enforcement Guidelines

Community leaders will follow these Community Impact Guidelines in determining the consequences for any action they deem in violation of this Code of Conduct:

### 1. Correction
**Community Impact:** Use of inappropriate language or other behavior deemed unprofessional or unwelcome in the community.
**Consequence:** A private, written warning from community leaders, providing clarity around the nature of the violation and an explanation of why the behavior was inappropriate. An public apology may be requested.

### 2. Warning
**Community Impact:** A violation through a single incident or series of actions.
**Consequence:** A warning with consequences for continued behavior. No interaction with the people involved, including unsolicited interaction with those enforcing the Code of Conduct, for a specified period of time. This includes avoiding interactions in community spaces as well as external channels like social media. Violating these terms may lead to a temporary or permanent ban.

### 3. Temporary Ban
**Community Impact:** A serious violation of community standards, including sustained inappropriate behavior.
**Consequence:** A temporary ban from any sort of interaction or public communication with the community for a specified period of time. No public or private interaction with the people involved, including unsolicited interaction with those enforcing the Code of Conduct, is allowed during this period. Violating these terms may lead to a permanent ban.

### 4. Permanent Ban
**Community Impact:** Demonstrating a pattern of violation of community standards, including sustained inappropriate behavior, harassment of an individual, or demonstration of dislike or disparagement toward classes of individuals.
**Consequence:** A permanent ban from any sort of public interaction within the community.

## Attribution

This Code of Conduct is adapted from the [Contributor Covenant](https://www.contributor-covenant.org), version 2.1, available at [https://www.contributor-covenant.org/version/2/1/code_of_conduct.html](https://www.contributor-covenant.org/version/2/1/code_of_conduct/html).

Community Impact Guidelines were inspired by [Mozilla's code of conduct enforcement ladder](https://github.com/mozilla/diversity).

