# Clinical AXIS Example

A small independent project that installs the published [Clinical AXIS](https://github.com/yehonathank/clinical-AXIS) methodology (`axis`) and models a chest X-ray triage deployment end to end.

## Setup

1. Start the local registry from [`verdaccio`](../verdaccio) (`node registry.mjs`).
2. Publish Clinical AXIS from the method repository (`oml pack` then `oml publish -r http://localhost:4873`).
3. Install the method into this repository:

```bash
oml install -r http://localhost:4873
```

It lands in `deps/axis/`.

## Use

```bash
oml start
oml lint
oml codegen -c gate
oml stop
```

The notebooks under `src/md` compose the packaged editor templates. Codegen writes `build/docs/*-gate-readiness.md` using the Spec shipped inside `axis`.
