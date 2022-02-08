---
title: 了解可训练的分类器
f1.keywords:
  - NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: null
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
description: 可训练分类器可以通过提供要查看的正面和负面示例来识别用于标记或策略应用程序的各种类型的内容。
---

# <a name="learn-about-trainable-classifiers"></a>了解可训练的分类器

对内容进行分类和标记，以便可以保护和正确处理内容是信息保护规范的起点。 Microsoft 365三种方法对内容进行分类。

## <a name="manually"></a>手动

手动分类需要人为判断和操作。 用户和管理员在遇到内容时将其应用于内容。 可以使用预先存在的标签和敏感信息类型，或使用自定义创建的标签和敏感信息类型。  然后，您可以保护内容并管理其处置。

## <a name="automated-pattern-matching"></a>自动模式匹配

此分类机制类别包括按以下方法查找内容：

- 关键字查询语言 (关键字或元数据) 。
- 使用之前标识的敏感信息模式（如社会保险、信用卡或银行帐号） ([ 敏感信息类型实体定义) ](sensitive-information-type-entity-definitions.md)。
- 识别项目，因为它是模板上的变体 ([ 文档手指) ](document-fingerprinting.md)。
- 使用精确字符串的存在确切 [数据匹配](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)。

然后，可以自动应用敏感度和保留标签，使内容可供在了解数据丢失防护和[](dlp-learn-about-dlp.md)自动应用保留标签策略中[使用](apply-retention-labels-automatically.md)。

## <a name="classifiers"></a>分类器

此分类方法非常适合无法通过手动或自动模式匹配方法轻松标识的内容。 这种分类方法更与使用分类器根据项目内容来标识项目有关，而不是按项目 (模式匹配) 。 分类器通过查看对分类感兴趣的内容的数百个示例来了解如何识别内容类型。

> [!NOTE]
> 在"预览 - 通过展开筛选器面板中的可训练分类器"，可以在内容资源管理器 **中查看可** 训练分类器。 可训练分类器将自动显示在安全、SharePoint、Teams和OneDrive中发现的事件数，而无需任何标记。
> 如果不想使用此功能，则必须向 Microsoft 支持人员提出请求以禁用开箱即用分类。 这将在您创建标签策略之前禁用对敏感和标记内容的扫描。

### <a name="where-you-can-use-classifiers"></a>可以使用分类器的地方

分类器可用于使用敏感度标签Office标签自动标记[](apply-sensitivity-label-automatically.md)，根据条件和通信合规性自动应用保留[标签策略](communication-compliance.md)。 [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) 

