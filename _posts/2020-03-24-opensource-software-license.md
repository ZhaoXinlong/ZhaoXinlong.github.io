---
layout: post
title: 从“中国GPL诉讼第一案”聊聊开源软件许可证
pid: 2020032401
tags: [开源, 官司]
excerpt_separator: <!--more-->
---

![图片](/uploads/2020/03/01-grassland.jpeg)

2020 年 3 月摄于北京奥林匹克森林公园


说起柚子（北京）科技有限公司，可能没多少人知道。要说 APICloud，那估计听说过的人就多得多了。APICloud在2018年完成了近亿元人民币的B轮融资，由复兴领头。


![图片](/uploads/2020/03/02-youzi.png)

<!--more-->

中国判决文书网是国内法院判决文书的官方展示平台，有接近 9000 万篇法律文书。其中一个案例是数字天堂（北京）网络技术有限公司起诉柚子（北京）科技有限公司。柚子科技在网站提供了 APICloud 软件的下载，数字天堂在网站提供了HBuilder.window软件的下载。数字天堂认为 APICloud  1.1.12软件抄袭了HBuilder.window.5.5.0	三个插件的源代码。证据之一是 APICloud  1.1.12 的ResetPwdll.dll文件属性显示的数字签名是“数字天堂（北京）网络技术有限公司”。这个判例在2015年一审的结果是柚子科技赔偿数字天堂146万，在2018年二审更改为71万元。

这个例子和开源软件许可证有什么关系呢？主要是在庭审中的双方举证。

一审判决书的内容显示，柚子科技认为“原告的HBuilder软件是GPL协议下的开源软件分支。根据GPL协议的规定，原告的HBuilder软件使用了受GPL协议保护的第三方软件源程序，其软件亦为开源软件，任何第三方有权在GPL协议授权下使用其代码并构建衍生软件产品。因此，被诉APICloud的软件中对于原告软件相关源程序的使用**无需经过原告许可**，二被告的被诉行为未侵犯原告的著作权……原被告双方的涉案软件**均为免费软件**”。（我这里直接全文引用判决书内容）。

这个案子也因此被部分人称为“中国 GPL 诉讼第一案”。

当然了，这个案件已经由法院做出了终审判决，尘埃落定。开源运动如火如荼，开源软件无孔不入。在当下，如何充分而优雅地利用开源软件，就是几乎所有科技公司和 CTO 不得不注意的问题。没看过合同文本就没资格谈法律，类似的，不了解开源软件许可就谈开源也无异于盲人骑瞎马、夜半临深池。

这周因为工作缘故，我学习了一些关于开源软件许可证的内容，这里做个整理和分享。主要内容包括三个方面：是不是必须有许可证、常见的许可证有哪些、如何选择许可证。

# 什么是开源软件？
有句话说的是“一流企业卖标准，二流企业卖技术，三流企业卖产品。”在这个之上，还有一个顶流企业做的事情，定概念。新事物的产生，一定是先衍生出概念，随着概念流传逐渐广泛，参与的人和企业越来越多，需要定标准；在统一标准之下，拼的是技术；在相同的技术水准之上，比的才是产品。就像是“百度一下”说的其实是用搜索引擎搜一下，而不一定是用百度搜一下；“淘宝”几乎等同于网购，而不一定是在淘宝 APP 里网购，这是最顶级的把产品做成行业概念的案例。

说回开源软件。你认为什么是开源软件？应该如何定义？现在广泛应用的开源软件的定义可以参考 OSI 确定的标准，一共 10 条，列举其中几条

1. 不受限制的自由分发/Free Redistribution
2. 代码开源/Source Code
3. 不得歧视任何个人或团体/No Discrimination Against Persons or Groups
4. 许可证不得限制其他软件/License Must Not Restrict Other Software
5. 许可证必须是技术中立的/License Must Be Technology-Neutral

……

