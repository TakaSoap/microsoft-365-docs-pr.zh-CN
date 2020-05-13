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
ms.openlocfilehash: 50c8db59cfd5e9a7de3da0dc696227e85dab1cee
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208086"
---
# <a name="search-for-and-find-personal-data"></a><span data-ttu-id="a0a2e-103">搜索和查找个人数据</span><span class="sxs-lookup"><span data-stu-id="a0a2e-103">Search for and find personal data</span></span>

<span data-ttu-id="a0a2e-104">个人数据在 GDPR 中的定义非常宽泛，即指属于欧盟 (EU) 居民的已确定身份的或可识别的自然人的任何相关数据。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-104">Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="a0a2e-105">第 4 条 – 定义</span><span class="sxs-lookup"><span data-stu-id="a0a2e-105">Article 4 – Definitions</span></span>

> <span data-ttu-id="a0a2e-106">“个人数据”表示已确定身份或可识别的自然人（“数据主体”）的任何相关信息；可识别的自然人是指可被直接或间接识别出的自然人，尤其是通过参考姓名、证件号码、位置数据、网络标识等标识，或通过参考特定于该自然人的身体、生理、基因、精神、经济、文化或社会标识的一个或多个因素进行识别；</span><span class="sxs-lookup"><span data-stu-id="a0a2e-106">'personal data' means any information relating to an identified or identifiable natural person ('data subject'); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="a0a2e-107">本文演示了如何查找存储在 SharePoint Online 和 OneDrive for Business（其中包含所有 Microsoft 365 组和 Microsoft Teams 的网站）中的个人数据。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-107">This article demonstrates how to find personal data stored in SharePoint Online and OneDrive for Business (which includes the sites for all Microsoft 365 groups and Microsoft Teams).</span></span>

<span data-ttu-id="a0a2e-108">查找受 GDPR 约束的个人数据需要使用 Office 365 中的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-108">Finding personal data subject to GDPR relies on using sensitive information types in Office 365.</span></span> <span data-ttu-id="a0a2e-109">这些信息类型定义了自动化过程如何识别健康服务号码和信用卡号等特定信息类型。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-109">These define how the automated process recognizes specific information types such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="a0a2e-110">你可以使用数据丢失防护策略在传送过程中查找邮件中的个人数据。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-110">You can use data loss prevention policies to find personal data in mail while in transit.</span></span> <span data-ttu-id="a0a2e-111">可以使用为 GDPR 策展的敏感信息类型来查找和保护通过电子邮件发送的个人信息。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-111">You can use the sensitive information types you curate for GDPR to find and protect personal information as it is sent through email.</span></span> <span data-ttu-id="a0a2e-112">另请参阅[在安全与合规中心内使用 DSR 案例工具管理 GDPR 数据主体请求](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool)。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-112">Also see [Managed GDPR data subject requests with the DSR case tool in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).</span></span>

## <a name="use-content-search-to-find-personal-data"></a><span data-ttu-id="a0a2e-113">使用内容搜索查找个人数据</span><span class="sxs-lookup"><span data-stu-id="a0a2e-113">Use Content Search to find personal data</span></span>

<span data-ttu-id="a0a2e-p102">Microsoft 建议分三个阶段在 Office 365 中查找个人数据。本主题的剩余部分介绍了每个阶段的相关指南。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p102">Microsoft recommends a three-stage approach to finding personal data in Office 365. The rest of this topic provides guidance for each of these stages.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a2e-116"><strong>步骤</strong></span><span class="sxs-lookup"><span data-stu-id="a0a2e-116"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="a0a2e-117"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="a0a2e-117"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a2e-118">1. 搜索敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a0a2e-118">1. Search for sensitive information types</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a2e-p103">首先使用敏感信息类型查找个人数据。为每种敏感信息类型创建内容搜索查询。运行查询并分析结果。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p103">Start by using sensitive information types to find personal data. Create a Content Search query for each sensitive information type. Run the query and analyze the results.</span></span></p>
<span data-ttu-id="a0a2e-122">必要时，向查询添加参数，以减少误报：</span><span class="sxs-lookup"><span data-stu-id="a0a2e-122">If needed, add parameters to the query to reduce false positives:</span></span> <li><span data-ttu-id="a0a2e-123">计数范围</span><span class="sxs-lookup"><span data-stu-id="a0a2e-123">Count range</span></span></li>
    <li><span data-ttu-id="a0a2e-124">置信区间</span><span class="sxs-lookup"><span data-stu-id="a0a2e-124">Confidence range</span></span></li>
    <li><span data-ttu-id="a0a2e-125">用于更为复杂的查询的其他属性或运算符</span><span class="sxs-lookup"><span data-stu-id="a0a2e-125">Other properties or operators for more complex queries</span></span></li>
