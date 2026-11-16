# Results: 430 SGLang Prompt-Response Benchmark

**Main goal:** Measure sequential SGLang prompt-response latency  
**Tools:** Every profile starts sglang.launch_server with Mistral-7B-v0.3, then prompt_response_client.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_142 · recorded 2026-11-16). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 26.04.1 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-16T11:54:07Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 06:25 · benchmark 00:12 · whole run 07:41
- **Source:** run 430_20261116_115407
- **Command:** `bash run_benchmark.sh --smoke --dtype bfloat16 --input-len 64 --output-len 16 --model-name mistralai/Mistral-7B-v0.3 --num-prompts 2 --max-running-requests 1 --max-total-tokens 1024 --seed 42`

| # | Metric | Result |
|---|---|---|
| 1 | E2E latency p50, ms (end_to_end_latency_ms) | 140.36320336163044 |
| 2 | Time To First Token p50, ms (ttft_ms) | 25.456887437030673 |
| 3 | Output token generation rate (decode) p50, tokens/s (output_tokens_per_s) | 130.55345586185155 |
| 4 | RadixAttn hit rate, pct (radixattention_cache_hit_rate_pct) | 26.865671641791046 |
| 5 | Completed request rate, pct (completed_request_rate_pct) | 100.0 |
<!-- /profile:smoke -->
