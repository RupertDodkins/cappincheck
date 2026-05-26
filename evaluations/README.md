# Archive Evaluations

This directory holds review-time evaluation inputs for the audited launch archive.

Current files:

- `gold_set_seed.json`
  - small starter seed set used to score verdict agreement and rewrite-quality proxies
  - not benchmark-grade
  - should be expanded before using archive-quality scores as a serious publication signal
- `prompts/discovery_prompt.md`
  - independent deep-research prompt for suspect-claim discovery
- `prompts/adjudication_prompt.md`
  - independent deep-research prompt for claim-level adjudication

Current workflows:

- `light QA layer`
  - per-launch deep-research second-reader workflow
  - initialize with `python scripts/init_qa_packet.py <slug>`
  - described in `docs/temporary/deep-research-qa-workflow.md`
- `evaluation layer`
  - gold-set and archive-quality scoring
  - driven by `python scripts/evaluate_archive.py`

Recommended next step:

- grow the seed set into a reviewed gold set of at least `30-50` claims across Google, Anthropic, OpenAI, and xAI
