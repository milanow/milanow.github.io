---
layout: post
title:  "Let's build GPT: from scratch, in code, spelled out."
---

## Let's build GPT: from scratch, in code, spelled out.

视频地址：https://www.youtube.com/watch?v=kCc8FmEb1nY

内容简介：这期主要关注Andrej实现「Self-attention」「Multihead self-attention」的过程，他以莎士比亚的剧本为训练数据写出了更多的仿莎士比亚剧本，比如：
> The top in a world by susphoring grace. LUCIO: We muse hath resistes him so sovere: son't his other wrough stands of coverent sh'd: he has here, and stand it and poor exceeder or a Henry's last, stay not in faith, forewell's base of graves, thanks, happy comparel, warmentfully: may as face by the courst, that strangth errise hath breathed. Hastings come to 
Valenting. HERMIONE: Well have been bolly poor late Is the lords.

视频的最后比对了他自己在两小时实现的tiny GPT与ChatGPT的区别（然而似乎他并不打算继续介绍fine-tune和PPO的部分，也许和他入职OpenAI有关）。
视频里面的一些资料（原Youtube视频介绍中有提到）：
- Google colab for the video: https://colab.research.google.com/dri...
- GitHub repo for the video: https://github.com/karpathy/ng-video-...
- Playlist of the whole Zero to Hero series so far: https://www.youtube.com/watch?v=VMj-3...
- nanoGPT repo: https://github.com/karpathy/nanoGPT
- my website: https://karpathy.ai
- my twitter: https://twitter.com/karpathy
- our Discord channel: https://discord.gg/3zy8kqD9Cp

Supplementary links:
- Attention is All You Need paper: https://arxiv.org/abs/1706.03762
- OpenAI GPT-3 paper: https://arxiv.org/abs/2005.14165 
- OpenAI ChatGPT blog post: https://openai.com/blog/chatgpt/
- The GPU I'm training the model on is from Lambda GPU Cloud, I think the best and easiest way to spin up an on-demand GPU instance in the cloud that you can ssh to: https://lambdalabs.com . If you prefer to work in notebooks, I think the easiest path today is Google Colab.
