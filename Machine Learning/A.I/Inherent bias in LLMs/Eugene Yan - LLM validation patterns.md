Source: [eugenyan.com](https://eugeneyan.com/writing/llm-patterns/#retrieval-augmented-generation-to-add-knowledge)

- An A.I service/product can be comprised of multiple components such as:
	- LLMs
	- Prompt templates
	- Retrieved context
	- Paramters, i.e:
		- Temperature 🌡️(?)
### 1. Evals
- Enables regression detection in the performance of models
- Avoids the requirement for the visual inspection of every output 

	**Common LLM Benchmarks**
	- MMLU - 
		- Fixed set of 57 tasks which span maths, US History, Comp. Sci, law, etc.
		- Success contingent on signifiant World knowledge
	- EleutherAI Eval - Unified framework for testing via 'Zero-shot' techniques
	- HELM - Comprehensive assessment of LLMs by evaluating across domains
		- Evaluates responses based upon criterion for  a specific response aspect, i.e: 'accuracy', 'calibration', 'robustness', 'fairness', 'bias', 'toxicity'
		- Defers to specific high-level task categories such as 'Classification'
		- What a typical task looks like on [dataannotation.tech](dataannotation.tech) 😉
	- [AlpacaEval](**[AlpacaEval](https://github.com/tatsu-lab/alpaca_eval)**)
### 2. RAG (Retrieval-Augmented Generation)
- Helps reduce model hallucinations by 'grounding the model using retreived context'.
- 
