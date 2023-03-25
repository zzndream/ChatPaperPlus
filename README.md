<div style="font-size: 1.5rem;">
  <a href="./README.md">中文</a> |
  <a href="./readme_en.md">English</a>
</div>
</br>

<h1 align="center">ChatPaperPlus</h1>
<div align="center">
  <a href="https://github.com/zzndream/ChatPaperPlus">
    <img src="https://github.com/zzndream/ChatPaperPlus/blob/main/images/home.png" alt="Logo" height="210">
  </a>



  <p align="center">
    <h3>Read Paper more efficiently with ChatPaperPlus</h3>
      <a href="https://github.com/zzndream/ChatPaperPlus/graphs/contributors">
        <img alt="GitHub Contributors" src="https://img.shields.io/github/contributors/zzndream/ChatPaperPlus" />
      </a>
      <a href="https://github.com/zzndream/ChatPaper/issues">
        <img alt="Issues" src="https://img.shields.io/github/issues/zzndream/ChatPaperPlus?color=0088ff" />
      </a>
      <a href="https://github.com/zzndream/ChatPaper/pulls">
        <img alt="GitHub pull requests" src="https://img.shields.io/github/issues-pr/zzndream/ChatPaperPlus?color=0088ff" />
      <a href="https://github.com/zzndream/ChatPaperPlus/stargazers">
        <img alt="GitHub stars" src="https://img.shields.io/github/stars/zzndream/ChatPaperPlus?color=ccf" />
      </a>
      <br/>
      <em>基于ChatPaper构建 </em>
      <br/>
    </p>

    
  </p>
</div>

# 开发动机及优化功能

ChatPaper很好用，但是作者没有把写论文的实验数据解析。我自己有个Notion论文阅读笔记，会总结论文使用到的数据集和主要实验结果，因此我在ChatPaper的基础上增加了这些功能，以后还会持续优化。

**基于ChatPaper，基本功能完全相同**

**增加了以下功能**：

- 增加了功能：总结论文实验部分；
- 汇总输出论文实验使用的数据集；
- 用表格形式给出主要实验结果；
- 优化了生成的markdown文件格式，使其具有层次；

# 使用方法

请调用chat_paper_plus,py，参数与ChatPaper完全相同。

以本地pdf总结为例： 运行chat_paper_plus.py：

```python
python chat_paper_plus.py --pdf_path "demo.pdf"
```



## 解析示例：



