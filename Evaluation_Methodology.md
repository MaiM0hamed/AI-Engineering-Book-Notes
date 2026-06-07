Chapter 3: Evaluation Methodology
Why Evaluation Matters

As AI systems become more capable, evaluating them becomes significantly harder.

Traditional ML evaluation relies on comparing outputs against ground truth labels. However, Foundation Models generate open-ended responses where multiple answers can be correct.

Challenges of Evaluating Foundation Models
1. Open-ended outputs

For a single prompt, there may be many valid responses.

Example:

Prompt:

Summarize this article

Several summaries may all be correct.

2. Black-box models

Most modern LLMs expose only their outputs.

Developers often don't know:

Training data
Architecture details
Alignment process
3. Benchmark Saturation

Popular benchmarks quickly become saturated.

Examples:

GLUE
SuperGLUE
MMLU
MMLU-Pro
Language Modeling Metrics
Perplexity

Perplexity measures how uncertain a model is when predicting the next token.

Lower Perplexity = Better Next Token Prediction

Important note:

Lower Perplexity does not always mean a better user experience after RLHF or Instruction Tuning.

Cross Entropy

Cross Entropy measures how closely the model's learned distribution matches the true data distribution.

Training objective of most autoregressive language models:

Minimize Cross Entropy
Exact Evaluation
Functional Correctness

Instead of comparing generated text with a reference answer:

Ask:

Does the output actually work?

Examples:

Code Generation
Text-to-SQL
Agents
Tool Calling

Popular benchmarks:

HumanEval
MBPP
Spider
Similarity-based Evaluation
BLEU

Measures lexical overlap.

Commonly used in:

Machine Translation

Limitation:

Different wording can express the same meaning.

ROUGE

Measures overlap between generated summaries and reference summaries.

Commonly used in:

Summarization
Semantic Similarity

Uses Embeddings instead of exact word matching.

Examples:

How are you?
How's it going?

Low lexical similarity.

High semantic similarity.

AI as a Judge

Using an LLM to evaluate another LLM.

Common evaluation criteria:

Relevance
Faithfulness
Coherence
Toxicity
Hallucination Detection

Advantages:

Fast
Scalable
Cheap compared to human evaluation

Limitations:

Self-bias
Position bias
Verbosity bias
Inconsistency
Key Takeaways
Evaluation is often harder than model development.
Perplexity is useful but insufficient.
BLEU and ROUGE have important limitations.
Functional Correctness is the gold standard whenever possible.
AI-as-a-Judge is becoming the dominant evaluation approach.
No single metric can fully capture model quality.