OSI，全称 Open Source Initiative，中文译为开放源代码促进会，或开放源代码组织，是一个旨在推动开源软件发展的非盈利组织，其官网十分“正统”，直接就是 Open Source ：[https://opensource.org/](https://opensource.org/) 。

现行的各种开源软件许可证不下百种，其中经过了 OSI 认可的，相当于颁发了度了一层金，这是所有选择许可证的第一考虑因素：一定选择经过 OSI 认可的。

![图片](/uploads/2020/03/03-license-guideline.jpeg)

# 什么是开源软件许可证
开源软件许可证就是与OSI的开源软件定义一直的许可证，简言之，开源软件许可证允许软件自由使用、修改和分享（be freely used, modified, and shared）。

虽然都符合OSI的开源软件定义，但是不同的许可证对于使用、修改和分享的要求不同，因此具体使用中会有极大的差别。比如开头提到的GPL许可就被称为“病毒”，因为GPL许可证要求使用了包含 GPL代码或动态连接到 GPL 库上的软件，也必须使用GPL许可，就像病毒一样是层层传递下去的。其思想根源是开源软件应当具备自我保护和可持续发展的能力，或者更直白的说，避免吸血和白嫖。

GPL 应用最广泛和最新的是第三个版本，也就是 GPL V3 。Linux 创始人Linus Torvalds也忍不住在多个场合一在的吐槽 GPL V3，表示“GPL V3 is a nice licence but it violates everything that V2 stood for.”


![图片](/uploads/2020/03/04-Linus-Torvalds.jpeg)


GPL 还有衍生的版本 AGPL。Hadoop 领域仅存的独苗，曾经获得 Intel 7.5 亿美金投资后估值高达 41 亿美金、现在市值不到 20  亿美金的美股上市公司 Cloudera 就在去年宣布把旗下的许可证改为 GPL 系列许可的一种：AGPL-3.0。

也有一些十分任性和随意的许可证，比如我翻译为“爱咋咋地许可证”的 WTFPL（Do What The Fuck You *Want To Public License*）。这个许可文如其名，内容十分简单，风格极其粗暴，就是随便做什么都可以，我在下文截了个图。WTFPL也有着像模像样的网站[www.wtfpl.net](http://www.wtfpl.net/about/)和Wikipedia词条。

![图片](/uploads/2020/03/05-WTFPL-license.jpeg)




正因如此，对于新手来说，如何选择合适的开源软件许可证也是个比较头疼的事情。

好在全球最大的程序员同性社交网站GitHub推出了一个“如何选择许可证”的网站 [choosealicense.com](https://choosealicense.com/appendix/)，可以帮助大家轻松入门。

必须提醒的是，开源本身就是重在参与的，软件如此，许可证也是如此。所以你完全可以自己制定自己的许可证，只不过这个使用范围有多广，就要看你的推动力了。

到这里，就不能不提两种重要的许可证类别的：Permissive 和 Copyleft。Copyleft要求使用相应许可证的软件的衍生版本（正式说法是“修改及延伸版本”）也都必须保持相同的许可证。Copyleft 许可证中最广为人知的就是 GPL 了，也就是开头的判例中涉及的，也被Linus Torvalds吐槽过的。

Permissive free software licence，译为宽松自由软件许可协议条款，或宽容式自由软件许可协议条款，不要求开源软件的衍生版本继续保持相应的许可证。Permissive许可证中最广为人知的MIT许可证与BSD许可证。有时候Permissive也被称为Copyfree。

简言之，Permissive的要求更少，限制更低。

根据WhiteSource的数据，从趋势杀上也能看出，从 2012 年到 2019 年，Permissive 许可证的占比一步步反超了 Copyleft 许可证。

![图片](/uploads/2020/03/06-permissive-vs-copyleft.jpeg)


# 常见的开源软件许可证有哪些？
在 OSI 网站上经过认可的许可证已经有 96 个，未经认可的更是不计其数。可想而知的是，这些许可证中的绝大部分是无人问津的，所以我们不应该求全责备，而是先抓西瓜，放着芝麻不管。

根据WhiteSource的数据，在 2019 年各种许可证的市场占比从高到低前三名分别是 MIT、AApache-2.0 和 GPL v3。下图的 top 10 名单基本就是当前比较热门的许可证了，尤其是 GPC 的三个版本、BSD 的 2 个版本都在其中出现了。

![图片](/uploads/2020/03/07-top-OSS-license-2019.jpeg)


排名第一的 MIT 许可证确实是起源于 MIT 大学的，源自上世纪 80 年代。MIT 许可证是 Permissive 许可证的代表之一，其要求极其宽松，比如开源软件 M2IT 使用了 MIT 许可证，修改后的 M2I2T 软件可以不用 MIT 许可证，甚至可以改用 Copyleft 类型的 GPL 许可证。根据 GitHub 官方博客的数据，2015 年 GitHub 上最流行的就是 MIT 许可证，45% 的项目都用了这个许可证。

排名第二的 Apache-2.0 是由阿帕奇基金会ASF在2004年通过的。Apache-2.0不强制衍生软件使用相同的许可证，但它要求未修改部分必须应用相同许可证，并且在更改的许可文件中都必须说明做过更改。

BSD 最早是用于操作系统的名字，即 Berkeley Software Distribution。BSD 操作系统最早由加州伯克利开发和分发，现在仍然有着庞大的家族如 FreeBSD, OpenBSD, NetBSD, or DragonFly BSD。BSD 许可证已经衍生出了一系列的许可证，比如Zero-Clause BSD、3-clause BSD license 、2-clause BSD license、BSD+Patent。现在比较常用的是 3-clause BSD，这是由最早的 4-clause BSD 延伸而来的。在前面提到的 2015 年度 GitHub 官方报告中，3-clause BSD 和 2-clause BSD 的占有率分别是 4.5%和2.7%。

## Perl、PHP和Python都在用什么许可证？
说起开源软件，不得不提到开源的编程语言，比如 PHP 和 Python。

你有没有好奇过，他们使用的是什么许可证？

实际上，在开源软件许可证中有一个大类是不可复用许可证（Non-reusable licenses），这在 OSI 的网站上也单独类为一个类别的。比如 Python 编程语言的许可证就是 Python-2.0。这个 Python -2.0 可不是 Python 版本的 2.0、3.0，而是“Python License, Version 2 ”的简称。PHP 编程语言的许可证就是The PHP License 3.0 ，简称PHP-3.0。Perl 编程语言的许可证是独一份的Artistic license 2.0 (Artistic-2.0)。学术排版和印刷中广泛应用的 LaTeX 也有自己的许可证，那就是LPPL-1.3c，全称是 LaTeX Project Public License, Version 1.3c 。W3C也有自己的专用license，The W3C® SOFTWARE NOTICE AND LICENSE ，简称W3C。

# 如何选择开源软件许可证
对于大部分人来说，阮一峰在 2011 年制作的这张流程图就够用了，按照流程走下去，看看你

* 是不是允许其他人在修改源码后闭源（是：Permissive；否：Copyleft）
* 新增代码是不是需要采用同样的许可证（是：GPL，“病毒”模式传播）
* 衍生软件是否可以用你的名字促销，这是最广泛的两个 Permissive 许可证的差异，BSD 许可证不允许，而 MIT 许可证是可以的。

![图片](/uploads/2020/03/08-flowchart-by-ruanyifeng.jpeg)


对于专业人士来说，还需要更加详细和覆盖更广的表格，这就不得不用到开头提过的 GitHub 专门建立的网站 [choosealicense.com](https://choosealicense.com/appendix/) 了。该网站从 12 个方面对比了 27 中不同的许可证。如下图。这 12 各方面分别是：

1. 商业用途/Commercial use
2. 分发/Distribution
3. 修改/Modification
4. 专利授权/Patent use
5. 私用/Private use
6. 公开源码/Disclose source
7. 放置许可协议与版权信息/License and copyright notice
8. 使用网络分发/Network use is distribution
9. 使用相同协议/Same license
10. 声明变更/State changes
11. 承担责任/Liability
12. 使用商标/Trademark use



![图片](/uploads/2020/03/.jpeg)


开源协议中标注绿色为**允许，**表示允许进行这样的行为，否则可能表示不允许。

开源协议中标注蓝色为**要求，**表示使用者必须遵循的内容。

开源协议中标注红色为**禁止，**通常为作者免责协议，有时也表示明确禁止授予使用者专利或者商标使用权。

通过这个表格，我们也可以看到开源软件最大的共性就是允许商业用途、分发、修改和私有——这又回到了前面提到的 OSI 对于开源软件的定义中去了。


如果这个表格还不尽兴，想要更深一步的研究，那可能就需要去看许可证的文本了。

文章稍长，总结一下：

1. 开源软件不仅仅是代码开源，还包含自由分发、技术中立、不得歧视等原则
2. 开源软件许可证种类众多，可以分为宽松型 Permissive 如 BSD 和 MIT、严格型 Copyleft 如 GPL
3. 每个人都可以制作和发行自己的开源软件许可证，就如制作自己的开源软件一样；同时 Perl、PHP 和 Python 等是有着自己的独有许可证的
4. 如何选择开源软件许可证，可以简单的按照阮一峰提供的流程图，稍微复杂的按照 GitHub 给出的对比表格，或者自己研究许可证文本。


文中几张彩色图片引用自 WhiteSource 的报告[Open Source Licenses in 2020: Trends and Predictions](https://resources.whitesourcesoftware.com/blog-whitesource/top-open-source-licenses-trends-and-predictions)，点击查看此报告

### 链接
1. 北京知识产权法院民事判决书（2015）京知民初字第631号
2. 北京市高级人民法院民事判决书(2018)京民终471号
3. [https://www.youtube.com/watch?v=PaKIZ7gJlRU](https://www.youtube.com/watch?v=PaKIZ7gJlRU)
4. [https://www.youtube.com/watch?v=OnmWFxlG2GA](https://www.youtube.com/watch?v=OnmWFxlG2GA)
5. [https://resources.whitesourcesoftware.com/blog-whitesource/top-open-source-licenses-trends-and-predictions](https://resources.whitesourcesoftware.com/blog-whitesource/top-open-source-licenses-trends-and-predictions)
6. [https://github.blog/2015-03-09-open-source-license-usage-on-github-com/](https://github.blog/2015-03-09-open-source-license-usage-on-github-com/)
7. [https://zh.wikipedia.org/wiki/Apache%E8%AE%B8%E5%8F%AF%E8%AF%81](https://zh.wikipedia.org/wiki/Apache%E8%AE%B8%E5%8F%AF%E8%AF%81)



本文首发于微信公众号[不能不讲理（ID：jiang3dao4li3）](https://mp.weixin.qq.com/s/d9L8h4aBLx0afwgs1voEvQ)
