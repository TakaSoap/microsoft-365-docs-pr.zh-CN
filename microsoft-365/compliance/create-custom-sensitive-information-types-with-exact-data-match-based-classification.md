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
ms.openlocfilehash: 699cea6aec6f11462aed0c08db98ca4620df519a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686556"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="98228-103">使用基于精确数据匹配的分类创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="98228-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="98228-104">[自定义敏感信息类型](custom-sensitive-info-types.md) 用于帮助防止无意或不适当的敏感信息共享。</span><span class="sxs-lookup"><span data-stu-id="98228-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="98228-105">作为管理员，你可以使用安全与合规中心或 PowerShell，根据模式、证据（ *员工*、 *徽章*、 *ID* 等关键字）、字符邻近度（特定模式下证据与字符的邻近度）以及可信度来定义自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="98228-105">As an administrator, you can use the Security & Compliance Center or PowerShell to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="98228-106">此类自定义敏感信息类型可满足许多组织的业务需求。</span><span class="sxs-lookup"><span data-stu-id="98228-106">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="98228-107">但是，如果你需要自定义敏感信息类型（它使用精确数据值而不是仅与泛型模式匹配），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="98228-107">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="98228-108">通过基于精确数据匹配 (EDM) 的分类，你可以创建专门设计的自定义敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="98228-108">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="98228-109">动态并且可刷新；</span><span class="sxs-lookup"><span data-stu-id="98228-109">be dynamic and refreshable;</span></span>
- <span data-ttu-id="98228-110">更具可伸缩性；</span><span class="sxs-lookup"><span data-stu-id="98228-110">be more scalable;</span></span>
- <span data-ttu-id="98228-111">导致更少的误报；</span><span class="sxs-lookup"><span data-stu-id="98228-111">result in fewer false-positives;</span></span>
- <span data-ttu-id="98228-112">处理结构化敏感数据；</span><span class="sxs-lookup"><span data-stu-id="98228-112">work with structured sensitive data;</span></span>
- <span data-ttu-id="98228-113">更安全地处理敏感信息以及</span><span class="sxs-lookup"><span data-stu-id="98228-113">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="98228-114">与多种 Microsoft 云服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="98228-114">be used with several Microsoft cloud services.</span></span>

![基于 EDM 的分类](../media/EDMClassification.png)

