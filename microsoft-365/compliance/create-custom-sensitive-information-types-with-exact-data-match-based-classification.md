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
description: 使用基于精确数据匹配的分类创建自定义敏感信息类型。
ms.openlocfilehash: 044801416c7db4ddec8936a496862c432a63acde
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42077592"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="87cc8-103">使用基于精确数据匹配的分类创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="87cc8-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

## <a name="overview"></a><span data-ttu-id="87cc8-104">概述</span><span class="sxs-lookup"><span data-stu-id="87cc8-104">Overview</span></span>

<span data-ttu-id="87cc8-105">[自定义敏感信息类型](custom-sensitive-info-types.md) 用于帮助防止无意或不适当的敏感信息共享。</span><span class="sxs-lookup"><span data-stu-id="87cc8-105">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="87cc8-106">作为管理员，你可以使用 [安全与合规中心](create-a-custom-sensitive-information-type.md)或 [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)，根据模式、证据（“员工”、“徽章”、“ID”等关键字）、字符邻近度（特定模式下证据与字符的邻近度）以及可信度来定义自定义敏感信息类型。   ** ** \*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-106">As an administrator, you can use the [Security & Compliance Center](create-a-custom-sensitive-information-type.md) or [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="87cc8-107">此类自定义敏感信息类型可满足许多组织的业务需求。</span><span class="sxs-lookup"><span data-stu-id="87cc8-107">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="87cc8-108">但是，如果你需要自定义敏感信息类型（它使用精确数据值而不是仅与泛型模式匹配），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="87cc8-108">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="87cc8-109">通过基于精确数据匹配 (EDM) 的分类，你可以创建专门设计的自定义敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="87cc8-109">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="87cc8-110">动态并且可刷新；</span><span class="sxs-lookup"><span data-stu-id="87cc8-110">be dynamic and refreshable;</span></span>
- <span data-ttu-id="87cc8-111">更具可伸缩性；</span><span class="sxs-lookup"><span data-stu-id="87cc8-111">be more scalable;</span></span>
- <span data-ttu-id="87cc8-112">导致更少的误报；</span><span class="sxs-lookup"><span data-stu-id="87cc8-112">result in fewer false-positives;</span></span>
- <span data-ttu-id="87cc8-113">处理结构化敏感数据；</span><span class="sxs-lookup"><span data-stu-id="87cc8-113">work with structured sensitive data;</span></span>
- <span data-ttu-id="87cc8-114">更安全地处理敏感信息以及</span><span class="sxs-lookup"><span data-stu-id="87cc8-114">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="87cc8-115">与多种 Microsoft 云服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="87cc8-115">be used with several Microsoft cloud services.</span></span>

![基于 EDM 的分类](../media/EDMClassification.png)

