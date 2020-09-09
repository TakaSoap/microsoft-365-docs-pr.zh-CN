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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用基于精确数据匹配的分类来创建自定义敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f4bbbe8726370297e9ef6317cd468789bb3b3bfe
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300430"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="89c36-103">使用基于精确数据匹配的分类创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="89c36-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="89c36-104">[自定义敏感信息类型](custom-sensitive-info-types.md) 用于帮助标识敏感项目，以防止它们被意外或不当地共享。</span><span class="sxs-lookup"><span data-stu-id="89c36-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="89c36-105">可基于以下内容定义自定义敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="89c36-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="89c36-106">模式</span><span class="sxs-lookup"><span data-stu-id="89c36-106">patterns</span></span>
- <span data-ttu-id="89c36-107">如 *员工*、 *徽章*或 *ID 等关键字证据*</span><span class="sxs-lookup"><span data-stu-id="89c36-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="89c36-108">字符近似特定模式的证据</span><span class="sxs-lookup"><span data-stu-id="89c36-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="89c36-109">可信度</span><span class="sxs-lookup"><span data-stu-id="89c36-109">confidence levels</span></span>

 <span data-ttu-id="89c36-110">此类自定义敏感信息类型可满足许多组织的业务需求。</span><span class="sxs-lookup"><span data-stu-id="89c36-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="89c36-111">但是，如果你需要使用精确数据值的自定义敏感信息类型（而非基于泛型模式的匹配项），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="89c36-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="89c36-112">通过基于精确数据匹配 (EDM) 的分类，你可以创建专门设计的自定义敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="89c36-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="89c36-113">动态并且可刷新的</span><span class="sxs-lookup"><span data-stu-id="89c36-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="89c36-114">更具可伸缩性</span><span class="sxs-lookup"><span data-stu-id="89c36-114">be more scalable</span></span>
- <span data-ttu-id="89c36-115">导致更少的误报</span><span class="sxs-lookup"><span data-stu-id="89c36-115">result in fewer false-positives</span></span>
- <span data-ttu-id="89c36-116">处理结构化敏感数据</span><span class="sxs-lookup"><span data-stu-id="89c36-116">work with structured sensitive data</span></span>
- <span data-ttu-id="89c36-117">更安全地处理敏感信息</span><span class="sxs-lookup"><span data-stu-id="89c36-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="89c36-118">与多种 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="89c36-118">be used with several Microsoft cloud services</span></span>

![基于 EDM 的分类](../media/EDMClassification.png)

<span data-ttu-id="89c36-120">基于 EDM 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。</span><span class="sxs-lookup"><span data-stu-id="89c36-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="89c36-121">数据库可以每天刷新一次，最多可包含 1 亿行数据。</span><span class="sxs-lookup"><span data-stu-id="89c36-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="89c36-122">因此，当员工、患者或客户往来并且记录发生更改时，你的自定义敏感信息类型仍将保持最新并且适用。</span><span class="sxs-lookup"><span data-stu-id="89c36-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="89c36-123">你还可以将基于 EDM 的分类与策略一起使用，例如 [数据丢失防护策略](data-loss-prevention-policies.md) (DLP) 或 [Microsoft Cloud App Security 文件策略](https://docs.microsoft.com/cloud-app-security/data-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="89c36-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="89c36-124">Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持（预览）：</span><span class="sxs-lookup"><span data-stu-id="89c36-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="89c36-125">简体中文</span><span class="sxs-lookup"><span data-stu-id="89c36-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="89c36-126">繁体中文</span><span class="sxs-lookup"><span data-stu-id="89c36-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="89c36-127">韩语</span><span class="sxs-lookup"><span data-stu-id="89c36-127">Korean</span></span>
> - <span data-ttu-id="89c36-128">日语</span><span class="sxs-lookup"><span data-stu-id="89c36-128">Japanese</span></span>
> 
><span data-ttu-id="89c36-129">此功能预览仅在商业云中提供，并且仅在以下地区推出：</span><span class="sxs-lookup"><span data-stu-id="89c36-129">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="89c36-130">日本</span><span class="sxs-lookup"><span data-stu-id="89c36-130">Japan</span></span>
> - <span data-ttu-id="89c36-131">韩国</span><span class="sxs-lookup"><span data-stu-id="89c36-131">Korea</span></span>
> - <span data-ttu-id="89c36-132">中国大陆</span><span class="sxs-lookup"><span data-stu-id="89c36-132">China</span></span>
> - <span data-ttu-id="89c36-133">香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="89c36-133">Hong Kong</span></span>
> - <span data-ttu-id="89c36-134">澳门特别行政区</span><span class="sxs-lookup"><span data-stu-id="89c36-134">Macau</span></span>
> - <span data-ttu-id="89c36-135">中国台湾</span><span class="sxs-lookup"><span data-stu-id="89c36-135">Taiwan</span></span>
>
><span data-ttu-id="89c36-136">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="89c36-136">This support is available for sensitive information types.</span></span> <span data-ttu-id="89c36-137">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="89c36-137">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="89c36-138">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="89c36-138">Required licenses and permissions</span></span>

