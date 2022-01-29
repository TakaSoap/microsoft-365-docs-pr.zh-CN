---
title: 为基于精确数据匹配的敏感信息类型创建架构
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 为基于精确数据匹配的敏感信息类型创建架构
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0d10d399d0e1d9930a6132f802fb1482ad2f18c6
ms.sourcegitcommit: 99067d5eb1fa7b094e7cdb1f7be65acaaa235a54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2022
ms.locfileid: "62272038"
---
# <a name="create-the-schema-for-exact-data-match-based-sensitive-information-types"></a>为基于精确数据匹配的敏感信息类型创建架构

可以使用"使用确切的数据匹配架构和敏感信息类型模式"向导[](#use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard)或[手动](#create-exact-data-match-schema-manually-and-upload)创建架构和 EDM SIT。 您还可以使用一种方法创建架构，然后使用另一种方法编辑架构，以组合这两种方法。

如果不熟悉基于 EDM 的 SITS 及其实现，应熟悉：

- [了解敏感信息类型](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [基于精确数据匹配的敏感信息类型入门](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

单个 EDM 架构可用于使用同一敏感数据表的多个敏感信息类型。 您可以在一个租户内创建最多 10 个不同的 EDM Microsoft 365架构。

## <a name="working-with-specific-types-of-data"></a>使用特定类型的数据

出于性能原因，使用模式将不必要的匹配数降至最低至关重要。 例如，您可以基于正则表达式使用敏感信息类型。

`\b\w*\b`

这将匹配任何文档或电子邮件中每个单词或数字。 这可能会导致服务过载并出现匹配，并错过检测 true 匹配项的情况。 使用更精确的模式可以避免这种情况。 下面是一些建议，用于标识某些常见数据类型的合适配置。

**电子邮件地址**：电子邮件地址易于识别，但由于它们在内容中很常见，因此，如果用作主字段，则可能会导致系统出现大量负载。 仅将它们用作辅助证据。 `From` `To`如果它们必须用作主要证据，请尝试定义一个自定义敏感信息类型，该类型使用逻辑来排除它们在电子邮件中的使用方式或字段，并排除那些包含公司电子邮件地址的字符串，以减少需要匹配的不必要字符串的数量。

**电话：** 电话号码可能采用许多不同的格式，包括或排除国家/地区前缀、区号和分隔符。 若要减少漏报，同时将负载保持为最小值，请仅将它们用作辅助元素，排除所有可能的分隔符（如括号和短划线）并仅将始终存在于电话号码中的部件包括在敏感数据表中。

人员 **姓名：如果使用** 基于正则表达式的敏感信息类型作为此 EDM 类型的分类元素，则不要将人名用作主要元素，因为它们很难与常用词区分。

如果必须使用难以通过特定模式标识的主要元素（如可能生成大量要处理的匹配项的项目代码名称），请确保在用作 EDM 类型的分类元素的敏感信息类型中包括关键字。 `project`例如，如果使用可能是常规字词的项目代码名称，可以在用作 EDM 类型的分类元素的敏感类型中，将字词用作所需附加证据，与基于项目名称正则表达式的模式非常接近。 或者，你可以考虑使用基于常规字典的敏感类型作为 EDM SIT 的分类元素。

尝试匹配数字字符串时，指定允许的数字范围，如位数或起始数字（如果已知）。 如果需要匹配相对灵活的号码范围，可以使用基本 SIT 中的关键字减少匹配次数。 例如，如果尝试匹配由 7-11 `account`个数字组成的帐户编号，则向 SIT 添加字词 ， `customer``acct.` 作为所需的其他证据。 这将减少不必要的匹配的可能性，这些匹配可能会导致超出 EDM 处理的匹配项的限制。

如果需要用作主要元素的字段遵循可能导致大量匹配的简单模式，并且无法将关键字的存在添加为敏感信息类型中的附加证据，则也可以要求至少需要该模式出现次数。 例如，您可以使用以下方式定义的自定义敏感信息类型来检测与 EDM 匹配的潜在五位数周围的至少 29 个其他 5 位数字：

```xml
 <Entity id="98703510-18b3-43d4-961f-15317594beb7"
                  patternsProximity="300"
                  recommendedConfidence="85"
                  relaxProximity="false">
                  <Pattern confidenceLevel="85"
                              proximity="300">
                              <IdMatch idRef="MRN"/>
                              <Match idRef="30 AccountNrs"
                                    minCount="30"
                                    proximity="3000"
                                    uniqueResults="true"/>
                  </Pattern>
      </Entity>
      <Regex id="30 AccountNrs">\d{5}</Regex>
```

在某些情况下，您可能必须确定某些帐户或记录标识号，这些标识号由于历史原因不遵循标准化模式。 例如， `Medical Record Numbers` 可以由同一组织中许多不同字母和数字排列组成。 尽管一开始可能很难识别模式，但更仔细的检查通常允许您缩小描述所有有效值的模式，而不会导致过多无效匹配。 例如，可能会检测到"所有 MRN 长度至少为 7 个字符，其中至少包含两个数字，并且如果其中有任何字母，则以 1 开头"。 基于此类条件创建正则表达式应允许您在捕获所有所需值时最大程度地减少不必要的匹配，进一步分析可能通过定义描述不同格式的单独模式来增加精确度。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>使用精确数据匹配架构和敏感信息类型向导

可以使用此向导帮助简化架构文件创建过程。

## <a name="pre-requisites"></a>先决条件

- 执行导出源 [数据中的步骤，了解基于准确数据匹配的敏感信息类型](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>使用精确数据匹配架构和敏感信息类型模式向导

1. In the Microsoft 365 Compliance center for your tenant go to **Data classificationExact** >  **data matchesEDM** >  **schemas**.

2. 选择 **创建 EDM 架构** 打开架构向导配置弹出菜单t。

   ![EDM 架构创建向导配置飞出控件。](../media/edm-schema-wizard-1.png)

3. 填入相应的 **名称** 和 **说明**。

4. 如果需要 **整个架构的行为** ，请选择"忽略所有架构字段的分隔符和标点符号"。 若要了解有关将 EDM 配置为忽略大小写或分隔符的详细信息，请参阅使用 [caseInsensitive 和 ignoredDelimiters](#using-the-caseinsensitive-and-ignoreddelimiters-fields) 字段了解有关此功能的更多详细信息。

5. 在 **架构字段 #1** 中填入所需值，并按需要添加新字段。 每个架构字段都必须与敏感信息源文件中的列标题相同。

6. 如果需要，请为以下字段设置每个字段值：
    1. **字段可搜索**
    1. **字段不区分大小写**
    1. **为此字段选择要忽略的分隔符和标点**
    1. **输入此字段的自定义分隔符和标点符号**

   > [!IMPORTANT]
   > 必须指定至少 1 个，但不超过 5 个架构字段为可搜索字段。

7. 选择“**保存**”。 现在将列出您的架构，并且该架构可供使用。

   > [!IMPORTANT]
   > 若要删除已经关联某一 EDM 敏感信息类型的架构，必须先删除此 EDM 敏感信息类型，然后才能删除架构。 删除具有与其关联的数据存储的架构也会在 24 小时内删除数据存储。

## <a name="export-of-the-edm-schema-file-in-xml-format"></a>以 XML 格式导出 EDM 架构文件

如果在 EDM 架构向导中创建 EDM 架构，则必须以 XML 格式导出 EDM 架构文件。 你将在哈希中需要它，并上传敏感信息源 [表，以完全匹配敏感信息类型](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) 阶段。

1. [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

2. 若要导出 EDM 架构文件，请使用以下语法：

   ```powershell
   $Schema = Get-DlpEdmSchema -Identity "[your EDM Schema name]"
   Set-Content -Path ".\Schemafile.xml" -Value $Schema.EdmSchemaXML
   ```

3. 保存此文件供以后使用。

## <a name="create-exact-data-match-schema-manually-and-upload"></a>手动创建精确数据匹配架构并上载

在架构文件中，使用语法为敏感信息源表中的每一列配置一个条目：

```xml
<Field name="FieldName" searchable="true/false" caseInsensitive="true/false" ignoredDelimiters="delimiter characters" />
```

### <a name="using-the-caseinsensitive-and-ignoreddelimiters-fields"></a>使用 caseInsensitive 和 ignoredDelimiters 字段

下面的架构 XML 示例使用 *caseInsensitive* 和 *ignoredDelimiters* 字段。

当您在架构定义中包括设置为 的值的 *caseInsensitive* `true` 字段时，EDM 不会根据大小写差异排除项目。 例如，EDM 将看到 **字段的 FOO-1234** 和 **fOo-1234** `PatientID` 值相同。

当您将 *ignoredDelimiters* 字段包含支持的字符时，EDM 将忽略这些字符。 因此，EDM 将看到字段的 **FOO-1234** 和 **FOO#1234** `PatienID` 值相同。

在同时使用 和 的示例中，EDM 将 **看到 FOO-1234** 和 **fOo#1234** 相同，并且将项目分类为患者记录敏感信息类型。`caseInsensitive` `ignoredDelimiters`

这两个参数都基于每个字段使用。

> [!IMPORTANT]
> 如果将空格 *配置为* 忽略，则仅对主字段列和定义可检测多词字符串的敏感信息类型有效。 否则，将对照所分析的内容中的每个单词进行比较。

*ignoredDelimiters* 标志支持任何非字母数字字符，下面是一些示例：

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

> [!IMPORTANT]
> 定义 EDM 敏感信息类型时， *ignoreDelimiters* 不会影响与 EDM 模式中的主元素关联的 Classification 敏感信息类型如何标识项中的内容。 因此，如果为可搜索字段配置 *ignoreDelimiters* ，则需要确保用于基于该字段的主元素的敏感信息类型将选取包含和不带这些字符的字符串。
>
> 敏感信息源表中的列数和架构中的字段数必须匹配，顺序无关紧要。

1. 使用 XML 格式定义架构 (类似于下面示例) 。 将此架构文件 **edm.xml**，并对其进行配置，使对于敏感信息源表中的每一列，都有一个使用语法的行：

      `\<Field name="" searchable=""/\>`.

      - 将列名称用于 *字段名称* 值。
      - 对要搜索的字段使用 *searchable="true"* ，对主要字段最多使用 5 个字段。 必须至少有一个字段可搜索。

      例如，以下 XML 文件定义患者记录数据库的架构，其中五个字段指定为可搜索字段：*患者 ID*、*MRN*、*SSN*、*电话* 和 *DOB*。

      （可复制、修改和使用我们的示例。）

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

   创建 XML 格式的 EDM 架构文件后，必须将其上载到云服务。

2. [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

3. 若要上载数据库架构，请运行以下命令：

      ```powershell
      New-DlpEdmSchema -FileData ([System.IO.File]::ReadAllBytes('.\\edm.xml')) -Confirm:$true
      ```

      系统将提示你进行确认，如下所示：

      > 确认
      >
      > 是否确实要执行此操作？
      >
      > 将导入数据存储“patientrecords”的新 EDM 架构。
      >
      > \[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：

   > [!TIP]
   > 如果希望更改在未确认的情况下发生，请不要 `-Confirm:$true` 在步骤 3 中使用。

> [!NOTE]
> 为 EDMSchema 更新新增内容可能需要10-60 分钟。 更新必须完成，然后才能执行使用这些新增操作的步骤。

## <a name="next-step"></a>后续步骤

- [为基于精确数据匹配的敏感信息类型哈希并上传敏感信息源表](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)