> # Paper:“Good Robot!”: Efﬁcient Reinforcement Learning for Multi-Step Visual Tasks with Sim to Real Transfer
>
> 
>
>
> ## 文章概要
>
> ### 1. Title: 
>
> - "Good Robot!": Efficient Reinforcement Learning for Multi-Step Visual Tasks with Sim to Real Transfer (“好机器人!”:带有模拟到真实转移的多步视觉任务的有效强化学习)
>
> ### 2. Authors: 
>
> - Andrew Hundt, Benjamin Killeen, Nicholas Greene, Hongtao Wu, Heeyeon Kwon, Chris Paxton, and Gregory D. Hager
>
> ### 3. Affiliation:  
>
> - Andrew Hundt, Benjamin Killeen, Nicholas Greene, Hongtao Wu, Heeyeon Kwon, and Gregory D. Hager are with The Johns Hopkins University, Baltimore, MD 21218 USA
> - Chris Paxton is with NVIDIA, Seattle, WA, 98105 USA
>
> ### 4. Keywords: 
>
> - Computer vision for other robotic applications, deep learning in grasping and manipulation, reinforcement learning
>
> ### 5. Urls and Code
>
> - Url: https://ieeexplore.ieee.org/document/9127666
> - Code: https://github.com/jhulcsr/good_robot
>
> ### 6. Summary: 
>
> - (1):本文研究背景是在真实环境下学习多步长的机器人任务是非常具有挑战性的，需要同时学习在短时间内如何行动，以及如何将行动对任务目标的影响。
> - (2):现有的强化学习算法在处理多步任务时效果并不好，存在着任务进展容易被逆转、浪费时间探索不相关的行动等问题。基于此，作者提出了SPOT框架，探索行为安全区域，学习有关不安全区域的知识，优先考虑反转早期进展的经验，从而实现高效学习。 
> - (3):文章提出了一个新的强化学习框架: Schedule for Positive Task(SPOT)，能够在行动的安全区域中进行探索，在学习时不需要花费时间探索不相关的区域，同时优先考虑早期进展反转的经验，以此来提高学习效率。
> - (4):作者在多个任务上对SPOT框架进行了测试，在处理4个方块堆叠、4个方块排列和消除拼图3个任务上，任务的成功率分别从13%、13%和84%提高到100%、99%、95%以上。同时，每轮行动数量的效率一般提高了30%以上，而训练时间只需要1-20 k行动，具有较好的可靠性和高效性。另外，作者还展示了直接从真实环境中学习的结果，成功创造了100%的真实物体堆放和排列结果，具有61%和59%的效率。这项研究成果支持了他们的目标。
>
> ## 文章提出的方法
>
> ### 7. Methods: 
>
> - (1): 本文提出了一种基于SPOT（Schedule for Positive Task）框架的强化学习算法，该算法通过控制行为空间和优先考虑反转早期进展的经验来实现高效学习。
>
> - (2): 为了提高学习效率，文章采用奖励塑形和环境知识的方法，提出了基本奖励（Rbase）、情况消除奖励（RSR）和进展奖励（RP）作为奖励函数。
>
> - (3): 本文中通过引入动态行动空间Mt，提出了SPOT-Q学习，该学习算法将0值奖励操作作为失败处理，并通过尝试次佳行动来选择性地探索动作空间，从而最大化任务成功率和行动效率。
>
> - (4): 测试表明，SPOT框架的强化学习算法在多个任务上均取得了较好的表现，且训练时间和行动数量相对较少，具有较高的可靠性和高效性。同时，算法在3个任务中的成功率得分从13%、13%和84%分别提高到了100%、99%和95%以上。
>
> ## 主要实验结果
>
> ## 8. Experiments: 
>
> - (1): 本文实验章节中使用的具体数据集包括：在真实机器人上进行的推和抓实验，堆叠和排列实验的模拟数据集。
>
> - (2): 在实验章节中，作者使用了成功率和行动效率作为评估指标。
>
> - (3): 成功率定义为完成任务的次数除以总次数，并且与环境中的场景相关；行动效率定义为平均每个成功尝试所需的轮次数。
>
> - (4): 在多个数据集上测试表明，SPOT-Q框架的强化学习算法显示出很好的学习效果，具体结果如下表：
>
> | 实验数据集        | 成功率 | 行动效率 |
> | ----------------- | ------ | -------- |
> | 4个方块堆叠(模拟) | 100%   | 42       |
> | 4个方块堆叠(真实) | 100%   | 61       |
> | 4个方块排列(模拟) | 99%    | 9        |
> | 4个方块排列(真实) | 99%    | 59       |
> | 消除拼图(模拟)    | 95%    | 13       |
> | 消除拼图(真实)    | 95%    | 58       |
>
> 以上结果表明，SPOT-Q框架能够在多个任务上展现出较好的可靠性和高效性，具有较为广阔的应用前景。
>
> # 全文总结
>
> ### 9. Conclusion: 
>
> - (1): 本文介绍了一种基于SPOT框架的强化学习算法，能够有效地学习多步长机器人任务。通过比较模拟与现实场景的表现结果，证明SPOT框架能够实现成功的模拟到现实转移，取得了区别于以往的优秀效果。
>
> - (2): Innovation point: 本文提出了SPOT框架，能够有效地处理多步长机器人任务。创新之处在于：在行动的安全区域中进行探索，不需要探索不相关的动作区域，同时，优先考虑反转早期进展的经验，提高强化学习的效率。
>
> - (3): Performance: 实验结果表明SPOT框架的强化学习算法在4个方块堆叠、4个方块排列和消除拼图3个任务上取得了良好的效果。成功率得分从13%、13%和84%提高到了100%、99%、95%以上。同时，每轮行动数量的效率一般提高了30%以上，而训练时间只需要1-20 k行动，具有较高的可靠性和高效性。
>
> - (4): Workload: 本文提供了详细的实验数据，并通过真实机器人实验准确评估了算法的性能。虽然算法的中间奖励可能比较稀疏，但SPOT框架已经证明是对于处理多步长机器人任务非常有效的方法。不过，SPOT框架存在一个限制因素是需要中间奖励。在未来的研究中，可以探索学习任务结构的新方法，同时，研究行动空间掩码M的自动化设计及更高层次的开环行动学习。此外，也需要研究更具挑战性的任务场景，以进一步推进该领域的研究发展。
>





# 使用方法请参考ChatPaper帮助

