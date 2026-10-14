### AI / LLM Engineer

I build LLM-powered products and the engineering around them that makes them trustworthy:
**evaluation, retrieval, agent tooling** and the systems underneath. Recent graduate, open to AI
engineering roles.

**Stack:** Python · TypeScript · Go · Node.js · Claude API · FastAPI · numpy · Docker · GitHub Actions

---

#### Projects

| | |
|---|---|
| **[evalkit](https://github.com/omergazi34/evalkit)** · Python | Regression tests for LLM apps. YAML suites, deterministic and LLM-as-judge assertions, multi-model comparison, flakiness detection, and a GitHub Action that fails PRs when quality drops. |
| **[grounded](https://github.com/omergazi34/grounded)** · Python | RAG with verified citations. BM25, dense retrieval and two fusion strategies written from scratch, a labelled benchmark, and a fusion weight chosen by cross-validation. |
| **[tcmb-mcp](https://github.com/omergazi34/tcmb-mcp)** · TypeScript | MCP server that gives AI assistants the Turkish central bank's exchange rates, with holiday-aware fallback and structured outputs, tested end to end against the live feed. |
| **[cvpilot](https://github.com/omergazi34/cvpilot)** · Node.js | AI job-application assistant for the Turkish market: ATS analysis, job-specific CV rewrites and cover letters on Claude structured outputs and streaming. |
| **[minikv](https://github.com/omergazi34/minikv)** · Go | Redis-compatible key-value server on the standard library: RESP, sharded locks, append-only file with group commit and online compaction. Works with `redis-cli`. |

#### Things I measured along the way

- **Textbook hybrid search lost to plain dense retrieval** on my RAG benchmark (MRR 0.75 vs 0.90).
  The cause was rank fusion rewarding agreement over confidence. A score-based fusion with a
  cross-validated weight got the best recall of all modes. → [grounded](https://github.com/omergazi34/grounded#what-the-numbers-say)
- **One example in a prompt** raised Llama 3's fully-cited answers from 68% to 92%, and the remaining
  failure showed why citation *format* checks aren't enough. → [grounded](https://github.com/omergazi34/grounded)
- **Group commit** took durable writes in my Redis clone from 722 to 9.7k ops/s, and replacing a
  slice with a deque fixed an O(n) `LPUSH` the benchmark exposed. → [minikv](https://github.com/omergazi34/minikv#three-bottlenecks-the-benchmark-found-and-what-fixed-them)
- **An eval caught a real model failure:** asked for "only JSON", a local model wrapped it in prose
  3/3 times. → [evalkit](https://github.com/omergazi34/evalkit#real-run-llama-3-on-a-laptop)

#### How I work

Every project has tests and CI from the first commit, a benchmark or eval behind its claims, and a
`DESIGN.md` that explains the trade-offs, including what didn't work.

📫 omerim@hotmail.com
