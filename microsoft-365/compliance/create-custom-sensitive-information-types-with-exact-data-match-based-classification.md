---
title: 使用精确数据匹配创建自定义敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用基于精确数据匹配的分类来创建自定义敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17b9d9b1f551c62e42b2f5291f4d1fba8622f1ae
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287037"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="e9505-103">使用基于精确数据匹配的分类创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="e9505-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="e9505-104">[自定义敏感信息类型](sensitive-information-type-learn-about.md)用于帮助标识敏感项目，以防止它们被意外或不当地共享。</span><span class="sxs-lookup"><span data-stu-id="e9505-104">[Custom sensitive information types](sensitive-information-type-learn-about.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="e9505-105">你可以根据以下信息在 SIT () 敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="e9505-105">You define a custom sensitive information type (SIT)based on:</span></span>

- <span data-ttu-id="e9505-106">模式</span><span class="sxs-lookup"><span data-stu-id="e9505-106">patterns</span></span>
- <span data-ttu-id="e9505-107">如 *员工*、*徽章* 或 *ID 等关键字证据*</span><span class="sxs-lookup"><span data-stu-id="e9505-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="e9505-108">字符近似特定模式的证据</span><span class="sxs-lookup"><span data-stu-id="e9505-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="e9505-109">可信度</span><span class="sxs-lookup"><span data-stu-id="e9505-109">confidence levels</span></span>

 <span data-ttu-id="e9505-110">此类自定义敏感信息类型可满足许多组织的业务需求。</span><span class="sxs-lookup"><span data-stu-id="e9505-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="e9505-111">但如果希望自定义敏感信息类型 （SIT） 使用精确数据值，而不是找到基于通用模式的匹配项，又该怎么操作呢？</span><span class="sxs-lookup"><span data-stu-id="e9505-111">But what if you wanted a custom sensitive information type (SIT) that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="e9505-112">通过基于精确数据匹配 (EDM) 的分类，你可以创建专门设计的自定义敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="e9505-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="e9505-113">动态且轻松地刷新</span><span class="sxs-lookup"><span data-stu-id="e9505-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="e9505-114">更具可伸缩性</span><span class="sxs-lookup"><span data-stu-id="e9505-114">be more scalable</span></span>
- <span data-ttu-id="e9505-115">导致更少的误报</span><span class="sxs-lookup"><span data-stu-id="e9505-115">result in fewer false-positives</span></span>
- <span data-ttu-id="e9505-116">处理结构化敏感数据</span><span class="sxs-lookup"><span data-stu-id="e9505-116">work with structured sensitive data</span></span>
- <span data-ttu-id="e9505-117">更安全地处理敏感信息</span><span class="sxs-lookup"><span data-stu-id="e9505-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="e9505-118">与多种 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="e9505-118">be used with several Microsoft cloud services</span></span>

![基于 EDM 的分类](../media/EDMClassification.png)

<span data-ttu-id="e9505-120">基于 EDM 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。</span><span class="sxs-lookup"><span data-stu-id="e9505-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="e9505-121">数据库可以每天刷新一次，最多可包含 1 亿行数据。</span><span class="sxs-lookup"><span data-stu-id="e9505-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="e9505-122">因此，当员工、患者或客户往来并且记录发生更改时，你的自定义敏感信息类型仍将保持最新并且适用。</span><span class="sxs-lookup"><span data-stu-id="e9505-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="e9505-123">你还可以将基于 EDM 的分类与策略一起使用，例如[数据丢失防护策略](dlp-learn-about-dlp.md)或[Microsoft Cloud App Security 文件策略](/cloud-app-security/data-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="e9505-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](dlp-learn-about-dlp.md) or [Microsoft Cloud App Security file policies](/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="e9505-124">Microsoft 365 信息保护支持双字节字符集语言，用于:</span><span class="sxs-lookup"><span data-stu-id="e9505-124">Microsoft 365 Information Protection supports double byte character set languages for:</span></span>
>
> - <span data-ttu-id="e9505-125">简体中文</span><span class="sxs-lookup"><span data-stu-id="e9505-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="e9505-126">繁体中文</span><span class="sxs-lookup"><span data-stu-id="e9505-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="e9505-127">韩语</span><span class="sxs-lookup"><span data-stu-id="e9505-127">Korean</span></span>
> - <span data-ttu-id="e9505-128">日语</span><span class="sxs-lookup"><span data-stu-id="e9505-128">Japanese</span></span>
>
> <span data-ttu-id="e9505-129">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e9505-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="e9505-130">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="e9505-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="e9505-131">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="e9505-131">Required licenses and permissions</span></span>

<span data-ttu-id="e9505-132">你必须是全局管理员、合规性管理员或 Exchange Online 管理员才能执行本文中描述的任务。</span><span class="sxs-lookup"><span data-stu-id="e9505-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="e9505-133">若要了解有关 DLP 权限的详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="e9505-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="e9505-134">这些订阅中包含基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="e9505-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="e9505-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e9505-135">Office 365 E5</span></span>
- <span data-ttu-id="e9505-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e9505-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="e9505-137">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="e9505-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="e9505-138">Microsoft E5/A5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="e9505-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="e9505-139">订阅门户链接</span><span class="sxs-lookup"><span data-stu-id="e9505-139">Portal links for your subscription</span></span>

|<span data-ttu-id="e9505-140">门户</span><span class="sxs-lookup"><span data-stu-id="e9505-140">Portal</span></span>|<span data-ttu-id="e9505-141">全球/GCC</span><span class="sxs-lookup"><span data-stu-id="e9505-141">World Wide/GCC</span></span>|<span data-ttu-id="e9505-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="e9505-142">GCC-High</span></span>|<span data-ttu-id="e9505-143">DOD</span><span class="sxs-lookup"><span data-stu-id="e9505-143">DOD</span></span>|
|---|---|---|---|
|<span data-ttu-id="e9505-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="e9505-144">Office SCC</span></span>|<span data-ttu-id="e9505-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="e9505-145">protection.office.com</span></span>|<span data-ttu-id="e9505-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="e9505-146">scc.office365.us</span></span>|<span data-ttu-id="e9505-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="e9505-147">scc.protection.apps.mil</span></span>|
|<span data-ttu-id="e9505-148">Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="e9505-148">Microsoft 365 Security center</span></span>|<span data-ttu-id="e9505-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e9505-149">security.microsoft.com</span></span>|<span data-ttu-id="e9505-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="e9505-150">security.microsoft.us</span></span>|<span data-ttu-id="e9505-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="e9505-151">security.apps.mil</span></span>|
|<span data-ttu-id="e9505-152">Microsoft 365 合规中心</span><span class="sxs-lookup"><span data-stu-id="e9505-152">Microsoft 365 Compliance center</span></span>|<span data-ttu-id="e9505-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e9505-153">compliance.microsoft.com</span></span>|<span data-ttu-id="e9505-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="e9505-154">compliance.microsoft.us</span></span>|<span data-ttu-id="e9505-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="e9505-155">compliance.apps.mil</span></span>|

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="e9505-156">工作流程概览</span><span class="sxs-lookup"><span data-stu-id="e9505-156">The work flow at a glance</span></span>

|<span data-ttu-id="e9505-157">阶段</span><span class="sxs-lookup"><span data-stu-id="e9505-157">Phase</span></span>|<span data-ttu-id="e9505-158">所需项</span><span class="sxs-lookup"><span data-stu-id="e9505-158">What's needed</span></span>|
|---|---|
|[<span data-ttu-id="e9505-159">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="e9505-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="e9505-160">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="e9505-160">(As needed)</span></span><br/><span data-ttu-id="e9505-161">- [编辑数据库架构](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="e9505-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="e9505-162">- [删除架构](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="e9505-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span>|<span data-ttu-id="e9505-163">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="e9505-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="e9505-164">- XML 格式的数据库架构（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="e9505-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="e9505-165">- XML 格式的规则包（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="e9505-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="e9505-166">- 安全与合规中心的管理员权限（使用 PowerShell）</span><span class="sxs-lookup"><span data-stu-id="e9505-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span>|
|[<span data-ttu-id="e9505-167">第 2 部分：为敏感数据创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="e9505-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="e9505-168">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="e9505-168">(As needed)</span></span><br/>[<span data-ttu-id="e9505-169">刷新数据</span><span class="sxs-lookup"><span data-stu-id="e9505-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database)|<span data-ttu-id="e9505-170">- 自定义安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="e9505-170">- Custom security group and user account</span></span><br/><span data-ttu-id="e9505-171">- 使用 EDM 上载代理对计算机进行本地管理员访问</span><span class="sxs-lookup"><span data-stu-id="e9505-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="e9505-172">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="e9505-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="e9505-173">- 刷新数据的流程和计划</span><span class="sxs-lookup"><span data-stu-id="e9505-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="e9505-174">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="e9505-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services)|<span data-ttu-id="e9505-175">- 具有 DLP 的 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="e9505-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="e9505-176">- 已启用基于 EDM 的分类功能</span><span class="sxs-lookup"><span data-stu-id="e9505-176">- EDM-based classification feature enabled</span></span>|

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="e9505-177">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="e9505-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="e9505-178">设置和配置基于 EDM 的分类包括：</span><span class="sxs-lookup"><span data-stu-id="e9505-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="e9505-179">以 .tsv .csv保存敏感数据</span><span class="sxs-lookup"><span data-stu-id="e9505-179">Saving sensitive data in .csv or .tsv format</span></span>](#save-sensitive-data-in-csv-or-tsv-format)
2. [<span data-ttu-id="e9505-180">定义你的敏感信息数据库架构</span><span class="sxs-lookup"><span data-stu-id="e9505-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="e9505-181">设置规则包</span><span class="sxs-lookup"><span data-stu-id="e9505-181">Create a rule package</span></span>](#set-up-a-rule-package)

#### <a name="save-sensitive-data-in-csv-or-tsv-format"></a><span data-ttu-id="e9505-182">以 .tsv .csv保存敏感数据</span><span class="sxs-lookup"><span data-stu-id="e9505-182">Save sensitive data in .csv or .tsv format</span></span>

1. <span data-ttu-id="e9505-183">确定要使用的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e9505-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="e9505-184">将数据导出到应用（如 Microsoft Excel）中，将文件保存在文本文件中。</span><span class="sxs-lookup"><span data-stu-id="e9505-184">Export the data to an app, such as Microsoft Excel, and save the file in a text file.</span></span> <span data-ttu-id="e9505-185">文件可以保存在逗号分隔.csv (值中) .tsv (制表符分隔) 值或以管道分隔 (|) 格式。</span><span class="sxs-lookup"><span data-stu-id="e9505-185">The file can be saved in .csv (comma-separated values), .tsv (tab-separated values), or pipe-separated (|) format.</span></span> <span data-ttu-id="e9505-186">如果数据值可能包含逗号（如街道地址），则建议使用 .tsv 格式。</span><span class="sxs-lookup"><span data-stu-id="e9505-186">The .tsv format is recommended in cases where your data values may included commas, such as street addresses.</span></span>
<span data-ttu-id="e9505-187">数据文件最多可包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="e9505-187">The data file can include a maximum of:</span></span>
   - <span data-ttu-id="e9505-188">高达 1 亿行的敏感数据</span><span class="sxs-lookup"><span data-stu-id="e9505-188">Up to 100 million rows of sensitive data</span></span>
   - <span data-ttu-id="e9505-189">每个数据源最多 32 列（字段）</span><span class="sxs-lookup"><span data-stu-id="e9505-189">Up to 32 columns (fields) per data source</span></span>
   - <span data-ttu-id="e9505-190">最多 5 个列（字段）标记为可搜索</span><span class="sxs-lookup"><span data-stu-id="e9505-190">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="e9505-191">在数据库或 .tsv .csv构造敏感数据，使第一行包含用于基于 EDM 的分类的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="e9505-191">Structure the sensitive data in the .csv or .tsv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="e9505-192">在你的文件中，你可能有字段名称，如"ssn"、"birthdate"、"firstname"、"lastname"。</span><span class="sxs-lookup"><span data-stu-id="e9505-192">In your file you might have field names such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="e9505-193">列标题名称不能包含空格或下划线。</span><span class="sxs-lookup"><span data-stu-id="e9505-193">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="e9505-194">例如，本文中使用的示例 .csv 文件名为 *PatientRecords.csv*，其中包含 *PatientID*、*MRN*、*LastName*、*FirstName* 和 *SSN* 等列。</span><span class="sxs-lookup"><span data-stu-id="e9505-194">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="e9505-195">注意敏感数据字段的格式。</span><span class="sxs-lookup"><span data-stu-id="e9505-195">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="e9505-196">特别是，如果选择了".csv"格式，则分析内容中可能包含逗号的字段（例如，包含值"Seattle，WA"的街道地址）将分析为两个单独的字段。</span><span class="sxs-lookup"><span data-stu-id="e9505-196">In particular, fields that may contain commas in their content, for example, a street address that contains the value "Seattle,WA" would be parsed as two separate fields when parsed if the .csv format is selected.</span></span> <span data-ttu-id="e9505-197">若要避免这种情况，请使用 .tsv 格式，或在敏感数据表中用双引号将包含值的逗号括起来。</span><span class="sxs-lookup"><span data-stu-id="e9505-197">To avoid this, use the .tsv format or surrounded the comma containing values by double quotes in the sensitive data table.</span></span> <span data-ttu-id="e9505-198">如果逗号包含的值也包含空格，则需要创建与相应格式匹配的自定义 SIT。</span><span class="sxs-lookup"><span data-stu-id="e9505-198">If comma containing values also contain spaces, you need to create a custom SIT that matches the corresponding format.</span></span> <span data-ttu-id="e9505-199">例如，用于检测包含逗号和空格的多词字符串的 SIT。</span><span class="sxs-lookup"><span data-stu-id="e9505-199">For example, a SIT that detects multi-word string with commas and spaces in it.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="e9505-200">定义敏感信息数据库的架构</span><span class="sxs-lookup"><span data-stu-id="e9505-200">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="e9505-201">如果出于商业或技术原因不希望使用 PowerShell 或命令行创建架构和 EDM 敏感信息类型模式（规则包），可以使用 [精确数据匹配架构和敏感信息类型向导](sit-edm-wizard.md) 来创建。</span><span class="sxs-lookup"><span data-stu-id="e9505-201">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type pattern (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="e9505-202">完成创建架构和 EDM 敏感信息类型模式后，返回以完成所有必要步骤，使基于 EDM 的敏感信息类型处于可用状态。</span><span class="sxs-lookup"><span data-stu-id="e9505-202">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="e9505-203">精确数据匹配架构和敏感信息类型向导仅用于 World Wide 和 GCC。</span><span class="sxs-lookup"><span data-stu-id="e9505-203">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="e9505-204">以 XML 格式定义敏感信息数据库的架构（类似于下面的示例）。</span><span class="sxs-lookup"><span data-stu-id="e9505-204">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="e9505-205">命名此架构文件 **edm.xml** 并对其进行配置，确保对于数据库中的每一列，都有一行使用语法：</span><span class="sxs-lookup"><span data-stu-id="e9505-205">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span>

      <span data-ttu-id="e9505-206">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="e9505-206">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="e9505-207">将列名称用于 *字段名称* 值。</span><span class="sxs-lookup"><span data-stu-id="e9505-207">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="e9505-208">将 *searchable="true"* 用于可搜索的字段，最多 5 个字段。</span><span class="sxs-lookup"><span data-stu-id="e9505-208">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="e9505-209">必须至少有一个字段可搜索。</span><span class="sxs-lookup"><span data-stu-id="e9505-209">At least one field must be searchable.</span></span>

      <span data-ttu-id="e9505-210">例如，以下 XML 文件定义患者记录数据库的架构，其中五个字段指定为可搜索字段：*患者 ID*、*MRN*、*SSN*、*电话* 和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="e9505-210">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="e9505-211">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="e9505-211">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="e9505-212">使用 caseInsensitive 和 ignoredDelimiters 字段的可配置匹配项</span><span class="sxs-lookup"><span data-stu-id="e9505-212">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="e9505-213">以上 XML 示例使用了 `caseInsensitive` 和 `ignoredDelimiters` 字段。</span><span class="sxs-lookup"><span data-stu-id="e9505-213">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span>

<span data-ttu-id="e9505-214">当在架构定义中包括 \***caseInsensitive** _ 字段并将其设置为值 `true` 时，EDM 不会根据 `PatientID` 字段的大小写差异排除项目。</span><span class="sxs-lookup"><span data-stu-id="e9505-214">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="e9505-215">因此，EDM 会将 `PatientID` _ *FOO-1234*\* 和 **fOo-1234** 视为完全相同。</span><span class="sxs-lookup"><span data-stu-id="e9505-215">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="e9505-216">如果包括带支持字符和 \***ignoredDelimiters** _ 字段，EDM 将忽略 `PatientID` 中的这些字符。</span><span class="sxs-lookup"><span data-stu-id="e9505-216">When you include the \***ignoredDelimiters** _ field with supported characters,  EDM will ignore those characters in the `PatientID`.</span></span> <span data-ttu-id="e9505-217">因此，EDM 会将 `PatientID` _ *FOO-1234*\* 和 `PatientID` **FOO#1234** 视为完全相同。</span><span class="sxs-lookup"><span data-stu-id="e9505-217">So EDM will see, `PatientID` _ *FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="e9505-218">`ignoredDelimiters` 标志支持任何非字母数字字符，以下是一些示例：</span><span class="sxs-lookup"><span data-stu-id="e9505-218">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>

- <span data-ttu-id="e9505-219">\.</span><span class="sxs-lookup"><span data-stu-id="e9505-219">\.</span></span>
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \;

<span data-ttu-id="e9505-220">`ignoredDelimiters` 标志不支持：</span><span class="sxs-lookup"><span data-stu-id="e9505-220">The `ignoredDelimiters` flag doesn't support:</span></span>

- <span data-ttu-id="e9505-221">字符 0-9</span><span class="sxs-lookup"><span data-stu-id="e9505-221">characters 0-9</span></span>
- <span data-ttu-id="e9505-222">A-Z</span><span class="sxs-lookup"><span data-stu-id="e9505-222">A-Z</span></span>
- <span data-ttu-id="e9505-223">a-z</span><span class="sxs-lookup"><span data-stu-id="e9505-223">a-z</span></span>
- \"
- \,

<span data-ttu-id="e9505-224">在此示例中，如果同时使用 `caseInsensitive` 和 `ignoredDelimiters`，EDM 会将 **FOO-1234** 和 **fOo#1234** 视为完全相同，并将项目归类为患者记录敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e9505-224">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span>

1. <span data-ttu-id="e9505-225">连接安全&安全与合规中心 PowerShell 中的过程，连接安全与合规& [PowerShell。](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="e9505-225">Connect to the Security & Compliance Center PowerShell using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e9505-226">要上传数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e9505-226">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="e9505-227">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e9505-227">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="e9505-228">确认</span><span class="sxs-lookup"><span data-stu-id="e9505-228">Confirm</span></span>
      >
      > <span data-ttu-id="e9505-229">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="e9505-229">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="e9505-230">将导入数据存储“patientrecords”的新 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="e9505-230">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="e9505-231">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="e9505-231">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="e9505-232">若想更改但不进行确认，请在步骤 5 中改用此 cmdlet：New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="e9505-232">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="e9505-233">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="e9505-233">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="e9505-234">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="e9505-234">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="e9505-235">设置规则包</span><span class="sxs-lookup"><span data-stu-id="e9505-235">Set up a rule package</span></span>

1. <span data-ttu-id="e9505-236">按 XML 格式创建一个规则包（采用 Unicode 编码），如下例类似。</span><span class="sxs-lookup"><span data-stu-id="e9505-236">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="e9505-237">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="e9505-237">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="e9505-238">设置规则包时，请确保正确引用 .csv 或 .tsv **edm.xml文件。**</span><span class="sxs-lookup"><span data-stu-id="e9505-238">When you set up your rule package, make sure to correctly reference your .csv or .tsv file and **edm.xml** file.</span></span> <span data-ttu-id="e9505-239">可复制、修改和使用我们的示例。</span><span class="sxs-lookup"><span data-stu-id="e9505-239">You can copy, modify, and use our example.</span></span> <span data-ttu-id="e9505-240">在此示例 xml 中，需要对以下字段进行自定义，以创建 EDM 敏感类型：</span><span class="sxs-lookup"><span data-stu-id="e9505-240">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="e9505-241">**RulePack id & ExactMatch id**：使用 [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) 生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="e9505-241">**RulePack id & ExactMatch id**: Use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) to generate a GUID.</span></span>

      - <span data-ttu-id="e9505-242">**数据存储**：此字段指定要使用的 EDM 查找数据存储。</span><span class="sxs-lookup"><span data-stu-id="e9505-242">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="e9505-243">提供已配置的 EDM 架构的数据源名称。</span><span class="sxs-lookup"><span data-stu-id="e9505-243">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="e9505-244">**idMatch**：此字段指向 EDM 的主要元素。</span><span class="sxs-lookup"><span data-stu-id="e9505-244">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="e9505-245">匹配：指定要在精确查找中使用的字段。</span><span class="sxs-lookup"><span data-stu-id="e9505-245">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="e9505-246">在数据存储的 EDM 架构中提供可搜索的字段名称。</span><span class="sxs-lookup"><span data-stu-id="e9505-246">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="e9505-247">分类：此字段指定触发 EDM 查找的敏感类型匹配。</span><span class="sxs-lookup"><span data-stu-id="e9505-247">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="e9505-248">可提供现有内建或自定义敏感信息类型的名称或 GUID。</span><span class="sxs-lookup"><span data-stu-id="e9505-248">You can provide the Name or GUID of an existing built-in or custom sensitive information type.</span></span> <span data-ttu-id="e9505-249">请注意，与所提供敏感信息类型相匹配的任何字符串将进行哈希处理，并与敏感信息表中的每个条目相比较。</span><span class="sxs-lookup"><span data-stu-id="e9505-249">Be aware that any string that matches the sensitive information type provided will be hashed and compared to every entry in the sensitive information table.</span></span> <span data-ttu-id="e9505-250">为避免导致性能问题，如果将自定义敏感信息类型用作 EDM 中的分类元素，请通过添加辅助关键词或在自定义分类敏感信息类型定义中包含格式的方法，避免使用与较大百分比内容（如“任何数字”或“任何五个字母的单词”）相匹配的类型。</span><span class="sxs-lookup"><span data-stu-id="e9505-250">In order to avoid causing performance issues, if you use a custom sensitive information type as the Classification element in EDM, avoid using one that will match a large percentage of content (such as "any number" or "any five-letter word") by adding supporting keywords or including formatting in the definition of the custom classification sensitive information type.</span></span>

      - <span data-ttu-id="e9505-251">**匹配：** 此字段指向邻近 idMatch 找到的其他证据。</span><span class="sxs-lookup"><span data-stu-id="e9505-251">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="e9505-252">匹配：在数据存储的 EDM 架构中提供任何字段名称。</span><span class="sxs-lookup"><span data-stu-id="e9505-252">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="e9505-253">**资源：** 此部分在多个区域设置中指定敏感类型的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e9505-253">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="e9505-254">idRef：提供 ExactMatch ID 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="e9505-254">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="e9505-255">名称和说明：按需自定义。</span><span class="sxs-lookup"><span data-stu-id="e9505-255">Name & descriptions: customize as required.</span></span>

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

2. <span data-ttu-id="e9505-256">通过逐一运行下列 PowerShell cmdlet 来上传规则包：</span><span class="sxs-lookup"><span data-stu-id="e9505-256">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="e9505-257">此时，你已设置基于 EDM 的分类。</span><span class="sxs-lookup"><span data-stu-id="e9505-257">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="e9505-258">下一步是为敏感数据创建哈希，然后上传哈希以便编制索引。</span><span class="sxs-lookup"><span data-stu-id="e9505-258">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="e9505-259">回想一下，在前面的过程中我们的 PatientRecords 架构将 5 个文件定义为可搜索的项：*PatientID*、*MRN*、*SSN*、*Phone* 和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="e9505-259">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="e9505-260">我们的示例规则包中有这些字段并引用数据库架构文件 (**edm.xml**)，其中每个可搜索的字段具有一个 *ExactMatch* 项目。</span><span class="sxs-lookup"><span data-stu-id="e9505-260">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="e9505-261">请考虑以下 ExactMatch 项目：</span><span class="sxs-lookup"><span data-stu-id="e9505-261">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="e9505-262">在此示例中，请注意：</span><span class="sxs-lookup"><span data-stu-id="e9505-262">In this example, note that:</span></span>

- <span data-ttu-id="e9505-263">dataStore 名称引用了我们之前创建的 .csv 文件：**dataStore = "PatientRecords"**。</span><span class="sxs-lookup"><span data-stu-id="e9505-263">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="e9505-264">idMatch 值引用了数据库架构文件中列出的可搜索字段： **idMatch matches = "SSN"**。</span><span class="sxs-lookup"><span data-stu-id="e9505-264">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="e9505-265">分类值引用了现有或自定义敏感信息类型：**classification = "U.S. Social Security Number (SSN)"**。</span><span class="sxs-lookup"><span data-stu-id="e9505-265">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="e9505-266">（在此情况下，我们使用美国社会保障号的现有敏感信息类型。）</span><span class="sxs-lookup"><span data-stu-id="e9505-266">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="e9505-267">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="e9505-267">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="e9505-268">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="e9505-268">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="e9505-269">导入带有 EDM 敏感信息类型的规则包并导入敏感数据表后，可以使用合规中心的 EDM 向导中的 **测试** 功能测试新创建的类型。</span><span class="sxs-lookup"><span data-stu-id="e9505-269">After you have imported your rule package with your EDM sensitive info type and have imported your sensitive data table, you can test your newly created type by using the **Test** function in the EDM wizard in the compliance center.</span></span> <span data-ttu-id="e9505-270">有关使用此功能的说明，请参阅[使用精确数据匹配架构和敏感信息类型向导](sit-edm-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="e9505-270">See [Use the Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) for instructions on using this functionality.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="e9505-271">编辑基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="e9505-271">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="e9505-272">如果想要更改 **edm.xml** 文件，例如更改要对基于 EDM 的分类使用的字段，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="e9505-272">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="e9505-273">可更改 EDM 架构和数据文件以利用 **可配置匹配项**。</span><span class="sxs-lookup"><span data-stu-id="e9505-273">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="e9505-274">配置后，EDM 在对某个项目进行求值时将忽略大小写差异和某些分隔符。</span><span class="sxs-lookup"><span data-stu-id="e9505-274">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="e9505-275">这使你能够更轻松地定义 xml 架构和敏感数据文件。</span><span class="sxs-lookup"><span data-stu-id="e9505-275">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="e9505-276">若要了解详细信息，请参阅[修改精确数据匹配架构，以使用可配置匹配项](sit-modify-edm-schema-configurable-match.md)。</span><span class="sxs-lookup"><span data-stu-id="e9505-276">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="e9505-277">编辑 **edm.mxl** 文件（即本文的 [定义架构](#define-the-schema-for-your-database-of-sensitive-information)部分中讨论的文件）。</span><span class="sxs-lookup"><span data-stu-id="e9505-277">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="e9505-278">使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="e9505-278">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="e9505-279">要更新数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e9505-279">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="e9505-280">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e9505-280">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="e9505-281">确认</span><span class="sxs-lookup"><span data-stu-id="e9505-281">Confirm</span></span>
      >
      > <span data-ttu-id="e9505-282">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="e9505-282">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="e9505-283">将更新数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="e9505-283">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="e9505-284">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="e9505-284">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="e9505-285">若想更改但不进行确认，请在步骤 3 中改用此 cmdlet：Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="e9505-285">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="e9505-286">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="e9505-286">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="e9505-287">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="e9505-287">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="e9505-288">删除基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="e9505-288">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="e9505-289">（根据需要）若想删除正在对基于 EDM 的分类使用的架构，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="e9505-289">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="e9505-290">使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="e9505-290">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e9505-291">运行下列 PowerShell cmdlet，用“patient records”的数据存储名称替换要删除的名称：</span><span class="sxs-lookup"><span data-stu-id="e9505-291">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="e9505-292">系统将提示你进行确认：</span><span class="sxs-lookup"><span data-stu-id="e9505-292">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="e9505-293">确认</span><span class="sxs-lookup"><span data-stu-id="e9505-293">Confirm</span></span>
      >
      > <span data-ttu-id="e9505-294">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="e9505-294">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="e9505-295">将删除数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="e9505-295">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="e9505-296">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="e9505-296">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="e9505-297">若想更改但不进行确认，请在步骤 2 中改用此 cmdlet：Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="e9505-297">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="e9505-298">第 2 部分：为敏感数据创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="e9505-298">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="e9505-299">在此阶段，你将设置自定义安全组和用户帐户，并设置 EDM 上传代理工具。</span><span class="sxs-lookup"><span data-stu-id="e9505-299">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="e9505-300">然后，使用此工具为敏感数据创建带随机混淆值的哈希并上传。</span><span class="sxs-lookup"><span data-stu-id="e9505-300">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="e9505-301">可使用一台计算机完成哈希创建和上传，也可以将哈希创建步骤与上传步骤分离，以实现更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="e9505-301">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="e9505-302">如果想要在一台计算机上创建哈希并上传，则需要在可直接连接到 Microsoft 365 租户的计算机上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e9505-302">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="e9505-303">这要求计算机上需要具备明文敏感数据文件以便创建哈希。</span><span class="sxs-lookup"><span data-stu-id="e9505-303">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="e9505-p129">如果不希望公开明文敏感数据文件，可在计算机的安全位置上为其创建哈希，然后将哈希文件和随机混淆值文件复制到可直接连接到 Microsoft 365 租户的计算机以进行上传。在这种情况下，两台计算机上都需要 EDMUploadAgent。</span><span class="sxs-lookup"><span data-stu-id="e9505-p129">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload. In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9505-306">如果你使用"精确数据匹配"架构和敏感信息类型向导来创建你的架构和模式文件， ***必须*** 此过程的架构。</span><span class="sxs-lookup"><span data-stu-id="e9505-306">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you ***must*** download the schema for this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="e9505-307">如果你的组织为租户级别的Microsoft 365[](customer-key-overview.md)密钥，精确数据匹配将自动使用其加密功能。</span><span class="sxs-lookup"><span data-stu-id="e9505-307">If your organization has set up [Customer Key for Microsoft 365 at the tenant level](customer-key-overview.md), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="e9505-308">这仅适用于商业云中 E5 许可的租户。</span><span class="sxs-lookup"><span data-stu-id="e9505-308">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="e9505-309">先决条件</span><span class="sxs-lookup"><span data-stu-id="e9505-309">Prerequisites</span></span>

- <span data-ttu-id="e9505-310">向 **EDM\_DataUploaders** 安全组中添加一个 Microsoft 365 工作或学校帐户</span><span class="sxs-lookup"><span data-stu-id="e9505-310">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="e9505-311">准备一台使用.NET 版本 4.6.2 的 Windows 10 或 Windows Server 2016 计算机，用于运行 EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="e9505-311">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="e9505-312">用于上传的计算机上应含有以下内容的目录：</span><span class="sxs-lookup"><span data-stu-id="e9505-312">a directory on your upload machine for the:</span></span>
  - <span data-ttu-id="e9505-313">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="e9505-313">EDMUploadAgent</span></span>
  - <span data-ttu-id="e9505-314">您的敏感项目文件.csv .tsv 格式 **，PatientRecords.csv** 示例中所示</span><span class="sxs-lookup"><span data-stu-id="e9505-314">your sensitive item file in .csv or .tsv format, **PatientRecords.csv** in our examples</span></span>
  - <span data-ttu-id="e9505-315">输出哈希和 salt 文件</span><span class="sxs-lookup"><span data-stu-id="e9505-315">the output hash and salt files</span></span>
  - <span data-ttu-id="e9505-316">来自 **edm .xml** 文件的数据存储名称，在本示例中为 `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="e9505-316">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="e9505-317">如果使用 [精确数据匹配架构和敏感信息类型向导](sit-edm-wizard.md)，您 ***必须*** 将其下载。</span><span class="sxs-lookup"><span data-stu-id="e9505-317">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you ***must*** download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="e9505-318">设置安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="e9505-318">Set up the security group and user account</span></span>

1. <span data-ttu-id="e9505-319">作为全局管理员，使用相应的 [订阅链接](#portal-links-for-your-subscription)转到管理中心并 [创建安全组](/office365/admin/email/create-edit-or-delete-a-security-group)，名为 **EDM\_DataUploaders**。</span><span class="sxs-lookup"><span data-stu-id="e9505-319">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](/office365/admin/email/create-edit-or-delete-a-security-group) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="e9505-320">将一个或多个用户添加到 **EDM\_DataUploaders** 安全组。</span><span class="sxs-lookup"><span data-stu-id="e9505-320">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="e9505-321">（这些用户将管理敏感信息的数据库。）</span><span class="sxs-lookup"><span data-stu-id="e9505-321">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="e9505-322">从一台计算机上创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="e9505-322">Hash and upload from one computer</span></span>

<span data-ttu-id="e9505-323">此计算机必须对你的 Microsoft 365 租户拥有直接访问权限。</span><span class="sxs-lookup"><span data-stu-id="e9505-323">This computer must have direct access to your Microsoft 365 tenant.</span></span>

> [!NOTE]
>
> <span data-ttu-id="e9505-324">在开始此过程之前，请确保你是 **EDM\_DataUploaders** 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="e9505-324">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>
>
> <span data-ttu-id="e9505-325">（可选）您可以通过运行：在.csv对文件或 .tsv 文件运行验证：</span><span class="sxs-lookup"><span data-stu-id="e9505-325">Optionally, you can run a validation against your .csv or .tsv file before uploading by running:</span></span>
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> <span data-ttu-id="e9505-326">有关 EdmUploadAgent.exe 支持的所有参数的详细信息，请运行</span><span class="sxs-lookup"><span data-stu-id="e9505-326">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="e9505-327">按订阅类型链接到 EDM 上传代理</span><span class="sxs-lookup"><span data-stu-id="e9505-327">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="e9505-328">[商用 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 商业客户应使用此文件</span><span class="sxs-lookup"><span data-stu-id="e9505-328">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="e9505-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 这是专为高安全性政府云订阅者提供的</span><span class="sxs-lookup"><span data-stu-id="e9505-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="e9505-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 这是专为美国国防部云客户提供的</span><span class="sxs-lookup"><span data-stu-id="e9505-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="e9505-331">创建 EDMUploadAgent 要使用的工作目录。</span><span class="sxs-lookup"><span data-stu-id="e9505-331">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="e9505-332">例如，**C:\EDM\Data**。</span><span class="sxs-lookup"><span data-stu-id="e9505-332">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="e9505-333">将 **PatientRecords .csv** 文件放入该目录中。</span><span class="sxs-lookup"><span data-stu-id="e9505-333">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="e9505-334">下载并将适合你的订阅的 [EDM 上传代理](#links-to-edm-upload-agent-by-subscription-type)安装到步骤 1 创建的目录中。</span><span class="sxs-lookup"><span data-stu-id="e9505-334">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e9505-335">上述链接中的 EDMUploadAgent 已更新，可自动将随机混淆值添加到哈希数据。</span><span class="sxs-lookup"><span data-stu-id="e9505-335">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="e9505-336">或者，你可以提供自己的随机混淆值。</span><span class="sxs-lookup"><span data-stu-id="e9505-336">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="e9505-337">使用此版本后，你将不能使用 EDMUploadAgent 的先前版本。</span><span class="sxs-lookup"><span data-stu-id="e9505-337">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
   >
   > <span data-ttu-id="e9505-338">每天只能使用 EDMUploadAgent 上传数据到任何给定的数据存储空间两次。</span><span class="sxs-lookup"><span data-stu-id="e9505-338">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

   > [!TIP]
   > <span data-ttu-id="e9505-p134">要获取受支持命令参数的列表，请运行无代理参数。例如“EdmUploadAgent.exe”。</span><span class="sxs-lookup"><span data-stu-id="e9505-p134">To a get a list out of the supported command parameters, run the agent no arguments. For example 'EdmUploadAgent.exe'.</span></span>

3. <span data-ttu-id="e9505-341">授权 “EDM 上传代理”，打开命令提示符窗口（以管理员身份），切换到 **C:\EDM\Data** 目录，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9505-341">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="e9505-342">使用添加到 EDM_DataUploaders 安全组的 Microsoft 365 工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e9505-342">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="e9505-343">将从用户帐户提取你的租户信息以建立连接。</span><span class="sxs-lookup"><span data-stu-id="e9505-343">Your tenant information is extracted from the user account to make the connection.</span></span>

   <span data-ttu-id="e9505-344">可选：如使用精确数据匹配架构和敏感信息类型向导创建架构和模式文件，请在命令提示符窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9505-344">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. <span data-ttu-id="e9505-345">若要为敏感数据创建哈希并上传，请在命令提示符窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9505-345">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"]
   ```

   <span data-ttu-id="e9505-346">示例：**EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="e9505-346">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="e9505-347">敏感数据文件的默认格式是逗号分隔的值。</span><span class="sxs-lookup"><span data-stu-id="e9505-347">The default format for the sensitive data file is comma-separated values.</span></span> <span data-ttu-id="e9505-348">可以通过使用 /ColumnSeparator 参数指示"{Tab}"选项来指定以制表符分隔的文件，或者通过指示"|"选项指定管道分隔的文件。</span><span class="sxs-lookup"><span data-stu-id="e9505-348">You can specify a tab-separated file by indicating the "{Tab}" option with the /ColumnSeparator parameter, or you can specify a pipe-separated file by indicating the "|" option.</span></span>
   <span data-ttu-id="e9505-349">此命令将自动将随机生成的 salt 值添加到哈希中，以增强安全性。</span><span class="sxs-lookup"><span data-stu-id="e9505-349">This command will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="e9505-350">或者，如果你想要使用自己的随机混淆值，请将 **/Salt <saltvalue>** 值添加到命令中。</span><span class="sxs-lookup"><span data-stu-id="e9505-350">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="e9505-351">该值的长度必须为 64 个字符，并且只能包含 a-z 的字符和 0-9 的数字。</span><span class="sxs-lookup"><span data-stu-id="e9505-351">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

6. <span data-ttu-id="e9505-352">运行以下命令，检查“上传”状态：</span><span class="sxs-lookup"><span data-stu-id="e9505-352">Check the upload status by running this command:</span></span>

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   <span data-ttu-id="e9505-353">示例：**EdmUploadAgent/GetSession/DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="e9505-353">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

   <span data-ttu-id="e9505-354">在 **ProcessingInProgress** 中查找状态。</span><span class="sxs-lookup"><span data-stu-id="e9505-354">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="e9505-355">每隔几分钟再次检查，直到状态更改为“**已完成**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-355">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="e9505-356">在状态为已完成后，即可使用 EDM 数据。</span><span class="sxs-lookup"><span data-stu-id="e9505-356">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="e9505-357">将哈希与上传分开操作</span><span class="sxs-lookup"><span data-stu-id="e9505-357">Separate Hash and upload</span></span>

<span data-ttu-id="e9505-358">在处于安全环境中的计算机上执行哈希。</span><span class="sxs-lookup"><span data-stu-id="e9505-358">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="e9505-359">可选：如使用精确数据匹配架构和敏感信息类型向导创建架构和模式文件，请在命令提示符窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9505-359">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

```dos
EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
````

1. <span data-ttu-id="e9505-360">在命令提示符窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9505-360">Run the following command in Command Prompt windows:</span></span>

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file]
   ```

   <span data-ttu-id="e9505-361">例如：</span><span class="sxs-lookup"><span data-stu-id="e9505-361">For example:</span></span>

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml
   ```

   <span data-ttu-id="e9505-362">如果没有指定“**/Salt <saltvalue>**”选项，这将会输出具有以下扩展名的哈希文件和随机混淆值文件：</span><span class="sxs-lookup"><span data-stu-id="e9505-362">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>

   - <span data-ttu-id="e9505-363">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="e9505-363">.EdmHash</span></span>
   - <span data-ttu-id="e9505-364">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="e9505-364">.EdmSalt</span></span>

2. <span data-ttu-id="e9505-365">以安全的方式将这些文件复制到计算机，以将敏感项目.csv .tsv 文件 (PatientRecords) 租户。</span><span class="sxs-lookup"><span data-stu-id="e9505-365">Copy these files in a secure fashion to the computer you will use to upload your sensitive items .csv or .tsv file (PatientRecords) to your tenant.</span></span>

   <span data-ttu-id="e9505-366">若要上传哈希数据，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9505-366">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>
   ```

   <span data-ttu-id="e9505-367">例如：</span><span class="sxs-lookup"><span data-stu-id="e9505-367">For example:</span></span>

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**
   ```

   <span data-ttu-id="e9505-368">若要验证是否已上传敏感数据，请在“命令提示符”窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9505-368">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>

   ```dos
   EdmUploadAgent.exe /GetDataStore
   ```

   <span data-ttu-id="e9505-369">你将看到数据存储区列表以及上次更新时间。</span><span class="sxs-lookup"><span data-stu-id="e9505-369">You'll see a list of data stores and when they were last updated.</span></span>

   <span data-ttu-id="e9505-370">如果要查看所有数据上载到特定存储的信息，请在 Windows 命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9505-370">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```

   <span data-ttu-id="e9505-371">继续设置[刷新敏感信息数据库](#refreshing-your-sensitive-information-database)的流程和计划。</span><span class="sxs-lookup"><span data-stu-id="e9505-371">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="e9505-372">此时，你已准备好将基于 EDM 的分类与 Microsoft 云服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="e9505-372">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="e9505-373">例如，你可以[使用基于 EDM 的分类设置 DLP 策略](#to-create-a-dlp-policy-with-edm)。</span><span class="sxs-lookup"><span data-stu-id="e9505-373">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="e9505-374">刷新敏感信息数据库</span><span class="sxs-lookup"><span data-stu-id="e9505-374">Refreshing your sensitive information database</span></span>

<span data-ttu-id="e9505-375">可以每天刷新敏感信息数据库，EDM 上传工具会重新为敏感数据创建索引，然后重新上传索引数据。</span><span class="sxs-lookup"><span data-stu-id="e9505-375">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="e9505-376">确定刷新敏感信息数据库的流程和频率（每天或每周）。</span><span class="sxs-lookup"><span data-stu-id="e9505-376">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="e9505-377">将敏感数据重新导出到应用程序（如 Microsoft Excel）并保存为 .csv .tsv 格式的文件。</span><span class="sxs-lookup"><span data-stu-id="e9505-377">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv or .tsv format.</span></span> <span data-ttu-id="e9505-378">在按照[为敏感数据创建哈希并上传](#part-2-hash-and-upload-the-sensitive-data)中所述的步骤执行操作时，让所使用的文件名和位置保持不变。</span><span class="sxs-lookup"><span data-stu-id="e9505-378">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="e9505-379">如果 .csv 或 .tsv 文件的结构 (字段名) ，则刷新数据时无需对数据库架构文件进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="e9505-379">If there are no changes to the structure (field names) of the .csv or .tsv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="e9505-380">但是，如果必须进行更改，请确保相应地编辑数据库架和规则包。</span><span class="sxs-lookup"><span data-stu-id="e9505-380">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="e9505-381">使用[任务计划程序](/windows/desktop/TaskSchd/task-scheduler-start-page)自动执行[创建哈希并上载敏感数据](#part-2-hash-and-upload-the-sensitive-data)流程中的步骤 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="e9505-381">Use [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="e9505-382">你可以使用多种方法来计划任务：</span><span class="sxs-lookup"><span data-stu-id="e9505-382">You can schedule tasks using several methods:</span></span>

   |<span data-ttu-id="e9505-383">方法</span><span class="sxs-lookup"><span data-stu-id="e9505-383">Method</span></span>|<span data-ttu-id="e9505-384">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="e9505-384">What to do</span></span>|
   |---|---|
   |<span data-ttu-id="e9505-385">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9505-385">Windows PowerShell</span></span>|<span data-ttu-id="e9505-386">请参阅本文中的[计划任务](/powershell/module/scheduledtasks/)文档和[示例 PowerShell 脚本](#example-powershell-script-for-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="e9505-386">See the [ScheduledTasks](/powershell/module/scheduledtasks/) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span>|
   |<span data-ttu-id="e9505-387">任务计划程序 API</span><span class="sxs-lookup"><span data-stu-id="e9505-387">Task Scheduler API</span></span>|<span data-ttu-id="e9505-388">请参阅[任务计划程序](/windows/desktop/TaskSchd/using-the-task-scheduler)文档</span><span class="sxs-lookup"><span data-stu-id="e9505-388">See the [Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>|
   |<span data-ttu-id="e9505-389">Windows 用户界面</span><span class="sxs-lookup"><span data-stu-id="e9505-389">Windows user interface</span></span>|<span data-ttu-id="e9505-390">在 Windows 中单击“**开始**”，然后键入 Task Scheduler。</span><span class="sxs-lookup"><span data-stu-id="e9505-390">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="e9505-391">然后，在结果列表中，右键单击“**任务计划程序**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-391">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>|

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="e9505-392">任务计划程序的示例 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="e9505-392">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="e9505-393">此部分包含一个示例 PowerShell 脚本，你可以使用该脚本来计划为数据创建哈希并上传哈希数据的任务：</span><span class="sxs-lookup"><span data-stu-id="e9505-393">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="e9505-394">在合并步骤中计划哈希和上传</span><span class="sxs-lookup"><span data-stu-id="e9505-394">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="e9505-395">将计划哈希和上传作为单独的步骤</span><span class="sxs-lookup"><span data-stu-id="e9505-395">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="e9505-396">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="e9505-396">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="e9505-397">这些位置支持 EDM 敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="e9505-397">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="e9505-398">针对 Exchange Online 的 DLP（电子邮件）</span><span class="sxs-lookup"><span data-stu-id="e9505-398">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="e9505-399">OneDrive for Business（文件）</span><span class="sxs-lookup"><span data-stu-id="e9505-399">OneDrive for Business (files)</span></span>
- <span data-ttu-id="e9505-400">Microsoft Teams（对话）</span><span class="sxs-lookup"><span data-stu-id="e9505-400">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="e9505-401">针对 SharePoint 的 DLP（文件）</span><span class="sxs-lookup"><span data-stu-id="e9505-401">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="e9505-402">Microsoft Cloud App Security DLP 策略</span><span class="sxs-lookup"><span data-stu-id="e9505-402">Microsoft Cloud App Security DLP policies</span></span>
- <span data-ttu-id="e9505-403">服务器端自动标记策略 - 适用于商业云客户和政府云客户</span><span class="sxs-lookup"><span data-stu-id="e9505-403">Server-side auto-labeling policies - available for commercial cloud customers and government cloud customers</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="e9505-404">使用 EDM 创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="e9505-404">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="e9505-405">使用相应的[订阅链接](#portal-links-for-your-subscription)转到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="e9505-405">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="e9505-406">选择 **数据丢失防护** \> **策略**。</span><span class="sxs-lookup"><span data-stu-id="e9505-406">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="e9505-407">选择 **创建策略** \> **自定义** \> "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e9505-407">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="e9505-408">在“**命名策略**”选项卡上，指定名称和说明，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-408">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="e9505-409">在“**选择位置**”选项卡上，选择“**允许选择特定位置**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-409">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="e9505-410">在“**状态**”列中，选择“**Exchange 电子邮件、OneDrive 帐户、团队聊天和频道邮件**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-410">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message**, and then choose **Next**.</span></span>

7. <span data-ttu-id="e9505-411">在“**策略设置**”选项卡上，选择“**使用高级设置**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-411">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="e9505-412">选择“**+ 新建规则**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-412">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="e9505-413">在“**名称**”部分中，指定规则的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e9505-413">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="e9505-414">在“**条件**”部分的“**+ 添加条件**”列表中，选择“**内容包含敏感类型**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-414">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![内容包含敏感信息类型](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="e9505-416">搜索你在设置规则包时创建的敏感信息类型，然后选择“**+ 添加**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-416">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>
    <span data-ttu-id="e9505-417">然后选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-417">Then choose **Done**.</span></span>

12. <span data-ttu-id="e9505-418">完成为规则选择相关选项，例如“**用户通知**”、“**用户覆盖**”、“**事件报告**”等，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-418">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="e9505-419">在“**策略设置**”选项卡上，查看你的规则，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-419">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="e9505-420">指定是立即打开策略、测试它还是保持关闭。</span><span class="sxs-lookup"><span data-stu-id="e9505-420">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="e9505-421">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-421">Then choose **Next**.</span></span>

15. <span data-ttu-id="e9505-422">在“**查看你的设置**”选项卡上，查看你的策略。</span><span class="sxs-lookup"><span data-stu-id="e9505-422">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="e9505-423">执行任何必要的更改。</span><span class="sxs-lookup"><span data-stu-id="e9505-423">Make any needed changes.</span></span> <span data-ttu-id="e9505-424">准备好后，选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="e9505-424">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="e9505-425">新 DLP 策略大约需要一个小时才能通过你的数据中心。</span><span class="sxs-lookup"><span data-stu-id="e9505-425">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e9505-426">相关文章</span><span class="sxs-lookup"><span data-stu-id="e9505-426">Related articles</span></span>

- [<span data-ttu-id="e9505-427">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="e9505-427">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="e9505-428">了解敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="e9505-428">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="e9505-429">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="e9505-429">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="e9505-430">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e9505-430">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="e9505-431">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="e9505-431">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)
- [<span data-ttu-id="e9505-432">修改精确数据匹配架构，以使用可配置匹配项</span><span class="sxs-lookup"><span data-stu-id="e9505-432">Modify Exact Data Match schema to use configurable match</span></span>](sit-modify-edm-schema-configurable-match.md)
