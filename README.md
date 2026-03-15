# claude-learn-plugin

> A Socratic tutoring plugin for Claude Code that teaches developers the fundamentals of any codebase — explaining the *why* before the *what*.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Plugin-blue)](https://github.com/anthropics/claude-code)
[![Version](https://img.shields.io/badge/version-1.0.0-green)](CHANGELOG.md)

---

## What This Plugin Does

When you join a new codebase — or return to one you haven't touched in months — understanding it deeply takes time. Most tools describe *what* the code does. This plugin teaches you *why* it exists.

**claude-learn-plugin** turns Claude Code into an interactive Socratic tutor. Instead of passively reading documentation or skimming files, you engage in a guided learning session that builds genuine understanding through questions, analogies, and incremental concept building.

### The Socratic Approach

Rather than dumping information at you, the tutor:
- Asks you questions after each concept to verify understanding
- Waits for your answer before moving forward
- Uses analogies to connect unfamiliar patterns to things you already know
- Explains architectural decisions, not just architectural facts
- Gently redirects misunderstandings with new angles

### Learning Path (via `/learn`)

Every session follows a structured 6-stage path:

| Stage | Topic |
|-------|-------|
| 1 | What problem does this project solve? |
| 2 | High-level architecture and folder structure |
| 3 | Core concepts and patterns used |
| 4 | Key files and their responsibilities |
| 5 | Data flow end to end |
| 6 | How to extend or modify this project |

### Focused Deep Dives (via `/learn-topic`)

Already know the basics? Use `/learn-topic [topic]` to deep-dive into any specific concept:

```
/learn-topic authentication
/learn-topic database layer
/learn-topic event handling
/learn-topic caching strategy
```

---

## Installation

### Option 1 — Install from GitHub (recommended)

```bash
# Step 1: Add the repo as a marketplace source
claude plugin marketplace add osamaatef1/claude-learn-plugin

# Step 2: Install the plugin
claude plugin install claude-learn-plugin@osamaatef1-claude-learn-plugin
```

### Option 2 — Test locally (development / offline)

```bash
git clone https://github.com/osamaatef1/claude-learn-plugin
claude --plugin-dir ./claude-learn-plugin
```

---

## Usage

### Start a full learning session

Navigate to any project and run:

```
/learn
```

Claude will silently analyze your codebase, then begin a guided tutoring session from Stage 1.

### Learn a specific topic

```
/learn-topic authentication
/learn-topic how middleware works
/learn-topic the database schema
```

### Session commands (available at any time)

| Command | Effect |
|---------|--------|
| `skip` | Move to the next topic without answering |
| `hint` | Get a Socratic clue (not the full answer) |
| `back` | Revisit the previous topic |
| `summary` | Get a bullet-point recap of everything covered so far |
| `exit` | End the session with a full summary of key takeaways |

---

## Example Session

```
> /learn

Welcome to your codebase learning session! I've analyzed the project
and I'm ready to guide you through it using a Socratic approach.

---

## Stage 1: What Problem Does This Project Solve?

This project is a task queue processor built with Node.js and Redis.
Before it existed, background jobs had to be handled inline — blocking
HTTP requests while sending emails, generating reports, or calling
third-party APIs. That made APIs slow and unreliable...

[explanation continues]

---

**Check your understanding:**
In your own words, why would you want to process tasks asynchronously
rather than inside the HTTP request handler?

> Because it keeps the API response fast and doesn't make the user wait
> for slow operations like sending email.

Exactly right — and that's the core insight behind every task queue
ever built. Fast responses + reliable background work = better UX and
more resilient systems.

Let's move to Stage 2. 👇
```

---

## Screenshots

> *Screenshots coming soon. Contributions welcome!*

---

## Why Socratic?

The Socratic method has been used to teach since ancient Greece because it works: active recall outperforms passive reading by a wide margin in retention studies. When you have to answer a question — even if you're not sure — your brain encodes the concept more deeply than when you simply read an explanation.

This plugin applies that to code: instead of reading docs, you're tested on understanding. Instead of being told the architecture, you're asked to predict it. The result is faster onboarding and longer-lasting comprehension.

---

## Compatibility

- Works with any language or framework
- Works with any size codebase (from a 3-file script to a large monorepo)
- Requires [Claude Code](https://github.com/anthropics/claude-code) ≥ 1.0.0

---

## Contributing

Contributions are very welcome. Here are some great ways to help:

- **Improve the tutor prompt** — better questions, better analogies, better structure
- **Add new commands** — e.g., `/learn-tests`, `/learn-deploy`, `/learn-security`
- **Add examples** — screenshots or recorded sessions showing the plugin in action
- **Report issues** — if the tutor gives bad explanations for a particular stack, open an issue

### Development setup

```bash
git clone https://github.com/osamaatef1/claude-learn-plugin
cd claude-learn-plugin

# Install locally for testing
claude plugin install .

# Navigate to a test project
cd /path/to/some/other/project
/learn
```

### Submitting changes

1. Fork the repository
2. Create a branch: `git checkout -b feature/your-feature-name`
3. Make your changes
4. Open a pull request with a clear description of what changed and why

---

## License

MIT — see [LICENSE](LICENSE) for details.

---

## Author

Made by [@osamaatef1](https://github.com/osamaatef1)
