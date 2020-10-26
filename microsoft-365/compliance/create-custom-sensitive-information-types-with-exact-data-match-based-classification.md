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
ms.openlocfilehash: 229eb733af85ea5f450969c6d70709cfadcb8f06
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681770"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="f441d-103">使用基于精确数据匹配的分类创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="f441d-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="f441d-104">[自定义敏感信息类型](custom-sensitive-info-types.md)用于帮助标识敏感项目，以防止它们被意外或不当地共享。</span><span class="sxs-lookup"><span data-stu-id="f441d-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="f441d-105">可基于以下内容定义自定义敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="f441d-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="f441d-106">模式</span><span class="sxs-lookup"><span data-stu-id="f441d-106">patterns</span></span>
- <span data-ttu-id="f441d-107">如*员工*、*徽章*或\* ID 等关键字证据\*</span><span class="sxs-lookup"><span data-stu-id="f441d-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="f441d-108">字符近似特定模式的证据</span><span class="sxs-lookup"><span data-stu-id="f441d-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="f441d-109">可信度</span><span class="sxs-lookup"><span data-stu-id="f441d-109">confidence levels</span></span>

 <span data-ttu-id="f441d-110">此类自定义敏感信息类型可满足许多组织的业务需求。</span><span class="sxs-lookup"><span data-stu-id="f441d-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="f441d-111">但是，如果你需要使用精确数据值的自定义敏感信息类型（而非基于泛型模式的匹配项），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="f441d-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="f441d-112">通过基于精确数据匹配 (EDM) 的分类，你可以创建专门设计的自定义敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="f441d-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="f441d-113">动态并且可刷新的</span><span class="sxs-lookup"><span data-stu-id="f441d-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="f441d-114">更具可伸缩性</span><span class="sxs-lookup"><span data-stu-id="f441d-114">be more scalable</span></span>
- <span data-ttu-id="f441d-115">导致更少的误报</span><span class="sxs-lookup"><span data-stu-id="f441d-115">result in fewer false-positives</span></span>
- <span data-ttu-id="f441d-116">处理结构化敏感数据</span><span class="sxs-lookup"><span data-stu-id="f441d-116">work with structured sensitive data</span></span>
- <span data-ttu-id="f441d-117">更安全地处理敏感信息</span><span class="sxs-lookup"><span data-stu-id="f441d-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="f441d-118">与多种 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="f441d-118">be used with several Microsoft cloud services</span></span>

![基于 EDM 的分类](../media/EDMClassification.png)

<span data-ttu-id="f441d-120">基于 EDM 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。</span><span class="sxs-lookup"><span data-stu-id="f441d-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="f441d-121">数据库可以每天刷新一次，最多可包含 1 亿行数据。</span><span class="sxs-lookup"><span data-stu-id="f441d-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="f441d-122">因此，当员工、患者或客户往来并且记录发生更改时，你的自定义敏感信息类型仍将保持最新并且适用。</span><span class="sxs-lookup"><span data-stu-id="f441d-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="f441d-123">你还可以将基于 EDM 的分类与策略一起使用，例如[数据丢失防护策略](data-loss-prevention-policies.md) (DLP) 或[Microsoft Cloud App Security 文件策略](https://docs.microsoft.com/cloud-app-security/data-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="f441d-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="f441d-124">Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持（预览）：</span><span class="sxs-lookup"><span data-stu-id="f441d-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="f441d-125">简体中文</span><span class="sxs-lookup"><span data-stu-id="f441d-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="f441d-126">繁体中文</span><span class="sxs-lookup"><span data-stu-id="f441d-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="f441d-127">韩语</span><span class="sxs-lookup"><span data-stu-id="f441d-127">Korean</span></span>
> - <span data-ttu-id="f441d-128">日语</span><span class="sxs-lookup"><span data-stu-id="f441d-128">Japanese</span></span>

><span data-ttu-id="f441d-129">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="f441d-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="f441d-130">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="f441d-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="f441d-131">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="f441d-131">Required licenses and permissions</span></span>

<span data-ttu-id="f441d-132">你必须是全局管理员、合规性管理员或 Exchange Online 管理员才能执行本文中描述的任务。</span><span class="sxs-lookup"><span data-stu-id="f441d-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="f441d-133">若要了解有关 DLP 权限的详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="f441d-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="f441d-134">这些订阅中包含基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="f441d-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="f441d-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f441d-135">Office 365 E5</span></span>
- <span data-ttu-id="f441d-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f441d-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="f441d-137">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="f441d-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="f441d-138">Microsoft E5/A5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="f441d-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="f441d-139">订阅门户链接</span><span class="sxs-lookup"><span data-stu-id="f441d-139">Portal links for your subscription</span></span>


