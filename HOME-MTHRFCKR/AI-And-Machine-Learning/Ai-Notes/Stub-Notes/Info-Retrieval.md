# Info-retrieval

- In late 2021, DeepMind proposed [RETRO](https://www.deeplearning.ai/the-batch/large-language-models-shrink/), a model that retrieves passages from the MassiveText dataset and integrates them into its output.
- AI21 Labs' spring launch of [Jurassic-X](https://www.deeplearning.ai/the-batch/neural-nets-rules-truer-text/)introduced a suite of modules—including a calculator and a system that queries Wikipedia—to fact-check a language model’s answers to math problems, historical facts, and the like.
- Researchers at Stanford and École Polytechnique Fédérale de Lausanne created [SERAC](https://www.deeplearning.ai/the-batch/update-any-language-model/), a system that updates language models with new information without retraining them. A separate system stores new data and learns to provide output to queries that are relevant to that data.
- Meta built [Atlas](https://www.deeplearning.ai/the-batch/how-small-language-models-can-perform-specialized-tasks/), a language model that answer questions by retrieving information from a database of documents. Published in August, this approach enabled an 11 billion-parameter Atlas to outperform a 540 billion-parameter PaLM at answering questions.

Rethinking with Retrieval” which looks promising.  
arxiv.org/abs/2301.00303

- https://twitter.com/colinfortuner/status/1610638593537474561
- Common sense reasoning ->

For each sentence explanation in the CoT output:

1. get the top 10 relevant paragraphs from their knowledge base
2. find most similar paragraph to to the sentence
3. Score sentence faithfulness
4. (Faithfulness determined by entailment/contradiction scores and similarity of all sentences)
5. Make a prediction with “faithful inference” (details in paper)
