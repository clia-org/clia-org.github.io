# `!pwd` Performance (Process Execution Baseline)

This page provides a simple baseline for subprocess overhead so we can talk about CLIA performance in concrete terms.

## Baseline: shelling out to `pwd`

Measured on the current dev host (macOS, local process spawn; 200 runs, median):

| Command | Median (ms) | Notes |
| :--- | ---: | :--- |
| `pwd` | ~5.1 | shell builtin/command resolution overhead included |
| `/bin/pwd` | ~6.8 | explicit binary path |

This is **not** a CLIA measurement — it’s the floor for “spawn a process and get output”.

## Measuring CLIA shell execution (`!pwd`)

CLIA runs shell commands via CommonProcess runners from within `clia chat`.

Once you have a built `clia` binary installed, you can measure startup+execution with one-shot mode:

```bash
clia chat --prompt "!pwd" --shell-output text
```

For deeper context (runner lifecycle):

```bash
clia chat --prompt "!pwd" --shell-trace
```

### Why `!pwd` matters

- It’s the smallest possible “tool execution” workload.
- It makes overhead visible: startup cost, isolation boundaries, streaming plumbing.

## Next

If you want, we can add a small benchmark harness and publish:

- cold start vs warm start
- median/mean/p95
- comparison: raw subprocess vs CLIA runner
