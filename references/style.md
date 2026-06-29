# Style Guide

## Tone

Write in a technical, direct, lightly conversational voice.

Prefer:

- short declarative sentences;
- concrete verbs;
- exact nouns;
- specific commands and results;
- restrained informality after technical proof.

Avoid:

- corporate language;
- exaggerated claims;
- generic enthusiasm;
- long conceptual introductions;
- repeated summaries;
- formal documentation boilerplate.

## Opening

A strong opening defines the project immediately.

Weak:

> Modern AI workflows are becoming increasingly complex, creating a growing need for accessible tools.

Stronger:

> A small Python implementation of byte-pair encoding with separate basic and regex tokenizers.

The stronger version tells the reader what exists.

## Design priority

Do not merely attach adjectives.

Weak:

> A simple, fast, and powerful framework.

Stronger:

> The implementation keeps the model and training loop in two small files so the complete path from tokens to loss can be read in one sitting.

The stronger version explains what “simple” means.

## Commands

Introduce commands with only the context required to run them.

After the command, explain its effect and show output when available.

Do not surround a command with several paragraphs of abstract explanation.

## Informal comments

A short remark such as “Not bad for the CPU path.” may appear after a measured result.

Use this sparingly. The result must remain understandable without the comment.

## Section headings

Use headings natural to the project.

Do not normalize every README to the same headings. `Quick start`, `Usage`, `To run`, and `Example usage` may all be appropriate depending on the project.

## Lists

Use lists when they make technical information easier to scan.

Do not convert every paragraph into bullets. A README should still read as an explanation, not a checklist pasted into Markdown.