<span data-ttu-id="89c36-139">你必须是全局管理员、合规性管理员或 Exchange Online 管理员才能执行本文中描述的任务。</span><span class="sxs-lookup"><span data-stu-id="89c36-139">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="89c36-140">若要了解有关 DLP 权限的详细信息，请参阅 [权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="89c36-140">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="89c36-141">这些订阅中包含基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="89c36-141">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="89c36-142">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="89c36-142">Office 365 E5</span></span>
- <span data-ttu-id="89c36-143">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="89c36-143">Microsoft 365 E5</span></span>
- <span data-ttu-id="89c36-144">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="89c36-144">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="89c36-145">Microsoft E5/A5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="89c36-145">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="89c36-146">订阅门户链接</span><span class="sxs-lookup"><span data-stu-id="89c36-146">Portal links for your subscription</span></span>


|<span data-ttu-id="89c36-147">门户</span><span class="sxs-lookup"><span data-stu-id="89c36-147">Portal</span></span>  |<span data-ttu-id="89c36-148">全球/GCC</span><span class="sxs-lookup"><span data-stu-id="89c36-148">World Wide/GCC</span></span>  |<span data-ttu-id="89c36-149">GCC-High</span><span class="sxs-lookup"><span data-stu-id="89c36-149">GCC-High</span></span>  |<span data-ttu-id="89c36-150">DOD</span><span class="sxs-lookup"><span data-stu-id="89c36-150">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="89c36-151">Office SCC</span><span class="sxs-lookup"><span data-stu-id="89c36-151">Office SCC</span></span>     |  <span data-ttu-id="89c36-152">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="89c36-152">protection.office.com</span></span>       |<span data-ttu-id="89c36-153">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="89c36-153">scc.office365.us</span></span>         |<span data-ttu-id="89c36-154">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="89c36-154">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="89c36-155">Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="89c36-155">Microsoft 365 Security center</span></span>     |<span data-ttu-id="89c36-156">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="89c36-156">security.microsoft.com</span></span>         |<span data-ttu-id="89c36-157">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="89c36-157">security.microsoft.us</span></span>         |<span data-ttu-id="89c36-158">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="89c36-158">security.apps.mil</span></span>|
|<span data-ttu-id="89c36-159">Microsoft 365 合规中心</span><span class="sxs-lookup"><span data-stu-id="89c36-159">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="89c36-160">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="89c36-160">compliance.microsoft.com</span></span>         |<span data-ttu-id="89c36-161">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="89c36-161">compliance.microsoft.us</span></span>         |<span data-ttu-id="89c36-162">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="89c36-162">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="89c36-163">工作流程概览</span><span class="sxs-lookup"><span data-stu-id="89c36-163">The work flow at a glance</span></span>

|<span data-ttu-id="89c36-164">阶段</span><span class="sxs-lookup"><span data-stu-id="89c36-164">Phase</span></span>  |<span data-ttu-id="89c36-165">所需项</span><span class="sxs-lookup"><span data-stu-id="89c36-165">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="89c36-166">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="89c36-166">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="89c36-167">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="89c36-167">(As needed)</span></span><br/><span data-ttu-id="89c36-168">- [编辑数据库架构](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="89c36-168">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="89c36-169">- [删除架构](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="89c36-169">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="89c36-170">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="89c36-170">- Read access to the sensitive data</span></span><br/><span data-ttu-id="89c36-171">- XML 格式的数据库架构（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="89c36-171">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="89c36-172">- XML 格式的规则包（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="89c36-172">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="89c36-173">- 安全与合规中心的管理员权限（使用 PowerShell）</span><span class="sxs-lookup"><span data-stu-id="89c36-173">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="89c36-174">第 2 部分：为敏感数据创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="89c36-174">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="89c36-175">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="89c36-175">(As needed)</span></span><br/>[<span data-ttu-id="89c36-176">刷新数据</span><span class="sxs-lookup"><span data-stu-id="89c36-176">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="89c36-177">- 自定义安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="89c36-177">- Custom security group and user account</span></span><br/><span data-ttu-id="89c36-178">- 使用 EDM 上载代理对计算机进行本地管理员访问</span><span class="sxs-lookup"><span data-stu-id="89c36-178">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="89c36-179">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="89c36-179">- Read access to the sensitive data</span></span><br/><span data-ttu-id="89c36-180">- 刷新数据的流程和计划</span><span class="sxs-lookup"><span data-stu-id="89c36-180">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="89c36-181">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="89c36-181">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="89c36-182">- 具有 DLP 的 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="89c36-182">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="89c36-183">- 已启用基于 EDM 的分类功能</span><span class="sxs-lookup"><span data-stu-id="89c36-183">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="89c36-184">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="89c36-184">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="89c36-185">设置和配置基于 EDM 的分类包括：</span><span class="sxs-lookup"><span data-stu-id="89c36-185">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="89c36-186">保存 .csv 格式的敏感数据</span><span class="sxs-lookup"><span data-stu-id="89c36-186">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="89c36-187">定义你的敏感信息数据库架构</span><span class="sxs-lookup"><span data-stu-id="89c36-187">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="89c36-188">设置规则包</span><span class="sxs-lookup"><span data-stu-id="89c36-188">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="89c36-189">保存 .csv 格式的敏感数据</span><span class="sxs-lookup"><span data-stu-id="89c36-189">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="89c36-190">确定要使用的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="89c36-190">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="89c36-191">将数据导出到应用（如 Microsoft Excel），然后以 .csv 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="89c36-191">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="89c36-192">数据文件最多可包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="89c36-192">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="89c36-193">高达 1 亿行的敏感数据</span><span class="sxs-lookup"><span data-stu-id="89c36-193">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="89c36-194">每个数据源最多 32 列（字段）</span><span class="sxs-lookup"><span data-stu-id="89c36-194">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="89c36-195">最多 5 个列（字段）标记为可搜索</span><span class="sxs-lookup"><span data-stu-id="89c36-195">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="89c36-196">在 .csv 文件中构造敏感数据，使第一行包含用于基于 EDM 的分类的字段名称。</span><span class="sxs-lookup"><span data-stu-id="89c36-196">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="89c36-197">在 .csv 文件中，你可能拥有“ssn”、“生日”、“名字”、“姓氏”等字段名称。</span><span class="sxs-lookup"><span data-stu-id="89c36-197">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="89c36-198">列标题名称不能包含空格或下划线。</span><span class="sxs-lookup"><span data-stu-id="89c36-198">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="89c36-199">例如，本文中使用的示例 .csv 文件名为 *PatientRecords.csv*，其中包含 *PatientID*、 *MRN*、 *LastName*、 *FirstName* 和  *SSN* 等列。</span><span class="sxs-lookup"><span data-stu-id="89c36-199">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="89c36-200">定义敏感信息数据库的架构</span><span class="sxs-lookup"><span data-stu-id="89c36-200">Define the schema for your database of sensitive information</span></span>

3. <span data-ttu-id="89c36-201">以 XML 格式定义敏感信息数据库的架构（类似于下面的示例）。</span><span class="sxs-lookup"><span data-stu-id="89c36-201">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="89c36-202">命名此架构文件 **edm.xml**并对其进行配置，确保对于数据库中的每一列，都有一行使用语法：</span><span class="sxs-lookup"><span data-stu-id="89c36-202">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="89c36-203">`\<Field name="" searchable=""/\>`（）。</span><span class="sxs-lookup"><span data-stu-id="89c36-203">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="89c36-204">将列名用于 *字段名称*值。 </span><span class="sxs-lookup"><span data-stu-id="89c36-204">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="89c36-205">将 *searchable="true"* 用于可搜索的字段，最多 5 个字段。</span><span class="sxs-lookup"><span data-stu-id="89c36-205">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="89c36-206">必须至少有一个字段可搜索。</span><span class="sxs-lookup"><span data-stu-id="89c36-206">At least one field must be searchable.</span></span>

      <span data-ttu-id="89c36-207">例如，以下 XML 文件定义患者记录数据库的架构，其中五个字段指定为可搜索字段： *患者 ID*、 *MRN*、 *SSN*、 *电话*和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="89c36-207">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="89c36-208">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="89c36-208">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" />
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

4. <span data-ttu-id="89c36-209">使用[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="89c36-209">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="89c36-210">要上传数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="89c36-210">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="89c36-211">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="89c36-211">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="89c36-212">确认</span><span class="sxs-lookup"><span data-stu-id="89c36-212">Confirm</span></span>
      >
      > <span data-ttu-id="89c36-213">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="89c36-213">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="89c36-214">将导入数据存储“patientrecords”的新 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="89c36-214">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="89c36-215">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="89c36-215">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="89c36-216">若想更改但不进行确认，请在步骤 5 中改用此 cmdlet：New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="89c36-216">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="89c36-217">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="89c36-217">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="89c36-218">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="89c36-218">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="89c36-219">设置规则包</span><span class="sxs-lookup"><span data-stu-id="89c36-219">Set up a rule package</span></span>

1. <span data-ttu-id="89c36-220">按 XML 格式创建一个规则包（采用 Unicode 编码），如下例类似。</span><span class="sxs-lookup"><span data-stu-id="89c36-220">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="89c36-221">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="89c36-221">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="89c36-222">设置规则包时，请确保正确引用 .csv 文件和 **edm.xml** 文件。</span><span class="sxs-lookup"><span data-stu-id="89c36-222">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="89c36-223">可复制、修改和使用我们的示例。</span><span class="sxs-lookup"><span data-stu-id="89c36-223">You can copy, modify, and use our example.</span></span> <span data-ttu-id="89c36-224">在此示例 xml 中，需要对以下字段进行自定义，以创建 EDM 敏感类型：</span><span class="sxs-lookup"><span data-stu-id="89c36-224">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="89c36-225">**RulePack id & ExactMatch id**：使用 [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) 生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="89c36-225">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="89c36-226">**数据存储**：此字段指定要使用的 EDM 查找数据存储。</span><span class="sxs-lookup"><span data-stu-id="89c36-226">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="89c36-227">提供已配置的 EDM 架构的数据源名称。</span><span class="sxs-lookup"><span data-stu-id="89c36-227">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="89c36-228">**idMatch**：此字段指向 EDM 的主要元素。</span><span class="sxs-lookup"><span data-stu-id="89c36-228">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="89c36-229">匹配：指定要在精确查找中使用的字段。</span><span class="sxs-lookup"><span data-stu-id="89c36-229">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="89c36-230">在数据存储的 EDM 架构中提供可搜索的字段名称。</span><span class="sxs-lookup"><span data-stu-id="89c36-230">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="89c36-231">分类：此字段指定触发 EDM 查找的敏感类型匹配。</span><span class="sxs-lookup"><span data-stu-id="89c36-231">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="89c36-232">可提供现有内置或自定义分类的名称或 GUID。</span><span class="sxs-lookup"><span data-stu-id="89c36-232">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="89c36-233">**匹配：** 此字段指向邻近 idMatch 找到的其他证据。</span><span class="sxs-lookup"><span data-stu-id="89c36-233">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="89c36-234">匹配：在数据存储的 EDM 架构中提供任何字段名称。</span><span class="sxs-lookup"><span data-stu-id="89c36-234">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="89c36-235">**资源：** 此部分在多个区域设置中指定敏感类型的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="89c36-235">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="89c36-236">idRef：提供 ExactMatch ID 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="89c36-236">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="89c36-237">名称和说明：按需自定义。</span><span class="sxs-lookup"><span data-stu-id="89c36-237">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="89c36-238">通过逐一运行下列 PowerShell cmdlet 来上传规则包：</span><span class="sxs-lookup"><span data-stu-id="89c36-238">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="89c36-239">此时，你已设置基于 EDM 的分类。</span><span class="sxs-lookup"><span data-stu-id="89c36-239">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="89c36-240">下一步是为敏感数据创建哈希，然后上传哈希以便编制索引。</span><span class="sxs-lookup"><span data-stu-id="89c36-240">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="89c36-241">回想一下，在前面的过程中我们的 PatientRecords 架构将五个字段定义为可搜索： *PatientID*、 *MRN*、 *SSN*、 *Phone* 和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="89c36-241">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="89c36-242">我们的示例规则包中有这些字段并引用数据库架构文件 (**edm.xml**)，其中每个可搜索的字段具有一个 *ExactMatch* 项目。</span><span class="sxs-lookup"><span data-stu-id="89c36-242">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="89c36-243">请考虑以下 ExactMatch 项目：</span><span class="sxs-lookup"><span data-stu-id="89c36-243">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="89c36-244">在此示例中，请注意：</span><span class="sxs-lookup"><span data-stu-id="89c36-244">In this example, note that:</span></span>

- <span data-ttu-id="89c36-245">dataStore 名称引用了我们之前创建的 .csv 文件： **dataStore = "PatientRecords"**。</span><span class="sxs-lookup"><span data-stu-id="89c36-245">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="89c36-246">idMatch 值引用了数据库架构文件中列出的可搜索字段： **idMatch matches = "SSN"**。</span><span class="sxs-lookup"><span data-stu-id="89c36-246">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="89c36-247">分类值引用了现有或自定义敏感信息类型： **classification = "U.S. Social Security Number (SSN)"**。</span><span class="sxs-lookup"><span data-stu-id="89c36-247">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="89c36-248">（在此情况下，我们使用美国社会保障号的现有敏感信息类型。）</span><span class="sxs-lookup"><span data-stu-id="89c36-248">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="89c36-249">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="89c36-249">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="89c36-250">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="89c36-250">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="89c36-251">编辑基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="89c36-251">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="89c36-252">如果想要更改**edm.xml** 文件，例如更改要对基于 EDM 的分类使用的字段，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="89c36-252">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="89c36-253">编辑 **edm.xml** 文件（即本文的 [定义架构](#define-the-schema-for-your-database-of-sensitive-information) 部分中讨论的文件）。</span><span class="sxs-lookup"><span data-stu-id="89c36-253">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="89c36-254">使用[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="89c36-254">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="89c36-255">要更新数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="89c36-255">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="89c36-256">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="89c36-256">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="89c36-257">确认</span><span class="sxs-lookup"><span data-stu-id="89c36-257">Confirm</span></span>
      >
      > <span data-ttu-id="89c36-258">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="89c36-258">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="89c36-259">将更新数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="89c36-259">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="89c36-260">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="89c36-260">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="89c36-261">若想更改但不进行确认，请在步骤 3 中改用此 cmdlet：Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="89c36-261">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="89c36-262">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="89c36-262">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="89c36-263">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="89c36-263">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="89c36-264">删除基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="89c36-264">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="89c36-265">（根据需要）若想删除正在对基于 EDM 的分类使用的架构，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="89c36-265">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="89c36-266">使用[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="89c36-266">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="89c36-267">运行下列 PowerShell cmdlet，用“patient records”的数据存储名称替换要删除的名称：</span><span class="sxs-lookup"><span data-stu-id="89c36-267">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="89c36-268">系统将提示你进行确认：</span><span class="sxs-lookup"><span data-stu-id="89c36-268">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="89c36-269">确认</span><span class="sxs-lookup"><span data-stu-id="89c36-269">Confirm</span></span>
      >
      > <span data-ttu-id="89c36-270">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="89c36-270">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="89c36-271">将删除数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="89c36-271">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="89c36-272">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="89c36-272">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="89c36-273">若想更改但不进行确认，请在步骤 2 中改用此 cmdlet：Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="89c36-273">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


<!-- salt notes
need two salting procedures, one for onestep from the externally facing and another for two step, on an internal machine then the upload from the external machine

- create A  folder put the edmupload agent and, csv and salt file there, run all processes there
- 
- stuff you need to have first: DataStoreName, /DataFile name (csv file)  /Hashlocation

- salt can be randomly generated by Microsoft or can be provided by the customer. If provided by the customer it must follow  format of 64 character, and can contain only letters or 0-9 characters.  Use a website to generate a valid salt value.
 
- can run EDMuploadagent.exe from PS or Windows cmd window . tested on Windows Server 2016 or Windows 10 and dot net version 4.6.2

when defiuning the schema file the searchable fields must be either an out of box SIT or custom SIT, only 5 fields )column headings) can be searchable

1. From outbound access device from the cmd prompt run EdmUploadAgent.exe /Authorize -  
2. data store schema must have already been uploaded
3.  create hash first then do upload
4. EdmUploadAgent.exe /CreateHash /DataFile (where the data file is ) E:\emd\test\data\schema32_1000000,csv /HashLocation  (where to store it) E:\edm\tat\hash this makes the salt file and the hash file as output
5. next is upload EdmUploadAgent.exe /UploadHash /DataStoreName (found in the Schema file DataSore name="FOO" /HashFile (path to hash file locaztion and file name /HashLocation path to hash)  for example
1.EdmUploadAgent/exe /UploadHash /DataStoreName schema321 /HashFile E:\edm\test\hash\schema32_10000000.EdmHash /HashLocation E:\edm\test\hash  -this one  uses MSFT generated salt, so no need to provide

Salt is an optional parameter so if yo uwant to use a custom salt add /salt and the salt value if salt file not copied to the outbound machine 

OR copy both files hash and salt to the same directory and the commmand will get both


OR do it in single step hash, salt ulopad

!! once they download the updated upload agent they will always have SALT, there is no going back.


all in one step: EdmUploadAgent.exe /UploadData /DataStoreName schema321 /DataFile E:\edm\test\data\schema32_10000.csv /HashLocation E:\edm\test\hash

tshooting/check status cmd



Once it gets to completed the admin can start using it in the custom SIT

they have to get their own custom SALT

just copy SALT over in a secure fashion










1.
6.
7.
1.  


 -->

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="89c36-274">第 2 部分：为敏感数据创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="89c36-274">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="89c36-275">在此阶段，你将设置自定义安全组和用户帐户，并设置 EDM 上传代理工具。</span><span class="sxs-lookup"><span data-stu-id="89c36-275">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="89c36-276">然后，使用此工具为敏感数据创建带随机混淆值的哈希并上传。</span><span class="sxs-lookup"><span data-stu-id="89c36-276">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="89c36-277">可使用一台计算机完成哈希创建和上传，也可以将哈希创建步骤与上传步骤分离，以实现更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="89c36-277">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="89c36-278">如果想要在一台计算机上创建哈希并上传，则需要在可直接连接到 Microsoft 365 租户的计算机上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="89c36-278">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="89c36-279">这要求计算机上需要具备明文敏感数据文件以便创建哈希。</span><span class="sxs-lookup"><span data-stu-id="89c36-279">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="89c36-280">如果不希望公开明文敏感数据文件，可在计算机的安全位置上为其创建哈希，然后将哈希文件和随机混淆值文件复制到可直接连接到 Microsoft 365 租户的计算机以进行上传。</span><span class="sxs-lookup"><span data-stu-id="89c36-280">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="89c36-281">在这种情况下，需要在两台计算机上都有 EDMUploadAgent。</span><span class="sxs-lookup"><span data-stu-id="89c36-281">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="89c36-282">先决条件</span><span class="sxs-lookup"><span data-stu-id="89c36-282">Prerequisites</span></span>

- <span data-ttu-id="89c36-283">向 **EDM\_DataUploaders** 安全组中添加一个 Microsoft 365 工作或学校帐户</span><span class="sxs-lookup"><span data-stu-id="89c36-283">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="89c36-284">准备一台使用.NET 版本 4.6.2 的 Windows 10 或 Windows Server 2016 计算机，用于运行 EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="89c36-284">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="89c36-285">用于上传的计算机上应含有以下内容的目录：</span><span class="sxs-lookup"><span data-stu-id="89c36-285">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="89c36-286">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="89c36-286">EDMUploadAgent</span></span>
    - <span data-ttu-id="89c36-287">我们示例中使用的 csv 格式的敏感项目文件 **PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="89c36-287">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="89c36-288">以及输出的哈希和随机混淆值文件</span><span class="sxs-lookup"><span data-stu-id="89c36-288">and the output hash and salt files</span></span>
    - <span data-ttu-id="89c36-289">来自 **edm .xml** 文件的数据存储名称，在本示例中为 `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="89c36-289">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="89c36-290">设置安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="89c36-290">Set up the security group and user account</span></span>

1. <span data-ttu-id="89c36-291">作为全局管理员，使用相应的[订阅链接](#portal-links-for-your-subscription)转到管理中心并 [创建安全组](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) ，名为  **EDM\_DataUploaders**。</span><span class="sxs-lookup"><span data-stu-id="89c36-291">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="89c36-292">将一个或多个用户添加到 **EDM\_DataUploaders** 安全组。</span><span class="sxs-lookup"><span data-stu-id="89c36-292">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="89c36-293">（这些用户将管理敏感信息的数据库。）</span><span class="sxs-lookup"><span data-stu-id="89c36-293">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="89c36-294">从一台计算机上创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="89c36-294">Hash and upload from one computer</span></span>

<span data-ttu-id="89c36-295">此计算机必须对你的 Microsoft 365 租户拥有直接访问权限。</span><span class="sxs-lookup"><span data-stu-id="89c36-295">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="89c36-296">在开始此过程之前，请确保你是  **EDM\_DataUploaders** 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="89c36-296">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="89c36-297">按订阅类型链接到 EDM 上传代理</span><span class="sxs-lookup"><span data-stu-id="89c36-297">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="89c36-298">商用 + GCC</span><span class="sxs-lookup"><span data-stu-id="89c36-298">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="89c36-299">GCC-High</span><span class="sxs-lookup"><span data-stu-id="89c36-299">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="89c36-300">DoD</span><span class="sxs-lookup"><span data-stu-id="89c36-300">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="89c36-301">创建 EDMUploadAgent 要使用的工作目录。</span><span class="sxs-lookup"><span data-stu-id="89c36-301">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="89c36-302">例如，**C:\EDM\Data**。</span><span class="sxs-lookup"><span data-stu-id="89c36-302">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="89c36-303">将 **PatientRecords .csv** 文件放入该目录中。</span><span class="sxs-lookup"><span data-stu-id="89c36-303">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="89c36-304">下载并将适合你的订阅的 [EDM 上传代理](#links-to-edm-upload-agent-by-subscription-type)安装到步骤 1 创建的目录中。</span><span class="sxs-lookup"><span data-stu-id="89c36-304">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="89c36-305">上述链接中的 EDMUploadAgent 已更新，可自动将随机混淆值添加到哈希数据。</span><span class="sxs-lookup"><span data-stu-id="89c36-305">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="89c36-306">或者，你可以提供自己的随机混淆值。</span><span class="sxs-lookup"><span data-stu-id="89c36-306">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="89c36-307">使用此版本后，你将不能使用 EDMUploadAgent 的先前版本。</span><span class="sxs-lookup"><span data-stu-id="89c36-307">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="89c36-308">每天只能使用 EDMUploadAgent 上传数据到任何给定的数据存储空间两次。</span><span class="sxs-lookup"><span data-stu-id="89c36-308">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="89c36-309">要获取受支持命令参数的列表，请运行无代理参数。</span><span class="sxs-lookup"><span data-stu-id="89c36-309">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="89c36-310">例如“EdmUploadAgent.exe”。</span><span class="sxs-lookup"><span data-stu-id="89c36-310">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="89c36-311">授权 “EDM 上传代理”，打开命令提示符窗口（以管理员身份），切换到 **C:\EDM\Data** 目录，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89c36-311">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="89c36-312">使用添加到 EDM_DataUploaders 安全组的 Microsoft 365 工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="89c36-312">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="89c36-313">将从用户帐户提取你的租户信息以建立连接。</span><span class="sxs-lookup"><span data-stu-id="89c36-313">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="89c36-314">若要为敏感数据创建哈希并上传，请在命令提示符窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89c36-314">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="89c36-315">示例：**EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="89c36-315">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="89c36-316">这会自动将随机生成的随机混淆值添加到哈希，以实现更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="89c36-316">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="89c36-317">或者，如果你想要使用自己的随机混淆值，请将 **/Salt <saltvalue>** 值添加到命令中。</span><span class="sxs-lookup"><span data-stu-id="89c36-317">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="89c36-318">该值的长度必须为 64 个字符，并且只能包含 a-z 的字符和 0-9 的数字。</span><span class="sxs-lookup"><span data-stu-id="89c36-318">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="89c36-319">运行以下命令，检查“上传”状态：</span><span class="sxs-lookup"><span data-stu-id="89c36-319">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="89c36-320">示例：**EdmUploadAgent/GetSession/DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="89c36-320">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="89c36-321">在 **ProcessingInProgress** 中查找状态。</span><span class="sxs-lookup"><span data-stu-id="89c36-321">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="89c36-322">每隔几分钟再次检查，直到状态更改为“**已完成**”。</span><span class="sxs-lookup"><span data-stu-id="89c36-322">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="89c36-323">在状态为已完成后，即可使用 EDM 数据。</span><span class="sxs-lookup"><span data-stu-id="89c36-323">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="89c36-324">将哈希与上传分开操作</span><span class="sxs-lookup"><span data-stu-id="89c36-324">Separate Hash and upload</span></span>

<span data-ttu-id="89c36-325">在处于安全环境中的计算机上执行哈希。</span><span class="sxs-lookup"><span data-stu-id="89c36-325">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="89c36-326">在命令提示符窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89c36-326">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="89c36-327">例如：</span><span class="sxs-lookup"><span data-stu-id="89c36-327">For example:</span></span>

> <span data-ttu-id="89c36-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="89c36-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="89c36-329">如果没有指定“**/Salt <saltvalue>**”选项，这将会输出具有以下扩展名的哈希文件和随机混淆值文件：</span><span class="sxs-lookup"><span data-stu-id="89c36-329">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="89c36-330">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="89c36-330">.EdmHash</span></span>
- <span data-ttu-id="89c36-331">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="89c36-331">.EdmSalt</span></span>

2. <span data-ttu-id="89c36-332">通过安全方式将这些文件复制到计算机，该计算机用于向租户上传敏感项目 csv 文件 (PatientRecords)。</span><span class="sxs-lookup"><span data-stu-id="89c36-332">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="89c36-333">若要上传哈希数据，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89c36-333">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="89c36-334">例如：</span><span class="sxs-lookup"><span data-stu-id="89c36-334">For example:</span></span>

> <span data-ttu-id="89c36-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="89c36-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="89c36-336">若要验证是否已上传敏感数据，请在“命令提示符”窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89c36-336">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="89c36-337">你将看到数据存储区列表以及上次更新时间。</span><span class="sxs-lookup"><span data-stu-id="89c36-337">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="89c36-338">如果要查看所有数据上载到特定存储的信息，请在 Windows 命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89c36-338">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="89c36-339">继续设置 [刷新敏感信息数据库](#refreshing-your-sensitive-information-database)的流程和计划。</span><span class="sxs-lookup"><span data-stu-id="89c36-339">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="89c36-340">此时，你已准备好将基于 EDM 的分类与 Microsoft 云服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="89c36-340">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="89c36-341">例如，你可以 [使用基于 EDM 的分类设置 DLP 策略](#to-create-a-dlp-policy-with-edm)。</span><span class="sxs-lookup"><span data-stu-id="89c36-341">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="89c36-342">刷新敏感信息数据库</span><span class="sxs-lookup"><span data-stu-id="89c36-342">Refreshing your sensitive information database</span></span>

<span data-ttu-id="89c36-343">可以每天刷新敏感信息数据库，EDM 上传工具会重新为敏感数据创建索引，然后重新上传索引数据。</span><span class="sxs-lookup"><span data-stu-id="89c36-343">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="89c36-344">确定刷新敏感信息数据库的流程和频率（每天或每周）。</span><span class="sxs-lookup"><span data-stu-id="89c36-344">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="89c36-345">将敏感数据重新导出到应用（如 Microsoft Excel），并以 .csv 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="89c36-345">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="89c36-346">在按照 [为敏感数据创建哈希并上传](#part-2-hash-and-upload-the-sensitive-data)中所述的步骤执行操作时，让所使用的文件名和位置保持不变。</span><span class="sxs-lookup"><span data-stu-id="89c36-346">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="89c36-347">如果 .csv 文件的结构（字段名称）未发生更改，则刷新数据时无需对数据库架构文件进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="89c36-347">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="89c36-348">但是，如果必须进行更改，请确保相应地编辑数据库架和规则包。</span><span class="sxs-lookup"><span data-stu-id="89c36-348">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="89c36-349">使用 [任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) 自动执行 [为敏感数据创建哈希并上传流程中的步骤 2 和 3](#part-2-hash-and-upload-the-sensitive-data) 。</span><span class="sxs-lookup"><span data-stu-id="89c36-349">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="89c36-350">你可以使用多种方法来计划任务：</span><span class="sxs-lookup"><span data-stu-id="89c36-350">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="89c36-351">方法</span><span class="sxs-lookup"><span data-stu-id="89c36-351">Method</span></span>             | <span data-ttu-id="89c36-352">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="89c36-352">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="89c36-353">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89c36-353">Windows PowerShell</span></span>     | <span data-ttu-id="89c36-354">请参阅本文中的 [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) 文档和 [示例 PowerShell 脚本](#example-powershell-script-for-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="89c36-354">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="89c36-355">任务计划程序 API</span><span class="sxs-lookup"><span data-stu-id="89c36-355">Task Scheduler API</span></span>     | <span data-ttu-id="89c36-356">请参阅 [任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)文档 </span><span class="sxs-lookup"><span data-stu-id="89c36-356">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="89c36-357">Windows 用户界面</span><span class="sxs-lookup"><span data-stu-id="89c36-357">Windows user interface</span></span> | <span data-ttu-id="89c36-358">在 Windows 中单击“开始”，然后键入 Task Scheduler。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-358">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="89c36-359">然后，在结果列表中，右键单击“任务计划程序”，然后选择“以管理员身份运行”。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-359">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="89c36-360">任务计划程序的示例 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="89c36-360">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="89c36-361">此部分包含一个示例 PowerShell 脚本，你可以使用该脚本来计划为数据创建哈希并上传哈希数据的任务：</span><span class="sxs-lookup"><span data-stu-id="89c36-361">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="89c36-362">在合并步骤中计划哈希和上传</span><span class="sxs-lookup"><span data-stu-id="89c36-362">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation
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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="89c36-363">将计划哈希和上传作为单独的步骤</span><span class="sxs-lookup"><span data-stu-id="89c36-363">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="89c36-364">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="89c36-364">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="89c36-365">这些位置支持 EDM 敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="89c36-365">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="89c36-366">针对 Exchange Online 的 DLP（电子邮件）</span><span class="sxs-lookup"><span data-stu-id="89c36-366">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="89c36-367">OneDrive for Business（文件）</span><span class="sxs-lookup"><span data-stu-id="89c36-367">OneDrive for Business (files)</span></span>
- <span data-ttu-id="89c36-368">Microsoft Teams（对话）</span><span class="sxs-lookup"><span data-stu-id="89c36-368">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="89c36-369">针对 SharePoint 的 DLP（文件）</span><span class="sxs-lookup"><span data-stu-id="89c36-369">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="89c36-370">Microsoft Cloud App Security DLP 策略</span><span class="sxs-lookup"><span data-stu-id="89c36-370">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="89c36-371">以下方案的 EDM 敏感信息类型目前正在开发中，尚不可用：</span><span class="sxs-lookup"><span data-stu-id="89c36-371">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="89c36-372">灵敏度标签和保留标签的自动分类</span><span class="sxs-lookup"><span data-stu-id="89c36-372">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="89c36-373">使用 EDM 创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="89c36-373">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="89c36-374">使用相应的[订阅链接](#portal-links-for-your-subscription)转到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="89c36-374">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="89c36-375">选择“数据丢失防护”\>“策略”。 \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-375">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="89c36-376">选择“创建策略”\>“自定义”\>“下一步”。 \*\*\*\*  \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-376">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="89c36-377">在“命名策略”选项卡上，指定名称和说明，然后选择“下一步”。 \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-377">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="89c36-378">在“选择位置”选项卡上，选择“允许选择特定位置”，然后选择“下一步”。 \*\*\*\*  \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-378">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="89c36-379">在“状态”列中，选择“Exchange 电子邮件、OneDrive 帐户、团队聊天和频道邮件”，然后选择“下一步”。 \*\*\*\*  \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-379">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="89c36-380">在“策略设置”选项卡上，选择“使用高级设置”，然后选择“下一步”。 \*\*\*\*  \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-380">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="89c36-381">选择“+ 新建规则”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-381">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="89c36-382">在“名称”部分中，指定规则的名称和说明。 \*\*\*\* </span><span class="sxs-lookup"><span data-stu-id="89c36-382">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="89c36-383">在“条件”部分的“+ 添加条件”列表中，选择“内容包含敏感类型”。 \*\*\*\*  \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-383">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![内容包含敏感信息类型](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="89c36-385">搜索你在设置规则包时创建的敏感信息类型，然后选择“+ 添加”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-385">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="89c36-386">然后选择“完成”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-386">Then choose **Done**.</span></span>

12. <span data-ttu-id="89c36-387">完成为规则选择相关选项，例如“用户通知”、“用户覆盖”、“事件报告”等，然后选择“保存”。 \*\*\*\* \*\*\*\* \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-387">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="89c36-388">在“策略设置”选项卡上，查看你的规则，然后选择“下一步”。 \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-388">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="89c36-389">指定是立即打开策略、测试它还是保持关闭。</span><span class="sxs-lookup"><span data-stu-id="89c36-389">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="89c36-390">然后选择“下一步” \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89c36-390">Then choose **Next**.</span></span>

15. <span data-ttu-id="89c36-391">在“查看你的设置”选项卡上，查看你的策略。 \*\*\*\* </span><span class="sxs-lookup"><span data-stu-id="89c36-391">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="89c36-392">执行任何必要的更改。</span><span class="sxs-lookup"><span data-stu-id="89c36-392">Make any needed changes.</span></span> <span data-ttu-id="89c36-393">准备好后，选择“创建”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="89c36-393">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="89c36-394">新 DLP 策略大约需要一个小时才能通过你的数据中心。</span><span class="sxs-lookup"><span data-stu-id="89c36-394">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="89c36-395">相关文章</span><span class="sxs-lookup"><span data-stu-id="89c36-395">Related articles</span></span>

- [<span data-ttu-id="89c36-396">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="89c36-396">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="89c36-397">自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="89c36-397">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="89c36-398">DLP 策略概述</span><span class="sxs-lookup"><span data-stu-id="89c36-398">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="89c36-399">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="89c36-399">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="89c36-400">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="89c36-400">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