|<span data-ttu-id="f441d-140">门户</span><span class="sxs-lookup"><span data-stu-id="f441d-140">Portal</span></span>  |<span data-ttu-id="f441d-141">全球/GCC</span><span class="sxs-lookup"><span data-stu-id="f441d-141">World Wide/GCC</span></span>  |<span data-ttu-id="f441d-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="f441d-142">GCC-High</span></span>  |<span data-ttu-id="f441d-143">DOD</span><span class="sxs-lookup"><span data-stu-id="f441d-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="f441d-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="f441d-144">Office SCC</span></span>     |  <span data-ttu-id="f441d-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="f441d-145">protection.office.com</span></span>       |<span data-ttu-id="f441d-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="f441d-146">scc.office365.us</span></span>         |<span data-ttu-id="f441d-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="f441d-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="f441d-148">Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="f441d-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="f441d-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f441d-149">security.microsoft.com</span></span>         |<span data-ttu-id="f441d-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="f441d-150">security.microsoft.us</span></span>         |<span data-ttu-id="f441d-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="f441d-151">security.apps.mil</span></span>|
|<span data-ttu-id="f441d-152">Microsoft 365 合规中心</span><span class="sxs-lookup"><span data-stu-id="f441d-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="f441d-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f441d-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="f441d-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="f441d-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="f441d-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="f441d-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="f441d-156">工作流程概览</span><span class="sxs-lookup"><span data-stu-id="f441d-156">The work flow at a glance</span></span>

