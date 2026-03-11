# Shreyas Natarajan
MS Data Science @ UW-Madison | BS CS '25
[LinkedIn](https://linkedin.com/in/shreyas-natarajan) · shreyas.2003.natarajan@gmail.com

I'm most interested in the layer of ML where theory meets real constraints --
where you have to understand what's actually happening inside a model to make good
decisions about architecture, cost, and tradeoffs. I like building things that require
understanding the internals, not just the API.

---

## Featured Projects

### [DNN-Mnist](https://github.com/shreyasnat2804/DNN) `C++17`
I wanted to understand what PyTorch is actually doing before using it. So I built a
neural network library from scratch -- no external dependencies, just C++17 and math.
Custom backpropagation, SGD, modular layer abstractions. Then I got interested in the
performance problem: added OpenMP parallelism for gradient computation and SIMD
intrinsics (AVX/AVX2) for vectorized matrix ops. It trains on 70K MNIST images to 95%+
accuracy. The point was never the accuracy number -- it was building the intuition for
what's expensive and why.

### [Double Agent](https://github.com/shreyasnat2804/Double_Agent) `Python`
A two-layer LLM pipeline where a Router decides whether a prompt is worth optimizing
before sending to the main model. The insight was simple: not every prompt needs the
same treatment, and routing decisions based on prompt length and intent signals can
meaningfully reduce latency and token cost without hurting output quality. Built with
automatic retry logic, fallback handling, and JSONL interaction logging. More
interesting to me as a cost/quality tradeoff problem than as a software project.

### [Hedge Fund Competition](https://github.com/shreyasnat2804/hedge_fund) `Python · scikit-learn · XGBoost · LightGBM`
Quantitative finance competition: predict financial time-series targets across 23
instruments and 4 horizons using ~5.3M rows of training data, evaluated on weighted
RMSE. The interesting design decision was per-code vs. global modeling -- training one
model per instrument rather than a single model across all codes, which turned out to
be the better approach. Pipeline supports Ridge, Histogram Gradient Boosting, XGBoost,
LightGBM, and CatBoost with temporal train/tune/val splits that respect the
time-series structure. The scoring metric penalizes variance relative to the target,
so the problem is really about calibration under distribution shift across different
instruments and horizons.

### Synthetic Focus Group Simulator `Python · pgvector · PostgreSQL`
Using LLMs to simulate consumer personas for pricing and product research. The hard
problem wasn't the RAG pipeline -- it was making personas behave like real demographic
segments instead of like a language model that knows everything. Solved with epistemic
constraints in persona prompts: the model is instructed to reason only from what someone
in that demographic context would plausibly know, not from general world knowledge.
Includes Van Westendorp and Gabor-Granger pricing modules.

---

## Currently thinking about
- How small models degrade under long-context instruction following ("context rot")
- What it takes to evaluate AI startups from a technical due diligence perspective
- Inference cost structures and where the real moats are in the AI stack
