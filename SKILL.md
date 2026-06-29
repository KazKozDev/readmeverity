---
name: readmeverity
description: Write, rewrite, or improve a repository README using a recurring composition, technical detail, and direct code-first style. Use this skill when the user wants a README that defines the project immediately, explains its main design priority, reaches a working example quickly, shows complete commands and real outputs, uses exact technical details, states limitations directly, and includes only sections justified by the project.
---

# ReadmeVerity

Use this skill to produce a repository README that follows the recurring patterns documented in `references/principles.md`.

The goal is not to imitate any particular author's wording. The goal is to reproduce the observed method:

- define the project immediately;
- explain the main design priority or tradeoff;
- move quickly to a working example;
- show complete commands;
- explain what each command does;
- show real output when available;
- use exact technical details;
- state limitations directly;
- include only sections that belong to the actual project.

## Required reading

Before writing or rewriting a README, read:

1. `references/principles.md`
2. `references/process.md`
3. `references/style.md`

Use `templates/readme-outline.md` only as a composition aid. It is not a mandatory section list.

Use `examples/compact-example.md` only to understand the intended density and flow. Do not copy its wording or invent equivalent facts.

## Core rule

The README must be built from the project itself.

Use only facts supported by the repository, code, configuration, logs, screenshots, benchmark results, or information explicitly supplied by the user.

Never invent:

- commands;
- filenames;
- outputs;
- metrics;
- benchmark conditions;
- hardware results;
- compatibility claims;
- implementation size;
- limitations;
- project status;
- license information.

When a fact is unavailable, omit it or clearly mark what the user still needs to provide. Do not fill the gap with a plausible example.

## Writing task

When creating a README:

1. Inspect the available project material.
2. Identify what the project is, what it does, its implementation level, its stack, and its main distinction.
3. Identify the main design priority or tradeoff.
4. Identify the shortest real path to a meaningful result.
5. Collect the exact commands required for that path.
6. Collect the real output, visible result, or success signal if available.
7. Identify only the additional scenarios that are genuinely part of the project.
8. Write the README in the order best suited to that project, following the principles rather than a rigid template.
9. Remove repeated explanations, unsupported claims, generic marketing language, and irrelevant standard sections.

## Rewriting task

When rewriting an existing README:

- preserve correct project-specific facts;
- correct unsupported or outdated statements only when the available material proves they are wrong;
- move the project definition and first useful scenario earlier;
- replace vague prose with exact commands and concrete explanations;
- place outputs next to the commands that produce them;
- place limitations next to the scenarios they affect;
- remove duplicated content;
- remove sections that exist only because a generic README template usually includes them;
- do not add new sections unless the project itself requires them.

## Output requirements

Return the finished README, not an essay about how to write it, unless the user explicitly asks for analysis.

The final README should normally follow this broad composition:

1. Project title.
2. Concise technical definition.
3. Main design idea or priority.
4. Implementation scale or key files, when useful.
5. First working example.
6. Real result or success signal.
7. Additional project-specific scenarios.
8. Tests, todos, references, or license only when they are actually needed.

This is an observed composition pattern, not a mandatory template. Do not force every item into every README.

## Final check

Before returning the README, verify that:

- the opening defines the project directly;
- the main priority or tradeoff is clear;
- the first working scenario appears early;
- commands are complete and copyable;
- each important command has an explanation;
- real outputs are placed next to their commands when available;
- exact numbers are supported;
- hardware variants are included only when real;
- limitations are stated where they matter;
- tests explain what success means when included;
- no unnecessary sections were added;
- the tone is technical, direct, and lightly conversational;
- no facts were invented.
