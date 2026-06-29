# Observed README Principles

These principles are based on recurring patterns across the README files of:

- `nanoGPT`
- `llm.c`
- `minGPT`
- `minbpe`
- `llama2.c`
- `micrograd`
- `arxiv-sanity-lite`

They describe repeated composition, technical, and stylistic patterns. They are not a rigid template.

## 1. Start with a direct project definition

Immediately after the title, explain what the project is.

The opening should usually answer:

- what is implemented;
- at what level of abstraction;
- in which language or stack;
- for which task;
- how it differs from a larger or more complex alternative.

Do not begin with a long origin story, a general overview of the field, or broad marketing language.

## 2. State the main project priority

Explain the property the implementation is built around, such as:

- simplicity;
- minimalism;
- readability;
- interpretability;
- educational value;
- speed;
- hackability.

Do not merely list features. Explain the underlying priority or tradeoff.

## 3. Use implementation size as explanation when relevant

When compactness is an important part of the project, mention the size of the core implementation.

Examples of useful measures include:

- lines of model code;
- lines of training-loop code;
- size of a reference implementation;
- number of core files.

Use this as evidence of readability or inspectability, not as a promotional number. Verify it before including it.

## 4. Explain the project through key files

Prefer a short list of important files over a complete repository tree.

Describe only the files that explain the core logic, for example:

- model architecture;
- training loop;
- inference or sampling;
- tokenizer implementation;
- data preparation;
- reference implementation;
- main CLI or server.

Keep each description short and functional.

## 5. Reach a working scenario quickly

Place a practical first-use section early.

Possible headings include:

- `Quick start`
- `Usage`
- `Example usage`
- `To run`
- another heading natural to the project.

The first scenario usually contains:

- installation or build steps;
- data preparation or model download;
- the run command;
- an example result.

## 6. Keep installation close to first use

A separate `Installation` section is not mandatory.

Installation may appear as:

- a dedicated section;
- a requirements block;
- commands inside quick start;
- clone, build, download, and run steps in one scenario.

The important pattern is proximity to the first working example.

## 7. Show complete commands

Provide commands in copyable form.

Do not replace them with vague instructions such as “run training” or “install dependencies.”

Include real flags and parameters when they matter.

## 8. Explain the effect of each command

After a command, explain what it does.

Useful details include:

- files created;
- model or dataset loaded;
- number of steps run;
- checkpoint location;
- data processed;
- process or interface started;
- expected result.

## 9. Show real program output

When available, place real output directly after the command that produces it.

Possible outputs include:

- generated text;
- train and validation loss;
- tokens per second;
- terminal output;
- gradients or tensor values;
- tokenizer output;
- screenshots;
- the expected success line from a test.

Do not invent output.

## 10. Allow a short authorial comment after proof

A brief informal comment may follow a technical result.

It should be short, natural, and secondary to the evidence. It must not replace explanation or become promotional copy.

## 11. Use exact technical numbers

Include concrete numbers when they help reproduce or understand the scenario, such as:

- layers;
- attention heads;
- embedding size;
- context length;
- parameter count;
- checkpoint size;
- thread count;
- GPU count;
- training time;
- validation loss;
- throughput;
- batch size;
- training steps.

Integrate them into the scenario instead of automatically creating a specification table.

## 12. Provide different hardware scenarios when real

When supported by the project, provide separate paths for:

- CPU;
- Apple Silicon;
- one GPU;
- multiple GPUs;
- multiple nodes;
- smaller models;
- quantized inference;
- large checkpoints.

Explain what changes between scenarios, such as context length, batch size, model size, precision, or number of steps.

## 13. State limitations where they occur

Place a limitation next to the scenario it affects when possible.

Examples include:

- impractical CPU training;
- high memory requirements;
- incomplete model support;
- weak test coverage;
- intentionally simplified mainline code;
- frozen or archived implementations.

Do not hide every limitation in a generic section at the end.

## 14. Put obsolete-project status near the beginning

When a project is archived, semi-archived, superseded, or no longer the recommended implementation, say so in the opening area.

Include:

- current status;
- the newer project when known;
- a brief reason the old repository remains available.

## 15. Let later sections follow the project

There is no universal complete section set.

Possible sections include:

- training;
- finetuning;
- sampling or inference;
- datasets;
- baselines;
- efficiency notes;
- tests;
- tutorials;
- multi-GPU training;
- multi-node training;
- experiments or sweeps;
- quantization;
- tracing or visualization;
- community extensions;
- lecture;
- exercises;
- todos;
- references;
- license.

Include only the sections that correspond to real project scenarios.

## 16. Describe training as a reproducible scenario

For training projects, include the relevant combination of:

- data preparation;
- launch command;
- configuration;
- hardware;
- approximate duration;
- expected metric;
- output or checkpoint location.

The goal is reproducibility, not exhaustive explanation.

## 17. Separate inference when it is meaningfully different

Give inference or sampling its own scenario when it differs substantially from training.

Show:

- the command or code;
- the input;
- important parameters;
- example output.

## 18. Explain tests through command and meaning

When tests matter, include:

- the command;
- the test framework when useful;
- what is compared or checked;
- which output means success;
- any extra dependencies.

Do not merely say that tests exist.

## 19. Use a reference implementation as correctness evidence

When the project compares itself with a trusted implementation, explain the comparison.

Examples include:

- C output against PyTorch;
- autograd results against PyTorch;
- tokenizer output against `tiktoken`;
- model behavior against known checkpoints.

State both what is compared and what agreement means.

## 20. Present benchmarks as part of a practical scenario

Performance information may include:

- validation loss;
- tokens per second;
- step time;
- total training time;
- model size;
- checkpoint size;
- baseline tables;
- comparisons with another implementation.

Keep the model, workload, and hardware close to the number whenever they are known.

## 21. Keep the style technical and conversational

Use:

- direct statements;
- short explanations;
- natural transitions;
- occasional restrained informality;
- technical language without corporate tone.

Avoid inflated marketing promises, formal documentation boilerplate, and generic promotional phrasing.

## 22. Use references only when useful

A dedicated `References` section is optional.

References may instead appear inline and point to:

- papers;
- datasets;
- checkpoints;
- discussions;
- tutorials;
- related projects;
- external implementations.

Do not add a references section simply to satisfy a template.

## 23. Keep todos concrete

When a `Todos` section exists, list specific technical tasks, for example:

- add mixed precision;
- add distributed training;
- implement another language version;
- improve mobile layout;
- support another tokenizer format.

Do not turn it into a dated product roadmap unless the project already has one.

## 24. Keep the license section brief

When a license section is needed, keep it short and accurate.

A simple form is often enough:

```md
## License

MIT
```

Do not explain the license at length unless the project has a real reason to do so.

# Most Stable Composition Pattern

The most common broad sequence is:

1. Project title.
2. Concise technical definition.
3. Main idea and priorities.
4. Implementation scale or key files.
5. First working example.
6. Real output.
7. Additional project-specific scenarios.
8. Tests, todos, references, or license when needed.

This is an observed pattern, not a required template.

# Style Summary

A README in this style is built around working code.

It:

- defines the project quickly;
- explains the main idea;
- highlights simplicity or compactness when real;
- points to the key files;
- provides a working command early;
- shows a real result;
- uses exact numbers;
- accounts for real hardware differences;
- states limitations directly;
- remains technical but informal;
- includes only sections justified by the project.
