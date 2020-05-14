---
title: 搜索和查找个人数据
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何在 Office 365 中搜索和查找符合一般数据保护条例 (GDPR) 的个人数据。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0d29697a28221b5ff998f5ce923c143bf7a0804
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214576"
---
# <a name="search-for-and-find-personal-data"></a>搜索和查找个人数据

个人数据在 GDPR 中的定义非常宽泛，即指属于欧盟 (EU) 居民的已确定身份的或可识别的自然人的任何相关数据。

第 4 条 – 定义

> “个人数据”表示已确定身份或可识别的自然人（“数据主体”）的任何相关信息；可识别的自然人是指可被直接或间接识别出的自然人，尤其是通过参考姓名、证件号码、位置数据、网络标识等标识，或通过参考特定于该自然人的身体、生理、基因、精神、经济、文化或社会标识的一个或多个因素进行识别；

本文演示了如何查找存储在 SharePoint Online 和 OneDrive for Business（其中包含所有 Microsoft 365 组和 Microsoft Teams 的网站）中的个人数据。

查找受 GDPR 约束的个人数据需要使用 Office 365 中的敏感信息类型。 这些信息类型定义了自动化过程如何识别健康服务号码和信用卡号等特定信息类型。 你可以使用数据丢失防护策略在传送过程中查找邮件中的个人数据。 可以使用为 GDPR 策展的敏感信息类型来查找和保护通过电子邮件发送的个人信息。 另请参阅[在安全与合规中心内使用 DSR 案例工具管理 GDPR 数据主体请求](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool)。

## <a name="use-content-search-to-find-personal-data"></a>使用内容搜索查找个人数据

Microsoft 建议分三个阶段在 Office 365 中查找个人数据。本主题的剩余部分介绍了每个阶段的相关指南。

<table>
<thead>
<tr class="header">
<th align="left"><strong>步骤</strong></th>
<th align="left"><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>1. 搜索敏感信息类型</p></td>
<td align="left"><p>首先使用敏感信息类型查找个人数据。为每种敏感信息类型创建内容搜索查询。运行查询并分析结果。</p>
必要时，向查询添加参数，以减少误报： <li>计数范围</li>
    <li>置信区间</li>
    <li>用于更为复杂的查询的其他属性或运算符</li>
<p>必要时，修改敏感信息类型，以提高组织的准确性：</p>
<p><li>直接在 XML 中调整可信度。</li></p>
<p><li>添加关键字。</li></p>
<p><li>调整关键字的邻近度要求。</li></p></td>
</tr>
<tr class="even">
<td align="left"><p>2. 使用关键字查询语言 (KQL) 查找环境中的其他个人数据</p></td>
<td align="left"><p>如果要查找的数据不包含在敏感信息类型中，可以使用 KQL 查询语言生成自定义查询。</p>
<p>测试搜索结果，并调整 KQL 查询字符串，直至获得所需的结果。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3. 使用 KQL 查询创建新的自定义敏感信息类型</p></td>
<td align="left">在优化 KQL 查询以查找目标数据后，使用这些查询创建新的自定义敏感信息类型。然后可以在 DLP 策略和其他工具及其他 KQL 查询中结合使用这些自定义敏感信息类型和内容搜索。</td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a>使用内容搜索功能搜索敏感信息类型

通过使用 Office 365 附带的敏感信息类型开始搜索个人数据。 安全中心和合规中心中的“分类”下列出了这些类型。

本主题列出了适用于欧盟公民的某些敏感信息类型。 请检查安全中心或合规中心，了解是否有可帮助实现 GDPR 合规性的新增内容。