<span data-ttu-id="87cc8-117">基于 EDM 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。</span><span class="sxs-lookup"><span data-stu-id="87cc8-117">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="87cc8-118">数据库可以每天或每周刷新一次，最多可包含 1000 万行数据。</span><span class="sxs-lookup"><span data-stu-id="87cc8-118">The database can be refreshed daily or weekly, and it can contain up to 10 million rows of data.</span></span> <span data-ttu-id="87cc8-119">因此，当员工、患者或客户往来并且记录发生更改时，你的自定义敏感信息类型仍将保持最新并且适用。</span><span class="sxs-lookup"><span data-stu-id="87cc8-119">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="87cc8-120">你还可以将基于 EDM 的分类与策略一起使用，例如 [数据丢失防护策略](data-loss-prevention-policies.md) (DLP) 或 [Microsoft Cloud App Security 文件策略](https://docs.microsoft.com/cloud-app-security/data-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="87cc8-120">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="87cc8-121">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="87cc8-121">Required licenses and permissions</span></span>

<span data-ttu-id="87cc8-122">你必须是全局管理员、合规性管理员或 Exchange Online 管理员才能执行本文中描述的任务。</span><span class="sxs-lookup"><span data-stu-id="87cc8-122">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="87cc8-123">若要了解有关 DLP 权限的详细信息，请参阅 [权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="87cc8-123">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="87cc8-124">当正式发布时，基于 EDM 的分类将包含在这些订阅中</span><span class="sxs-lookup"><span data-stu-id="87cc8-124">When generally available, EDM-based classification will be included in these subscriptions</span></span>

- <span data-ttu-id="87cc8-125">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="87cc8-125">Office 365 E5</span></span>
- <span data-ttu-id="87cc8-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="87cc8-126">Microsoft 365 E5</span></span>
- <span data-ttu-id="87cc8-127">Microsoft 365 信息保护与合规性</span><span class="sxs-lookup"><span data-stu-id="87cc8-127">Microsoft 365 Information Protection and Compliance</span></span>
- <span data-ttu-id="87cc8-128">Office 365 高级合规版</span><span class="sxs-lookup"><span data-stu-id="87cc8-128">Office 365 Advanced Compliance</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="87cc8-129">工作流程概览</span><span class="sxs-lookup"><span data-stu-id="87cc8-129">The work flow at a glance</span></span>

|<span data-ttu-id="87cc8-130">阶段</span><span class="sxs-lookup"><span data-stu-id="87cc8-130">Phase</span></span>  |<span data-ttu-id="87cc8-131">所需项</span><span class="sxs-lookup"><span data-stu-id="87cc8-131">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="87cc8-132">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="87cc8-132">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="87cc8-133">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="87cc8-133">(As needed)</span></span><br/><span data-ttu-id="87cc8-134">- [编辑数据库架构](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="87cc8-134">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="87cc8-135">- [删除架构](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="87cc8-135">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="87cc8-136">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="87cc8-136">- Read access to the sensitive data</span></span><br/><span data-ttu-id="87cc8-137">- .xml 格式的数据库架构（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="87cc8-137">- Database schema in .xml format (example provided)</span></span><br/><span data-ttu-id="87cc8-138">- .xml 格式的规则包（提供了示例）</span><span class="sxs-lookup"><span data-stu-id="87cc8-138">- Rule package in .xml format (example provided)</span></span><br/><span data-ttu-id="87cc8-139">- 安全与合规中心的管理员权限（使用 PowerShell）</span><span class="sxs-lookup"><span data-stu-id="87cc8-139">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="87cc8-140">第 2 部分：创建索引并上载敏感数据</span><span class="sxs-lookup"><span data-stu-id="87cc8-140">Part 2: Index and upload the sensitive data</span></span>](#part-2-index-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="87cc8-141">（根据需要）</span><span class="sxs-lookup"><span data-stu-id="87cc8-141">(As needed)</span></span><br/>[<span data-ttu-id="87cc8-142">刷新数据</span><span class="sxs-lookup"><span data-stu-id="87cc8-142">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="87cc8-143">- 自定义安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="87cc8-143">- Custom security group and user account</span></span><br/><span data-ttu-id="87cc8-144">- 使用 EDM 上载代理对计算机进行本地管理员访问</span><span class="sxs-lookup"><span data-stu-id="87cc8-144">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="87cc8-145">- 敏感数据的读取权限</span><span class="sxs-lookup"><span data-stu-id="87cc8-145">- Read access to the sensitive data</span></span><br/><span data-ttu-id="87cc8-146">- 刷新数据的流程和计划</span><span class="sxs-lookup"><span data-stu-id="87cc8-146">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="87cc8-147">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="87cc8-147">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="87cc8-148">- 包含 DLP 的 Office 365 订阅</span><span class="sxs-lookup"><span data-stu-id="87cc8-148">- Office 365 subscription with DLP</span></span><br/><span data-ttu-id="87cc8-149">- 已启用基于 EDM 的分类功能</span><span class="sxs-lookup"><span data-stu-id="87cc8-149">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="87cc8-150">第 1 部分：设置基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="87cc8-150">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="87cc8-151">设置和配置基于 EDM 的分类涉及以 .csv 格式保存敏感数据、为敏感信息数据库定义架构、创建规则包以及上载架构和规则包。</span><span class="sxs-lookup"><span data-stu-id="87cc8-151">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="87cc8-152">定义敏感信息数据库的架构</span><span class="sxs-lookup"><span data-stu-id="87cc8-152">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="87cc8-153">确定要使用的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="87cc8-153">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="87cc8-154">将数据导出到应用（如 Microsoft Excel），然后以 .csv 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="87cc8-154">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="87cc8-155">数据文件最多可包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="87cc8-155">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="87cc8-156">高达 1000 万行的敏感数据</span><span class="sxs-lookup"><span data-stu-id="87cc8-156">Up to 10 million rows of sensitive data</span></span>
      - <span data-ttu-id="87cc8-157">每个数据源最多 32 列（字段）</span><span class="sxs-lookup"><span data-stu-id="87cc8-157">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="87cc8-158">最多 5 个列（字段）标记为可搜索</span><span class="sxs-lookup"><span data-stu-id="87cc8-158">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="87cc8-159">在 .csv 文件中构造敏感数据，使第一行包含用于基于 EDM 的分类的字段名称。</span><span class="sxs-lookup"><span data-stu-id="87cc8-159">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="87cc8-160">在 .csv 文件中，你可能拥有“ssn”、“生日”、“名字”、“姓氏”等字段名称。</span><span class="sxs-lookup"><span data-stu-id="87cc8-160">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="87cc8-161">例如，我们的 .csv 文件称为  *PatientRecords.csv*，其列包含 *患者 ID*、 *MRN*、 *姓氏*、 *名字*、 *SSN* 等。</span><span class="sxs-lookup"><span data-stu-id="87cc8-161">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* and more.</span></span>

3. <span data-ttu-id="87cc8-162">以 .xml 格式定义敏感信息数据库的架构（类似于下面的示例）。</span><span class="sxs-lookup"><span data-stu-id="87cc8-162">Define the schema for the database of sensitive information in .xml format (similar to our example below).</span></span> <span data-ttu-id="87cc8-163">命名此架构文件 **edm.xml**并对其进行配置，确保对于数据库中的每一列，都有一行使用语法：</span><span class="sxs-lookup"><span data-stu-id="87cc8-163">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

<span data-ttu-id="87cc8-164">`\<Field name="" searchable=""/\>`（）。</span><span class="sxs-lookup"><span data-stu-id="87cc8-164">`\<Field name="" searchable=""/\>`.</span></span>

- <span data-ttu-id="87cc8-165">将列名用于 *字段名称*值。 </span><span class="sxs-lookup"><span data-stu-id="87cc8-165">Use column names for *Field name* values.</span></span>
- <span data-ttu-id="87cc8-166">将 *searchable="true"* 用于可搜索的字段，最多 5 个字段。</span><span class="sxs-lookup"><span data-stu-id="87cc8-166">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="87cc8-167">必须至少将一个字段指定为可搜索。</span><span class="sxs-lookup"><span data-stu-id="87cc8-167">You must designate a minimum of one field as searchable.</span></span>

<span data-ttu-id="87cc8-168">例如，以下 .xml 文件定义患者记录数据库的架构，其中五个字段指定为可搜索字段： *患者 ID*、 *MRN*、 *SSN*、 *电话*和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="87cc8-168">As an example, the following .xml file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

<span data-ttu-id="87cc8-169">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="87cc8-169">(You can copy, modify, and use our example.)</span></span>

 ```xml
<EdmSchema xmlns="https://schemas.microsoft.com/office/2018/edm">
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

4. <span data-ttu-id="87cc8-170">[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="87cc8-170">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="87cc8-171">要上传数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="87cc8-171">To upload the database schema, run the following cmdlets, one at a time:</span></span>

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

<span data-ttu-id="87cc8-172">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="87cc8-172">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="87cc8-173">确认</span><span class="sxs-lookup"><span data-stu-id="87cc8-173">Confirm</span></span>
>
> <span data-ttu-id="87cc8-174">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="87cc8-174">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="87cc8-175">将导入数据存储“patientrecords”的新 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="87cc8-175">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
>
> <span data-ttu-id="87cc8-176">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="87cc8-176">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="87cc8-177">若想更改但不进行确认，请在步骤 5 中改用此 cmdlet：New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="87cc8-177">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="87cc8-178">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="87cc8-178">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="87cc8-179">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="87cc8-179">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="87cc8-180">敏感信息数据库的架构现已定义，接下来是设置规则包。</span><span class="sxs-lookup"><span data-stu-id="87cc8-180">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="87cc8-181">继续到 [设置规则包](#set-up-a-rule-package)部分。</span><span class="sxs-lookup"><span data-stu-id="87cc8-181">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="87cc8-182">编辑基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="87cc8-182">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="87cc8-183">如果想要更改**edm.xml** 文件，例如更改要对基于 EDM 的分类使用的字段，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="87cc8-183">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="87cc8-184">编辑 **edm.xml** 文件（即本文的 [定义架构](#define-the-schema-for-your-database-of-sensitive-information) 部分中讨论的文件）。</span><span class="sxs-lookup"><span data-stu-id="87cc8-184">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="87cc8-185">[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="87cc8-185">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="87cc8-186">要更新数据库架构，请逐一运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="87cc8-186">To update your database schema, run the following cmdlets, one at a time:</span></span>

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

<span data-ttu-id="87cc8-187">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="87cc8-187">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="87cc8-188">确认</span><span class="sxs-lookup"><span data-stu-id="87cc8-188">Confirm</span></span>
>
> <span data-ttu-id="87cc8-189">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="87cc8-189">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="87cc8-190">将更新数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="87cc8-190">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
>
> <span data-ttu-id="87cc8-191">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="87cc8-191">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="87cc8-192">若想更改但不进行确认，请在步骤 3 中改用此 cmdlet：Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="87cc8-192">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="87cc8-193">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="87cc8-193">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="87cc8-194">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="87cc8-194">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="87cc8-195">删除基于 EDM 的分类的架构</span><span class="sxs-lookup"><span data-stu-id="87cc8-195">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="87cc8-196">（根据需要）若想删除正在对基于 EDM 的分类使用的架构，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="87cc8-196">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="87cc8-197">[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="87cc8-197">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="87cc8-198">运行下列 PowerShell cmdlet，将“patientrecords”的数据存储名称替换为要删除的名称：</span><span class="sxs-lookup"><span data-stu-id="87cc8-198">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

```powershell
Remove-DlpEdmSchema -Identity patientrecords
```

<span data-ttu-id="87cc8-199">系统将提示你进行确认，如下所示：</span><span class="sxs-lookup"><span data-stu-id="87cc8-199">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="87cc8-200">确认</span><span class="sxs-lookup"><span data-stu-id="87cc8-200">Confirm</span></span>
>
> <span data-ttu-id="87cc8-201">是否确实要执行此操作？</span><span class="sxs-lookup"><span data-stu-id="87cc8-201">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="87cc8-202">将删除数据存储“patientrecords”的 EDM 架构。</span><span class="sxs-lookup"><span data-stu-id="87cc8-202">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
>
> <span data-ttu-id="87cc8-203">\[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：</span><span class="sxs-lookup"><span data-stu-id="87cc8-203">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
>  <span data-ttu-id="87cc8-204">若想更改但不进行确认，请在步骤 2 中改用此 cmdlet：Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="87cc8-204">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="87cc8-205">设置规则包</span><span class="sxs-lookup"><span data-stu-id="87cc8-205">Set up a rule package</span></span>

1. <span data-ttu-id="87cc8-206">按 .xml 格式创建一个规则包（采用 Unicode 编码），如下例类似。</span><span class="sxs-lookup"><span data-stu-id="87cc8-206">Create a rule package in .xml format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="87cc8-207">（可复制、修改和使用我们的示例。）</span><span class="sxs-lookup"><span data-stu-id="87cc8-207">(You can copy, modify, and use our example.)</span></span>

<span data-ttu-id="87cc8-208">设置规则包时，请确保正确引用 .csv 文件和 **edm.xml** 文件。</span><span class="sxs-lookup"><span data-stu-id="87cc8-208">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="87cc8-209">可复制、修改和使用我们的示例。</span><span class="sxs-lookup"><span data-stu-id="87cc8-209">You can copy, modify, and use our example.</span></span> <span data-ttu-id="87cc8-210">在此示例 xml 中，需要对以下字段进行自定义，以创建 EDM 敏感类型：</span><span class="sxs-lookup"><span data-stu-id="87cc8-210">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

- <span data-ttu-id="87cc8-211">**RulePack id & ExactMatch id**：使用 [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) 生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="87cc8-211">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

- <span data-ttu-id="87cc8-212">**数据存储**：此字段指定要使用的 EDM 查找数据存储。</span><span class="sxs-lookup"><span data-stu-id="87cc8-212">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="87cc8-213">提供已配置的 EDM 架构的数据源名称。</span><span class="sxs-lookup"><span data-stu-id="87cc8-213">You provide a data source name of a configured EDM Schema.</span></span>

- <span data-ttu-id="87cc8-214">**idMatch**：此字段指向 EDM 的主要元素。</span><span class="sxs-lookup"><span data-stu-id="87cc8-214">**idMatch**: This field points to the primary element for EDM.</span></span>
  - <span data-ttu-id="87cc8-215">匹配：指定要在精确查找中使用的字段。</span><span class="sxs-lookup"><span data-stu-id="87cc8-215">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="87cc8-216">在数据存储的 EDM 架构中提供可搜索的字段名称。</span><span class="sxs-lookup"><span data-stu-id="87cc8-216">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
  - <span data-ttu-id="87cc8-217">分类：此字段指定触发 EDM 查找的敏感类型匹配。</span><span class="sxs-lookup"><span data-stu-id="87cc8-217">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="87cc8-218">可提供现有内置或自定义分类的名称或 GUID。</span><span class="sxs-lookup"><span data-stu-id="87cc8-218">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

- <span data-ttu-id="87cc8-219">**匹配：** 此字段指向邻近 idMatch 找到的其他证据。</span><span class="sxs-lookup"><span data-stu-id="87cc8-219">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
  - <span data-ttu-id="87cc8-220">匹配：在数据存储的 EDM 架构中提供任何字段名称。</span><span class="sxs-lookup"><span data-stu-id="87cc8-220">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
- <span data-ttu-id="87cc8-221">**资源：** 此部分在多个区域设置中指定敏感类型的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="87cc8-221">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
  - <span data-ttu-id="87cc8-222">idRef：提供 ExactMatch id 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="87cc8-222">idRef: You provide GUID for ExactMatch id.</span></span>
  - <span data-ttu-id="87cc8-223">名称与说明编辑架构标题：按需自定义。</span><span class="sxs-lookup"><span data-stu-id="87cc8-223">Name & des Editing the schema criptions: customize as required.</span></span>

```xml
<RulePackage xmlns="https://schemas.microsoft.com/office/2018/edm">
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
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
```

1. <span data-ttu-id="87cc8-224">通过逐一运行下列 PowerShell cmdlet 来上传规则包：</span><span class="sxs-lookup"><span data-stu-id="87cc8-224">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

```powershell
$rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
```

<span data-ttu-id="87cc8-225">此时，你已设置基于 EDM 的分类。</span><span class="sxs-lookup"><span data-stu-id="87cc8-225">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="87cc8-226">下一步是为敏感数据创建索引，然后上传索引数据。</span><span class="sxs-lookup"><span data-stu-id="87cc8-226">The next step is to index the sensitive data, and then upload the indexed data.</span></span>

<span data-ttu-id="87cc8-227">回想一下，在前面的过程中我们的 PatientRecords 架构将五个字段定义为可搜索： *PatientID*、 *MRN*、 *SSN*、 *Phone* 和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="87cc8-227">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="87cc8-228">我们的示例规则包中有这些字段并引用数据库架构文件 (**edm.xml**)，其中每个可搜索的字段具有一个 *ExactMatch* 项目。</span><span class="sxs-lookup"><span data-stu-id="87cc8-228">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="87cc8-229">请考虑以下 ExactMatch 项目：</span><span class="sxs-lookup"><span data-stu-id="87cc8-229">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="87cc8-230">在本例中，请注意以下内容：</span><span class="sxs-lookup"><span data-stu-id="87cc8-230">In this example, note the following:</span></span>

- <span data-ttu-id="87cc8-231">dataStore 名称引用了我们之前创建的 .csv 文件： **dataStore = "PatientRecords"**。</span><span class="sxs-lookup"><span data-stu-id="87cc8-231">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="87cc8-232">idMatch 值引用了数据库架构文件中列出的可搜索字段： **idMatch matches = "SSN"**。</span><span class="sxs-lookup"><span data-stu-id="87cc8-232">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="87cc8-233">分类值引用了现有或自定义敏感信息类型： **classification = "U.S. Social Security Number (SSN)"**。</span><span class="sxs-lookup"><span data-stu-id="87cc8-233">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="87cc8-234">（在此情况下，我们使用美国社会保障号的现有敏感信息类型。）</span><span class="sxs-lookup"><span data-stu-id="87cc8-234">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="87cc8-235">为 EDMSchema 更新新增内容可能需要10-60 分钟。</span><span class="sxs-lookup"><span data-stu-id="87cc8-235">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="87cc8-236">更新必须完成，然后才能执行使用这些新增操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="87cc8-236">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-index-and-upload-the-sensitive-data"></a><span data-ttu-id="87cc8-237">第 2 部分：创建索引并上传敏感数据</span><span class="sxs-lookup"><span data-stu-id="87cc8-237">Part 2: Index and upload the sensitive data</span></span>

<span data-ttu-id="87cc8-238">在此阶段，你将设置自定义安全组和用户帐户，并设置 EDM 上载代理工具。</span><span class="sxs-lookup"><span data-stu-id="87cc8-238">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="87cc8-239">然后，使用该工具为敏感数据创建索引，并上载索引数据。</span><span class="sxs-lookup"><span data-stu-id="87cc8-239">Then, you use the tool to index the sensitive data, and upload the indexed data.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="87cc8-240">设置安全组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="87cc8-240">Set up the security group and user account</span></span>

1. <span data-ttu-id="87cc8-241">以全局管理员身份转到管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com/)) 并 [创建安全组](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) 名为  **EDM\_DataUploaders**。</span><span class="sxs-lookup"><span data-stu-id="87cc8-241">As a global administrator, go to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com/)) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="87cc8-242">将一个或多个用户添加到 **EDM\_DataUploaders** 安全组。</span><span class="sxs-lookup"><span data-stu-id="87cc8-242">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="87cc8-243">（这些用户将管理敏感信息的数据库。）</span><span class="sxs-lookup"><span data-stu-id="87cc8-243">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="87cc8-244">确保负责管理敏感数据的每个用户都是装有 EDM 上载代理的计算机上的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="87cc8-244">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="87cc8-245">设置 EDM 上载代理</span><span class="sxs-lookup"><span data-stu-id="87cc8-245">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="87cc8-246">在开始此过程之前，请确保你是  **EDM\_DataUploaders** 安全组的成员和计算机上的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="87cc8-246">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

1. <span data-ttu-id="87cc8-247">下载并安装[EDM 上载代理](https://go.microsoft.com/fwlink/?linkid=2088639)。</span><span class="sxs-lookup"><span data-stu-id="87cc8-247">Download and install the [EDM Upload Agent](https://go.microsoft.com/fwlink/?linkid=2088639).</span></span> <span data-ttu-id="87cc8-248">默认情况下，安装位置应为 \*\* C:\\Program Files\\Microsoft\\EdmUploadAgent\*\*。</span><span class="sxs-lookup"><span data-stu-id="87cc8-248">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

> [!TIP]
> <span data-ttu-id="87cc8-249">要获取受支持命令参数的列表，请运行无代理参数。</span><span class="sxs-lookup"><span data-stu-id="87cc8-249">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="87cc8-250">例如“EdmUploadAgent.exe”。</span><span class="sxs-lookup"><span data-stu-id="87cc8-250">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="87cc8-251">若要授权 EDM 上载代理，请打开 Windows 命令提示符（以管理员身份），然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="87cc8-251">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

    `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="87cc8-252">使用 Office 365 的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="87cc8-252">Sign in with your work or school account for Office 365.</span></span>

<span data-ttu-id="87cc8-253">下一步是使用 EDM 上载代理为敏感数据创建索引，然后上载索引数据。</span><span class="sxs-lookup"><span data-stu-id="87cc8-253">The next step is to use the EDM Upload Agent to index the sensitive data, and then upload the indexed data.</span></span>

#### <a name="index-and-upload-the-sensitive-data"></a><span data-ttu-id="87cc8-254">创建索引并上传敏感数据</span><span class="sxs-lookup"><span data-stu-id="87cc8-254">Index and upload the sensitive data</span></span>

<span data-ttu-id="87cc8-255">将敏感数据文件（注意我们的示例为 **PatientRecords.csv**）保存到计算机上的本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="87cc8-255">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="87cc8-256">（我们已将示例 **PatientRecords.csv** 文件保存到 **C:\\Edm\\Data**。）</span><span class="sxs-lookup"><span data-stu-id="87cc8-256">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="87cc8-257">若要为敏感数据创建索引并上传，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="87cc8-257">To index and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="87cc8-258">示例：**EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="87cc8-258">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="87cc8-259">若要分隔和执行独立环境中的敏感数据索引，请单独执行索引和上传步骤。</span><span class="sxs-lookup"><span data-stu-id="87cc8-259">To separate and execute index of sensitive data in an isolated environment, execute index and upload steps separately.</span></span>

<span data-ttu-id="87cc8-260">若要为敏感数据创建索引，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="87cc8-260">To index the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="87cc8-261">例如，</span><span class="sxs-lookup"><span data-stu-id="87cc8-261">for example,</span></span>

> <span data-ttu-id="87cc8-262">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="87cc8-262">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="87cc8-263">若要上传索引数据，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="87cc8-263">To upload the indexed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="87cc8-264">例如，</span><span class="sxs-lookup"><span data-stu-id="87cc8-264">for example,</span></span> 

> <span data-ttu-id="87cc8-265">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="87cc8-265">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>

<span data-ttu-id="87cc8-266">若要验证是否已上传敏感数据，请在 Windows 命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="87cc8-266">To verify your sensitive data has been uploaded, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="87cc8-267">你将看到数据存储区列表以及上次更新时间。</span><span class="sxs-lookup"><span data-stu-id="87cc8-267">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="87cc8-268">继续设置 [刷新敏感信息数据库](#refreshing-your-sensitive-information-database)的流程和计划。</span><span class="sxs-lookup"><span data-stu-id="87cc8-268">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="87cc8-269">此时，你已准备好将基于 EDM 的分类与 Microsoft 云服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="87cc8-269">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="87cc8-270">例如，你可以 [使用基于 EDM 的分类设置 DLP 策略](#to-create-a-dlp-policy-with-edm)。</span><span class="sxs-lookup"><span data-stu-id="87cc8-270">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="87cc8-271">刷新敏感信息数据库</span><span class="sxs-lookup"><span data-stu-id="87cc8-271">Refreshing your sensitive information database</span></span>

<span data-ttu-id="87cc8-272">你可以每天或每周刷新敏感信息数据库，EDM 上载工具可以重新为敏感数据创建索引，然后重新上载索引数据。</span><span class="sxs-lookup"><span data-stu-id="87cc8-272">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="87cc8-273">确定刷新敏感信息数据库的流程和频率（每天或每周）。</span><span class="sxs-lookup"><span data-stu-id="87cc8-273">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="87cc8-274">将敏感数据重新导出到应用（如 Microsoft Excel），并以 .csv 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="87cc8-274">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="87cc8-275">在按照 [创建索引并上传敏感数据](#index-and-upload-the-sensitive-data)中所述的步骤执行操作时，让所使用的文件名和位置保持不变。</span><span class="sxs-lookup"><span data-stu-id="87cc8-275">Keep the same file name and location you used when you followed the steps described in [Index and upload the sensitive data](#index-and-upload-the-sensitive-data).</span></span>

> [!NOTE]
> <span data-ttu-id="87cc8-276">如果 .csv 文件的结构（字段名称）未发生更改，则刷新数据时无需对数据库架构文件进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="87cc8-276">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="87cc8-277">但是，如果必须进行更改，请确保相应地编辑数据库架和规则包。</span><span class="sxs-lookup"><span data-stu-id="87cc8-277">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="87cc8-278">使用 [任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)自动执行 [创建索引并上载敏感数据](#index-and-upload-the-sensitive-data)流程中的步骤 2 和 3。  </span><span class="sxs-lookup"><span data-stu-id="87cc8-278">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Index and upload the sensitive data](#index-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="87cc8-279">你可以使用多种方法来计划任务：</span><span class="sxs-lookup"><span data-stu-id="87cc8-279">You can schedule tasks using several methods:</span></span>

| <span data-ttu-id="87cc8-280">**方法**</span><span class="sxs-lookup"><span data-stu-id="87cc8-280">**Method**</span></span>             | <span data-ttu-id="87cc8-281">**需执行的操作**</span><span class="sxs-lookup"><span data-stu-id="87cc8-281">**What to do**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="87cc8-282">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87cc8-282">Windows PowerShell</span></span>     | <span data-ttu-id="87cc8-283">请参阅本文中的 [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) 文档和 [示例 PowerShell 脚本](#example-powershell-script-for-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="87cc8-283">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
| <span data-ttu-id="87cc8-284">任务计划程序 API</span><span class="sxs-lookup"><span data-stu-id="87cc8-284">Task Scheduler API</span></span>     | <span data-ttu-id="87cc8-285">请参阅 [任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)文档 </span><span class="sxs-lookup"><span data-stu-id="87cc8-285">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
| <span data-ttu-id="87cc8-286">Windows 用户界面</span><span class="sxs-lookup"><span data-stu-id="87cc8-286">Windows user interface</span></span> | <span data-ttu-id="87cc8-287">在 Windows 中单击“开始”，然后键入 Task Scheduler。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-287">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="87cc8-288">然后，在结果列表中，右键单击“任务计划程序”，然后选择“以管理员身份运行”。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-288">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="87cc8-289">任务计划程序的示例 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="87cc8-289">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="87cc8-290">此部分包含一个示例 PowerShell 脚本，你可以使用该脚本来计划创建数据索引并上传索引数据的任务：</span><span class="sxs-lookup"><span data-stu-id="87cc8-290">This section includes an example PowerShell script you can use to schedule your tasks for indexing data and uploading the indexed data:</span></span>

##### <a name="to-schedule-index-and-upload-in-a-combined-step"></a><span data-ttu-id="87cc8-291">在合并步骤中安排索引和上传</span><span class="sxs-lookup"><span data-stu-id="87cc8-291">To schedule index and upload in a combined step</span></span>

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
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ‘ /HashLocation’ + $hashLocation
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

#### <a name="to-schedule-index-and-upload-as-separate-steps"></a><span data-ttu-id="87cc8-292">将索引和上传安排为单独的步骤</span><span class="sxs-lookup"><span data-stu-id="87cc8-292">To schedule index and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="87cc8-293">第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用</span><span class="sxs-lookup"><span data-stu-id="87cc8-293">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="87cc8-294">Office 365 DLP for Exchange Online（电子邮件）、OneDrive for Business（文件）、Microsoft Teams（对话）和 Microsoft Cloud App Security DLP 策略将支持 EDM 敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="87cc8-294">Office 365 DLP for Exchange Online (email), OneDrive for Business (files), Microsoft Teams (conversations) and Microsoft Cloud App Security DLP policies will support EDM sensitive information types.</span></span>

<span data-ttu-id="87cc8-295">以下方案的 EDM 敏感信息类型目前正在开发中，尚不可用：</span><span class="sxs-lookup"><span data-stu-id="87cc8-295">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="87cc8-296">Office 365 DLP for SharePoint（文件）</span><span class="sxs-lookup"><span data-stu-id="87cc8-296">Office 365 DLP for SharePoint (files)</span></span>
- <span data-ttu-id="87cc8-297">灵敏度标签和保留标签的自动分类</span><span class="sxs-lookup"><span data-stu-id="87cc8-297">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="87cc8-298">使用 EDM 创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="87cc8-298">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="87cc8-299">转到“安全与合规中心”([https://protection.office.com](https://protection.office.com/))。</span><span class="sxs-lookup"><span data-stu-id="87cc8-299">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com/)).</span></span>

2. <span data-ttu-id="87cc8-300">选择“数据丢失防护”\>“策略”。 \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-300">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="87cc8-301">选择“创建策略”\>“自定义”\>“下一步”。 \*\*\*\*  \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-301">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="87cc8-302">在“命名策略”选项卡上，指定名称和说明，然后选择“下一步”。 \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-302">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="87cc8-303">在“选择位置”选项卡上，选择“允许选择特定位置”，然后选择“下一步”。 \*\*\*\*  \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-303">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="87cc8-304">在“状态”列中，选择“Exchange 电子邮件、OneDrive 帐户、团队聊天和频道邮件”，然后选择“下一步”。 \*\*\*\*  \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-304">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span> <span data-ttu-id="87cc8-305">（注意：目前 SharePoint 网站不支持 EDM，并且 DLP 策略不会检测 Sharepoint for EDM 中的文件）</span><span class="sxs-lookup"><span data-stu-id="87cc8-305">(Note: EDM is currently not supported in SharePoint sites and DLP policy will not detect files in Sharepoint for EDM)</span></span>

7. <span data-ttu-id="87cc8-306">在“策略设置”选项卡上，选择“使用高级设置”，然后选择“下一步”。 \*\*\*\*  \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-306">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="87cc8-307">选择“+ 新建规则”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-307">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="87cc8-308">在“名称”部分中，指定规则的名称和说明。 \*\*\*\* </span><span class="sxs-lookup"><span data-stu-id="87cc8-308">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="87cc8-309">在“条件”部分的“+ 添加条件”列表中，选择“内容包含敏感类型”。 \*\*\*\*  \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-309">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span><br/><span data-ttu-id="87cc8-310">![内容包含敏感信息类型](../media/edm-dlp-newrule-conditions.png)</span><span class="sxs-lookup"><span data-stu-id="87cc8-310">![Content contains sensitive info types](../media/edm-dlp-newrule-conditions.png)</span></span><br/>

11. <span data-ttu-id="87cc8-311">搜索你在设置规则包时创建的敏感信息类型，然后选择“+ 添加”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-311">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="87cc8-312">然后选择“完成”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-312">Then choose **Done**.</span></span>

12. <span data-ttu-id="87cc8-313">完成为规则选择相关选项，例如“用户通知”、“用户覆盖”、“事件报告”等，然后选择“保存”。 \*\*\*\* \*\*\*\* \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-313">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="87cc8-314">在“策略设置”选项卡上，查看你的规则，然后选择“下一步”。 \*\*\*\*  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-314">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="87cc8-315">指定是立即打开策略、测试它还是保持关闭。</span><span class="sxs-lookup"><span data-stu-id="87cc8-315">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="87cc8-316">然后选择“下一步” \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87cc8-316">Then choose **Next**.</span></span>

15. <span data-ttu-id="87cc8-317">在“查看你的设置”选项卡上，查看你的策略。 \*\*\*\* </span><span class="sxs-lookup"><span data-stu-id="87cc8-317">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="87cc8-318">执行任何必要的更改。</span><span class="sxs-lookup"><span data-stu-id="87cc8-318">Make any needed changes.</span></span> <span data-ttu-id="87cc8-319">准备好后，选择“创建”。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87cc8-319">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="87cc8-320">新 DLP 策略大约需要一个小时才能通过你的数据中心。</span><span class="sxs-lookup"><span data-stu-id="87cc8-320">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="87cc8-321">相关文章</span><span class="sxs-lookup"><span data-stu-id="87cc8-321">Related articles</span></span>

[<span data-ttu-id="87cc8-322">内置敏感信息类型以及它们查找的内容</span><span class="sxs-lookup"><span data-stu-id="87cc8-322">Built-in sensitive information types and what they look for</span></span>](what-the-sensitive-information-types-look-for.md)

[<span data-ttu-id="87cc8-323">自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="87cc8-323">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)

[<span data-ttu-id="87cc8-324">DLP 策略概述</span><span class="sxs-lookup"><span data-stu-id="87cc8-324">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)

[<span data-ttu-id="87cc8-325">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="87cc8-325">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)

[<span data-ttu-id="87cc8-326">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="87cc8-326">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpedmschema?view=exchange-ps)

## <a name="feedback"></a><span data-ttu-id="87cc8-327">反馈</span><span class="sxs-lookup"><span data-stu-id="87cc8-327">Feedback</span></span>

<span data-ttu-id="87cc8-328">已启用 GitHub 反馈，但是添加问题仅适用于公共网站。</span><span class="sxs-lookup"><span data-stu-id="87cc8-328">GitHub feedback is enabled, but adding issues is only available on the public site.</span></span>
