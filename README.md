# Local GPU & Cloud LLM Benchmarks (llmbenchmarks.io)

Live interactive leaderboard: **https://llmbenchmarks.io/local-gpu-benchmarks/**  
Main cloud & frontier comparison: **https://llmbenchmarks.io/**

## Overview

Whenever I looked at existing LLM leaderboards I was missing practical numbers for running quantized open weight models on affordable local hardware. Most tables only copy vendor cloud scores or run tiny subsets of a benchmark, and none of them tell you how long a model actually sits there calculating before it finishes.

Because nothing like that existed, I set up a dedicated Linux test server with two RTX 5060 Ti cards giving 32 GB of VRAM in total, running vLLM in Docker. Over the past weeks I ran 12 current local models from 4B up to 35B through complete benchmark datasets without any subsampling, including IFEval, IFBench, ARC AGI 1, SimpleQA, SimpleQA Verified, SciCode and vLLM bench serve.

## Tested Models (Thinking ON and Thinking OFF)

* **Qwen 3.8, 3.6 and 3.5** (4B, 9B, 27B Dense and 35B A3B MoE in NVFP4, AWQ and BF16)
* **Google Gemma 4** (E4B, 26B A4B MoE and 31B in NVFP4, 4 bit QAT and BF16)
* **GLM 4.7 Flash** (30B A3B MoE in AWQ)
* **Mistral Ministral 3 14B Reasoning** (AWQ 4 bit and 8 bit)
* **Llama 3.1 8B Instruct** (BF16 and NVFP4)

Every cell in the interactive table shows the score in percent alongside the exact wall clock duration, throughput in tokens per second and a time efficiency rating from 0 to 100.