<p><span data-ttu-id="a0a2e-126">必要时，修改敏感信息类型，以提高组织的准确性：</span><span class="sxs-lookup"><span data-stu-id="a0a2e-126">If necessary, modify a sensitive information type to improve accuracy for your organization:</span></span></p>
<p><li><span data-ttu-id="a0a2e-127">直接在 XML 中调整可信度。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-127">Adjust the confidence level directly in the XML.</span></span></li></p>
<p><li><span data-ttu-id="a0a2e-128">添加关键字。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-128">Add key words.</span></span></li></p>
<p><li><span data-ttu-id="a0a2e-129">调整关键字的邻近度要求。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-129">Adjust the proximity requirements for keywords.</span></span></li></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a2e-130">2. 使用关键字查询语言 (KQL) 查找环境中的其他个人数据</span><span class="sxs-lookup"><span data-stu-id="a0a2e-130">2. Use Keyword Query Language (KQL) to find additional personal data in your environment</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a2e-131">如果要查找的数据不包含在敏感信息类型中，可以使用 KQL 查询语言生成自定义查询。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-131">To find data not included in sensitive information types, use the KQL query language to develop custom queries.</span></span></p>
<p><span data-ttu-id="a0a2e-132">测试搜索结果，并调整 KQL 查询字符串，直至获得所需的结果。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-132">Test the results of these searches and adjust the KQL query string until you achieve the expected result.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a2e-133">3. 使用 KQL 查询创建新的自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a0a2e-133">3. Create new custom sensitive information types using the KQL queries</span></span></p></td>
<td align="left"><span data-ttu-id="a0a2e-p104">在优化 KQL 查询以查找目标数据后，使用这些查询创建新的自定义敏感信息类型。然后可以在 DLP 策略和其他工具及其他 KQL 查询中结合使用这些自定义敏感信息类型和内容搜索。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p104">After optimizing KQL queries to find target data, create new custom sensitive information types using these queries. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span></td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a><span data-ttu-id="a0a2e-136">使用内容搜索功能搜索敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a0a2e-136">Search for sensitive information types using Content Search</span></span>

<span data-ttu-id="a0a2e-137">通过使用 Office 365 附带的敏感信息类型开始搜索个人数据。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-137">Begin searching for personal data by using the sensitive information types that are included with Office 365.</span></span> <span data-ttu-id="a0a2e-138">安全中心和合规中心中的“分类”下列出了这些类型。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-138">These are listed under Classification in the security center and compliance center.</span></span>

<span data-ttu-id="a0a2e-139">本主题列出了适用于欧盟公民的某些敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-139">This topic includes a list of some sensitive information types that apply to citizens in the European Union.</span></span> <span data-ttu-id="a0a2e-140">请检查安全中心或合规中心，了解是否有可帮助实现 GDPR 合规性的新增内容。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-140">Check the security center or the compliance center for new additions that can help with GDPR compliance.</span></span>

