# 前言

> 原文：<https://datascienceatthecommandline.com/2e/preface.html>
> 
> 贡献者：[Ting-xin](https://github.com/Ting-xin)

数据科学是一个令人兴奋的工作领域，相对而言它还比较年轻。不幸的是，许多人和许多公司都认为，你需要新技术来解决数据科学带来的问题。然而，正如这本书所展示的，许多事情可以通过使用命令行来完成，有时它是一种更有效的方式。

在我读博士期间，我逐渐从使用微软 Windows 转向使用 Linux。因为这种过渡一开始有点吓人，所以我先把两个操作系统安装在一起（称为双启动）。在 Microsoft Windows 和 Linux 之间来回切换的冲动最终小时了，甚至在某个时候我开始摆弄 Arch Linux 了，它允许你从头开始构建自己的 Linux 机器。从 Linux 能得到的只是命令行，至于怎么做完全就看你自己了。出于需要，我很快就能非常自如地使用命令行了。最终，随着空闲时间变得越来越少，并且由于 Linux 发行版 Ubuntu 的易用性和庞大的社区，我最终选择了它作为我的操作系统，但是命令行仍然是我花费时间最多的地方。 

事实上在不久之前，我就意识到命令行不仅仅是用来安装软件、配置系统和搜索文件的。我开始学习诸如`cut`、`sort`和`sed`之类的工具。这些都是命令行工具的例子，它们将数据作为输入，对其进行处理，并打印结果。Ubuntu 自带了其中一些小工具，当我意识到了利用这些小工具的潜力，我就被深深地吸引住了。

在获得博士学位后，我成为了一名数据科学家，我就想尽可能多地使用命令行这种方法来做数据科学。多亏了一些新的开源命令行工具，包括`xml2json`、`jq`和`json2csv`，我甚至能够使用命令行来完成抓取网站和处理大量 JSON 数据等任务。

2013 年 9 月，我决定写一篇名为[数据科学的七个命令行工具](http://www.jeroenjanssens.com/2013/09/19/seven-command-line-tools-for-data-science.html)的博客（译者：相关博客的内容是几个命令行工具的简要用法）。令我惊讶的是，这篇博文引起了相当多的反响，并且我收到了很多关于其他命令行工具的建议。于是我开始有了一个想法，我是不是可以把这篇博文扩充成一本书？大约 10 个月后，我在许多有才华的人的帮助下（见致谢），给出了这个问题的答案——YES！

我分享这个故事并不是因为我想让你该知道这本书是怎么来的，而是因为我想表明一个事实：我也必须学习命令行。因为命令行与使用图形用户界面有很大的不同，所以它一开始看起来很吓人。但如果我能学会，那你应该也可以。不管你当前的操作系统是什么，也不管你当前如何处理数据，当你读完这本书后，你将能够以命令行的方式开展数据科学。如果您已经熟悉了命令行，即使说你熟的做梦都是 Shell 编程了，但是你仍然有可能发现一些有趣的技巧或命令行工具，用于你的下一个数据科学项目。

## 对这本书有什么期待

在本书中，我们将获取、清理、探索和建模大量的数据。这本书并不是关于如何让这些数据科学任务中变得更合理。这个领域现在已经有了很好的资源了，例如，何时应用哪种统计测试、如何更好地将数据可视化。相反，这本书旨在通过教你如何在命令行中执行这些数据科学任务，从而使你更有效率和生产力。

虽然这本书讨论了 90 多种命令行工具，但最重要的不是工具本身。一些命令行工具已经存在了很长时间，而另一些将被更好的工具所取代。就在你阅读这篇文章的时候，新的命令行工具也许正在诞生。这些年来，我发现了许多令人惊奇的命令行工具。不幸的是，其中一些发现得太晚，没有收入书中。简而言之，命令行工具来来去去，但是没关系，随它去吧。

最重要的是如何使用工具、管道和数据的基本理念。大多数命令行工具只做一件事并把它做得很好。这句话是 Unix 哲学的一部分，也将在整本书中多次出现。一旦你熟悉了命令行，知道如何组合使用命令行工具，你甚至可以创建新的命令行工具，这也意味着你已经发展了一项宝贵的技能。

## 第二版的变化

虽然命令行作为一项技术和一种工作方式是不过时的，但第一版中讨论的一些工具要么已经被更新的工具取代（例如，`csvkit`几乎已经被`xsv`取代），要么被它们的开发人员放弃（例如，`drake`），或者说它们已经是次优的选择（例如，`weka`)。自 2014 年 10 月第一版出版以来，我学到了很多东西，要么是通过我自己本身的经历，要么是来自读者有用的反馈。尽管这本书非常的小众，因为它位于两个学科的交叉点，但数据科学界仍然对它保持着稳定的兴趣，我几乎每天都收到的许多积极的消息就证明了这一点。通过更新第一版，我希望能让这本书至少再保持五年的相关性。以下是我所做的非详尽的改变清单：

*   我尽可能把`csvkit`换成了`xsv`，`xsv`是处理 CSV 文件的一种更快的替代方式
*   在 2.2 和 3.2 节中，我用 Docker 映像替换了 VirtualBox 映像，Docker 是一种比 VirtualBox 更快、更轻量级的运行隔离环境的方式
*   我现在使用`pup`而不是`scrape`来处理 HTML`scrape`是我自己创造的一个 Python 工具，`pup`速度更快，功能更多，更易于安装
*   第六章已经从头重写，我现在用`make`而不是`drake`来做项目管理，`drake`不再维护，`make`更加成熟，并且非常受开发者欢迎
*   我把`Rio`换成了`rush`，`Rio`是我自己创建的一个笨拙的 Bash 脚本，`rush`是一个 R 包，它是从命令行使用 R 的一种更加稳定和灵活的方式
*   [在第九章](https://datascienceatthecommandline.com/2e/chapter-9-modeling-data.html#chapter-9-modeling-data)中，我用 Vowpal Wabbit（`vw`）替换了 Weka 和 BigML，Weka 很旧，从命令行使用它的方式也很笨拙。BigML 是一个商业 API，我不想再依赖它。Vowpal Wabbit 是一个非常成熟的机器学习工具，它开始在雅虎开发，现在在微软。
*   第十章是关于将命令行集成到现有工作流的全新章节，包括 Python、R 和 Apache Spark。在第一版中，我提到过命令行可以很容易地与现有的工作流集成，但我从未深入探讨过，本章解决了这个问题

## 如何阅读这本书

总的来说，我建议你以线性方式阅读这本书。一旦我在前面介绍了一个概念或命令行工具，我就有可能在后面的章节中用到它。例如，在第九章中，我大量使用了在第八章中广泛介绍的并行。

数据科学是一个广泛的领域，与许多其他领域都都有交叉，比如编程、数据可视化和机器学习。因此，这本书触及了许多有趣的话题，但遗憾的是，这些话题无法得到充分的讨论。在全书中，每一章的结尾都有进一步探索的建议。为了跟上本书的进度，并不要求阅读这些材料，但当你有兴趣时，你就知道还有很多东西要学。

## 这本书是写给谁的

本书只对你做了一个假设：你在与数据打交道。你目前正在使用哪种编程语言或统计计算环境并不重要。本书从一开始就解释了所有必要的概念。

无论你的操作系统是微软的 Windows，macOS，还是某种类型的 Linux，这些都无所谓。本书附带一个 Docker 镜像，这是一个易于安装的虚拟环境，它允许你在与本书相同的环境中运行命令行工具并跟随代码示例。你不必浪费时间去弄清楚如何安装所有的命令行工具和它们的依赖关系。

这本书包含了一些 Bash、Python 和 R 的代码，所以如果你有一些编程经验的话会很有帮助，你也不一定非要跟着例子走。

## 本书中使用的惯例

本书使用了以下排版惯例：

*Italic*

表示新的术语、URL、目录名和文件名。

`Constant width`

用于代码和命令，以及在段落中引用命令行工具及其选项。

`Constant width bold`

显示应由用户按字面意思输入的命令或其他文本。

> This element signifies a tip or suggestion.


> This element signifies a general note.


> This element indicates a warning or caution.


## 承认

### 第二版（2021）致谢

自第一版问世以来，已经过去了七年。在这段时间里，特别是在过去 13 个月里，许多人帮助了我。没有他们，我就永远无法写出第二版。

我再次有幸与 O'Reilly 公司中的三位出色的编辑合作。我要感谢 "拥抱最后期限 "的 Sarah Grey、"全力以赴 "的 Jess Haberman 和 "顺其自然 "的 Kate Galloway。在他们不可思议的帮助下，我能够最后期限前完成，并且在关键时刻心无旁骛，最终放手其它事。我还要感谢他们的同事：Angela Rufino, Arthur Johnson, Cassandra Furtado, David Futato, Helen Monroe, Karen Montgomery, Kate Dullea, Kristen Brown, Marie Beaugureau, Marsee Henon, Nick Adams, Regina Wilkinson, Shannon Cutt, Shannon Turlington, and Yasmina Greco, 是他们让我与 O'Reilly 公司的合作变得如此愉快。

尽管有一个自动化的程序来执行代码并将结果粘贴回来（感谢 R Markdown 和 Docker），但我能够犯的错误数量还是令人印象深刻。感谢 Aaditya Maruthi、Brian Eoff、Caitlin Hudon、Julia Silge、Mike Dewar 和 Shane Reustle 极大地减少了这个数字。当然，留下的任何错误都是我的责任。

Marc Canaleta 值得我们特别感谢。2014 年 10 月，在第一版问世后不久，马克邀请我为他在巴塞罗那 Social Point 的团队举办了为期一天的关于命令行的数据科学的研讨会。我们都不知道，接下来会有很多研讨会。这最终促使我成立了自己的公司：数据科学研讨会。每次授课，我都能学到新东西。他们可能不知道，但每个学生都以这样或那样的方式对这本书产生了影响。我对他们说：谢谢你们。我希望我可以在很长一段时间内教书。

吸引人的对话、精彩的建议和热情的拉动请求。我非常感谢以下慷慨人士的每一个贡献：Adam Johnson, Andre Manook, Andrea Borruso, Andres Lowrie, Andrew Berisha, Andrew Gallant, Andrew Sanchez, Anicet Ebou, Anthony Egerton, Ben Isenhart, Chris Wiggins, Chrys Wu, Dan Nguyen, Darryl Amatsetam, Dmitriy Rozhkov, Doug Needham, Edgar Manukyan, Erik Swan, Felienne Hermans, George Kampolis, Giel van Lankveld, Greg Wilson, Hay Kranen, Ioannis Cherouvim, Jake Hofman, Jannes Muenchow, Jared Lander, Jay Roaf, Jeffrey Perkel, Jim Hester, Joachim Hagege, Joel Grus, John Cook, John Sandall, Joost Helberg, Joost van Dijk, Joyce Robbins, Julian Hatwell。Karlo Guidoni, Karthik Ram, Lissa Hyacinth, Longhow Lam, Lui Pillmann, Lukas Schmid, Luke Reding, Maarten van Gompel, Martin Braun, Max Schelker, Max Shron, Nathan Furnal, Noah Chase, Oscar Chic, Paige Bailey, Peter Saalbrink, Rich Pauloo, Richard Groot, Rico Huijbers, Rob Doherty, Robbert van Vlijmen, Russell Scudder, Sylvain Lapoix, TJ Lavelle, Tan Long, Thomas Stone, Tim O'Reilly, Vincent Warmerdam, and Yihui X。

在本书中，特别是在脚注和附录中，你会发现有数百个名字。这些名字属于许多工具、书籍和其他资源的作者，而本书正是基于这些资源。我非常感谢他们的辛勤工作，无论这些工作是在 50 年前还是 50 天前完成的。

最重要的是，我要感谢我的妻子 Esther、我的女儿 Florien 和我的儿子 Olivier，他们每天都在提醒我什么才是真正重要的。我保证要过几年才会开始写第三版。

### 第一版致谢 (2014)

首先，我要感谢 Mike Dewar 和 Mike Loukides，他们相信我在 2013 年 9 月写的博客文章[七个数据科学命令行工具](http://jeroenjanssens.com/2013/09/19/seven-command-line-tools-for-data-science.html)可以扩展成一本书。

特别感谢我的技术审查员 Mike Dewar、Brian Eoff 和 Shane Reustle 阅读了各种草稿，仔细测试了所有命令，并提供了宝贵的反馈。他们的努力极大地改进了这本书，留下的任何错误都是我的责任。

我有幸与三位了不起的编辑一起工作：Ann Spencer, Julie Steele, 和 Marie Beaugureau。感谢你们的指导，感谢你们成为 O'Reilly 公司众多优秀人才的联络人。这些人包括 Laura Baldwin, Huguette Barriere, Sophia DeMartini, Yasmina Greco, Rachel James, Ben Lorica, Mike Loukides, and Christopher Pappas。还有许多人我没有见过，因为他们在幕后操作。他们共同确保了与 O'Reilly 公司的合作确实是一种乐趣。

本书讨论了 80 多个命令行工具。不用说，没有这些工具，这本书首先就不会存在。因此，我非常感谢所有创造和贡献这些工具的作者。遗憾的是，完整的作者名单太长了，无法在此列出；在附录中提到了他们。特别感谢 Aaron Crow、Jehiah Czebotar、Christoph Groskopf、Dima Kogan、Sergey Lisitsyn、Francisco J. Martin 和 Ole Tange 提供的帮助，他们的命令行工具令人惊叹。

Eric Postma 和 Jaap van den Herik 在我的博士课程期间指导过我，值得特别感谢。在五年的时间里，他们给我上了很多课。尽管写一本技术书与写一篇博士论文有很大的不同，但其中许多教训在过去九个月里也被证明是非常有帮助的。

最后，我要感谢我在 YPlan 的同事，我的朋友，我的家人，特别是我的妻子 Esther，感谢他们支持我，并在适当的时候把我从命令行的工作中拉出来。