敏感度标签可以使用分类器作为条件，请参阅自动向内容 [应用敏感度标签](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> 分类器仅适用于未加密的项目。

## <a name="types-of-classifiers"></a>分类器的类型

- **预先训练的分类** 器 - Microsoft 已创建并预先训练多个分类器，无需培训即可开始使用这些分类器。 这些分类器将显示为 状态 `Ready to use`。
- **自定义可训练分类** 器 - 如果你的分类需求超出了预先训练的分类器涵盖范围，可以创建并训练自己的分类器。

### <a name="pre-trained-classifiers"></a>预先训练的分类器

Microsoft 365多个预先训练的分类器：

> [!CAUTION]
> 我们正在弃用 **冒犯性语言** 预训练分类器，因为它会生成大量误报。 请勿使用，如果当前正在使用，应将业务流程从其中移开。 我们建议改为使用 **威胁**、 **亵** 亵和 **骚扰** 预先训练的分类器。

- **简历**：检测 docx、.pdf、.rtf、.txt 项，这些项目是收信人个人、教育、专业资格、工作体验和其他个人识别信息的文本帐户
- 源代码：检测包含一组使用 GitHub 上的前 25 种计算机编程语言编写的指令和语句的项：ActionScript、C、C#、C++、Coffee且 CoffeeScript、Go、Haskell、Java、JavaScript、Lua、MATLAB、Objective-C、Perl、PHP、Python、R、Ruby、Scala、Shell、Swift、TeX、Vim Script。

> [!NOTE]
> 源代码经过训练，可检测大量文本何时是源代码。 它不会检测与纯文本交错的源代码文本。

- **协议**：检测与法律协议（如保密协议、工作声明、贷款和租赁协议、雇佣和非竞争协议）相关的内容。 检测 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml 文件中的内容。
- **种族**：检测明确的语言，并且与其他社区相比，它对于针对美洲/黑色社区的语言敏感。
- **财务**：检测公司财务、会计、经济、银行以及投资类别中的内容。 检测 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt 中的内容。 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xlt、.xlam、.xla 文件。
- **冒犯** 性：根据以下特征检测与针对一个或多个个人的冒犯性行为相关的特定冒犯性语言文本项：种族、国家/地区、性别、性取向、年龄、残障。 检测 .msg、.docx、.pdf、.txt、.rtf、.jpeg、.jpg、.png、.gif、.bmp、.svg 文件中的内容。
- **医疗保健**：检测医疗保健管理方面的内容，如医疗、诊断、处理、索赔等。检测 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt 中的内容。 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xlt、.xlam、.xla 文件。
- **HR**：检测人力资源相关类别的招聘、面试、招聘、培训、评估、警告和终止的内容。 检测 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt 中的内容。 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xlt、.xlam、.xla 文件。
- **IP**：检测知识产权相关类别中的内容，如商业秘密和类似的机密信息。 检测 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt 中的内容。 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xlt、.xlam、.xla 文件。
- **IT**：检测信息技术和网络安全类别中的内容，例如网络设置、信息安全、硬件和软件。 检测 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt 中的内容。 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xlt、.xlam、.xla 文件。
- **法律事务**：检测法律事务相关类别的内容，如诉讼、法律诉讼、法律要求、法律术语、法律和法律。 检测 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml 文件中的内容。
- **采购**：检测商品、报价、采购和商品与服务的提供类别的内容。 检测 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla 文件中的内容。
- **冒犯性**：检测特定类别的冒犯性语言文本项，这些文本项包含使大多数用户感同的表达式。 检测 .msg、.docx、.pdf、.txt、.rtf、.jpeg、.jpg、.png、.gif、.bmp、.svg 文件中的内容。
- **税务**：检测税务关系内容，如税务计划、税单、税务申报、税务法规。 检测 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、 .one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.pps、.ppam、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、xla 文件。
- **威胁**：检测与威胁相关的特定类别的冒犯性语言文本项，以实施暴力或对人员或属性进行物理损害或损害。 检测 .msg、.docx、.pdf、.txt、.rtf、.jpeg、.jpg、.png、.gif、.bmp、.svg 文件中的内容。

它们显示在 Microsoft 365 合规中心 > **Data classificationTrainable** >  **分类器** 视图中，状态为 `Ready to use`。

![classifiers-pre-trained-classifiers。](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 请注意，冒犯性语言、冒犯性以及威胁分类器仅适用于可搜索文本，并不包含这些领域的字词或语言的详尽或完整列表。 此外，语言和文化标准会不断改变，鉴于这些创新，Microsoft 保留自行决定更新这些分类器的权利。 虽然分类器可帮助组织检测这些方面，但分类器并非旨在提供组织检测或解决此类语言使用的唯一方法。 贵组织（而不是 Microsoft 或其子公司）仍负责与监视、扫描、阻止、删除和保留由预先训练的分类器确定的任何内容相关的所有决策，包括遵守本地隐私和其他适用法律。 Microsoft 鼓励在部署和使用之前咨询法律顾问。

经过预先训练的分类器可以扫描以下语言的内容：

• 中文 (简体) • 英语 • 法语 • 德语 • 意大利语 • 日语 • 葡萄牙语 • 西班牙语

### <a name="custom-classifiers"></a>自定义分类器

如果预先训练的分类器无法满足您的需求，您可以创建并训练自己的分类器。 创建自己的工作涉及明显更多工作，但它们可以更好地根据组织需求进行定制。

通过馈送该类别中肯定属于该类别的示例，你可以开始创建自定义可训练分类器。 处理这些示例后，通过同时提供匹配示例和非匹配示例进行测试。 然后，分类器将预测任何给定项目是否属于你正在构建的类别。 然后确认其结果，对真正的正数、负数、误报和漏报进行排序，以帮助提高预测的准确性。 

发布分类器时，分类器会按 SharePoint Online、Exchange 和 OneDrive 等位置中的项目进行排序，并对内容进行分类。 发布分类器后，可以继续使用与初始培训过程类似的反馈流程对分类器进行培训。

例如，你可以为：

- 法律文档 - 例如律师客户特权、结束集、工作说明
- 战略业务文档 - 如新闻稿、合并和收购、交易、业务或市场营销计划、知识产权、专利、设计文档
- 定价信息 - 如发票、报价、工作订单、采购文档
- 财务信息 - 如组织投资、季度或年度结果

#### <a name="process-flow-for-creating-custom-classifiers"></a>创建自定义分类器的过程流

创建和发布分类器以用于合规性解决方案（如保留策略和通信监督）遵循此流程。 有关创建自定义可训练分类器的详细信息，请参阅 [创建自定义分类器](classifier-get-started-with.md)。

![进程流自定义分类器。](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>重新分类器

您可以帮助提高所有自定义可训练分类器的准确性，并提供有关它们所执行分类的准确性的反馈。 这称为重新培训，遵循此工作流。

> [!NOTE]
> 预先训练的分类器无法重新训练。

![分类器重新设置工作流。](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>另请参阅

- [保留标签](retention.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [敏感度标签](sensitivity-labels.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [文档手指打印](document-fingerprinting.md)
- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
