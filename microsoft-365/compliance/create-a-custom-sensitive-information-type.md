---
title: 自定义敏感信息类型入门
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在安全与合规中心的图形用户界面中为 DLP 创建、修改、删除和测试自定义敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f0f6b68e9f952e0d52ce7cb71ccf03913584f4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929348"
---
# <a name="get-started-with-custom-sensitive-information-types"></a>自定义敏感信息类型入门

如果预先配置的敏感信息类型不满足你的需要，可以创建自己的自定义敏感信息类型，你可以完全定义这些类型，也可以复制其中一个预先配置的类型并进行修改。

使用此方法创建的自定义敏感信息类型将添加到名为 `Microsoft.SCCManaged.CustomRulePack` 的规则包中。

有两种方法可以创建新的敏感信息类型：

- [从头开始完全定义所有元素](#create-a-custom-sensitive-information-type)
- [复制和修改现有的敏感信息类型](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a>开始之前

- 应该熟悉敏感信息类型及其组成。 请参阅，[了解敏感信息类型](sensitive-information-type-learn-about.md)。 了解以下角色至关重要：
    - [正则表达式](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 敏感信息类型使用 Boost.RegEx 5.1.3 引擎
    - 关键字列表 - 可以在定义敏感信息类型或从现有关键字列表中选择时创建自己的关键字列表
    - [关键字字典](create-a-keyword-dictionary.md)
    - [函数](what-the-dlp-functions-look-for.md)
    - [可信度](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- 必须拥有全局管理员或合规性管理员权限，以便可以通过 UI 创建、测试和部署自定义的敏感信息类型。 请参阅 Office 365 中的[关于管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)。

- 组织必须具有包含数据丢失防护 (DLP) 的订阅（如 Office 365 企业版）。 请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。 


> [!IMPORTANT]
> 在创建自定义分类或正则表达式模式时，不可从 Microsoft 客户服务和支持获取帮助。 支持工程师可对功能提供有限的支持，例如提供用于测试目的的示例正则表达式，或者帮助排查未如期触发的现有正则表达式模式的问题，但无法保证所有自定义内容匹配开发都将满足你的要求或义务。

## <a name="create-a-custom-sensitive-information-type"></a>创建自定义敏感信息类型

使用以下步骤可以创建完全定义的新敏感信息类型。 

1. 在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后选择“**创建信息类型**”。
2. 填写“**名称**”和“**说明**” 的值，然后选择“**下一步**”。
3. 选择“**创建模式**”。 在定义新的敏感信息类型时，可以创建多个模式，每个模式具有不同的元素和置信度。
4. 选择模式的默认可信度。 这些值是“**低可信度**”、“**中可信度**”和“**高可信度**”。
5. 选择并定义 **主要元素**。 主要元素可以是带有可选验证程序的 **正则表达式**、**关键字列表**、**关键字字典** 或预先配置的 **函数** 之一。 有关 DLP 函数的详细信息，请参阅 [DLP 函数查找的内容](what-the-dlp-functions-look-for.md)。
6. 填写 **字符领近度** 的值。
7. （可选）添加支持元素（如有）。 支持元素可以是带有可选验证程序的正则表达式、关键字列表、关键字字典或预定义的函数之一。 
8.  （可选）从可用检查列表中添加其他检查
9. 选择“**创建**”。
10. 选择“**下一步**”。
11. 为此敏感信息类型选择 **建议的可信度**。
12. 检查设置并选择“**提交**”。

> [!IMPORTANT]
> Microsoft 365 使用搜索爬网程序来确定 SharePoint Online 和 OneDrive for Business 网站中的敏感信息并对其分类。 要确定现有内容中新的自定义敏感信息类型，必须对该内容重新爬网。 根据计划对内容进行爬网，但你可手动重新爬网内容来查找网站集、列表或库。 有关详细信息，请参阅[Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content)（手动请求对网站、库或列表进行爬网和重新编制索引）。

13. 在“**数据分类**”页面上，将看到列出的所有敏感信息类型。 选择“**刷新**”，然后浏览或使用搜索工具查找刚刚创建的敏感信息类型。

## <a name="test-a-sensitive-information-type"></a>测试敏感信息类型

可以测试列表中的任何敏感信息类型。 我们建议在策略中使用之前，测试创建的每种敏感信息类型。

1. 准备两个文件，比如 Word 文档。 一个包含与敏感信息类型中指定的元素匹配的内容，另一个不匹配。
2. 在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从列表中选择敏感信息类型，以打开“详细信息”窗格并选择“**测试**”。
3. 上传文件并选择“**测试**”。
4. 在“**匹配结果**”页面上，查看结果并选择“**完成**”。

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a>在合规中心内修改自定义敏感信息类型

1. 在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从要修改的列表中选择敏感信息类型，然后选择“**编辑**”。
2. 可以添加其他模式，其中包括唯一的主元素和支持元素、可信度、字符领近度和其他检查，或者编辑/删除现有的模式。 有关详细信息，请参阅[创建自定义敏感信息类型](#create-a-custom-sensitive-information-type)。

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a>移除合规中心中的自定义敏感信息类型 

> [!NOTE]
> 只能删除自定义敏感信息类型；不能删除内置敏感信息类型。

> [!IMPORTANT]
> 删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。

1. 在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从列表中选择要删除的敏感信息类型。
2. 在打开的浮出控件中，选择“**删除**”。

## <a name="copy-and-modify-a-sensitive-information-type"></a>复制和修改敏感信息类型

使用以下步骤可以创建基于现有敏感信息类型的新敏感信息类型。 

1. 在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后选择要复制的敏感信息类型。
2. 在浮出控件中，选择“**复制**”。
3. 在敏感信息类型列表中选择“**刷新**”，然后浏览或搜索刚刚创建的副本。 部分字串搜索有用，所以可以只搜索 `copy`，搜索将返回名称中包含 `copy` 文字的所有敏感信息类型。 
4. 填写“**名称**”和“**说明**” 的值，然后选择“**下一步**”。
5. 选择敏感信息类型“副本”，然后选择“**编辑**”。 
6. 为新的敏感信息类型提供新“**名称**”和“**描述**”。
7. 您可以选择编辑或删除现有模式，以及添加新模式。 选择新模式的默认可信度。 这些值是“**低可信度**”、“**中可信度**”和“**高可信度**”。
8. 选择并定义 **主要元素**。 主要元素可以是 **正则表达式**、**关键字列表**、**关键字字典** 或预先配置的 **函数** 之一。 请参阅，[DLP 函数查找的内容](what-the-dlp-functions-look-for.md)。
9. 填写 **字符领近度** 的值。
10. （可选）如果有 **支持元素** 或任何 **其他检查**，请添加它们。 如果需要，可以将你的 **支持元素** 分组。
11. 选择“**创建**”。
12. 选择“**下一步**”。
13. 为此敏感信息类型选择 **建议的可信度**。
14. 检查设置并选择“**提交**”。

此外，还可以使用 PowerShell 和精确的数据匹配功能创建自定义敏感信息类型。 若要了解有关这些方法的详细信息，请参阅：
- [使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [使用精确数据匹配 (EDM) 为 DLP 创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
 
> [!NOTE]
> Microsoft 365 信息保护可为以下语言提供双字节字符集语言支持（预览）：
> - 简体中文
> - 繁体中文
> - 韩语
> - 日语
>
>此支持适用于敏感信息类型。 有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。