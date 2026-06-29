<p align="center">
  <img src="assets/banner.png" alt="ReadmeVerity — Agent Skill" width="560">
</p>

Agent Skill for human-friendly README files.

For Claude Code and Codex that writes, rewrites, and audits a repository README against the actual state of the repository, rather than from a fixed documentation template.

The skill is built around one rule: every claim in the README must be supported by the repository itself — its files, code, configuration, tests, license, or output the user supplies. When a fact is missing, ReadmeVerity omits it or marks it for the user instead of inventing a plausible command, number, output, compatibility promise, or license.

The skill is plain Markdown. `SKILL.md` carries the instructions; the rest is reference material the agent reads on demand:

- `references/principles.md` — the recurring README patterns the skill reproduces.
- `references/process.md` — the step-by-step procedure for writing, rewriting, and auditing.
- `references/style.md` — tone and formatting guidance.
- `templates/readme-outline.md` — a composition aid, not a mandatory section list.
- `examples/compact-example.md` — a reference for the intended density and flow.

## Install

Download the `v1.0.0` release archive and its checksum, verify it, then unzip it into the agent's skills directory.

```bash
curl -L -O https://github.com/KazKozDev/readmeverity/releases/download/v1.0.0/readmeverity-v1.0.0.zip
curl -L -O https://github.com/KazKozDev/readmeverity/releases/download/v1.0.0/readmeverity-v1.0.0.zip.sha256
shasum -a 256 -c readmeverity-v1.0.0.zip.sha256
```

The checksum command confirms the archive is intact:

```text
readmeverity-v1.0.0.zip: OK
```

Install for Claude Code:

```bash
mkdir -p ~/.claude/skills
unzip readmeverity-v1.0.0.zip -d ~/.claude/skills
```

Install for Codex:

```bash
mkdir -p ~/.codex/skills
unzip readmeverity-v1.0.0.zip -d ~/.codex/skills
```

Either command installs the skill as `<skills-dir>/readmeverity/SKILL.md`. Restart the agent if the skill does not appear immediately.

## Use

Invoke the skill, then state the task. Create a README from the current repository:

```text
$readmeverity

Write a README for this repository.
```

Rewrite an existing README from current repository evidence:

```text
$readmeverity

Rewrite README.md from the current repository state. Preserve only verified facts, useful assets, limitations, and license information.
```

Audit a README without modifying files:

```text
$readmeverity

Audit README.md against the repository. Report blocking, structural, evidentiary, and stylistic problems with concrete fixes.
```

## What it checks

While writing or auditing, ReadmeVerity tests whether important README claims are supported by accessible evidence:

- install, build, test, and run commands;
- scripts, paths, entry points, and task-runner targets;
- observable success signals and example output;
- runtime, hardware, model, and benchmark conditions;
- local links, placeholders, and referenced files;
- project status, limitations, compatibility, and license text.

Existing README text is treated as evidence of intent, not proof of current behavior.

## How it classifies evidence

Every important claim is sorted into one of four states:

- **Executed** — observed in the current environment.
- **Grounded** — supported by repository files such as manifests, CI, tests, source, or license text.
- **Assembled** — composed from grounded pieces but not run end to end.
- **Unverified** — unsupported by accessible evidence and not publishable as fact.

When evidence is incomplete, ReadmeVerity narrows the claim, labels it for verification, or leaves it out.

## Limitations

- The skill reasons over accessible evidence and cannot prove that every documented command succeeds.
- Monorepos may require selecting the relevant package root before inspection.
- License detection recognizes common full-text licenses and treats custom texts cautiously.
- Benchmark-context checks are heuristic and still require human judgment.

## License

ReadmeVerity is released under the [MIT License](LICENSE).
