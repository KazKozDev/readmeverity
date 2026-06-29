<p align="center">
  <img src="assets/banner.png" alt="ReadmeVerity — Agent Skill" width="560">
</p>

ReadmeVerity is an Agent Skill that writes, rewrites, and audits README files against the actual state of a repository.

It turns manifests, source code, task runners, tests, CI workflows, licenses, existing documentation, and observed command output into a README that helps a reader understand the project, run it successfully, verify the result, and find the important code.

Unlike template-first generators, ReadmeVerity omits or labels claims that the repository cannot support. It does not invent commands, benchmark numbers, compatibility promises, output, or license information.

## Quick start

Install the published `v1.0.0` skill for Codex:

```bash
curl -L -O https://github.com/KazKozDev/readmeverity/releases/download/v1.0.0/readmeverity-v1.0.0.zip
curl -L -O https://github.com/KazKozDev/readmeverity/releases/download/v1.0.0/readmeverity-v1.0.0.zip.sha256
shasum -a 256 -c readmeverity-v1.0.0.zip.sha256
mkdir -p ~/.codex/skills
unzip readmeverity-v1.0.0.zip -d ~/.codex/skills
```

The checksum verifies the release archive. The final command installs the skill as `~/.codex/skills/readmeverity`.

For Claude Code, install the same archive into `~/.claude/skills`:

```bash
mkdir -p ~/.claude/skills
unzip readmeverity-v1.0.0.zip -d ~/.claude/skills
```

Restart the agent if the skill does not appear immediately.

## Use

Create a README from the current repository:

```text
$readmeverity

Write a README for this repository.
```

Rewrite an existing README from current repository evidence:

```text
$readmeverity

Rewrite README.md from the current repository state. Preserve only verified facts, useful assets, limitations, and license information.
```

Audit without modifying files:

```text
$readmeverity

Audit README.md against the repository. Report blocking, structural, evidentiary, and stylistic problems with concrete fixes.
```

## What it verifies

ReadmeVerity checks whether important README claims are supported by accessible evidence:

- install, build, test, and run commands;
- scripts, paths, entry points, and task-runner targets;
- observable success signals and example output;
- runtime, hardware, model, and benchmark conditions;
- local links, placeholders, and referenced files;
- project status, limitations, compatibility, and license text.

Existing README text is treated as evidence of intent, not proof of current behavior.

## How it works

1. Inspect the repository and collect candidate evidence.
2. Classify important claims as **executed**, **grounded**, **assembled**, or **unverified**.
3. Select the shortest meaningful path to a working result.
4. Write around the command, its effect, the observable result, key files, limitations, and license.
5. Validate the draft against the repository.
6. Apply a reader test: what is this, what should I run, what proves it worked, where is the logic, and what assumptions matter?

## Evidence states

- **Executed** — observed in the current environment.
- **Grounded** — supported by repository files such as manifests, CI, tests, source, or license text.
- **Assembled** — composed from grounded pieces but not run end to end.
- **Unverified** — unsupported by accessible evidence and not publishable as fact.

When evidence is incomplete, ReadmeVerity narrows the claim, labels it for verification, or leaves it out.

## What's included

The skill is defined by `SKILL.md` and a small set of supporting files:

- `references/principles.md` — the recurring README patterns the skill reproduces.
- `references/process.md` — the step-by-step procedure for writing and rewriting.
- `references/style.md` — tone and formatting guidance.
- `templates/readme-outline.md` — a composition aid, not a mandatory section list.
- `examples/compact-example.md` — a reference for the intended density and flow.

## Limitations

- The skill reasons over accessible evidence and cannot prove that every command succeeds.
- Monorepos may require selecting the relevant package root before inspection.
- License detection recognizes common full-text licenses and treats custom texts cautiously.
- Benchmark-context checks are heuristic and still require human judgment.

## License

ReadmeVerity is released under the [MIT License](LICENSE).