<span data-ttu-id="98228-116">基于 EDM 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。</span><span class="sxs-lookup"><span data-stu-id="98228-116">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="98228-117">数据库可以每天或每周刷新一次，最多可包含 1 亿行数据。</span><span class="sxs-lookup"><span data-stu-id="98228-117">The database can be refreshed daily or weekly, and it can contain up to 100 million rows of data.</span></span> <span data-ttu-id="98228-118">因此，当员工、患者或客户往来并且记录发生更改时，你的自定义敏感信息类型仍将保持最新并且适用。</span><span class="sxs-lookup"><span data-stu-id="98228-118">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="98228-119">你还可以将基于 EDM 的分类与策略一起使用，例如 [数据丢失防护策略](data-loss-prevention-policies.md) (DLP) 或 [Microsoft Cloud App Security 文件策略](https://docs.microsoft.com/cloud-app-security/data-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="98228-119">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="98228-120">Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持（预览）：</span><span class="sxs-lookup"><span data-stu-id="98228-120">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="98228-121">简体中文</span><span class="sxs-lookup"><span data-stu-id="98228-121">Chinese (simplified)</span></span>
> - <span data-ttu-id="98228-122">繁体中文</span><span class="sxs-lookup"><span data-stu-id="98228-122">Chinese (traditional)</span></span>
> - <span data-ttu-id="98228-123">韩语</span><span class="sxs-lookup"><span data-stu-id="98228-123">Korean</span></span>
> - <span data-ttu-id="98228-124">日语</span><span class="sxs-lookup"><span data-stu-id="98228-124">Japanese</span></span>
> 
><span data-ttu-id="98228-125">此功能预览仅在商业云中提供，并且仅在以下地区推出：</span><span class="sxs-lookup"><span data-stu-id="98228-125">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="98228-126">日本</span><span class="sxs-lookup"><span data-stu-id="98228-126">Japan</span></span>
> - <span data-ttu-id="98228-127">韩国</span><span class="sxs-lookup"><span data-stu-id="98228-127">Korea</span></span>
> - <span data-ttu-id="98228-128">中国大陆</span><span class="sxs-lookup"><span data-stu-id="98228-128">China</span></span>
> - <span data-ttu-id="98228-129">香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="98228-129">Hong Kong</span></span>
> - <span data-ttu-id="98228-130">澳门特别行政区</span><span class="sxs-lookup"><span data-stu-id="98228-130">Macau</span></span>
> - <span data-ttu-id="98228-131">中国台湾</span><span class="sxs-lookup"><span data-stu-id="98228-131">Taiwan</span></span>
>
><span data-ttu-id="98228-132">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="98228-132">This support is available for sensitive information types.</span></span> <span data-ttu-id="98228-133">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="98228-133">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="98228-134">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="98228-134">Required licenses and permissions</span></span>

<span data-ttu-id="98228-135">你必须是全局管理员、合规性管理员或 Exchange Online 管理员才能执行本文中描述的任务。</span><span class="sxs-lookup"><span data-stu-id="98228-135">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="98228-136">若要了解有关 DLP 权限的详细信息，请参阅 [权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="98228-136">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="98228-137">这些订阅中包含基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="98228-137">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="98228-138">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="98228-138">Office 365 E5</span></span>
- <span data-ttu-id="98228-139">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="98228-139">Microsoft 365 E5</span></span>
- <span data-ttu-id="98228-140">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="98228-140">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="98228-141">Microsoft E5/A5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="98228-141">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="98228-142">订阅门户链接</span><span class="sxs-lookup"><span data-stu-id="98228-142">Portal links for your subscription</span></span>


|<span data-ttu-id="98228-143">门户</span><span class="sxs-lookup"><span data-stu-id="98228-143">Portal</span></span>  |<span data-ttu-id="98228-144">全球/GCC</span><span class="sxs-lookup"><span data-stu-id="98228-144">World Wide/GCC</span></span>  |<span data-ttu-id="98228-145">GCC-High</span><span class="sxs-lookup"><span data-stu-id="98228-145">GCC-High</span></span>  |<span data-ttu-id="98228-146">DOD</span><span class="sxs-lookup"><span data-stu-id="98228-146">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="98228-147">Office SCC</span><span class="sxs-lookup"><span data-stu-id="98228-147">Office SCC</span></span>     |  <span data-ttu-id="98228-148">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="98228-148">protection.office.com</span></span>       |<span data-ttu-id="98228-149">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="98228-149">scc.office365.us</span></span>         |<span data-ttu-id="98228-150">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="98228-150">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="98228-151">Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="98228-151">Microsoft 365 Security center</span></span>     |<span data-ttu-id="98228-152">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="98228-152">security.microsoft.com</span></span>         |<span data-ttu-id="98228-153">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="98228-153">security.microsoft.us</span></span>         |<span data-ttu-id="98228-154">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="98228-154">security.apps.mil</span></span>|
|<span data-ttu-id="98228-155">Microsoft 365 合规中心</span><span class="sxs-lookup"><span data-stu-id="98228-155">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="98228-156">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="98228-156">compliance.microsoft.com</span></span>         |<span data-ttu-id="98228-157">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="98228-157">compliance.microsoft.us</span></span>         |<span data-ttu-id="98228-158">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="98228-158">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="98228-159">工作流程概览</span><span class="sxs-lookup"><span data-stu-id="98228-159">The work flow at a glance</span></span>

|<span data-ttu-id="98228-160">阶段</span><span class="sxs-lookup"><span data-stu-id="98228-160">Phase</span></span>  |<span data-ttu-id="98228-161">所需项</span><span class="sxs-lookup"><span data-stu-id="98228-161">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="98228-162">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="98228-162">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="98228-163">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="98228-163">(As needed)</span></span><br/><span data-ttu-id="98228-164">- [编辑数据库架构](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="98228-164">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="98228-165">- [删除架构](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="98228-165">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="98228-166">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="98228-166">- Read access to the sensitive data</span></span><br/><span data-ttu-id="98228-167">- XML 格式的数据库架构（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="98228-167">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="98228-168">- XML 格式的规则包（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="98228-168">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="98228-169">- 安全与合规中心的管理员权限（使用 PowerShell）</span><span class="sxs-lookup"><span data-stu-id="98228-169">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="98228-170">第 2 部分：为敏感数据创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="98228-170">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="98228-171">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="98228-171">(As needed)</span></span><br/>[<span data-ttu-id="98228-172">刷新数据</span><span class="sxs-lookup"><span data-stu-id="98228-172">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="98228-173">- 自定义安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="98228-173">- Custom security group and user account</span></span><br/><span data-ttu-id="98228-174">- 使用 EDM 上载代理对计算机进行本地管理员访问</span><span class="sxs-lookup"><span data-stu-id="98228-174">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="98228-175">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="98228-175">- Read access to the sensitive data</span></span><br/><span data-ttu-id="98228-176">- 刷新数据的流程和计划</span><span class="sxs-lookup"><span data-stu-id="98228-176">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="98228-177">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="98228-177">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="98228-178">- 具有 DLP 的 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="98228-178">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="98228-179">- 已启用基于 EDM 的分类功能</span><span class="sxs-lookup"><span data-stu-id="98228-179">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="98228-180">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="98228-180">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="98228-181">设置和配置基于 EDM 的分类涉及以 .csv 格式保存敏感数据、为敏感信息数据库定义架构、创建规则包以及上载架构和规则包。</span><span class="sxs-lookup"><span data-stu-id="98228-181">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="98228-182">定义敏感信息数据库的架构</span><span class="sxs-lookup"><span data-stu-id="98228-182">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="98228-183">确定要使用的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="98228-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="98228-184">将数据导出到应用（如 Microsoft Excel），然后以 .csv 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="98228-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="98228-185">数据文件最多可包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="98228-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="98228-186">高达 1 亿行的敏感数据</span><span class="sxs-lookup"><span data-stu-id="98228-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="98228-187">每个数据源最多 32 列（字段）</span><span class="sxs-lookup"><span data-stu-id="98228-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="98228-188">最多 5 个列（字段）标记为可搜索</span><span class="sxs-lookup"><span data-stu-id="98228-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="98228-189">在 .csv 文件中构造敏感数据，使第一行包含用于基于 EDM 的分类的字段名称。</span><span class="sxs-lookup"><span data-stu-id="98228-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="98228-190">在 .csv 文件中，你可能拥有“ssn”、“生日”、“名字”、“姓氏”等字段名称。</span><span class="sxs-lookup"><span data-stu-id="98228-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="98228-191">请注意，列标题名称不得包含空格或下划线字符。</span><span class="sxs-lookup"><span data-stu-id="98228-191">Please note that column headers can't include spaces or underscores in their names.</span></span> <span data-ttu-id="98228-192">例如，.csv 文件名为  *PatientRecords.csv*，其中包含  *PatientID*、 *MRN*、 *LastName*、 *FirstName*、 *SSN* 等列。</span><span class="sxs-lookup"><span data-stu-id="98228-192">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="98228-193">以 XML 格式定义敏感信息数据库的架构（类似于下面的示例）。</span><span class="sxs-lookup"><span data-stu-id="98228-193">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="98228-194">命名此架构文件 **edm.xml**并对其进行配置，确保对于数据库中的每一列，都有一行使用语法：</span><span class="sxs-lookup"><span data-stu-id="98228-194">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="98228-195">`\<Field name="" searchable=""/\>`（）。</span><span class="sxs-lookup"><span data-stu-id="98228-195">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="98228-196">将列名用于 *字段名称*值。 </span><span class="sxs-lookup"><span data-stu-id="98228-196">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="98228-197">将 *searchable="true"* 用于可搜索的字段，最多 5 个字段。</span><span class="sxs-lookup"><span data-stu-id="98228-197">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="98228-198">必须至少将一个字段指定为可搜索。</span><span class="sxs-lookup"><span data-stu-id="98228-198">You must designate a minimum of one field as searchable.</span></span>

      <span data-ttu-id="98228-199">例如，以下 XML 文件定义患者记录数据库的架构，其中五个字段指定为可搜索字段： *患者 ID*、 *MRN*、 *SSN*、 *电话*和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="98228-199">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="98228-200">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="98228-200">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="98228-201">使用[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="98228-201">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="98228-202">要上传数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="98228-202">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="98228-203">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98228-203">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="98228-204">确认</span><span class="sxs-lookup"><span data-stu-id="98228-204">Confirm</span></span>
      >
      > <span data-ttu-id="98228-205">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="98228-205">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="98228-206">将导入数据存储“patientrecords”的新 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="98228-206">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="98228-207">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="98228-207">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="98228-208">若想更改但不进行确认，请在步骤 5 中改用此 cmdlet：New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="98228-208">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="98228-209">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="98228-209">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="98228-210">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="98228-210">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="98228-211">敏感信息数据库的架构现已定义，接下来是设置规则包。</span><span class="sxs-lookup"><span data-stu-id="98228-211">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="98228-212">继续到 [设置规则包](#set-up-a-rule-package)部分。</span><span class="sxs-lookup"><span data-stu-id="98228-212">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="98228-213">编辑基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="98228-213">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="98228-214">如果想要更改**edm.xml** 文件，例如更改要对基于 EDM 的分类使用的字段，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="98228-214">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="98228-215">编辑 **edm.xml** 文件（即本文的 [定义架构](#define-the-schema-for-your-database-of-sensitive-information) 部分中讨论的文件）。</span><span class="sxs-lookup"><span data-stu-id="98228-215">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="98228-216">使用[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="98228-216">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="98228-217">要更新数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="98228-217">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="98228-218">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98228-218">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="98228-219">确认</span><span class="sxs-lookup"><span data-stu-id="98228-219">Confirm</span></span>
      >
      > <span data-ttu-id="98228-220">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="98228-220">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="98228-221">将更新数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="98228-221">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="98228-222">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="98228-222">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="98228-223">若想更改但不进行确认，请在步骤 3 中改用此 cmdlet：Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="98228-223">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="98228-224">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="98228-224">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="98228-225">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="98228-225">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="98228-226">删除基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="98228-226">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="98228-227">（根据需要）若想删除正在对基于 EDM 的分类使用的架构，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="98228-227">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="98228-228">使用[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="98228-228">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="98228-229">运行下列 PowerShell cmdlet，将“patientrecords”的数据存储名称替换为要删除的名称：</span><span class="sxs-lookup"><span data-stu-id="98228-229">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="98228-230">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98228-230">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="98228-231">确认</span><span class="sxs-lookup"><span data-stu-id="98228-231">Confirm</span></span>
      >
      > <span data-ttu-id="98228-232">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="98228-232">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="98228-233">将删除数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="98228-233">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="98228-234">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="98228-234">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="98228-235">若想更改但不进行确认，请在步骤 2 中改用此 cmdlet：Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="98228-235">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="98228-236">设置规则包</span><span class="sxs-lookup"><span data-stu-id="98228-236">Set up a rule package</span></span>

1. <span data-ttu-id="98228-237">按 XML 格式创建一个规则包（采用 Unicode 编码），如下例类似。</span><span class="sxs-lookup"><span data-stu-id="98228-237">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="98228-238">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="98228-238">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="98228-239">设置规则包时，请确保正确引用 .csv 文件和 **edm.xml** 文件。</span><span class="sxs-lookup"><span data-stu-id="98228-239">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="98228-240">可复制、修改和使用我们的示例。</span><span class="sxs-lookup"><span data-stu-id="98228-240">You can copy, modify, and use our example.</span></span> <span data-ttu-id="98228-241">在此示例 xml 中，需要对以下字段进行自定义，以创建 EDM 敏感类型：</span><span class="sxs-lookup"><span data-stu-id="98228-241">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="98228-242">**RulePack id & ExactMatch id**：使用 [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) 生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="98228-242">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="98228-243">**数据存储**：此字段指定要使用的 EDM 查找数据存储。</span><span class="sxs-lookup"><span data-stu-id="98228-243">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="98228-244">提供已配置的 EDM 架构的数据源名称。</span><span class="sxs-lookup"><span data-stu-id="98228-244">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="98228-245">**idMatch**：此字段指向 EDM 的主要元素。</span><span class="sxs-lookup"><span data-stu-id="98228-245">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="98228-246">匹配：指定要在精确查找中使用的字段。</span><span class="sxs-lookup"><span data-stu-id="98228-246">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="98228-247">在数据存储的 EDM 架构中提供可搜索的字段名称。</span><span class="sxs-lookup"><span data-stu-id="98228-247">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="98228-248">分类：此字段指定触发 EDM 查找的敏感类型匹配。</span><span class="sxs-lookup"><span data-stu-id="98228-248">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="98228-249">可提供现有内置或自定义分类的名称或 GUID。</span><span class="sxs-lookup"><span data-stu-id="98228-249">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="98228-250">**匹配：** 此字段指向邻近 idMatch 找到的其他证据。</span><span class="sxs-lookup"><span data-stu-id="98228-250">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="98228-251">匹配：在数据存储的 EDM 架构中提供任何字段名称。</span><span class="sxs-lookup"><span data-stu-id="98228-251">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="98228-252">**资源：** 此部分在多个区域设置中指定敏感类型的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="98228-252">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="98228-253">idRef：提供 ExactMatch ID 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="98228-253">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="98228-254">名称和说明：按需自定义。</span><span class="sxs-lookup"><span data-stu-id="98228-254">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="98228-255">通过逐一运行下列 PowerShell cmdlet 来上传规则包：</span><span class="sxs-lookup"><span data-stu-id="98228-255">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="98228-256">此时，你已设置基于 EDM 的分类。</span><span class="sxs-lookup"><span data-stu-id="98228-256">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="98228-257">下一步是为敏感数据创建哈希，然后上传哈希以便编制索引。</span><span class="sxs-lookup"><span data-stu-id="98228-257">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="98228-258">回想一下，在前面的过程中我们的 PatientRecords 架构将五个字段定义为可搜索： *PatientID*、 *MRN*、 *SSN*、 *Phone* 和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="98228-258">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="98228-259">我们的示例规则包中有这些字段并引用数据库架构文件 (**edm.xml**)，其中每个可搜索的字段具有一个 *ExactMatch* 项目。</span><span class="sxs-lookup"><span data-stu-id="98228-259">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="98228-260">请考虑以下 ExactMatch 项目：</span><span class="sxs-lookup"><span data-stu-id="98228-260">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="98228-261">在本例中，请注意以下内容：</span><span class="sxs-lookup"><span data-stu-id="98228-261">In this example, note the following:</span></span>

- <span data-ttu-id="98228-262">dataStore 名称引用了我们之前创建的 .csv 文件： **dataStore = "PatientRecords"**。</span><span class="sxs-lookup"><span data-stu-id="98228-262">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="98228-263">idMatch 值引用了数据库架构文件中列出的可搜索字段： **idMatch matches = "SSN"**。</span><span class="sxs-lookup"><span data-stu-id="98228-263">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="98228-264">分类值引用了现有或自定义敏感信息类型： **classification = "U.S. Social Security Number (SSN)"**。</span><span class="sxs-lookup"><span data-stu-id="98228-264">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="98228-265">（在此情况下，我们使用美国社会保障号的现有敏感信息类型。）</span><span class="sxs-lookup"><span data-stu-id="98228-265">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="98228-266">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="98228-266">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="98228-267">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="98228-267">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="98228-268">第 2 部分：为敏感数据创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="98228-268">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="98228-269">在此阶段，你将设置自定义安全组和用户帐户，并设置 EDM 上载代理工具。</span><span class="sxs-lookup"><span data-stu-id="98228-269">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="98228-270">然后，使用该工具为敏感数据创建哈希并上传哈希数据，以便对其编制索引。</span><span class="sxs-lookup"><span data-stu-id="98228-270">Then, you use the tool to hash the sensitive data, and upload the hashed data so it can be indexed.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="98228-271">设置安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="98228-271">Set up the security group and user account</span></span>

1. <span data-ttu-id="98228-272">作为全局管理员，使用相应的[订阅链接](#portal-links-for-your-subscription)转到管理中心并 [创建安全组](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) ，名为  **EDM\_DataUploaders**。</span><span class="sxs-lookup"><span data-stu-id="98228-272">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="98228-273">将一个或多个用户添加到 **EDM\_DataUploaders** 安全组。</span><span class="sxs-lookup"><span data-stu-id="98228-273">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="98228-274">（这些用户将管理敏感信息的数据库。）</span><span class="sxs-lookup"><span data-stu-id="98228-274">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="98228-275">确保负责管理敏感数据的每个用户都是装有 EDM 上载代理的计算机上的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="98228-275">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="98228-276">设置 EDM 上载代理</span><span class="sxs-lookup"><span data-stu-id="98228-276">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="98228-277">在开始此过程之前，请确保你是  **EDM\_DataUploaders** 安全组的成员和计算机上的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="98228-277">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="98228-278">按订阅类型链接到 EDM 上传代理</span><span class="sxs-lookup"><span data-stu-id="98228-278">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="98228-279">商用 + GCC</span><span class="sxs-lookup"><span data-stu-id="98228-279">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="98228-280">GCC-High</span><span class="sxs-lookup"><span data-stu-id="98228-280">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="98228-281">DoD</span><span class="sxs-lookup"><span data-stu-id="98228-281">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="98228-282">下载并安装适用于你的订阅的相应 [EDM 上载代理](#links-to-edm-upload-agent-by-subscription-type)。</span><span class="sxs-lookup"><span data-stu-id="98228-282">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription.</span></span> <span data-ttu-id="98228-283">默认情况下，安装位置应为 \*\* C:\\Program Files\\Microsoft\\EdmUploadAgent\*\*。</span><span class="sxs-lookup"><span data-stu-id="98228-283">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

   > [!TIP]
   > <span data-ttu-id="98228-284">要获取受支持命令参数的列表，请运行无代理参数。</span><span class="sxs-lookup"><span data-stu-id="98228-284">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="98228-285">例如“EdmUploadAgent.exe”。</span><span class="sxs-lookup"><span data-stu-id="98228-285">For example 'EdmUploadAgent.exe'.</span></span>

   > [!NOTE]
   > <span data-ttu-id="98228-286">每天只能使用 EDMUploadAgent 将数据上传到任何给定的数据存储空间两次。</span><span class="sxs-lookup"><span data-stu-id="98228-286">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

2. <span data-ttu-id="98228-287">若要授权 EDM 上载代理，请打开 Windows 命令提示符（以管理员身份），然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="98228-287">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="98228-288">使用添加到 EDM_DataUploaders 安全组的 Office 365 工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="98228-288">Sign in with your work or school account for Office 365 that was added to the EDM_DataUploaders security group.</span></span>

<span data-ttu-id="98228-289">下一步是使用 EDM 上载代理为敏感数据创建哈希，然后上传哈希数据。</span><span class="sxs-lookup"><span data-stu-id="98228-289">The next step is to use the EDM Upload Agent to hash the sensitive data, and then upload the hashed data.</span></span>

#### <a name="hash-and-upload-the-sensitive-data"></a><span data-ttu-id="98228-290">为敏感数据创建哈希并上传</span><span class="sxs-lookup"><span data-stu-id="98228-290">Hash and upload the sensitive data</span></span>

<span data-ttu-id="98228-291">将敏感数据文件（注意我们的示例为 **PatientRecords.csv**）保存到计算机上的本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="98228-291">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="98228-292">（我们已将示例 **PatientRecords.csv** 文件保存到 **C:\\Edm\\Data**。）</span><span class="sxs-lookup"><span data-stu-id="98228-292">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="98228-293">若要为敏感数据创建哈希并上传，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="98228-293">To hash and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="98228-294">示例：**EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="98228-294">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="98228-295">若要在独立环境中分隔和执行敏感数据哈希，请单独执行哈希和上传步骤。</span><span class="sxs-lookup"><span data-stu-id="98228-295">To separate and execute the hashing of sensitive data in an isolated environment, execute the hashing and upload steps separately.</span></span>

<span data-ttu-id="98228-296">若要为敏感数据创建哈希，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="98228-296">To hash the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="98228-297">例如：</span><span class="sxs-lookup"><span data-stu-id="98228-297">For example:</span></span>

> <span data-ttu-id="98228-298">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="98228-298">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="98228-299">若要上传哈希数据，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="98228-299">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="98228-300">例如：</span><span class="sxs-lookup"><span data-stu-id="98228-300">For example:</span></span>

> <span data-ttu-id="98228-301">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="98228-301">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="98228-302">若要验证是否已上传敏感数据，请在“命令提示符”窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="98228-302">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="98228-303">你将看到数据存储区列表以及上次更新时间。</span><span class="sxs-lookup"><span data-stu-id="98228-303">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="98228-304">如果要查看所有数据上载到特定存储的信息，请在 Windows 命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="98228-304">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="98228-305">继续设置 [刷新敏感信息数据库](#refreshing-your-sensitive-information-database)的流程和计划。</span><span class="sxs-lookup"><span data-stu-id="98228-305">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="98228-306">此时，你已准备好将基于 EDM 的分类与 Microsoft 云服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="98228-306">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="98228-307">例如，你可以 [使用基于 EDM 的分类设置 DLP 策略](#to-create-a-dlp-policy-with-edm)。</span><span class="sxs-lookup"><span data-stu-id="98228-307">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="98228-308">刷新敏感信息数据库</span><span class="sxs-lookup"><span data-stu-id="98228-308">Refreshing your sensitive information database</span></span>

<span data-ttu-id="98228-309">你可以每天或每周刷新敏感信息数据库，EDM 上载工具可以重新为敏感数据创建哈希，然后重新上载哈希数据。</span><span class="sxs-lookup"><span data-stu-id="98228-309">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can re-hash the sensitive data and then reupload the hashed data.</span></span>

1. <span data-ttu-id="98228-310">确定刷新敏感信息数据库的流程和频率（每天或每周）。</span><span class="sxs-lookup"><span data-stu-id="98228-310">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="98228-311">将敏感数据重新导出到应用（如 Microsoft Excel），并以 .csv 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="98228-311">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="98228-312">在按照 [为敏感数据创建哈希并上传](#hash-and-upload-the-sensitive-data)中所述的步骤执行操作时，让所使用的文件名和位置保持不变。</span><span class="sxs-lookup"><span data-stu-id="98228-312">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="98228-313">如果 .csv 文件的结构（字段名称）未发生更改，则刷新数据时无需对数据库架构文件进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="98228-313">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="98228-314">但是，如果必须进行更改，请确保相应地编辑数据库架和规则包。</span><span class="sxs-lookup"><span data-stu-id="98228-314">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="98228-315">使用 [任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) 自动执行 [为敏感数据创建哈希并上传流程中的步骤 2 和 3](#hash-and-upload-the-sensitive-data) 。</span><span class="sxs-lookup"><span data-stu-id="98228-315">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="98228-316">你可以使用多种方法来计划任务：</span><span class="sxs-lookup"><span data-stu-id="98228-316">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="98228-317">方法</span><span class="sxs-lookup"><span data-stu-id="98228-317">Method</span></span>             | <span data-ttu-id="98228-318">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="98228-318">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="98228-319">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98228-319">Windows PowerShell</span></span>     | <span data-ttu-id="98228-320">请参阅本文中的 [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) 文档和 [示例 PowerShell 脚本](#example-powershell-script-for-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="98228-320">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="98228-321">任务计划程序 API</span><span class="sxs-lookup"><span data-stu-id="98228-321">Task Scheduler API</span></span>     | <span data-ttu-id="98228-322">请参阅 [任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)文档 </span><span class="sxs-lookup"><span data-stu-id="98228-322">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="98228-323">Windows 用户界面</span><span class="sxs-lookup"><span data-stu-id="98228-323">Windows user interface</span></span> | <span data-ttu-id="98228-324">在 Windows 中单击“开始”，然后键入 Task Scheduler。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-324">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="98228-325">然后，在结果列表中，右键单击“任务计划程序”，然后选择“以管理员身份运行”。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-325">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="98228-326">任务计划程序的示例 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="98228-326">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="98228-327">此部分包含一个示例 PowerShell 脚本，你可以使用该脚本来计划为数据创建哈希并上传哈希数据的任务：</span><span class="sxs-lookup"><span data-stu-id="98228-327">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="98228-328">在合并步骤中计划哈希和上传</span><span class="sxs-lookup"><span data-stu-id="98228-328">To schedule hashing and upload in a combined step</span></span>

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="98228-329">将计划哈希和上传作为单独的步骤</span><span class="sxs-lookup"><span data-stu-id="98228-329">To schedule hashing and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="98228-330">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="98228-330">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="98228-331">这些位置支持 EDM 敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="98228-331">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="98228-332">针对 Exchange Online 的 DLP（电子邮件）</span><span class="sxs-lookup"><span data-stu-id="98228-332">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="98228-333">OneDrive for Business（文件）</span><span class="sxs-lookup"><span data-stu-id="98228-333">OneDrive for Business (files)</span></span>
- <span data-ttu-id="98228-334">Microsoft Teams（对话）</span><span class="sxs-lookup"><span data-stu-id="98228-334">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="98228-335">针对 SharePoint 的 DLP（文件）</span><span class="sxs-lookup"><span data-stu-id="98228-335">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="98228-336">Microsoft Cloud App Security DLP 策略</span><span class="sxs-lookup"><span data-stu-id="98228-336">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="98228-337">以下方案的 EDM 敏感信息类型目前正在开发中，尚不可用：</span><span class="sxs-lookup"><span data-stu-id="98228-337">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="98228-338">灵敏度标签和保留标签的自动分类</span><span class="sxs-lookup"><span data-stu-id="98228-338">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="98228-339">使用 EDM 创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="98228-339">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="98228-340">使用相应的[订阅链接](#portal-links-for-your-subscription)转到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="98228-340">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="98228-341">选择“数据丢失防护”\>“策略”。 \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-341">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="98228-342">选择“创建策略”\>“自定义”\>“下一步”。 \*\*\*\*  \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-342">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="98228-343">在“命名策略”选项卡上，指定名称和说明，然后选择“下一步”。 \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-343">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="98228-344">在“选择位置”选项卡上，选择“允许选择特定位置”，然后选择“下一步”。 \*\*\*\*  \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-344">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="98228-345">在“状态”列中，选择“Exchange 电子邮件、OneDrive 帐户、团队聊天和频道邮件”，然后选择“下一步”。 \*\*\*\*  \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-345">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="98228-346">在“策略设置”选项卡上，选择“使用高级设置”，然后选择“下一步”。 \*\*\*\*  \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-346">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="98228-347">选择“+ 新建规则”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-347">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="98228-348">在“名称”部分中，指定规则的名称和说明。 \*\*\*\* </span><span class="sxs-lookup"><span data-stu-id="98228-348">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="98228-349">在“条件”部分的“+ 添加条件”列表中，选择“内容包含敏感类型”。 \*\*\*\*  \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-349">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![内容包含敏感信息类型](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="98228-351">搜索你在设置规则包时创建的敏感信息类型，然后选择“+ 添加”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-351">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="98228-352">然后选择“完成”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-352">Then choose **Done**.</span></span>

12. <span data-ttu-id="98228-353">完成为规则选择相关选项，例如“用户通知”、“用户覆盖”、“事件报告”等，然后选择“保存”。 \*\*\*\* \*\*\*\* \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-353">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="98228-354">在“策略设置”选项卡上，查看你的规则，然后选择“下一步”。 \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-354">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="98228-355">指定是立即打开策略、测试它还是保持关闭。</span><span class="sxs-lookup"><span data-stu-id="98228-355">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="98228-356">然后选择“下一步” \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="98228-356">Then choose **Next**.</span></span>

15. <span data-ttu-id="98228-357">在“查看你的设置”选项卡上，查看你的策略。 \*\*\*\* </span><span class="sxs-lookup"><span data-stu-id="98228-357">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="98228-358">执行任何必要的更改。</span><span class="sxs-lookup"><span data-stu-id="98228-358">Make any needed changes.</span></span> <span data-ttu-id="98228-359">准备好后，选择“创建”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98228-359">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="98228-360">新 DLP 策略大约需要一个小时才能通过你的数据中心。</span><span class="sxs-lookup"><span data-stu-id="98228-360">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="98228-361">相关文章</span><span class="sxs-lookup"><span data-stu-id="98228-361">Related articles</span></span>

- [<span data-ttu-id="98228-362">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="98228-362">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="98228-363">自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="98228-363">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="98228-364">DLP 策略概述</span><span class="sxs-lookup"><span data-stu-id="98228-364">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="98228-365">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="98228-365">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="98228-366">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="98228-366">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

