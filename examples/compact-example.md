# Compact Example

This example demonstrates density and flow only. Its facts are fictional and must never be reused as project facts.

```md
# tinygrad-demo

A minimal scalar autograd engine in pure Python, built to show the complete forward and backward pass without framework internals. The core engine is intentionally small enough to read in one sitting.

The implementation lives in two files: `engine.py` contains scalar values and backpropagation, while `nn.py` contains the small neural-network layer built on top.

## Example usage

```bash
python demo.py
```

This builds a two-layer network, runs one forward pass, and backpropagates the final scalar loss through every parameter.

```text
loss: 0.8421
parameters with gradients: 41/41
```

Not much machinery, but the full computation is visible.

## Tests

```bash
python -m pytest
```

The tests compare forward values and gradients against the reference implementation. A successful run ends with all tests passing.

## License

MIT
```

Important characteristics of the example:

- the project is defined immediately;
- the design priority is explained rather than merely named;
- key files are described briefly;
- the first command appears early;
- the command's effect is explained;
- output follows the command;
- tests explain what is being compared;
- no generic feature list or full repository tree is added.