> **功能免费，代码开源，大家放心使用！** 关于API如何获取，首先你得有一个没有被封的ChatGPT账号，然后[获取Api Key](https://chatgpt.cn.obiscr.com/blog/posts/2023/How-to-get-api-key/) ,填入即可！
>
>
> - [💥最新讯息](#最新讯息)
> - [💫开发动机](#开发动机)
> - [⛏️使用步骤](#使用步骤)
> - [📄解析示例](#解析示例)
> - [👁️‍🗨️使用技巧](#使用技巧)
> - [🛠️常见报错](#常见报错)
> - [💐项目致谢](#项目致谢)
> - [🌟赞助我们](#赞助我们)
> - [🌈Starchart](#Starchart)
> - [🏆Contributors](#Contributors)
>
>
> ## 最新讯息
>
> - 🌟*2021.03.19*: 全新的ChatPaper即将上线！
>
> ## 开发动机
>
> 面对每天海量的arxiv论文，以及AI极速的进化，我们人类必须也要一起进化才能不被淘汰。
>
> 作为中科大强化学习方向的博士生，我深感焦虑，现在AI的进化速度，我开脑洞都赶不上。
>
> 因此我开发了这款ChatPaper，尝试用魔法打败魔法。
>
> ChatPaper是一款论文总结工具。AI用一分钟总结论文，用户用一分钟阅读AI总结的论文。
>
> 它可以根据用户输入的关键词，自动在arxiv上下载最新的论文，再利用ChatGPT3.5的API接口强大的总结能力，将论文总结为固定的格式，以最少的文本，最低的阅读门槛，为大家提供最大信息量，以决定该精读哪些文章。
>
> 也可以提供本地的PDF文档地址，直接处理。
>
> 一般一个晚上就可以速通一个小领域的最新文章。我自己测试了两天了。
>
> 祝大家在这个极速变化的时代中，能够和AI一起进化！
>
> 这段代码虽然不多，但整个流程走通也花了我近一周的时间，今天分享给大家。
>
> 不知道能不能用这个工具，实现我小时候的梦想-- 如果每个中国人给我一块钱，那我就发财了 哈哈~
>
> 言归正传，不强制付费，但是真的希望每个觉得能帮你节省时间的研究生，在花几块钱买API的同时，能够给我一块钱奖励，非常感谢！
>
> 您的支持，是我持续更新的动力！如果有大佬愿意多支持，也是非常欢迎的！
>
> 欢迎大家加入光荣的进化！
>
> ## 使用步骤
>
> Windows, Mac和Linux系统应该都可以
>
> python版本最好是3.9，其他版本应该也没啥问题
>
> 1. 在apikey.ini中填入你的openai key。注意，这个代码纯本地项目，你的key很安全！如果不被OpenAI封的话~
> 小白用户比较多，我直接给截图示意下可能会更好：
> <div style="text-align: center;">
>   <img src=https://user-images.githubusercontent.com/28528386/224497146-f5518553-04a2-4efa-90e6-4ac0febb8177.png width="500" height="220"/>
> </div>
>
> 2. 使用过程要保证全局代理！
> 如果客户端时clash的话，可以参考这个进行配置:
>
> <div style="text-align: center;">
>   <img src=https://user-images.githubusercontent.com/28528386/224529317-f49265d7-fb5f-4dd5-b462-930aaa0c682d.png width="500" height="350"/>
> </div>
>
> 3. 安装依赖：最好翻墙，或者用国内源。
> ``` bash
> pip install -r requirements.txt
> ```
>
> 4.1. Arxiv在线批量搜索+下载+总结： 运行chat_paper.py， 比如：
> ```python
> python chat_paper.py --query "chatgpt robot" --filter_keys "chatgpt robot" --max_results 3
> ```
>
> **注意：搜索词无法识别`-`，只能识别空格！所以原标题的连字符最好不要用！** 感谢网友提供的信息
>
> 4.2. Arxiv在线批量搜索+下载+总结+高级搜索： 运行chat_paper.py， 比如：
> ```python
> python chat_paper.py --query "all: reinforcement learning robot 2023" --filter_keys "reinforcement robot" --max_results 3
> ```
>
> 4.3. Arxiv在线批量搜索+下载+总结+高级搜索+指定作者： 运行chat_paper.py， 比如：
> ```python
> python chat_paper.py --query "ti: Sergey Levine" --filter_keys "reinforcement robot" --max_results 3
> ```
>
> 4.4. 本地pdf总结： 运行chat_paper.py， 比如：
> ```python
> python chat_paper.py --pdf_path "demo.pdf"
> ```
>
> 4.5. 本地文件夹批量总结： 运行chat_paper.py， 比如：
> ```python
> python chat_paper.py --pdf_path "your_absolute_path"
> ```
>
> B站讲解视频：[我把ChatPaper开源了！AI速读PDF论文和速通Arxiv论文](https://www.bilibili.com/video/BV1EM411x7Tr/)
>
> **注意：key_word不重要，但是filter_keys非常重要！**
> 一定要修改成你的关键词。
>
> 另外关于arxiv的搜索关键词可以参考下图：
> <div style="text-align: center;">
>   <img src=https://user-images.githubusercontent.com/28528386/224550698-f0e18bf7-f09f-40a1-a747-1d596b3edd01.png width="250" height="350"/>
> </div>
>
> 5. 参数介绍：
> ```
> [--pdf_path 是否直接读取本地的pdf文档？如果不设置的话，直接从arxiv上搜索并且下载] 
> [--query 向arxiv网站搜索的关键词，有一些缩写示范：all, ti(title), au(author)，一个query示例：all: ChatGPT robot] 
> [--key_word 你感兴趣领域的关键词，重要性不高] 
> [--filter_keys 你需要在摘要文本中搜索的关键词，必须保证每个词都出现，才算是你的目标论文] 
> [--max_results 每次搜索的最大文章数，经过上面的筛选，才是你的目标论文数，chat只总结筛选后的论文] 
> [--sort arxiv的排序方式，默认是相关性，也可以是时间，arxiv.SortCriterion.LastUpdatedDate 或者 arxiv.SortCriterion.Relevance， 别加引号] 
> [--save_image 是否存图片，如果你没注册gitee的图床的话，默认为false] 
> [--file_format 文件保存格式，默认是markdown的md格式，也可以是txt] 
> 
> parser.add_argument("--pdf_path", type=str, default='', help="if none, the bot will download from arxiv with query")
> parser.add_argument("--query", type=str, default='all: ChatGPT robot', help="the query string, ti: xx, au: xx, all: xx,")    
> parser.add_argument("--key_word", type=str, default='reinforcement learning', help="the key word of user research fields")
> parser.add_argument("--filter_keys", type=str, default='ChatGPT robot', help="the filter key words, 摘要中每个单词都得有，才会被筛选为目标论文")
> parser.add_argument("--max_results", type=int, default=1, help="the maximum number of results")
> parser.add_argument("--sort", default=arxiv.SortCriterion.Relevance, help="another is arxiv.SortCriterion.LastUpdatedDate")    
> parser.add_argument("--save_image", default=False, help="save image? It takes a minute or two to save a picture! But pretty")
> parser.add_argument("--file_format", type=str, default='md', help="导出的文件格式，如果存图片的话，最好是md，如果不是的话，txt的不会乱")
> ```
>
> ## 解析示例
>
> <details><summary><code>查看解析结果</code></summary>
> <h2>Paper:1</h2>
> <ol>
> <li>
> <p>Title: Diffusion Policy: Visuomotor Policy Learning via Action Diffusion 中文标题: 通过行为扩散的视觉运动策略学习</p>
> </li>
> <li>
> <p>Authors: Haonan Lu, Yufeng Yuan, Daohua Xie, Kai Wang, Baoxiong Jia, Shuaijun Chen</p>
> </li>
> <li>
> <p>Affiliation: 中南大学</p>
> </li>
> <li>
> <p>Keywords: Diffusion Policy, Visuomotor Policy, robot learning, denoising diffusion process</p>
> </li>
> <li>
> <p>Urls: http://arxiv.org/abs/2303.04137v1, Github: None</p>
> </li>
> <li>
> <p>Summary:</p>
> </li>
> </ol>
> <p>(1): 本文研究的是机器人视觉动作策略的学习。机器人视觉动作策略的学习是指根据观察到的信息输出相应的机器人运动动作，这一任务较为复杂和具有挑战性。</p>
> <p>(2): 过去的方法包括使用高斯混合模型、分类表示，或者切换策略表示等不同的动作表示方式，但依然存在多峰分布、高维输出空间等挑战性问题。本文提出一种新的机器人视觉运动策略模型 - Diffusion Policy，其结合了扩散模型的表达能力，克服了传统方法的局限性，可以表达任意分布并支持高维空间。本模型通过学习代价函数的梯度，使用随机Langevin动力学算法进行迭代优化，最终输出机器人动作。</p>
> <p>(3): 本文提出的机器人视觉动作策略 - Diffusion Policy，将机器人动作表示为一个条件去噪扩散过程。该模型可以克服多峰分布、高维输出空间等问题，提高了策略学习的表达能力。同时，本文通过引入展望控制、视觉诱导和时间序列扩散变换等技术，继续增强了扩散策略的性能。</p>
> <p>(4): 本文的方法在11个任务上进行了测试，包括4个机器人操纵基准测试。实验结果表明，Diffusion Policy相对于现有的机器人学习方法，表现出明显的优越性和稳定性，平均性能提升了46.9%。</p>
> <p><img alt="Fig" src="https://gitee.com/chatpaper/chatpaper/raw/master/images/Diffusion Policy: Visuomotor Policy Learning via Action Diffusion-2023-03-08-21-55-53.jpeg" /></p>
> <p>7.Methods:
> 本文提出的视觉动作策略学习方法，即Diffusion Policy，包括以下步骤：</p>
> <p>(1) 建立条件去噪扩散过程：将机器人动作表示为一个含有高斯噪声的源的条件随机扩散过程。在该过程中，机器人状态作为源，即输入，通过扩散过程输出机器人的运动动作。为了将其变为条件随机扩散模型，我们加入了代价函数，它在路径积分中作为条件。</p>
> <p>(2) 引入随机Langevin动力学：将学习代价函数的梯度转换为基于随机Langevin动力学的迭代优化问题。该方法可以避免显示计算扩散过程，并且可以满足无导数优化器的要求，使其受益于渐近高斯性质以及全局收敛性质。</p>
> <p>(3) 引入扩散策略增强技术：使用展望控制技术，结合决策网络，对由扩散产生的动作进行调整，从而增强策略的性能。同时，引入视觉诱导以及时间序列扩散变换，来进一步提高扩散策略的表达能力。</p>
> <p>(4) 在11个任务上进行测试：测试结果表明，该方法相对于现有的机器人学习方法，在机器人操纵基准测试中表现出明显的优越性和稳定性，平均性能提升了46.9%。</p>
> <p>7.Conclusion: </p>
> <p>(1):本文研究了机器人视觉动作策略的学习方法，提出了一种新的机器人视觉运动策略模型 - Diffusion Policy，通过引入扩散模型的表达能力，克服了传统方法的局限性，可以表达任意分布并支持高维空间。实验结果表明，该方法在11个任务上均表现出明显的优越性和稳定性，相对于现有机器人学习方法，平均性能提高了46.9%，这一研究意义巨大。</p>
> <p>(2):虽然本文提出了一种新的机器人视觉动作策略学习方法，并在实验中取得了良好的表现，但该方法的优化过程可能比较耗时。此外，该方法的性能受到多种因素的影响，包括演示的质量和数量、机器人的物理能力以及策略架构等，这些因素需在实际应用场景中加以考虑。</p>
> <p>(3):如果让我来推荐，我会给这篇文章打9分。该篇文章提出的Diffusion Policy方法具有较高的可解释性、性能表现良好、实验结果稳定等优点，能够为机器人视觉动作策略学习等领域带来很大的启发与借鉴。唯一的不足可能是方法的优化过程需要投入更多的时间和精力。</p>
> </details>
>
> ## 使用技巧
>
> 快速刷特定关键词的论文，不插图的话，每张篇文章需要花一分钟，阅读时间差不多一分钟。
>
> 本项目可以用于跟踪领域最新论文，或者关注其他领域的论文，可以批量生成总结，最大可生成1000（如果你能等得及的话）。
> 虽然Chat可能有瞎编的成分，但是在我的规范化提问的框架下，它的主要信息是保熟的。
>
> 数字部分需要大家重新去原文检查！
>
> 找到好的文章之后，可以精读这篇文章。
>
> 推荐另外两个精读论文的AI辅助网站：https://typeset.io/ 和chatpdf。
> 我的教程： [强化学徒：论文阅读神器SciSpace(Typeset.io)测评-和AI一起进化](https://zhuanlan.zhihu.com/p/611874187)
>
> 和上面这两个工具的主要优势在于，ChatPaper可以批量自动总结最新论文，可以极大的降低阅读门槛，尤其是我们国人。
> 缺点也很明显，ChatPaper没有交互功能，不能连续提问，但我觉得这个重要性不大~
>
> ## 常见报错
>
> 1. pip 安装错误：
> ![pip error](https://user-images.githubusercontent.com/28528386/224949301-5871610a-dd8e-4c44-b412-174ce593ad3d.png)
>
> 推荐关掉梯子，使用国内源下载：
> ```bash
> pip install -r requirements.txt -i  http://pypi.douban.com/simple  --trusted-host pypi.douban.com
> ```
>
> 2. 调用openai的chatgpt api时出现APIConnectionError, 如何解决?
> 参考知乎回答：
> https://www.zhihu.com/question/587322263/answer/2919916984
>
> 直接在chat_paper.py里加上
>
> os.environ["http_proxy"] = "http://<代理ip>:<代理端口>"
> os.environ["https_proxy"] = "http://<代理ip>:<代理端口>"
>
> 代理ip和端口需要你在Windows系统里面查找。
> ![2333](https://user-images.githubusercontent.com/28528386/224496999-1a8a7946-00aa-4d51-9f18-45bdde4215b9.png)
>
>
> 3. API被OpenAI禁了的报错：
>
> ![3222](https://user-images.githubusercontent.com/28528386/224464704-80f9b010-14f8-4df0-9635-cdfcb2faea51.png)
>
> 这种情况只能用新号了。另外一定要注意一个号尽量不要多刷，节点一定要靠谱，千万不能用大陆和香港的节点，用了就寄。
>
> ## 项目致谢
>
> 本项目三天一千star的时刻，我补一下对这个项目的促成的各位致谢！
> 1. 群友和实验室同学的技术支持和大量转发！还有张老板和化老板的出谋划策。
> 2. [Siyuan](https://github.com/HouSiyuan2001)同学在我开始项目的时候，分享了两个核心函数，节省了很多时间。
> 3. [rongsheng](https://github.com/WangRongsheng)同学的在线网站，让这个项目可以使得更多的技术小白，可以尝试。
> 4. [Arxiv](https://github.com/lukasschwab/arxiv.py)的作者提供的好用的arxiv论文下载包。
> 5. [PyMuPDF](https://github.com/pymupdf/PyMuPDF)提供良好的PDF解析工具。让整个信息流得以打通。
> 6. OpenAI一方面做出了杰出的AI，另外一方面禁了我们国家，搞得我都不知道该怎么写这行。
> 7. 感谢Ex-ChatGPT的作者分享的各种ChatGPT的开发细节，开发过程中学习良多。另外给计算机专业的佬们，推荐这款非常强大的开源工具：
> [Ex-ChatGPT](https://github.com/circlestarzero/EX-chatGPT) 是一个强大的工具平台，能让 ChatGPT 能够调用外部 API，例如 WolframAlpha、Google 和 WikiMedia，以提供更准确和及时的答案。
> 江湖人称 GoogleChat.
> 8. 最后感谢GitHub官方，帮我们这个项目列入了[热榜第五](https://github.com/trending)，获得了大量的关注！
>
> ## 赞助我们
>
> 感谢您对我们ChatPaper辅助论文写作工具开发项目的关注和支持！我们的项目旨在为科研人员提供一款高效、智能的辅助工具，帮助他们更便捷地完成论文总结等工作，提升学术水平和研究成果的质量。
> 与此同时，我们也欢迎来自各界的赞助和支持，这将帮助我们更快地推进项目的开发和完善，并且可以使我们的工具更加符合用户需求。如果您有意向对我们的项目进行赞助，我们将不胜感激，并期待与您的合作！
> 再次感谢您的关注和支持，愿我们的项目能够为您和更多的科研人员带来便捷和帮助。
>
> <div style="text-align: center;">
>   <img src=https://user-images.githubusercontent.com/28528386/224892765-d22a36ad-7bd6-41ed-9e89-f7fe5e88944b.png width="200" height="250"/>
> </div>
>
> <div style="text-align: center;">
>   <img src=https://user-images.githubusercontent.com/28528386/224335122-1e87eb7b-a922-4c2f-b2aa-9612f62a6314.jpg width="200" height="250"/>
> </div>
>
> ## Starchart
>
> [![Star History Chart](https://api.star-history.com/svg?repos=kaixindelele/ChatPaper&type=Date)](https://star-history.com/#kaixindelele/ChatPaper&Date)
>
> ## Contributors
>
> <a href="https://github.com/kaixindelele/ChatPaper/graphs/contributors">
>   <img src="https://contrib.rocks/image?repo=kaixindelele/ChatPaper" />
> </a>
