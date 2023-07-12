---
layout: post
title:  "AI x UX - Beyond ChatBox"
---

## AI x UX - Beyond ChatBox

一直对AI的产品形态很好奇。一方面是它带来的惊喜，在最初体验Perplexity.ai时，虽然前一两次搜索我并没有找到答案，但在这几次探索后，我逐渐发现原来是自己问错了问题，就像xy问题一样，AI帮我指出了那个原来我想问的x问题。然而，在传统的搜索引擎中，与此对标的功能「猜你想搜」，大部分时间只能解决错别字的问题，而并不能识别用户的真实意图，也就不能让用户得到想要的答案。另一方面则是对UI产生的悲观态度，如果像ChatGPT一样仅仅用一个对话框能够完成所有的事情，以后人机界面是否只会像Python REPL界面一样，以自然语言代替编程语言，完成所有的交互？


答案显然是否定的。最近听的两期Latent Space的podcast回答了我的大部分由此产生的疑问。[Building the AI × UX Scenius - with Linus Lee of@Notion](https://www.latent.space/p/ai-interfaces-and-notion) 关注如何更好的呈现现有的AI能力，请到了Linus Lee - Research Enginer, Notion AI，主要的分享涉及一些Notion AI的产品形态，包括「AI Autofills」「AI Block」以及背后的思考 。From RLHF to RLHB: The Case for Learning from Human Behavior - with Jeffrey Wang and Joe Reeve of Amplitude 则关注AI产品的数据分析工具，请来了[Jefferey Wang与Joe Reeve@Amplitude](https://www.latent.space/p/amplitude)，主要分享如何更精确地收集用户反馈用来做数据分析，或者帮助AI模型更好的迭代。两期着重强调了「用户引导」与「用户行为反馈」。

---
**Building the AI × UX Scenius**

先说说Linus Lee这期。与许多人设想地一样，Linus也着重强调了AI交互设计应该考虑到语言模型的局限性，应该将语言模型擅长的部分与正确的用户预期对齐。一个简单的例子是「聊天框」与「搜索框」：如果是一个像OpenAI一样的聊天框，用户可能会向聊天框里输入任何奇怪的问题，比如把对面当成人而在输入框里输入Hello，此时用户甚至对答案没有明确的预期，所以也不会「对齐预期」的发生。而搜索框在外观上区别于聊天框，更加直观地传递了它所代表的功能，让用户真正地把AI视作工具。同时，在搜索的语境下，因为有了更多的限制，比如在飞书中的「消息」搜索框智能够搜索到飞书的消息，让数据搜索的范围减小，也能让模型在更小的问题空间下更能准确地解决具体问题。


播客里主要有两个概念值得分享:

**Mental Models (心智模型)**: 正如聊天框与搜索框会对用户理解界面产生影响，Linus在后面的分享中提到了UX中很重要也很经典的概念 - Mental models，并举了一个现在电脑上音量条的设计作为例子：现在音量调节的大小都是通过数字0-10或0-100来显示的，假设当用户现在从音量40调节到80，用户会理所应当地认为音量增加了一倍。但实际上对扬声器来说它的耗电量实际为原来的4倍，然而这并不重要，重要的是用户如何理解眼前的UI以及它所采取的行动是否符合他所预期的效果。此时，consistent mental models - 对眼前的UI有统一的建模就显得尤为重要，它定义了用户如何理解眼前的界面。

**Constraints and Flexibility (语言模型的局限与灵活性)**: 除了调整用户预期，Notion AI在设计时也考虑了语言模型的局限性。正如前面所说，在小范围更问题空间内发问可以让语言模型更精确也更能发挥它的长处。这个概念在Notion里，就可以浓缩成一些确定性的高频使用场景，比如「总结」比如「会议纪要」。在Notion Project的设计中，「总结」是一个在其右键的context menu上的一个确定的按钮。另外也可以看到在菜单上除了「Summary」，Notion AI保留了「Custom autofill」兼顾了高级用户的创造性探索。

嘉宾Linus在其他的公开分享中的框架或概念我认为更值得借鉴：

**Point, Select & Action (充分表达的交互意图)**: 本期播客其实更像是为了新的Notion Projects与Notion AI做广告。实际上更加启发我的是嘉宾Linus在其日常blog里关于AI UX的分享。在 [Generative Interfaces Beyond Chat](https://www.youtube.com/watch?v=rd-J3hmycQs) 中，Linus提到了「Point, Select & Action」的概念，这个概念很容易在现有的交互中找到例子，比如此时用户希望复制一段文本，Ta可能需要将光标移动到一段文字的开头，按住并拖动光标选中高亮一部分的文本，再进行右键复制的操作。在这个例子里，光标的起始位置就是「Point」，而拖动光标则代表「Select」，用户由此来表达自己将要对这部分文本采取复制的「Action」。通过以上三点系统可以完全理解用户的交互意图，给到用户正确的响应预期。
实际上，上图的context menu就是「Action」的具体例子，其代表了在确定范围内，即某个table column作为「Point」和「Select」，提供给用户所能采取的所有可能的「Action」。这里我特别喜欢原文的表述：
> Funnel the users to the right action

funnel这个词我认为用得比narrow还要形象。

**Feedback Loops**: Linus也提到了user feedback loops的重要性。就像最初遇到ChatGPT我不知道该问什么问题而懵在那里一样，在多数情况下，用户更倾向于「选择」而不是「创造」。因此，在结果比较好衡量的情况下，可以尽量返回给用户更多的结果让用户来选择自己喜欢的那个。例如在Midjourney生成多张图片，或者对文章总结生成多个答案都属于此范畴。这样的设计在下面的一期播客也会提到，不止可以让用户更满意AI输出的结果，还能够根据用户行为（选择哪个答案）来评价模型输出的答案，以此来增强模型效果。
为了提供完整的Feedback loops，与此期播客相关的AIxUX NYC延伸出来另一个设计方向或者说理念 - 「Prompt space exploration」，通过保存本次与Generative AI对话session的所有路径，用户可以看到自己从最初的prompt通过何种路径一步一步修改到最终的成品的。与此相关的设计在 [AI X UX NYC](https://www.youtube.com/watch?v=76chBva31Iw&t=1744s) 有不少的展示，比如：
- [dreamwalker](https://dreamwalker.ai/) 就展示了如何通过variant一步步在Unity3D中与DALLE交互生成最终用户希望的art asset.
还有另一个Linus举过的例子我也很喜欢：
- https://twitter.com/quasimondo/status/1248648825864142848 用Joystick来探索生成人像的角度

---
**From RLHF to RLHB: The Case for Learning from Human Behavior**

Amplitude则先分享了自己的创业故事。Amplitude这家公司最初的名字为SonaLite，是一个主要解决语音转换文字问题的公司。它的设想是人们在开车或者类似不方便使用手机的时候，可以通过此种交互方式流畅地在手机上使用IM功能。随着时间推移，两个创始人Spencer和Curtis很快发现实现这个产品最困难的技术在于语音识别，但两个人都不是机器学习背景出身，对花精力解决此类问题并不是很感兴趣，相反地，他们开始思考类似「用户为什么喜欢他们的产品？」的问题，并以此构建了一系列分析工具来帮助他们理解用户行为。结果，与他们同一批在YC孵化的公司在看见他们使用的分析工具后，对此产生了浓厚的兴趣。同时他们发现市场上并没有与他们现有产品类似的工具，他们就此转型，变成了一家现在专攻于toB的数据分析工具公司。他们的目标，就是挖掘更多的用户行为信息，并以此来帮助客户实现商业化得最大成功。

以下三点对我很有启发：

**Thinking Path (思考路径)**: Joe的回答，从「我们希望将AI能力加入到我们的产品中」这个假设开始，做出了一系列的猜想。
- 他们的第一个落脚点是「协同」，把AI比做人，那么一个用户可以将哪些工作委托给另一个人呢？后来他们意识到，AI与人的合作实际上是区别于传统人与人之间的合作的。因为AI可以是无限多个，它可以在所有方面与用户进行协作。针对用户的每一个行动或需要给出输出与建议。
- 再来是从用户侧，思考用户在使用过程中会遇到哪些的障碍：比如在勾选茫茫多的复选框之前，我们有没有能力去预测哪些复选框是希望被勾选的？
- 最后是工具：Amplitude意识到，ChatGPT并不是某个领域范围内的工具，而是一个非常普世地可以用在各个方面的工具，甚至ChatGPT其实并不与Amplitude的产品有任何直接的联系。
- 公司的目标：Amplitude希望帮助客户可以通过标准的方法查询并收集到他们想要的数据，并且通过这些数据中获得一些insight。
他们在各方向的思考，最终逐渐形成了一个TextBox的产品 (Linus听到可能很想打人)。主要是根据客户对自身数据的各式各样的问题，来产生一系列的图表来回答客户的疑问。

**Evalution (结果评估)**: 此外，和Linus一样，Amplitude也提到了关于用户反馈的问题。作为以收集用户行为为根基产生商业洞察的公司，缺少用户行为的捕捉可能是一个毁灭性的打击。如果交互设计真的沦为了在文本框之中用户与AI的对话，那将无任何商业洞察可言。回想起让用户给语言模型生成的答案like/dislike的反馈，他们对此表示悲观，并没有许多用户会真的点击并发送反馈。而零反馈的结果会让整个系统无法衡量自己的输出。他们给到的解决方案与dreamwalker很类似，通过一系列用户的选择输出结果的行为来代表用户对AI系统的真实评价。这里引用他们的原话来做总结:
> Every AI application should figure out how to learn from all their real users

**Measure (衡量AI对产品的价值)**: 主持人@Swyx提了一个非常有价值的问题：作为数据分析工具的公司，在AI era可以给到一些公司什么样的建议？比如应该去关注什么样的Analytics的结果？
Jeffery的回答也干脆直接：北极星指标。他表示很多公司盲目地把AI加入自己的产品中，却不知道所加入的AI能力对自己的公司收益是否真的相关。比如任何一个有「界面」的公司理论上都可以推出一个chatbox (backing up with GPT) 在他们的界面中声称自己支持了AI能力。但这很有可能对公司收益没有任何帮助。所以在加入AI能力之前，一定要想清楚AI是如何与自己的北极星指标相关的。（相比之下我觉得Notion在今年3月左右就宣布了自己的AI战略 - Adding AI LEGO block into Notion，对比Amplitude的动作要坚决许多）

---
作为工程师，我总认为AI系统下的系统架构会与传统的后端系统相差许多。如果GPT的愿景是属于每个人的助手，那么他对系统的延迟敏感程度就再也不会是系统设计的首要重点。因为我对个人助手的期待是：只要结果够好，1min或10min并没有巨大的差别。

最后还想说说这个Notion AI的工程师Linus，嘉宾[Linus Lee](https://twitter.com/thesephist)称得上是一个高产的builder，在他的[blog](https://thesephist.com/projects/)中有超过100多个自己的side project。其中包括一门叫做Ink的编程语言、基于Ink实现的个人搜索引擎Monocle、以及甚至在Spotify上发行的两张音乐专辑等等，涉猎十分广泛。他在节目中也分享了自己做side project的习惯：对于每一个side project只选一小部分自己并不熟悉的部分，比如一个project只学习GPT API，另一个project只学习Next.js，这样设置milestone的方式可以很好地看见自己的进步也更容易建立自信。另一方面，如果有很多不熟悉的模块交织在一起，对于个人其问题的复杂度就会显著增加。「one thing at a time」可以帮助他让学习他的曲线显著降低。

关于「one thing at a time」这点，我想到了John Carmack之前也分享过，他认为如果自己当时先做好Doom的网络联机版本，再去开发Quake会让Quake的开发进程更加顺利。（对于一个多人联机的网络游戏Quake需要在多端上同步各个玩家的状态/行动/输入，而同时Quake这样的FPS游戏天生对帧率有极高的要求，这就让每一帧所需要同步的多端状态/行动/输入变得更加困难。「多人联机」与「3D实时渲染」两大模块之间的交互曾经让Carmack头痛不已。）