|<span data-ttu-id="f441d-157">阶段</span><span class="sxs-lookup"><span data-stu-id="f441d-157">Phase</span></span>  |<span data-ttu-id="f441d-158">所需项</span><span class="sxs-lookup"><span data-stu-id="f441d-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="f441d-159">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="f441d-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="f441d-160">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="f441d-160">(As needed)</span></span><br/><span data-ttu-id="f441d-161">- [编辑数据库架构](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="f441d-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="f441d-162">- [删除架构](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="f441d-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="f441d-163">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="f441d-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="f441d-164">- XML 格式的数据库架构（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="f441d-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="f441d-165">- XML 格式的规则包（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="f441d-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="f441d-166">- 安全与合规中心的管理员权限（使用 PowerShell）</span><span class="sxs-lookup"><span data-stu-id="f441d-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="f441d-167">第 2 部分：为敏感数据创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="f441d-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="f441d-168">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="f441d-168">(As needed)</span></span><br/>[<span data-ttu-id="f441d-169">刷新数据</span><span class="sxs-lookup"><span data-stu-id="f441d-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="f441d-170">- 自定义安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="f441d-170">- Custom security group and user account</span></span><br/><span data-ttu-id="f441d-171">- 使用 EDM 上载代理对计算机进行本地管理员访问</span><span class="sxs-lookup"><span data-stu-id="f441d-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="f441d-172">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="f441d-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="f441d-173">- 刷新数据的流程和计划</span><span class="sxs-lookup"><span data-stu-id="f441d-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="f441d-174">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="f441d-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="f441d-175">- 具有 DLP 的 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="f441d-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="f441d-176">- 已启用基于 EDM 的分类功能</span><span class="sxs-lookup"><span data-stu-id="f441d-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="f441d-177">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="f441d-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="f441d-178">设置和配置基于 EDM 的分类包括：</span><span class="sxs-lookup"><span data-stu-id="f441d-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="f441d-179">保存 .csv 格式的敏感数据</span><span class="sxs-lookup"><span data-stu-id="f441d-179">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="f441d-180">定义你的敏感信息数据库架构</span><span class="sxs-lookup"><span data-stu-id="f441d-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="f441d-181">设置规则包</span><span class="sxs-lookup"><span data-stu-id="f441d-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="f441d-182">保存 .csv 格式的敏感数据</span><span class="sxs-lookup"><span data-stu-id="f441d-182">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="f441d-183">确定要使用的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="f441d-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="f441d-184">将数据导出到应用（如 Microsoft Excel），然后以 .csv 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="f441d-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="f441d-185">数据文件最多可包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="f441d-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="f441d-186">高达 1 亿行的敏感数据</span><span class="sxs-lookup"><span data-stu-id="f441d-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="f441d-187">每个数据源最多 32 列（字段）</span><span class="sxs-lookup"><span data-stu-id="f441d-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="f441d-188">最多 5 个列（字段）标记为可搜索</span><span class="sxs-lookup"><span data-stu-id="f441d-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="f441d-189">在 .csv 文件中构造敏感数据，使第一行包含用于基于 EDM 的分类的字段名称。</span><span class="sxs-lookup"><span data-stu-id="f441d-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="f441d-190">在 .csv 文件中，你可能拥有“ssn”、“生日”、“名字”、“姓氏”等字段名称。</span><span class="sxs-lookup"><span data-stu-id="f441d-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="f441d-191">列标题名称不能包含空格或下划线。</span><span class="sxs-lookup"><span data-stu-id="f441d-191">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="f441d-192">例如，本文中使用的示例 .csv 文件名为*PatientRecords.csv*，其中包含*PatientID*、*MRN*、*LastName*、*FirstName* 和 *SSN* 等列。</span><span class="sxs-lookup"><span data-stu-id="f441d-192">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="f441d-193">定义敏感信息数据库的架构</span><span class="sxs-lookup"><span data-stu-id="f441d-193">Define the schema for your database of sensitive information</span></span>

3. <span data-ttu-id="f441d-194">以 XML 格式定义敏感信息数据库的架构（类似于下面的示例）。</span><span class="sxs-lookup"><span data-stu-id="f441d-194">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="f441d-195">命名此架构文件**edm.xml**并对其进行配置，确保对于数据库中的每一列，都有一行使用语法：</span><span class="sxs-lookup"><span data-stu-id="f441d-195">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="f441d-196">`\<Field name="" searchable=""/\>`（）。</span><span class="sxs-lookup"><span data-stu-id="f441d-196">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="f441d-197">将列名称用于*字段名称*值。</span><span class="sxs-lookup"><span data-stu-id="f441d-197">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="f441d-198">将 *searchable="true"* 用于可搜索的字段，最多 5 个字段。</span><span class="sxs-lookup"><span data-stu-id="f441d-198">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="f441d-199">必须至少有一个字段可搜索。</span><span class="sxs-lookup"><span data-stu-id="f441d-199">At least one field must be searchable.</span></span>

      <span data-ttu-id="f441d-200">例如，以下 XML 文件定义患者记录数据库的架构，其中五个字段指定为可搜索字段：*患者 ID*、*MRN*、*SSN*、*电话*和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="f441d-200">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="f441d-201">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="f441d-201">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="f441d-202">使用[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="f441d-202">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="f441d-203">要上传数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f441d-203">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="f441d-204">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f441d-204">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="f441d-205">确认</span><span class="sxs-lookup"><span data-stu-id="f441d-205">Confirm</span></span>
      >
      > <span data-ttu-id="f441d-206">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="f441d-206">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="f441d-207">将导入数据存储“patientrecords”的新 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="f441d-207">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="f441d-208">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="f441d-208">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="f441d-209">若想更改但不进行确认，请在步骤 5 中改用此 cmdlet：New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="f441d-209">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="f441d-210">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="f441d-210">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="f441d-211">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="f441d-211">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="f441d-212">设置规则包</span><span class="sxs-lookup"><span data-stu-id="f441d-212">Set up a rule package</span></span>

1. <span data-ttu-id="f441d-213">按 XML 格式创建一个规则包（采用 Unicode 编码），如下例类似。</span><span class="sxs-lookup"><span data-stu-id="f441d-213">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="f441d-214">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="f441d-214">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="f441d-215">设置规则包时，请确保正确引用 .csv 文件和 **edm.xml** 文件。</span><span class="sxs-lookup"><span data-stu-id="f441d-215">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="f441d-216">可复制、修改和使用我们的示例。</span><span class="sxs-lookup"><span data-stu-id="f441d-216">You can copy, modify, and use our example.</span></span> <span data-ttu-id="f441d-217">在此示例 xml 中，需要对以下字段进行自定义，以创建 EDM 敏感类型：</span><span class="sxs-lookup"><span data-stu-id="f441d-217">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="f441d-218">**RulePack id & ExactMatch id**：使用 [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) 生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="f441d-218">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="f441d-219">**数据存储**：此字段指定要使用的 EDM 查找数据存储。</span><span class="sxs-lookup"><span data-stu-id="f441d-219">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="f441d-220">提供已配置的 EDM 架构的数据源名称。</span><span class="sxs-lookup"><span data-stu-id="f441d-220">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="f441d-221">**idMatch**：此字段指向 EDM 的主要元素。</span><span class="sxs-lookup"><span data-stu-id="f441d-221">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="f441d-222">匹配：指定要在精确查找中使用的字段。</span><span class="sxs-lookup"><span data-stu-id="f441d-222">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="f441d-223">在数据存储的 EDM 架构中提供可搜索的字段名称。</span><span class="sxs-lookup"><span data-stu-id="f441d-223">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="f441d-224">分类：此字段指定触发 EDM 查找的敏感类型匹配。</span><span class="sxs-lookup"><span data-stu-id="f441d-224">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="f441d-225">可提供现有内置或自定义分类的名称或 GUID。</span><span class="sxs-lookup"><span data-stu-id="f441d-225">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="f441d-226">**匹配：** 此字段指向邻近 idMatch 找到的其他证据。</span><span class="sxs-lookup"><span data-stu-id="f441d-226">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="f441d-227">匹配：在数据存储的 EDM 架构中提供任何字段名称。</span><span class="sxs-lookup"><span data-stu-id="f441d-227">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="f441d-228">**资源：** 此部分在多个区域设置中指定敏感类型的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="f441d-228">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="f441d-229">idRef：提供 ExactMatch ID 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f441d-229">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="f441d-230">名称和说明：按需自定义。</span><span class="sxs-lookup"><span data-stu-id="f441d-230">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="f441d-231">通过逐一运行下列 PowerShell cmdlet 来上传规则包：</span><span class="sxs-lookup"><span data-stu-id="f441d-231">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="f441d-232">此时，你已设置基于 EDM 的分类。</span><span class="sxs-lookup"><span data-stu-id="f441d-232">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="f441d-233">下一步是为敏感数据创建哈希，然后上传哈希以便编制索引。</span><span class="sxs-lookup"><span data-stu-id="f441d-233">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="f441d-234">回想一下，在前面的过程中我们的 PatientRecords 架构将 5 个文件定义为可搜索的项：*PatientID*、*MRN*、*SSN*、*Phone* 和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="f441d-234">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="f441d-235">我们的示例规则包中有这些字段并引用数据库架构文件 (**edm.xml**)，其中每个可搜索的字段具有一个 *ExactMatch* 项目。</span><span class="sxs-lookup"><span data-stu-id="f441d-235">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="f441d-236">请考虑以下 ExactMatch 项目：</span><span class="sxs-lookup"><span data-stu-id="f441d-236">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="f441d-237">在此示例中，请注意：</span><span class="sxs-lookup"><span data-stu-id="f441d-237">In this example, note that:</span></span>

- <span data-ttu-id="f441d-238">dataStore 名称引用了我们之前创建的 .csv 文件：**dataStore = "PatientRecords"**。</span><span class="sxs-lookup"><span data-stu-id="f441d-238">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="f441d-239">idMatch 值引用了数据库架构文件中列出的可搜索字段： **idMatch matches = "SSN"**。</span><span class="sxs-lookup"><span data-stu-id="f441d-239">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="f441d-240">分类值引用了现有或自定义敏感信息类型：**classification = "U.S. Social Security Number (SSN)"**。</span><span class="sxs-lookup"><span data-stu-id="f441d-240">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="f441d-241">（在此情况下，我们使用美国社会保障号的现有敏感信息类型。）</span><span class="sxs-lookup"><span data-stu-id="f441d-241">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="f441d-242">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="f441d-242">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="f441d-243">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="f441d-243">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="f441d-244">编辑基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="f441d-244">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="f441d-245">如果想要更改**edm.xml** 文件，例如更改要对基于 EDM 的分类使用的字段，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f441d-245">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="f441d-246">编辑 **edm.mxl** 文件（即本文的[定义架构](#define-the-schema-for-your-database-of-sensitive-information)部分中讨论的文件）。</span><span class="sxs-lookup"><span data-stu-id="f441d-246">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="f441d-247">使用[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="f441d-247">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="f441d-248">要更新数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f441d-248">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="f441d-249">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f441d-249">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="f441d-250">确认</span><span class="sxs-lookup"><span data-stu-id="f441d-250">Confirm</span></span>
      >
      > <span data-ttu-id="f441d-251">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="f441d-251">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="f441d-252">将更新数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="f441d-252">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="f441d-253">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="f441d-253">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="f441d-254">若想更改但不进行确认，请在步骤 3 中改用此 cmdlet：Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="f441d-254">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="f441d-255">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="f441d-255">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="f441d-256">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="f441d-256">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="f441d-257">删除基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="f441d-257">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="f441d-258">（根据需要）若想删除正在对基于 EDM 的分类使用的架构，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f441d-258">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="f441d-259">使用[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="f441d-259">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="f441d-260">运行下列 PowerShell cmdlet，用“patient records”的数据存储名称替换要删除的名称：</span><span class="sxs-lookup"><span data-stu-id="f441d-260">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="f441d-261">系统将提示你进行确认：</span><span class="sxs-lookup"><span data-stu-id="f441d-261">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="f441d-262">确认</span><span class="sxs-lookup"><span data-stu-id="f441d-262">Confirm</span></span>
      >
      > <span data-ttu-id="f441d-263">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="f441d-263">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="f441d-264">将删除数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="f441d-264">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="f441d-265">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="f441d-265">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="f441d-266">若想更改但不进行确认，请在步骤 2 中改用此 cmdlet：Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="f441d-266">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


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

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="f441d-267">第 2 部分：为敏感数据创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="f441d-267">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="f441d-268">在此阶段，你将设置自定义安全组和用户帐户，并设置 EDM 上传代理工具。</span><span class="sxs-lookup"><span data-stu-id="f441d-268">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="f441d-269">然后，使用此工具为敏感数据创建带随机混淆值的哈希并上传。</span><span class="sxs-lookup"><span data-stu-id="f441d-269">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="f441d-270">可使用一台计算机完成哈希创建和上传，也可以将哈希创建步骤与上传步骤分离，以实现更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="f441d-270">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="f441d-271">如果想要在一台计算机上创建哈希并上传，则需要在可直接连接到 Microsoft 365 租户的计算机上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f441d-271">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="f441d-272">这要求计算机上需要具备明文敏感数据文件以便创建哈希。</span><span class="sxs-lookup"><span data-stu-id="f441d-272">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="f441d-273">如果不希望公开明文敏感数据文件，可在计算机的安全位置上为其创建哈希，然后将哈希文件和随机混淆值文件复制到可直接连接到 Microsoft 365 租户的计算机以进行上传。</span><span class="sxs-lookup"><span data-stu-id="f441d-273">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="f441d-274">在这种情况下，需要在两台计算机上都有 EDMUploadAgent。</span><span class="sxs-lookup"><span data-stu-id="f441d-274">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="f441d-275">先决条件</span><span class="sxs-lookup"><span data-stu-id="f441d-275">Prerequisites</span></span>

- <span data-ttu-id="f441d-276">向 **EDM\_DataUploaders** 安全组中添加一个 Microsoft 365 工作或学校帐户</span><span class="sxs-lookup"><span data-stu-id="f441d-276">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="f441d-277">准备一台使用.NET 版本 4.6.2 的 Windows 10 或 Windows Server 2016 计算机，用于运行 EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="f441d-277">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="f441d-278">用于上传的计算机上应含有以下内容的目录：</span><span class="sxs-lookup"><span data-stu-id="f441d-278">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="f441d-279">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="f441d-279">EDMUploadAgent</span></span>
    - <span data-ttu-id="f441d-280">我们示例中使用的 csv 格式的敏感项目文件 **PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="f441d-280">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="f441d-281">以及输出的哈希和随机混淆值文件</span><span class="sxs-lookup"><span data-stu-id="f441d-281">and the output hash and salt files</span></span>
    - <span data-ttu-id="f441d-282">来自 **edm .xml** 文件的数据存储名称，在本示例中为 `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="f441d-282">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="f441d-283">设置安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="f441d-283">Set up the security group and user account</span></span>

1. <span data-ttu-id="f441d-284">作为全局管理员，使用相应的[订阅链接](#portal-links-for-your-subscription)转到管理中心并[创建安全组](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide)，名为 **EDM\_DataUploaders**。</span><span class="sxs-lookup"><span data-stu-id="f441d-284">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="f441d-285">将一个或多个用户添加到 **EDM\_DataUploaders** 安全组。</span><span class="sxs-lookup"><span data-stu-id="f441d-285">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="f441d-286">（这些用户将管理敏感信息的数据库。）</span><span class="sxs-lookup"><span data-stu-id="f441d-286">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="f441d-287">从一台计算机上创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="f441d-287">Hash and upload from one computer</span></span>

<span data-ttu-id="f441d-288">此计算机必须对你的 Microsoft 365 租户拥有直接访问权限。</span><span class="sxs-lookup"><span data-stu-id="f441d-288">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="f441d-289">在开始此过程之前，请确保你是 **EDM\_DataUploaders** 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="f441d-289">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="f441d-290">按订阅类型链接到 EDM 上传代理</span><span class="sxs-lookup"><span data-stu-id="f441d-290">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="f441d-291">商用 + GCC</span><span class="sxs-lookup"><span data-stu-id="f441d-291">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="f441d-292">GCC-High</span><span class="sxs-lookup"><span data-stu-id="f441d-292">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="f441d-293">DoD</span><span class="sxs-lookup"><span data-stu-id="f441d-293">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="f441d-294">创建 EDMUploadAgent 要使用的工作目录。</span><span class="sxs-lookup"><span data-stu-id="f441d-294">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="f441d-295">例如，**C:\EDM\Data**。</span><span class="sxs-lookup"><span data-stu-id="f441d-295">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="f441d-296">将 **PatientRecords .csv** 文件放入该目录中。</span><span class="sxs-lookup"><span data-stu-id="f441d-296">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="f441d-297">下载并将适合你的订阅的 [EDM 上传代理](#links-to-edm-upload-agent-by-subscription-type)安装到步骤 1 创建的目录中。</span><span class="sxs-lookup"><span data-stu-id="f441d-297">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="f441d-298">上述链接中的 EDMUploadAgent 已更新，可自动将随机混淆值添加到哈希数据。</span><span class="sxs-lookup"><span data-stu-id="f441d-298">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="f441d-299">或者，你可以提供自己的随机混淆值。</span><span class="sxs-lookup"><span data-stu-id="f441d-299">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="f441d-300">使用此版本后，你将不能使用 EDMUploadAgent 的先前版本。</span><span class="sxs-lookup"><span data-stu-id="f441d-300">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="f441d-301">每天只能使用 EDMUploadAgent 上传数据到任何给定的数据存储空间两次。</span><span class="sxs-lookup"><span data-stu-id="f441d-301">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="f441d-302">要获取受支持命令参数的列表，请运行无代理参数。</span><span class="sxs-lookup"><span data-stu-id="f441d-302">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="f441d-303">例如“EdmUploadAgent.exe”。</span><span class="sxs-lookup"><span data-stu-id="f441d-303">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="f441d-304">授权 “EDM 上传代理”，打开命令提示符窗口（以管理员身份），切换到 **C:\EDM\Data** 目录，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f441d-304">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="f441d-305">使用添加到 EDM_DataUploaders 安全组的 Microsoft 365 工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f441d-305">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="f441d-306">将从用户帐户提取你的租户信息以建立连接。</span><span class="sxs-lookup"><span data-stu-id="f441d-306">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="f441d-307">若要为敏感数据创建哈希并上传，请在命令提示符窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f441d-307">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="f441d-308">示例：**EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="f441d-308">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="f441d-309">这会自动将随机生成的随机混淆值添加到哈希，以实现更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="f441d-309">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="f441d-310">或者，如果你想要使用自己的随机混淆值，请将 **/Salt <saltvalue>** 值添加到命令中。</span><span class="sxs-lookup"><span data-stu-id="f441d-310">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="f441d-311">该值的长度必须为 64 个字符，并且只能包含 a-z 的字符和 0-9 的数字。</span><span class="sxs-lookup"><span data-stu-id="f441d-311">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="f441d-312">运行以下命令，检查“上传”状态：</span><span class="sxs-lookup"><span data-stu-id="f441d-312">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="f441d-313">示例：**EdmUploadAgent/GetSession/DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="f441d-313">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="f441d-314">在 **ProcessingInProgress** 中查找状态。</span><span class="sxs-lookup"><span data-stu-id="f441d-314">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="f441d-315">每隔几分钟再次检查，直到状态更改为“**已完成**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-315">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="f441d-316">在状态为已完成后，即可使用 EDM 数据。</span><span class="sxs-lookup"><span data-stu-id="f441d-316">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="f441d-317">将哈希与上传分开操作</span><span class="sxs-lookup"><span data-stu-id="f441d-317">Separate Hash and upload</span></span>

<span data-ttu-id="f441d-318">在处于安全环境中的计算机上执行哈希。</span><span class="sxs-lookup"><span data-stu-id="f441d-318">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="f441d-319">在命令提示符窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f441d-319">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="f441d-320">例如：</span><span class="sxs-lookup"><span data-stu-id="f441d-320">For example:</span></span>

> <span data-ttu-id="f441d-321">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="f441d-321">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="f441d-322">如果没有指定“**/Salt <saltvalue>**”选项，这将会输出具有以下扩展名的哈希文件和随机混淆值文件：</span><span class="sxs-lookup"><span data-stu-id="f441d-322">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="f441d-323">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="f441d-323">.EdmHash</span></span>
- <span data-ttu-id="f441d-324">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="f441d-324">.EdmSalt</span></span>

2. <span data-ttu-id="f441d-325">通过安全方式将这些文件复制到计算机，该计算机用于向租户上传敏感项目 csv 文件 (PatientRecords)。</span><span class="sxs-lookup"><span data-stu-id="f441d-325">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="f441d-326">若要上传哈希数据，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f441d-326">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="f441d-327">例如：</span><span class="sxs-lookup"><span data-stu-id="f441d-327">For example:</span></span>

> <span data-ttu-id="f441d-328">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="f441d-328">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="f441d-329">若要验证是否已上传敏感数据，请在“命令提示符”窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f441d-329">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="f441d-330">你将看到数据存储区列表以及上次更新时间。</span><span class="sxs-lookup"><span data-stu-id="f441d-330">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="f441d-331">如果要查看所有数据上载到特定存储的信息，请在 Windows 命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f441d-331">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="f441d-332">继续设置[刷新敏感信息数据库](#refreshing-your-sensitive-information-database)的流程和计划。</span><span class="sxs-lookup"><span data-stu-id="f441d-332">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="f441d-333">此时，你已准备好将基于 EDM 的分类与 Microsoft 云服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="f441d-333">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="f441d-334">例如，你可以[使用基于 EDM 的分类设置 DLP 策略](#to-create-a-dlp-policy-with-edm)。</span><span class="sxs-lookup"><span data-stu-id="f441d-334">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="f441d-335">刷新敏感信息数据库</span><span class="sxs-lookup"><span data-stu-id="f441d-335">Refreshing your sensitive information database</span></span>

<span data-ttu-id="f441d-336">可以每天刷新敏感信息数据库，EDM 上传工具会重新为敏感数据创建索引，然后重新上传索引数据。</span><span class="sxs-lookup"><span data-stu-id="f441d-336">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="f441d-337">确定刷新敏感信息数据库的流程和频率（每天或每周）。</span><span class="sxs-lookup"><span data-stu-id="f441d-337">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="f441d-338">将敏感数据重新导出到应用（如 Microsoft Excel），并以 .csv 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="f441d-338">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="f441d-339">在按照[为敏感数据创建哈希并上传](#part-2-hash-and-upload-the-sensitive-data)中所述的步骤执行操作时，让所使用的文件名和位置保持不变。</span><span class="sxs-lookup"><span data-stu-id="f441d-339">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="f441d-340">如果 .csv 文件的结构（字段名称）未发生更改，则刷新数据时无需对数据库架构文件进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="f441d-340">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="f441d-341">但是，如果必须进行更改，请确保相应地编辑数据库架和规则包。</span><span class="sxs-lookup"><span data-stu-id="f441d-341">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="f441d-342">使用[任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)自动执行[创建哈希并上载敏感数据](#part-2-hash-and-upload-the-sensitive-data)流程中的步骤 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="f441d-342">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="f441d-343">你可以使用多种方法来计划任务：</span><span class="sxs-lookup"><span data-stu-id="f441d-343">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="f441d-344">方法</span><span class="sxs-lookup"><span data-stu-id="f441d-344">Method</span></span>             | <span data-ttu-id="f441d-345">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="f441d-345">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="f441d-346">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f441d-346">Windows PowerShell</span></span>     | <span data-ttu-id="f441d-347">请参阅本文中的[计划任务](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps)文档和[示例 PowerShell 脚本](#example-powershell-script-for-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="f441d-347">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="f441d-348">任务计划程序 API</span><span class="sxs-lookup"><span data-stu-id="f441d-348">Task Scheduler API</span></span>     | <span data-ttu-id="f441d-349">请参阅[任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)文档</span><span class="sxs-lookup"><span data-stu-id="f441d-349">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="f441d-350">Windows 用户界面</span><span class="sxs-lookup"><span data-stu-id="f441d-350">Windows user interface</span></span> | <span data-ttu-id="f441d-351">在 Windows 中单击“**开始**”，然后键入 Task Scheduler。</span><span class="sxs-lookup"><span data-stu-id="f441d-351">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="f441d-352">然后，在结果列表中，右键单击“**任务计划程序**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-352">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="f441d-353">任务计划程序的示例 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="f441d-353">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="f441d-354">此部分包含一个示例 PowerShell 脚本，你可以使用该脚本来计划为数据创建哈希并上传哈希数据的任务：</span><span class="sxs-lookup"><span data-stu-id="f441d-354">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="f441d-355">在合并步骤中计划哈希和上传</span><span class="sxs-lookup"><span data-stu-id="f441d-355">To schedule hashing and upload in a combined step</span></span>

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="f441d-356">将计划哈希和上传作为单独的步骤</span><span class="sxs-lookup"><span data-stu-id="f441d-356">To schedule hashing and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="f441d-357">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="f441d-357">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="f441d-358">这些位置支持 EDM 敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="f441d-358">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="f441d-359">针对 Exchange Online 的 DLP（电子邮件）</span><span class="sxs-lookup"><span data-stu-id="f441d-359">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="f441d-360">OneDrive for Business（文件）</span><span class="sxs-lookup"><span data-stu-id="f441d-360">OneDrive for Business (files)</span></span>
- <span data-ttu-id="f441d-361">Microsoft Teams（对话）</span><span class="sxs-lookup"><span data-stu-id="f441d-361">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="f441d-362">针对 SharePoint 的 DLP（文件）</span><span class="sxs-lookup"><span data-stu-id="f441d-362">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="f441d-363">Microsoft Cloud App Security DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f441d-363">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="f441d-364">以下方案的 EDM 敏感信息类型目前正在开发中，尚不可用：</span><span class="sxs-lookup"><span data-stu-id="f441d-364">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="f441d-365">灵敏度标签和保留标签的自动分类</span><span class="sxs-lookup"><span data-stu-id="f441d-365">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="f441d-366">使用 EDM 创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f441d-366">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="f441d-367">使用相应的[订阅链接](#portal-links-for-your-subscription)转到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="f441d-367">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="f441d-368">选择**数据丢失防护** \> **策略**。</span><span class="sxs-lookup"><span data-stu-id="f441d-368">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="f441d-369">选择**创建策略** \> **自定义** \> "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f441d-369">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="f441d-370">在“**命名策略**”选项卡上，指定名称和说明，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-370">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="f441d-371">在“**选择位置**”选项卡上，选择“**允许选择特定位置**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-371">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="f441d-372">在“**状态**”列中，选择“**Exchange 电子邮件、OneDrive 帐户、团队聊天和频道邮件**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-372">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="f441d-373">在“**策略设置**”选项卡上，选择“**使用高级设置**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-373">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="f441d-374">选择“**+ 新建规则**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-374">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="f441d-375">在“**名称**”部分中，指定规则的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="f441d-375">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="f441d-376">在“**条件**”部分的“**+ 添加条件**”列表中，选择“**内容包含敏感类型**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-376">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![内容包含敏感信息类型](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="f441d-378">搜索你在设置规则包时创建的敏感信息类型，然后选择“**+ 添加**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-378">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="f441d-379">然后选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-379">Then choose **Done**.</span></span>

12. <span data-ttu-id="f441d-380">完成为规则选择相关选项，例如“**用户通知**”、“**用户覆盖**”、“**事件报告**”等，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-380">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="f441d-381">在“**策略设置**”选项卡上，查看你的规则，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-381">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="f441d-382">指定是立即打开策略、测试它还是保持关闭。</span><span class="sxs-lookup"><span data-stu-id="f441d-382">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="f441d-383">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-383">Then choose **Next**.</span></span>

15. <span data-ttu-id="f441d-384">在“**查看你的设置**”选项卡上，查看你的策略。</span><span class="sxs-lookup"><span data-stu-id="f441d-384">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="f441d-385">执行任何必要的更改。</span><span class="sxs-lookup"><span data-stu-id="f441d-385">Make any needed changes.</span></span> <span data-ttu-id="f441d-386">准备好后，选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="f441d-386">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="f441d-387">新 DLP 策略大约需要一个小时才能通过你的数据中心。</span><span class="sxs-lookup"><span data-stu-id="f441d-387">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f441d-388">相关文章</span><span class="sxs-lookup"><span data-stu-id="f441d-388">Related articles</span></span>

- [<span data-ttu-id="f441d-389">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="f441d-389">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="f441d-390">自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="f441d-390">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="f441d-391">DLP 策略概述</span><span class="sxs-lookup"><span data-stu-id="f441d-391">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="f441d-392">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f441d-392">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="f441d-393">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="f441d-393">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)

