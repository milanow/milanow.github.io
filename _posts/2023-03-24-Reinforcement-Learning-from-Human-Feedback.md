---
layout: post
title:  "Reinforcement Learning from Human Feedback"
---

## Reinforcement Learning from Human Feedback

视频地址：https://www.youtube.com/watch?v=2MBJOuVq380&t=1s

内容简介：虽然听GPT有点听得PTSD，但为了看RLHF还是要结合它来看。一些前置的RL概念可以看这篇：https://paperexplained.cn/articles/article/detail/33/#id-h2-e37ba622acc1

这个视频主要讲了三件事儿：
1. RLHF的起源，从decision making开始：
- 08年基于TAMER framework，也就是人类直接给agent reward来应用到俄罗斯方块的AI (icdl08-knox.pdf (utexas.edu))
- 17年的时候将人对于特定agent移动任务的trajectory偏好训练了一个reward predictor得到了很好的效果 (https://arxiv.org/pdf/1706.03741.pdf)
- 20年的时候OpenAI尝试将human feedback应用于文本summarize (这篇就是之前@Zhenyu Duan  说KL距离公式写错了的那篇paper) (https://arxiv.org/pdf/2009.01325.pdf)
2. LLM与RLHF结合的方式（主要是基于InstructGPT的概括：https://arxiv.org/pdf/2203.02155.pdf）
- pre-trained supervised model + reward model + fine tuning with RL
3. 对比了Anthropic/OpenAI/DeepMind在apply RL on LM方法上的异同

视频下面给出了其他RLHF在LM上面的探索：

- Fine-Tuning Language Models from Human Preferences (Zieglar et al. 2019): An early paper that studies the impact of reward learning on four specific tasks.
- Learning to summarize with human feedback (Stiennon et al., 2020): RLHF applied to the task of summarizing text. Also, Recursively Summarizing Books with Human Feedback (OpenAI Alignment Team 2021), follow on work summarizing books.
- WebGPT: Browser-assisted question-answering with human feedback (OpenAI, 2021): Using RLHF to train an agent to navigate the web.
- GopherCite: Teaching language models to support answers with verified quotes (Menick et al. 2022): Train a LM with RLHF to return answers with specific citations.
- Sparrow: Improving alignment of dialogue agents via targeted human judgements (Glaese et al. 2022): Fine-tuning a dialogue agent with RLHF
- ChatGPT: Optimizing Language Models for Dialogue (OpenAI 2022): Training a LM with RLHF for suitable use as an all-purpose chat bot.
- Scaling Laws for Reward Model Overoptimization (Gao et al. 2022): studies the scaling properties of the learned preference model in RLHF.
- Training a Helpful and Harmless Assistant with Reinforcement Learning from Human Feedback (Anthropic, 2022): A detailed documentation of training a LM assistant with RLHF.
- Red Teaming Language Models to Reduce Harms: Methods, Scaling Behaviors, and Lessons Learned (Ganguli et al. 2022): A detailed documentation of efforts to “discover, measure, and attempt to reduce [language models] potentially harmful outputs.”
- Dynamic Planning in Open-Ended Dialogue using Reinforcement Learning (Cohen at al. 2022): Using RL to enhance the conversational skill of an open-ended dialogue agent.
- Is Reinforcement Learning (Not) for Natural Language Processing?: Benchmarks, Baselines, and Building Blocks for Natural Language Policy Optimization (Ramamurthy and Ammanabrolu et al. 2022): Discusses the design space of open-source tools in RLHF and proposes a new algorithm NLPO (Natural Language Policy Optimization) as an alternative to PPO.
