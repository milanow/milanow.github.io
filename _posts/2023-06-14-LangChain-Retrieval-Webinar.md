---
layout: post
title:  "The spelled-out intro to neural networks and backpropagation: building micrograd"
---

## LangChain Retrieval Webinar

分享还是一期LangChain的webinar: https://www.youtube.com/watch?v=VrL7AbrY438, 本期的标题为「LangChain Retrieval Webinar」，主要请到了两位分享人分享他们在knowledge-intensive的IR task下的一些最佳实践: \
\
一位是[Vespa.ai](https://vespa.ai/)的搜索工程师[Jo Kristian Bergum](https://twitter.com/i/flow/login?redirect_after_login=%2Fjobergum)，分享了他在Vespa所做的使用[google/flan-t5-xxl · Hugging Face](https://huggingface.co/google/flan-t5-xxl)来生成合成queries，补充标注ranking model数据的pipeline。主要是用几个精确的prompt examples来帮助生成q-d的正负例。核心模块我理解有两个，一个是synthetic query generator用来生成q-d，再用consistent check检查看生成的doc在现有搜索服务里是不是被排在第1位（如果不是第一位则丢弃这个q-d），接着根据留下的q-d再生成2个负例，最后喂给模型。同时也在[GitHub - vespa-cloud/cord-19-search: Vespa application making an index of the CORD-19 dataset.](https://github.com/vespa-cloud/cord-19-search)的例子中简单验证了此种方法以low cost迁移domain的可行性。更详细的介绍可以在[Improving Search Ranking with Few-Shot Prompting of LLMs | Vespa Blog](https://blog.vespa.ai/improving-text-ranking-with-few-shot-prompting/)中找到。\
\
另一位是Colbert的作者[Omar Khattab](https://omarkhattab.com/), 在简单回顾了下ColBert的发展后，他也将重点转移到了如何提高domain shift时的检索效果上，毕竟zero-shot能力有限。他在[[2212.14024] Demonstrate-Search-Predict: Composing retrieval and language models for knowledge-intensive NLP (arxiv.org)](https://arxiv.org/abs/2212.14024)提出了Demonstrate-Search-Predict编程模式，把DSP作为LangChain中的「Tool」的tool-builder，以此来告诉LangChain agent如何更好地使用Colbert（而不是zero-shot）。作为一个tool-builder，我理解的DSP实际上是一个python function, 是step-by-step的根据使用场景更精细化地封装LM与RM。在[dsp/intro.ipynb at main · stanfordnlp/dsp · GitHub](https://github.com/stanfordnlp/dsp/blob/main/intro.ipynb)的第4和5个例子里，可以看到如何用DSP的模板来构建multi-hop QA的检索过程。他把结果都写进cache里了，所以不需要更OpenAI key也可以在notebook中跑原文的结果。
