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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何修改 edm 架构以使用可配置匹配项。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a409b8bad43b6a6ade81c96ae14f691289e11cec
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "60336042"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>修改精确数据匹配架构，以使用可配置匹配项

基于精确数据匹配 (EDM) 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。 当需要允许精确字符串的变体时，可使用 *可配置匹配项* 来告知 Microsoft 365 忽略大小写和某些分隔符。 

> [!IMPORTANT]
> 请使用此过程来修改现有 EDM 架构和数据文件。

1. 从用于连接到 Microsoft 365 的计算机上卸载 **EdmUploadAgent.exe**，以实现 EDM 架构和数据文件上传目的。

2. 使用以下链接为你的订阅下载适当的 **EdmUploadAgent.exe** 文件：
    - [商用 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 商业客户应使用此文件
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 这是专为高安全性政府云订阅者提供的
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 这是专为美国国防部云客户提供的

3. 授权 EDM 上传代理，打开命令提示符窗口（以管理员身份），然后运行以下命令：

   `EdmUploadAgent.exe /Authorize`

4. 如果没有现有架构的当前副本，则需要下载现有架构的副本，然后运行以下命令：

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. 自定义架构，以便每个列都使用“caseInsensitive”和/或“ignoredDelimiters”。  “caseInsensitive”的默认值为“false”，而“ignoredDelimiters”的默认值为空字符串。 

> [!NOTE]
> 用于检测常规正则表达式模式的基础自定义敏感信息类型或内置敏感信息类型必须支持检测用 ignoredDelimiters 列出的变体输入。 例如，内置的美国社会保险号 (SSN) 敏感信息类型可以检测数据中的差异，包括短划线、空格或构成 SSN 的分组数字之间缺少空格。 因此，在 EDM 的 SSN 数据的 ignoredDelimiters 中包含的唯一相关分隔符是：短划线和空格。

下面是一个示例架构，它通过创建识别敏感数据中的大小写变体所需的额外列来模拟不区分大小写的匹配项。

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

在上面的示例中，如果同时添加 `caseInsensitive` 和 `ignoredDelimiters`，则不再需要原始 `PolicyNumber` 列的变体。

若要更新此架构以便 EDM 使用可配置匹配项，请使用 `caseInsensitive` 和 `ignoredDelimiters` 标志。 如下所示：

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

`ignoredDelimiters` 标志支持任何非字母数字字符，以下是一些示例：
- \.
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

`ignoredDelimiters` 标志不支持：
- 字符 0-9
- A-Z
- a-z
- \"
- \,
- |

6. 使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。

> [!NOTE]
> 如果你的组织已在[租户级别（公共预览）设置了 Microsoft 365 的客户密钥](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview)，则精确数据匹配将自动使用其加密功能。这仅适用于商业云中 E5 许可的租户。

7. 通过一次运行以下 cmdlet 中的一个来更新架构：

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. 如有必要，请更新数据文件以匹配新架构版本

> [!TIP]
> 或者，可在上传前对 csv 文件运行验证，方法是运行：
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>有关 EdmUploadAgent.exe 支持的所有参数的详细信息，请运行
>
> `EdmUploadAgent.exe /?`

9. 打开命令提示符窗口（以管理员身份），然后运行以下命令以便为敏感数据创建哈希并上传敏感数据：

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>相关文章

- [使用基于精确数据匹配的分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [自定义敏感信息类型](./sensitive-information-type-learn-about.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)
