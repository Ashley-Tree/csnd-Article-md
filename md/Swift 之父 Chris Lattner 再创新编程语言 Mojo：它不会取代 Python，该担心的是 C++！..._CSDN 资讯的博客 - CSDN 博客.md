> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [csdnnews.blog.csdn.net](https://csdnnews.blog.csdn.net/article/details/132613776?spm=1000.2115.3001.5926)

> 整理 | 屠敏出品 | CSDN（ID：CSDNnews）在 AI 带来全新开发范式之际，开发者底层工具发生了巨大变化，随之而来的是基础软件之编程语言领域也涌现出不少新面孔，Mojo 便是其中一个。

![](https://img-blog.csdnimg.cn/img_convert/3841b3868959c6fd5c728685bfaad054.gif)

整理 | 屠敏  

出品 | CSDN（ID：CSDNnews）

在 AI 带来全新开发范式之际，开发者底层工具发生了巨大变化，随之而来的是基础软件之[编程语言](https://so.csdn.net/so/search?q=%E7%BC%96%E7%A8%8B%E8%AF%AD%E8%A8%80&spm=1001.2101.3001.7020)领域也涌现出不少新面孔，Mojo 便是其中一个。

相信一直身处技术圈的很多从业者对 Mojo 也有所耳闻，这款编程语言自诞生之日起便自带光环，它是由 Swift 之父、[编译器](https://so.csdn.net/so/search?q=%E7%BC%96%E8%AF%91%E5%99%A8&spm=1001.2101.3001.7020)大神 Chris Lattner 背后的初创团队开发，在今年 5 月宣称 “比 Python 快 35000 倍” 的立场后惊艳亮相。

![](https://img-blog.csdnimg.cn/img_convert/ea4d8751b1c99182a28d60bdfe00bcd5.png)

如今仅仅几个月过去，旨在成为 AI 开发者的全新编程语言 Mojo 背后的开发商 Modular 备受资本的青睐，拿下 1 亿美元的融资。

这也再一次证明，在技术圈中，要论最火热的领域，无疑还属 AI。

**![](https://img-blog.csdnimg.cn/img_convert/9b29ed329db63e138d4936c432666065.png)**

**Mojo 背后的 Modular 公司获得 1 亿美元融资**

在谈及 Mojo 如何成为 AI 时代 “新利器” 之前，我们不妨来了解一下其背后的公司 Modular。

Modular 是 Chris Lattner 和 AI 领域专家 [Tim](https://so.csdn.net/so/search?q=Tim&spm=1001.2101.3001.7020) Davis 于 2022 年 1 月共同建立的 AI 初创公司。

众所周知，Chris Lattner 是 LLVM 项目的主要发起人与作者之一，他曾受雇于苹果公司，为苹果电脑开发应用程序系统，在这家公司任职的多年间，先后发起 Clang 项目、设计 Swift 编程语言，而后功成身退，选择离开苹果。又因认为「Swift 核心团队会议中的存在 “有毒环境”」，而选择正式退出 Swift 核心开发团队。

离开之后，Chris 进入特斯拉，负责自动驾驶软件开发；又在 2017 年 8 月加入了聚焦深度学习和人工智能研发的 Google Brain 团队；2020 年，Chris 加入了专注于 RISC-V 架构的芯片初创公司 SiFive，任职平台工程高级副总裁。

彼时在 Google 工作期间，他相识了为 TensorFlow 做开发的 AI 专家 Tim Davis，而后两人带着对「AI 未知的探索」于 2022 年创建 Modular。

谈及成立 Modular 的初衷，Lattner 和 Davis 都认为人工智能受到了过于复杂和分散的技术基础设施的阻碍，因此想要通过创立 Modular 来专注于消除大规模构建和维护人工智能系统的复杂性。

现如今他们对这一领域的探索受到了资本的支持，根据 Modular 官方发布的公告显示，其最新获得 1 亿美元融资由 General Catalyst 领投、Google Ventures、SV Angel、Greylock、Factory 等参与其中。

现任 Mojo CEO Chris Lattner 表示，Modular 的融资总额累计达到了 1.3 亿美元，所得款项将用于产品扩展、硬件支持和 Modular 编程语言的扩展。

![](https://img-blog.csdnimg.cn/img_convert/db61ff493cd112d0e26472586b956823.png)

**AI 时代的第一步——构建 AI 引擎**  

作为 AI 新时代的探索者，初创公司 Modular 为降低构建 AI 的复杂性，做出的第一步尝试就是研发了一个 AI 引擎，试图提高 AI 模型在 CPU 上的推理性能，同时节省成本。

值得关注的是，Modular 的引擎与现有的云环境、机器学习框架（如 Google 的 TensorFlow 和 Meta 的 PyTorch）以及其他 AI 加速器引擎兼容，只是目前该引擎仍处于内部预览状态，可让开发人员导入经过训练的模型，并比在原生框架上运行速度提高 7.5 倍。

Davis 表示，Modular AI 引擎在功能上是 AI 框架的新后端，可直接替代 PyTorch 和 TensorFlow 现有的执行引擎。

虽然当前 Modular 的引擎适用于人工智能推理，但它计划在未来扩展到训练工作负载。

![](https://img-blog.csdnimg.cn/img_convert/2c8d3c7694b1fcb6915d1d99f262bfe4.png)

**降低 AI 复杂度的第二步——开发一款全新的编程语言 Mojo**

Modular 想要解决 AI 时代的另一个挑战是 AI 编程语言。

就目前而言，相比不少开发者经常使用 [Python](https://so.csdn.net/so/search?q=Python&spm=1001.2101.3001.7020) 编程语言来开发 AI 模型，因为它相对简单，还拥有简洁的语法。与其他语言相比，Python 可以更轻松地实现神经网络。  

然而，不容忽视的是，Python 可以保持简单与简洁的背后是以性能为代价的，这意味着用 Python 编写的程序可能很慢。

与此同时，Python 面临的挑战是它有一些技术限制，比如全局解释器锁无法进行大规模并行化风格的执行。因此，当开发者处理更大的工作负载时，它们需要自定义内存布局，并且必须切换到 C++ 以获得性能并能够正确扩展。

在 Modular 团队来看，AI 时代在使用 Python 开发的同时，总是需要依赖 C、Rust 等其他高性能语言来实现特定性能的代码部分，总需要两种语言未免太为复杂，如今 Mojo 旨在解决这些问题。

Mojo 可以视为是 Python 的一个超集，它不需要开发人员了解 Python 和 C++，而是提供了一种可以支持现有 Python 代码并具有所需性能和可扩展性的单一语言。

其中，Mojo 提供了类似于 Python 的内存安全机制，但不会对性能产生重大影响。此外，它减少了确保 AI 模型在多种类型芯片上良好运行所需的手动编码量。

![](https://img-blog.csdnimg.cn/img_convert/36c1acd925c44194ebbe33572d209e35.png)

**Mojo 会取代 Python 吗？Mojo 之父：别担心，它对标的是 C++**

那么，Mojo 真的如官方所言，比 Python 快 35000 倍吗？

![](https://img-blog.csdnimg.cn/img_convert/af65b56fa08a06e29da613b3bff4a562.png)

需要了解的是，目前 Mojo 并未完全对外开放。Chris Lattner 表示，Mojo 的公开版本将在九月初上线。

![](https://img-blog.csdnimg.cn/img_convert/6a245e86bf84cfbfe85e12450407f2b2.png)

因此，具体的性能如何，可能还需要等待些时日才能知晓。

不过，对于现在要想要尝鲜的用户，Modular 通过 Modular Playground 提供对 Mojo 的早期访问，Modular Playground 是一个在 Modular 服务器上运行的基于 Web 的 Jupyter Notebook 环境，这也意味着你可以通过任何带有网络浏览器的计算机运行 Mojo。

根据 Mojo 的文档显示，Mojo 实现了系统级的优化和灵活性，能以 Python 无法实现的方式释放任何设备的性能。此前，Modular 在发布主题演讲中展示的 Mondelbrot 基准测试在 AWS r7iz.metal-16xl 机器上运行，得出了 Mojo 可以比 Python 快 35000 倍的概念。

而在其最新官方博客（https://www.modular.com/blog/how-mojo-gets-a-35-000x-speedup-over-python-part-1）中，Modular 开发团队采用了 Mandelbro 再次测试了 Mojo 的性能，最终得出：与 Python 相比，即使在不更改代码的情况下将代码从 Python 迁移到 Mojo，也能实现 46 倍的加速。

![](https://img-blog.csdnimg.cn/img_convert/c9910ea22a3f7cacdf4deeb29d8d3a69.png)

所以说，3500 倍是一个很大的数字，即使每台机器都无法保证这些数字，也并不意味着 Mojo 就是失败的。它的的确确有效地提升了 Python 的速度。

至此，有网友开始担心，「Python 能渡过难关吗？对于开发者而言，Mojo 会取代 Python 吗？」

![](https://img-blog.csdnimg.cn/img_convert/e875c3f8425090f1196756f83215622a.png)

对此，Mojo 之父 Chris Lattner 于近日正面回应道，「Mojo 对 Python 没有威胁：**它提升了 Python 的水平并赋予 Python 程序员超能力**。如果有人应该害怕的话，那就应该是 C++ ，这种很难使用加速器语言。Python 是开发人员所喜爱的：当你需要性能时，C++ 基本上是一种实用的必要之恶。」

![](https://img-blog.csdnimg.cn/img_convert/0d9ef309fd7d57a7d24a06aad1c7b605.png)

最后，在 AI 时代，作为开发者的你所使用的开发工具是否有变化？亦或者对于全新的 AI 开发工具持有什么样的看法？  

参考：

https://www.modular.com/blog/how-mojo-gets-a-35-000x-speedup-over-python-part-1

https://venturebeat.com/ai/modular-looks-to-boost-ai-mojo-with-100m-funding-raise/

https://techcrunch.com/2023/08/24/modular-raises-100m-for-ai-dev-tools/

![](https://img-blog.csdnimg.cn/img_convert/10a8079dc080b1e7909cb0e5c4b742ce.gif)

欢迎「**扫描下方小程序码**」或点击文末「**阅读原文**」，参与 CSDN 发起的《2023 AI 开发者生态调查问卷》！

![](https://img-blog.csdnimg.cn/img_convert/556908afbe2e111690d00cff54c763f2.png)

**推荐阅读：**

▶华为 Mate 60 Pro 未发先售 6999 元；iPhone 15 也要来了；Rust 1.72.0 发布 | 极客头条

▶HuggingFace 机器学习总监、Grafana Labs 团队与你相约 KubeCon 2023！

▶数据库战争 2.0：为什么每个人都在开发数据库？