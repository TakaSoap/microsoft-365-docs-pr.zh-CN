---
title: 修改精确数据匹配架构，以使用可配置匹配项
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
description: 了解如何修改 edm 架构以使用可配置匹配项。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dea641072983163c6fbbcc5888d5ee6ea91f6990
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408311"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="c173f-103">修改精确数据匹配架构，以使用可配置匹配项</span><span class="sxs-lookup"><span data-stu-id="c173f-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="c173f-104">基于精确数据匹配 (EDM) 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。</span><span class="sxs-lookup"><span data-stu-id="c173f-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="c173f-105">当需要允许精确字符串的变体时，可使用 *可配置匹配项* 来告知 Microsoft 365 忽略大小写和某些分隔符。</span><span class="sxs-lookup"><span data-stu-id="c173f-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c173f-106">请使用此过程来修改现有 EDM 架构和数据文件。</span><span class="sxs-lookup"><span data-stu-id="c173f-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="c173f-107">从用于连接到 Microsoft 365 的计算机上卸载 **EdmUploadAgent.exe**，以实现 EDM 架构和数据文件上传目的。</span><span class="sxs-lookup"><span data-stu-id="c173f-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="c173f-108">使用以下链接为你的订阅下载适当的 **EdmUploadAgent.exe** 文件：</span><span class="sxs-lookup"><span data-stu-id="c173f-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="c173f-109">[商用 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 商业客户应使用此文件</span><span class="sxs-lookup"><span data-stu-id="c173f-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="c173f-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 这是专为高安全性政府云订阅者提供的</span><span class="sxs-lookup"><span data-stu-id="c173f-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="c173f-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 这是专为美国国防部云客户提供的</span><span class="sxs-lookup"><span data-stu-id="c173f-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="c173f-112">授权 EDM 上传代理，打开命令提示符窗口（以管理员身份），然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c173f-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="c173f-113">如果没有现有架构的当前副本，则需要下载现有架构的副本，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c173f-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="c173f-114">自定义架构，以便每个列都使用“caseInsensitive”和/或“ignoredDelimiters”。</span><span class="sxs-lookup"><span data-stu-id="c173f-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="c173f-115">“caseInsensitive”的默认值为“false”，而“ignoredDelimiters”的默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="c173f-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="c173f-116">用于检测常规正则表达式模式的基础自定义敏感信息类型或内置敏感信息类型必须支持检测用 ignoredDelimiters 列出的变体输入。</span><span class="sxs-lookup"><span data-stu-id="c173f-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="c173f-117">例如，内置的美国社会保险号 (SSN) 敏感信息类型可以检测数据中的差异，包括短划线、空格或构成 SSN 的分组数字之间缺少空格。</span><span class="sxs-lookup"><span data-stu-id="c173f-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="c173f-118">因此，在 EDM 的 SSN 数据的 ignoredDelimiters 中包含的唯一相关分隔符是：短划线和空格。</span><span class="sxs-lookup"><span data-stu-id="c173f-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="c173f-119">下面是一个示例架构，它通过创建识别敏感数据中的大小写变体所需的额外列来模拟不区分大小写的匹配项。</span><span class="sxs-lookup"><span data-stu-id="c173f-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="c173f-120">在上面的示例中，如果同时添加 `caseInsensitive` 和 `ignoredDelimiters`，则不再需要原始 `PolicyNumber` 列的变体。</span><span class="sxs-lookup"><span data-stu-id="c173f-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="c173f-121">若要更新此架构以便 EDM 使用可配置匹配项，请使用 `caseInsensitive` 和 `ignoredDelimiters` 标志。</span><span class="sxs-lookup"><span data-stu-id="c173f-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="c173f-122">其外观如下：</span><span class="sxs-lookup"><span data-stu-id="c173f-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="c173f-123">`ignoredDelimiters` 标志支持任何非字母数字字符，以下是一些示例：</span><span class="sxs-lookup"><span data-stu-id="c173f-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="c173f-124">\.</span><span class="sxs-lookup"><span data-stu-id="c173f-124">\.</span></span>
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

<span data-ttu-id="c173f-125">`ignoredDelimiters` 标志不支持：</span><span class="sxs-lookup"><span data-stu-id="c173f-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="c173f-126">字符 0-9</span><span class="sxs-lookup"><span data-stu-id="c173f-126">characters 0-9</span></span>
- <span data-ttu-id="c173f-127">A-Z</span><span class="sxs-lookup"><span data-stu-id="c173f-127">A-Z</span></span>
- <span data-ttu-id="c173f-128">a-z</span><span class="sxs-lookup"><span data-stu-id="c173f-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="c173f-129">使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="c173f-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="c173f-130">如果您的组织已在[租户级别（公共预览）设置了Microsoft 365的客户密钥](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview)，则精确数据匹配将自动使用其加密功能。</span><span class="sxs-lookup"><span data-stu-id="c173f-130">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="c173f-131">这仅适用于商业云中 E5 许可的租户。</span><span class="sxs-lookup"><span data-stu-id="c173f-131">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

7. <span data-ttu-id="c173f-132">通过一次运行以下 cmdlet 中的一个来更新架构：</span><span class="sxs-lookup"><span data-stu-id="c173f-132">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="c173f-133">如有必要，请更新数据文件以匹配新架构版本</span><span class="sxs-lookup"><span data-stu-id="c173f-133">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="c173f-134">或者，可在上传前对 csv 文件运行验证，方法是运行：</span><span class="sxs-lookup"><span data-stu-id="c173f-134">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="c173f-135">有关 EdmUploadAgent.exe 支持的所有参数的详细信息，请运行</span><span class="sxs-lookup"><span data-stu-id="c173f-135">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="c173f-136">打开命令提示符窗口（以管理员身份），然后运行以下命令以便为敏感数据创建哈希并上传敏感数据：</span><span class="sxs-lookup"><span data-stu-id="c173f-136">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="c173f-137">相关文章</span><span class="sxs-lookup"><span data-stu-id="c173f-137">Related articles</span></span>

- [<span data-ttu-id="c173f-138">使用基于精确数据匹配的分类创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="c173f-138">Create a custom sensitive information type with Exact Data Match based classification</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="c173f-139">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="c173f-139">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="c173f-140">自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="c173f-140">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="c173f-141">DLP 策略概述</span><span class="sxs-lookup"><span data-stu-id="c173f-141">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="c173f-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c173f-142">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="c173f-143">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="c173f-143">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)