另请参阅下文：[敏感信息类型列表及每种类型可查找的内容](https://docs.microsoft.com/microsoft-365/compliance/content-search)。

敏感信息类型定义了自动进程识别特定信息类型的方式，例如银行帐号、卫生服务号码和信用卡号码等。敏感信息类型也可称为条件。敏感信息类型通过正则表达式或函数可以识别的模式定义。此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。可信度和邻近度也会在评估过程中使用。

目前，不能以静态方式使用敏感信息类型在邮箱中查找数据。

### <a name="using-content-search-with-sensitive-information-types"></a>结合使用内容搜索和敏感信息类型

<table>
<thead>
<tr class="header">
<th align="left"><strong>步骤</strong></th>
<th align="left"><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p>转到安全与合规中心的“内容搜索”</p></td>
<td align="left"><p>在安全与合规中心的左侧窗格中，单击“搜索和调查”****&gt;****“内容搜索”。</p>
<p>请参阅<a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">在安全与合规中心运行内容搜索</a>。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为每种敏感信息类型创建新的搜索项</p></td>
<td align="left"><p>使用以下语法：</p>
<blockquote>
<p>SensitiveType:"&lt;type&gt;"</p>
</blockquote>
<p>例如：</p>
<blockquote>
<p>SensitiveType:&quot;法国护照号码&quot;</p>
</blockquote>
<p>将搜索范围限定为 SharePoint（包括 OneDrive for Business）。确保语法准确无误，没有多余的空格或拼写错误。</p>
<p>请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites">创建查询以查找存储在站点上的敏感数据</a>。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>查看各个搜索的结果</p></td>
<td align="left"><p>查看是否存在以下类型的问题，确定查询准确性是否符合目标：</p>
<p><li>许多误报</li></p>
<p><li>缺少已知的数据实例</li></p>
<p>请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">从安全与合规中心导出内容搜索结果</a>。</p>
<p>注意：如果使用的是 Mozilla Firefox 或 Chrome，可能需要先使用 Internet Explorer 或 Microsoft Edge 下载报告，才能安装所需的加载项。</p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a>欧盟公民数据的敏感信息类型

从以下敏感信息类型入手。即将推出适用于欧盟国家/地区的个人数据的更多敏感信息类型。

> 比利时国家号码
>
> 信用卡号码
>
> 克罗地亚身份证号码
>
> 克罗地亚个人标识 (OIB) 号码
>
> 捷克国民身份证号码
>
> 丹麦个人识别号
>
> 欧盟借记卡号码
>
> 芬兰国家/地区身份证号码
>
> 芬兰护照号码
>
> 法国驾驶证号码
>
> 法国国家/地区身份证 (CNI)
>
> 法国护照号码
>
> 法国社会保险号码 (INSEE)
>
> 德国驾驶证号码
>
> 德国身份证号码
>
> 德国护照号码
>
> 希腊国民身份证
>
> 国际银行帐号 (IBAN)
>
> IP 地址
>
> 爱尔兰个人公共服务 (PPS) 号
>
> 意大利驾驶证号码
>
> 荷兰公民服务 (BSN) 号码
>
> 挪威标识号
>
> 波兰身份证
>
> 波兰国家/地区身份证号码 (PESEL)
>
> 波兰护照
>
> 葡萄牙公民卡号
>
> 西班牙社会保险号码 (SSN)
>
> 瑞典国家/地区身份证号码
>
> 瑞典护照号码
>
> 英国驾驶证号码
>
> 英国选民名册号码
>
> 英国国家卫生服务号码
>
> 英国国家保险号码 (NINO)
>
> 美国/英国护照号码

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a>向敏感信息类型查询添加参数以筛选出结果

可以向敏感信息类型查询添加以下参数：

-   计数范围 — 定义敏感信息在文档中出现多少次之后，才将该文档包含在查询结果中。

-   置信区间 — 已检测到的敏感类型实际匹配的置信水平，例如 85 (85%)。

语法：

-   SensitiveType:"\<type\>|\<count range\>|\<confidence range\>"

示例：

-   SensitiveType:"Credit Card Number|5"（只返回正好包含五个信用卡号码的文档）

-   SensitiveType:"Credit Card Number|\*|85.."（置信区间为 85 % 或更高）

注意：“SensitiveType”区分大小写，但查询的其余部分不区分大小写。

此外，还可以使用属性和运算符来说明如何优化查询。有关详细信息和示例，请参阅[创建查询以查找存储在站点上的敏感数据](https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites)。
