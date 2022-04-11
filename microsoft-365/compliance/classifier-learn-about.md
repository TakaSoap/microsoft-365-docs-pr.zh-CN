---
title: 了解可训练的分类器
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: 可训练分类器可以通过提供要查看的正反样本来识别用于标记或策略应用程序的各种类型的内容。
ms.openlocfilehash: 7da6c9ef6e26d25bb40cade4832abb7b73a4b095
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759868"
---
# <a name="learn-about-trainable-classifiers"></a>了解可训练的分类器

对内容进行分类和标记，使其能够得到保护和正确处理，是信息保护规则的起始位置。 Microsoft 365有三种方法可以对内容进行分类。

## <a name="manually"></a>手动

手动分类需要人工判断和操作。 用户和管理员在遇到内容时将其应用到内容。 可以使用预先存在的标签和敏感信息类型，也可以使用自定义创建的标签和敏感信息类型。  然后，可以保护内容并管理其处置。

## <a name="automated-pattern-matching"></a>自动模式匹配

此类分类机制包括通过以下方式查找内容：

- 关键字或元数据值 (关键字查询语言) 。
- 使用以前标识的敏感信息模式，如社会保障、信用卡或银行帐号 [ (敏感信息类型实体定义) ](sensitive-information-type-entity-definitions.md)。
- 识别项，因为它是模板上的变体 [ (文档手指打印) ](document-fingerprinting.md)。
- 使用确切的字符串与 [数据完全匹配](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)。

然后，可以自动应用敏感度和保留标签，使内容可用于 [了解数据丢失防护](dlp-learn-about-dlp.md) 和 [自动应用保留标签的策略](apply-retention-labels-automatically.md)。

## <a name="classifiers"></a>分类

此分类方法非常适合由手动或自动化模式匹配方法不容易识别的内容。 这种分类方法更多的是使用分类器来根据项是什么来标识项，而不是按项中的元素 (模式匹配) 。 分类器通过查看你对分类感兴趣的数百个示例来了解如何识别内容类型。

> [!NOTE]
> 在预览版中 - 可以通过在筛选器面板中展开可训练分类器来查看内容资源管理器中的 **可训练分类器** 。 可训练分类器将自动显示在SharePoint、Teams和OneDrive中发现的事件数，而无需任何标记。
> 如果不想使用此功能，则必须使用Microsoft 支持部门提交请求，以禁用现用分类。 这将在创建标记策略之前禁用对敏感内容和已标记内容的扫描。

### <a name="where-you-can-use-classifiers"></a>可在其中使用分类器

分类器可用于使用[敏感度标签Office自动标记](apply-sensitivity-label-automatically.md)、基于条件和[通信合规性](communication-compliance.md)[自动应用保留标签策略](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)的条件。 