<span data-ttu-id="a0a2e-141">另请参阅下文：[敏感信息类型列表及每种类型可查找的内容](https://support.office.com/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b)。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-141">Also see this article: [List of sensitive information types and what each one looks for](https://support.office.com/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span></span>

<span data-ttu-id="a0a2e-p107">敏感信息类型定义了自动进程识别特定信息类型的方式，例如银行帐号、卫生服务号码和信用卡号码等。敏感信息类型也可称为条件。敏感信息类型通过正则表达式或函数可以识别的模式定义。此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。可信度和邻近度也会在评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p107">Sensitive information types define how the automated process recognizes specific information types such as bank account numbers, health service numbers, and credit card numbers. Sensitive information types are also referred to as conditions. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>

<span data-ttu-id="a0a2e-147">目前，不能以静态方式使用敏感信息类型在邮箱中查找数据。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-147">At this time sensitive information types cannot be used to find data at rest in mailboxes.</span></span>

### <a name="using-content-search-with-sensitive-information-types"></a><span data-ttu-id="a0a2e-148">结合使用内容搜索和敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a0a2e-148">Using Content Search with sensitive information types</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a2e-149"><strong>步骤</strong></span><span class="sxs-lookup"><span data-stu-id="a0a2e-149"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="a0a2e-150"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="a0a2e-150"><strong>More information</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p><span data-ttu-id="a0a2e-151">转到安全与合规中心的“内容搜索”</span><span class="sxs-lookup"><span data-stu-id="a0a2e-151">Go to Content Search in the Security and Compliance Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a2e-152">在安全与合规中心的左侧窗格中，单击“搜索和调查”\*\*\*\*&gt;\*\*\*\*“内容搜索”。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-152">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** &gt; **Content search**.</span></span></p>
<p><span data-ttu-id="a0a2e-153">请参阅<a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">在安全与合规中心运行内容搜索</a>。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-153">See <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Run a Content Search in the Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a2e-154">为每种敏感信息类型创建新的搜索项</span><span class="sxs-lookup"><span data-stu-id="a0a2e-154">Create a new search item for each sensitive information type</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a2e-155">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a0a2e-155">Use the following syntax:</span></span></p>
<blockquote>
<p><span data-ttu-id="a0a2e-156">SensitiveType:"&lt;type&gt;"</span><span class="sxs-lookup"><span data-stu-id="a0a2e-156">SensitiveType:"&lt;type&gt;"</span></span></p>
</blockquote>
<p><span data-ttu-id="a0a2e-157">例如：</span><span class="sxs-lookup"><span data-stu-id="a0a2e-157">For example:</span></span></p>
<blockquote>
<p><span data-ttu-id="a0a2e-158">SensitiveType:&quot;法国护照号码&quot;</span><span class="sxs-lookup"><span data-stu-id="a0a2e-158">SensitiveType:&quot;France Passport Number&quot;</span></span></p>
</blockquote>
<p><span data-ttu-id="a0a2e-p108">将搜索范围限定为 SharePoint（包括 OneDrive for Business）。确保语法准确无误，没有多余的空格或拼写错误。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p108">Scope the search to SharePoint (includes OneDrive for Business). Make sure the syntax is exact and there are no extra spaces or typos.</span></span></p>
<p><span data-ttu-id="a0a2e-161">请参阅<a href="https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">创建查询以查找存储在站点上的敏感数据</a>。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-161">See <a href="https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Form a query to find sensitive data stored on sites</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a2e-162">查看各个搜索的结果</span><span class="sxs-lookup"><span data-stu-id="a0a2e-162">Review the results for each search</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a2e-163">查看是否存在以下类型的问题，确定查询准确性是否符合目标：</span><span class="sxs-lookup"><span data-stu-id="a0a2e-163">Look for these types of issues to determine if the query accuracy is on target:</span></span></p>
<p><li><span data-ttu-id="a0a2e-164">许多误报</span><span class="sxs-lookup"><span data-stu-id="a0a2e-164">Many false positives</span></span></li></p>
<p><li><span data-ttu-id="a0a2e-165">缺少已知的数据实例</span><span class="sxs-lookup"><span data-stu-id="a0a2e-165">Missing known instances of data</span></span></li></p>
<p><span data-ttu-id="a0a2e-166">请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">从安全与合规中心导出内容搜索结果</a>。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-166">See <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Export Content Search results from the Security &amp; Compliance Center</a>.</span></span></p>
<p><span data-ttu-id="a0a2e-167">注意：如果使用的是 Mozilla Firefox 或 Chrome，可能需要先使用 Internet Explorer 或 Microsoft Edge 下载报告，才能安装所需的加载项。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-167">Note: if you're using Mozilla Firefox or Chrome, you might need to first download reports using Internet Explorer or Edge in order to install the required add-in.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a><span data-ttu-id="a0a2e-168">欧盟公民数据的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a0a2e-168">Sensitive information types for EU citizen data</span></span>

<span data-ttu-id="a0a2e-p109">从以下敏感信息类型入手。即将推出适用于欧盟国家/地区的个人数据的更多敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p109">Start with these sensitive information types. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

> <span data-ttu-id="a0a2e-171">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-171">Belgium National Number</span></span>
>
> <span data-ttu-id="a0a2e-172">信用卡号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-172">Credit Card Number</span></span>
>
> <span data-ttu-id="a0a2e-173">克罗地亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-173">Croatia Identity Card Number</span></span>
>
> <span data-ttu-id="a0a2e-174">克罗地亚个人标识 (OIB) 号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-174">Croatia Personal Identification (OIB) Number</span></span>
>
> <span data-ttu-id="a0a2e-175">捷克国民身份证号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-175">Czech National Identity Card Number</span></span>
>
> <span data-ttu-id="a0a2e-176">丹麦个人识别号</span><span class="sxs-lookup"><span data-stu-id="a0a2e-176">Denmark Personal Identification Number</span></span>
>
> <span data-ttu-id="a0a2e-177">欧盟借记卡号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-177">EU Debit Card Number</span></span>
>
> <span data-ttu-id="a0a2e-178">芬兰国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-178">Finland National ID</span></span>
>
> <span data-ttu-id="a0a2e-179">芬兰护照号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-179">Finland Passport Number</span></span>
>
> <span data-ttu-id="a0a2e-180">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-180">France Driver's License Number</span></span>
>
> <span data-ttu-id="a0a2e-181">法国国家/地区身份证 (CNI)</span><span class="sxs-lookup"><span data-stu-id="a0a2e-181">France National ID Card (CNI)</span></span>
>
> <span data-ttu-id="a0a2e-182">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-182">France Passport Number</span></span>
>
> <span data-ttu-id="a0a2e-183">法国社会保险号码 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a0a2e-183">France Social Security Number (INSEE)</span></span>
>
> <span data-ttu-id="a0a2e-184">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-184">German Driver's License Number</span></span>
>
> <span data-ttu-id="a0a2e-185">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-185">Germany Identity Card Number</span></span>
>
> <span data-ttu-id="a0a2e-186">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-186">German Passport Number</span></span>
>
> <span data-ttu-id="a0a2e-187">希腊国民身份证</span><span class="sxs-lookup"><span data-stu-id="a0a2e-187">Greece National ID Card</span></span>
>
> <span data-ttu-id="a0a2e-188">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="a0a2e-188">International Banking Account Number (IBAN)</span></span>
>
> <span data-ttu-id="a0a2e-189">IP 地址</span><span class="sxs-lookup"><span data-stu-id="a0a2e-189">IP Address</span></span>
>
> <span data-ttu-id="a0a2e-190">爱尔兰个人公共服务 (PPS) 号</span><span class="sxs-lookup"><span data-stu-id="a0a2e-190">Ireland Personal Public Service (PPS) Number</span></span>
>
> <span data-ttu-id="a0a2e-191">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-191">Italy's Driver's License Number</span></span>
>
> <span data-ttu-id="a0a2e-192">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-192">Netherlands Citizen's Service (BSN) Number</span></span>
>
> <span data-ttu-id="a0a2e-193">挪威标识号</span><span class="sxs-lookup"><span data-stu-id="a0a2e-193">Norway Identity Number</span></span>
>
> <span data-ttu-id="a0a2e-194">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="a0a2e-194">Poland Identity Card</span></span>
>
> <span data-ttu-id="a0a2e-195">波兰国家/地区身份证号码 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a0a2e-195">Poland National ID (PESEL)</span></span>
>
> <span data-ttu-id="a0a2e-196">波兰护照</span><span class="sxs-lookup"><span data-stu-id="a0a2e-196">Poland Passport</span></span>
>
> <span data-ttu-id="a0a2e-197">葡萄牙公民卡号</span><span class="sxs-lookup"><span data-stu-id="a0a2e-197">Portugal Citizen Card Number</span></span>
>
> <span data-ttu-id="a0a2e-198">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a0a2e-198">Spain Social Security Number (SSN)</span></span>
>
> <span data-ttu-id="a0a2e-199">瑞典国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-199">Sweden National ID</span></span>
>
> <span data-ttu-id="a0a2e-200">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-200">Sweden Passport Number</span></span>
>
> <span data-ttu-id="a0a2e-p110">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p110">U.K. Driver's License Number</span></span>
>
> <span data-ttu-id="a0a2e-p111">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p111">U.K. Electoral Roll Number</span></span>
>
> <span data-ttu-id="a0a2e-p112">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p112">U.K. National Health Service Number</span></span>
>
> <span data-ttu-id="a0a2e-p113">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p113">U.K. National Insurance Number (NINO)</span></span>
>
> <span data-ttu-id="a0a2e-p114">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p114">U.S./U.K. Passport Number</span></span>

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a><span data-ttu-id="a0a2e-211">向敏感信息类型查询添加参数以筛选出结果</span><span class="sxs-lookup"><span data-stu-id="a0a2e-211">Add parameters to a sensitive information type query to hone the results</span></span>

<span data-ttu-id="a0a2e-212">可以向敏感信息类型查询添加以下参数：</span><span class="sxs-lookup"><span data-stu-id="a0a2e-212">You can add these parameters to a sensitive information type query:</span></span>

-   <span data-ttu-id="a0a2e-213">计数范围 — 定义敏感信息在文档中出现多少次之后，才将该文档包含在查询结果中。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-213">Count range — define the number of occurrences of sensitive information a document needs to contain before it's included in the query results.</span></span>

-   <span data-ttu-id="a0a2e-214">置信区间 — 已检测到的敏感类型实际匹配的置信水平，例如 85 (85%)。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-214">Confidence range — the level of confidence that the detected sensitive type is actually a match, such as 85 (85%).</span></span>

<span data-ttu-id="a0a2e-215">语法：</span><span class="sxs-lookup"><span data-stu-id="a0a2e-215">Syntax:</span></span>

-   <span data-ttu-id="a0a2e-216">SensitiveType:"\<type\>|\<count range\>|\<confidence range\>"</span><span class="sxs-lookup"><span data-stu-id="a0a2e-216">SensitiveType:"\<type\>|\<count range\>|\<confidence range\>"</span></span>

<span data-ttu-id="a0a2e-217">示例：</span><span class="sxs-lookup"><span data-stu-id="a0a2e-217">Examples:</span></span>

-   <span data-ttu-id="a0a2e-218">SensitiveType:"Credit Card Number|5"（只返回正好包含五个信用卡号码的文档）</span><span class="sxs-lookup"><span data-stu-id="a0a2e-218">SensitiveType:"Credit Card Number|5" (return only documents that contain exactly five credit card numbers)</span></span>

-   <span data-ttu-id="a0a2e-219">SensitiveType:"Credit Card Number|\*|85.."（置信区间为 85 % 或更高）</span><span class="sxs-lookup"><span data-stu-id="a0a2e-219">SensitiveType:"Credit Card Number|\*|85.." (confidence range is 85 percent or higher)</span></span>

<span data-ttu-id="a0a2e-220">注意：“SensitiveType”区分大小写，但查询的其余部分不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-220">Note: "SensitiveType" is case sensitive, but the rest of the query is not.</span></span>

<span data-ttu-id="a0a2e-p115">此外，还可以使用属性和运算符来说明如何优化查询。有关详细信息和示例，请参阅[创建查询以查找存储在站点上的敏感数据](https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836)。</span><span class="sxs-lookup"><span data-stu-id="a0a2e-p115">You can also use properties, and operators to illustrate how you can refine your queries. For more information and examples, see [Form a query to find sensitive data stored on sites](https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span></span>
