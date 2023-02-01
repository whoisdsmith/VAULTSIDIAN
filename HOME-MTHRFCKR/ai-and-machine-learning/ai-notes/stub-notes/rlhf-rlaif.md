# rlhf-rlaif

memes

- https://twitter.com/jordnb/status/1609501943889534977?s=46&t=oDskJuMscryc9UxtfIfsNg
- https://openai.com/blog/deep-reinforcement-learning-from-human-preferences/
- "rlhf wont scale" https://twitter.com/janleike/status/1615455144816291843?s=46&t=_aRhLI2212sARkuArtTutQ
- https://openai.com/blog/instruction-following/
	- The resulting InstructGPT models are much better at following instructions than GPT-3. They also make up facts less often, and show small decreases in toxic output generation. Our labelers prefer outputs from our 1.3B InstructGPT model over outputs from a 175B GPT-3 model, despite having more than 100x fewer parameters.
	- https://twitter.com/drjimfan/status/1600884409355227137?s=46&t=ZLDRV15juDMP7a5lkxr88g
- https://huggingface.co/blog/rlhf
	- progression
		- Basic: Cross Entropy
		- Intermediate: To compensate for the shortcomings of the loss itself people define metrics that are designed to better capture human preferences such as [BLEU](https://en.wikipedia.org/wiki/BLEU) or [ROUGE](https://en.wikipedia.org/wiki/ROUGE_(metric)).
		- HF: While being better suited than the loss function itself at measuring performance these metrics simply compare generated text to references with simple rules and are thus also limited. Wouldn't it be great if we use human feedback for generated text as a measure of performance or go even one step further and use that feedback as a loss to optimize the model?
		- another progression https://jmcdonnell.substack.com/p/openai-comes-clean-about-gpt-35
			- supervised finetuning
			- feedback made easy
			- ppo - policy optimization
	- The first [code](https://github.com/openai/lm-human-preferences) released to perform RLHF on LMs was from OpenAI in TensorFlow in 2019.
	- Today, there are already a few active repositories for RLHF in PyTorch that grew out of this. The primary repositories are Transformers Reinforcement Learning ([TRL](https://github.com/lvwerra/trl)), [TRLX](https://github.com/CarperAI/trlx) which originated as a fork of TRL, and Reinforcement Learning for Language models ([RL4LMs](https://github.com/allenai/RL4LMs)).
	- https://twitter.com/voidful_stack/status/1615032172632735747?s=46&t=_aRhLI2212sARkuArtTutQ Implementation of ChatGPT RLHF (Reinforcement Learning with Human Feedback) on small scale model (any generation model in hugging face's transformers)
- https://twitter.com/carperai/status/1582891780931874819
	- trlx walkthru https://twitter.com/carperai/status/1613645352514768897
	- https://wandb.ai/carperai/summarize_RLHF/reports/Implementing-RLHF-Learning-to-Summarize-with-trlX--VmlldzozMzAwODM2
- https://carper.ai/instruct-gpt-announcement/
- WebGPT paper dataset
	- https://huggingface.co/datasets/openai/webgpt_comparisons
	- This is the dataset of all comparisons that were marked as suitable for reward modeling by the end of the WebGPT project. There are 19,578 comparisons in total.

## RLAIF

- elicit work based on anthropic
	- https://twitter.com/Charlie43375818/status/1612569402129678336

## synthetic/model Written Feedback

https://twitter.com/cwolferesearch/status/1616896611828830208?s=46&t=_aRhLI2212sARkuArtTutQ

Recently, researchers used LLMs to generate 154 evaluation datasets and even created an interactive demo for the data!

evals.anthropic.com/model-written/ (thread https://twitter.com/AnthropicAI/status/1604883576218341376?s=20, evals https://github.com/anthropics/evals)

This synthetic data was used to study LLM behavior and uncover a couple of really interesting results. [4/9]

- larger LMs are more sycophantic, repeating back a user’s views as their own in 75-98% of conversations. https://twitter.com/AnthropicAI/status/1604883586103926784?s=20

## Quotes

- Human Instrumentality Project https://twitter.com/goodside/status/1603356265391890432