敏感度标签可以使用分类器作为条件，请参阅 [自动向内容应用敏感度标签](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> 分类器仅适用于未加密的项。

## <a name="types-of-classifiers"></a>分类器的类型

- **预先训练的分类器** - Microsoft 已创建并预先训练了多个分类器，无需训练即可开始使用这些分类器。 这些分类器将以状态 `Ready to use`显示。
- **自定义可训练分类器** - 如果分类需求超出了预先训练的分类器涵盖的范围，则可以创建和训练自己的分类器。

### <a name="pre-trained-classifiers"></a>预先训练的分类器

Microsoft 365附带多个预先训练的分类器：

> [!CAUTION]
> 我们正在弃用 **冒犯性语言** 预训练分类器，因为它会生成大量误报。 请勿使用，如果当前正在使用，应将业务流程从其中移开。 建议改用 **威胁**、 **亵渎** 和 **骚扰** 预先训练的分类器。

- **简历**：检测文档、.pdf、.rtf、.txt项，这些项目是申请人的个人、教育、专业资格、工作经验和其他个人身份信息的文本帐户
- **源代码**：检测包含在 GitHub 上使用的前 25 种计算机编程语言中编写的一组说明和语句的项目：ActionScript、C、C#、C++、Clojure、CoffeeScript、Go、Haskell、Java、JavaScript、Lua、MATLAB、Objective-C、Perl、PHP、Python、R、Ruby、Scala、Shell、Swift、TeX、Vim 脚本。 检测 .msg、.as、.h、.c、.cs、.cc、.cpp、.hpp、.cxx、.hh、.c++ 中的内容 .clj、.edn、.cljc、.cljs、.coffee、.litcoffee、.go、.hs、.lhs、.java、.jar、.js、.mjs、.lua、.m、.mm、.pl、.pm、.t、.xs、.pod、.php、.phar、.php4、.pyc、R， .r， .rda， .RData、.rds、.rb、.scala、.sc、.sh、.swift 文件。

> [!NOTE]
> 源代码经过训练，用于检测大部分文本何时为源代码。 它不会检测用纯文本穿插的源代码文本。

- **协议**：检测与保密协议、工作声明、贷款和租赁协议、就业和非竞争协议等法律协议相关的内容。 检测.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml 文件中的内容。
- **歧视**：检测明确的歧视性语言，与其他社区相比，对针对非裔美国人/黑人社区的歧视性语言很敏感。
- **财务**：检测企业财务、会计、经济、银行和投资类别的内容。 检测.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt中的内容 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.ppam、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla 文件。
- **骚扰**：根据以下特征，检测与针对一个或多个个人的攻击行为有关的特定类别攻击性语言文本项目：种族、种族、宗教、民族血统、性别、性取向、年龄、残疾。 检测 .msg、.docx、.pdf、.txt、.rtf、.jpeg、.jpg、.png、.gif、.bmp 和 .svg 文件中的内容。
- **医疗保健**：检测医疗和医疗保健管理方面的内容，如医疗服务、诊断、治疗、声明等。检测.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt中的内容 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.ppam、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla 文件。
- **人力资源**：检测人力资源相关类别中的内容，包括招聘、面试、招聘、培训、评估、警告和终止。 检测.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt中的内容 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.ppam、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla 文件。
- **IP**：检测知识产权相关类别中的内容，例如商业机密和类似的机密信息。 检测.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt中的内容 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.ppam、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla 文件。
- **IT**：检测信息技术和网络安全类别中的内容，例如网络设置、信息安全、硬件和软件。 检测.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt中的内容 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.ppam、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla 文件。
- **法律事务**：检测法律事务相关类别的内容，如诉讼、法律程序、法律义务、法律术语、法律和立法。 检测.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml 文件中的内容。
- **采购**：检测招标、报价、采购和支付商品和服务供应类别的内容。 检测.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla 文件中的内容。
- **亵渎**：检测包含让大多数人难堪的表达式的特定攻击性语言文本项类别。 检测 .msg、.docx、.pdf、.txt、.rtf、.jpeg、.jpg、.png、.gif、.bmp 和 .svg 文件中的内容。
- **税务**：检测税务关系内容，如税务规划、税务表单、纳税申报、税务法规等。 检测.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt中的内容， .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.ppam、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlt、.xlam、xla 文件。
- **威胁**：检测与威胁实施暴力或对个人或财产造成身体伤害或损害有关的攻击性语言文本项的特定类别。 检测 .msg、.docx、.pdf、.txt、.rtf、.jpeg、.jpg、.png、.gif、.bmp 和 .svg 文件中的内容。

这些显示在 **Microsoft 365 合规中心** > **Data classificationTrainable** >  **分类器** 视图中，其状态为 `Ready to use`。

![classifiers-pre-trained-classifiers.](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 请注意，冒犯性语言、骚扰、亵渎、歧视和威胁分类器仅适用于可搜索的文本，并且不是这些领域的完整或完整的术语或语言列表。 此外，语言和文化标准不断变化，鉴于这些现实，Microsoft 保留自行决定更新这些分类器的权利。 虽然分类器可能有助于组织检测这些区域，但分类器并不是为组织提供检测或解决此类语言使用问题的唯一方法。 你的组织（而不是 Microsoft 或其子公司）仍负责与监视、扫描、阻止、删除和保留预训练分类器标识的任何内容相关的所有决策，包括遵守本地隐私和其他适用法律。 Microsoft 鼓励在部署和使用之前咨询法律顾问。

预先训练的分类器可以扫描以下语言的内容：

- 简体中文
- 英语
- 法语
- 德语
- 意大利语
- 日语
- 葡萄牙语
- 西班牙语

### <a name="custom-classifiers"></a>自定义分类器

如果预先训练的分类器不能满足你的需求，则可以创建和训练自己的分类器。 创建自己的工作涉及更多，但它们将更好地满足组织需求。

开始创建自定义可训练分类器，方法是为其提供绝对属于类别的示例。 处理这些示例后，可通过同时提供匹配和非匹配示例来对其进行测试。 然后，分类器将预测任何给定项是否属于你正在生成的类别。 然后，确认其结果，对真正、真负、误报和误报进行排序，以帮助提高其预测的准确性。 

发布分类器时，它会对SharePoint联机、Exchange和OneDrive等位置中的项进行排序，然后对内容进行分类。 发布分类器后，可以使用类似于初始训练过程的反馈过程继续训练它。

例如，可以为以下内容创建可训练分类器：

- 法律文档 - 例如律师客户端特权、结案集、工作声明
- 战略业务文档 - 如新闻稿、并购、交易、商业或营销计划、知识产权、专利、设计文档
- 定价信息 - 如发票、报价、工作订单、投标文档
- 财务信息 - 例如组织投资、季度或年度业绩

#### <a name="process-flow-for-creating-custom-classifiers"></a>用于创建自定义分类器的流程

创建和发布分类器以用于合规性解决方案（如保留策略和通信监督）遵循此流程。 有关创建自定义可训练分类器的详细信息，请参阅 [：创建自定义分类器](classifier-get-started-with.md)。

![进程流自定义分类器。](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>重新训练分类器

你可以帮助提高所有可自定义可训练分类器的准确性，并向它们提供有关它们执行的分类准确性的反馈。 这称为重新训练，并遵循此工作流。

> [!NOTE]
> 无法重新训练预先训练的分类器。

![分类器重新训练工作流。](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>另请参阅

- [保留标签](retention.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [敏感度标签](sensitivity-labels.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [文档手指打印](document-fingerprinting.md)
- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
