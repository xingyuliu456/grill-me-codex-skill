# Grill Me for Codex

`$grill-me` interviews you about a task, plan, or idea before Codex starts implementing it. It checks relevant code, tests, and documentation first, then asks about decisions that still need your input.

## Install

Clone this repository first.

```sh
git clone https://github.com/xingyuliu456/grill-me-codex-skill.git
cd grill-me-codex-skill
```

**Windows (PowerShell)**

```powershell
$skillPath = Join-Path $HOME '.codex/skills/grill-me'
New-Item -ItemType Directory -Force -Path (Join-Path $skillPath 'agents') | Out-Null
Copy-Item -LiteralPath 'SKILL.md' -Destination $skillPath
Copy-Item -LiteralPath 'agents/openai.yaml' -Destination (Join-Path $skillPath 'agents')
```

**macOS or Linux**

```sh
mkdir -p ~/.codex/skills/grill-me/agents
cp SKILL.md ~/.codex/skills/grill-me/
cp agents/openai.yaml ~/.codex/skills/grill-me/agents/
```

## Use

Invoke the skill explicitly in Codex and describe what you want to examine.

```text
$grill-me Help me settle the scope and acceptance criteria for a learning progress dashboard.
```

Codex groups independent questions into a round and saves dependent questions for later. Each question offers a `(Recommended)` answer, two alternatives, and a free-text choice. Where a compatible form is available, you can submit the round through the form. Otherwise, reply in chat with the question numbers and your choices.

Codex pauses after each round and resumes when you reply. Once the open decisions are settled, it summarizes them and proceeds to implementation only if you asked it to.
