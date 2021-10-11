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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用基于精确数据匹配的分类来创建自定义敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98dae682c8837a87d7c757b25111f4985e6e6489
ms.sourcegitcommit: e3b0515fd8f2aad7b8cb308159c7bcecc2bcaa24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2021
ms.locfileid: "60264800"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a>使用基于精确数据匹配的分类创建自定义敏感信息类型

[自定义敏感信息类型](sensitive-information-type-learn-about.md)用于帮助标识敏感项目，以防止它们被意外或不当地共享。 你可以根据以下信息定义一个 (SIT) 类型：

- 模式
- 如 *员工*、*徽章* 或 *ID 等关键字证据*
- 字符近似特定模式的证据
- 可信度

 此类自定义敏感信息类型可满足许多组织的业务需求。

但如果希望自定义敏感信息类型 （SIT） 使用精确数据值，而不是找到基于通用模式的匹配项，又该怎么操作呢？ 通过基于精确数据匹配 (EDM) 的分类，你可以创建专门设计的自定义敏感信息类型：

- 动态且易于刷新。
- 更具可扩展性。
- 导致误报数减少。
- 处理结构化敏感数据。
- 更安全地处理敏感信息。
- 与多种 Microsoft 云服务一起使用。

![基于 EDM 的分类。](../media/EDMClassification.png)

基于 EDM 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。 数据库可以每天刷新一次，最多可包含 1 亿行数据。 因此，当员工、患者或客户往来并且记录发生更改时，你的自定义敏感信息类型仍将保持最新并且适用。 你还可以将基于 EDM 的分类与策略一起使用，例如[数据丢失防护策略](dlp-learn-about-dlp.md)或[Microsoft Cloud App Security 文件策略](/cloud-app-security/data-protection-policies)。

> [!NOTE]
> Microsoft 365 信息保护支持双字节字符集语言，用于:
>
> - 简体中文
> - 繁体中文
> - 韩语
> - 日语
>
> 此支持适用于敏感信息类型。 有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

你必须是全局管理员、合规性管理员或 Exchange Online 管理员才能执行本文中描述的任务。 若要了解有关 DLP 权限的详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

这些订阅中包含基于 EDM 的分类:

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 合规
- Microsoft E5/A5 信息保护和治理

## <a name="portal-links-for-your-subscription"></a>订阅门户链接

|门户|全球/GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Microsoft 365 安全中心|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Microsoft 365 合规中心|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>工作流程概览

|阶段|所需项|
|---|---|
|[第 1 部分：设置基于 EDM 的分类](#part-1-set-up-edm-based-classification)<br/><br/>（根据需要）<br/>- [编辑数据库架构](#editing-the-schema-for-edm-based-classification) <br/>- [删除架构](#removing-the-schema-for-edm-based-classification)|- 敏感数据的读取权限<br/>- XML 格式的数据库架构（提供了示例）<br/>- XML 格式的规则包（提供了示例）<br/>- 安全与合规中心的管理员权限（使用 PowerShell）|
|[第 2 部分：为敏感数据创建哈希并上传](#part-2-hash-and-upload-the-sensitive-data)<br/><br/>（根据需要）<br/>[刷新数据](#refreshing-your-sensitive-information-database)|- 自定义安全组和用户帐户<br/>- 使用 EDM 上载代理对计算机进行本地管理员访问<br/>- 敏感数据的读取权限<br/>- 刷新数据的流程和计划|
|[第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services)|- 具有 DLP 的 Microsoft 365 订阅<br/>- 已启用基于 EDM 的分类功能|

### <a name="part-1-set-up-edm-based-classification"></a>第 1 部分：设置基于 EDM 的分类

设置和配置基于 EDM 的分类包括：

1. [将敏感数据保存为.csv .tsv 格式](#save-sensitive-data-in-csv-or-tsv-format)。
2. [定义敏感信息数据库架构](#define-the-schema-for-your-database-of-sensitive-information)。
3. [创建规则包](#set-up-a-rule-package)。

#### <a name="save-sensitive-data-in-csv-or-tsv-format"></a>以 .tsv .csv保存敏感数据

1. 确定要使用的敏感信息。 将数据导出到应用（如 Microsoft Excel）中，将文件保存在文本文件中。 该文件可以保存在逗号分隔.csv (值中) .tsv (制表符分隔) 值或用管道分隔 (|) 格式。 如果数据值可能包含逗号（如街道地址），则建议使用 .tsv 格式。
数据文件最多可包括以下内容：
   - 高达 1 亿行的敏感数据
   - 每个数据源最多 32 列（字段）
   - 最多 5 个列（字段）标记为可搜索

2. 在数据库或 .tsv .csv构造敏感数据，使第一行包含用于基于 EDM 的分类的字段的名称。 在你的文件中，你可能有字段名称，如"ssn"、"birthdate"、"firstname"、"lastname"。 列标题名称不能包含空格或下划线。 例如，本文中使用的示例 .csv 文件名为 *PatientRecords.csv*，其中包含 *PatientID*、*MRN*、*LastName*、*FirstName* 和 *SSN* 等列。

3. 注意敏感数据字段的格式。 特别是，如果选择了值"Seattle，WA"，则分析内容中可能包含逗号的字段（例如，包含值"Seattle，WA"的街道地址）将分析为两个单独的字段.csv格式。 若要避免这种情况，请使用 .tsv 格式，或在敏感数据表中用双引号将包含值的逗号括起来。 如果逗号包含的值也包含空格，则需要创建与相应格式匹配的自定义 SIT。 例如，用于检测包含逗号和空格的多词字符串的 SIT。

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a>定义敏感信息数据库的架构

如果出于商业或技术原因不希望使用 PowerShell 或命令行创建架构和 EDM 敏感信息类型模式（规则包），可以使用 [精确数据匹配架构和敏感信息类型向导](sit-edm-wizard.md) 来创建。 完成创建架构和 EDM 敏感信息类型模式后，返回以完成所有必要步骤，使基于 EDM 的敏感信息类型处于可用状态。

1. 以 XML 格式定义敏感信息数据库的架构（类似于下面的示例）。 命名此架构文件 **edm.xml** 并对其进行配置，确保对于数据库中的每一列，都有一行使用语法：

      `\<Field name="" searchable=""/\>`.

      - 将列名称用于 *字段名称* 值。
      - 将 *searchable="true"* 用于可搜索的字段，最多 5 个字段。 必须至少有一个字段可搜索。

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

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a>使用 caseInsensitive 和 ignoredDelimiters 字段的可配置匹配项

以上 XML 示例使用了 `caseInsensitive` 和 `ignoredDelimiters` 字段。

当在架构定义中包括 ***caseInsensitive** _ 字段并将其设置为值 `true` 时，EDM 不会根据 `PatientID` 字段的大小写差异排除项目。 因此，EDM 会将 `PatientID` _ *FOO-1234** 和 **fOo-1234** 视为完全相同。

如果包括带支持字符和 ***ignoredDelimiters** _ 字段，EDM 将忽略 `PatientID` 中的这些字符。 因此，EDM 会将 `PatientID` _ *FOO-1234** 和 `PatientID` **FOO#1234** 视为完全相同。 `ignoredDelimiters` 标志支持任何非字母数字字符，以下是一些示例：

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

在此示例中，如果同时使用 `caseInsensitive` 和 `ignoredDelimiters`，EDM 会将 **FOO-1234** 和 **fOo#1234** 视为完全相同，并将项目归类为患者记录敏感信息类型。

1. 连接安全与&中心 PowerShell 中的过程，连接安全与合规& [PowerShell。](/powershell/exchange/connect-to-scc-powershell)

2. 要上传数据库架构，请逐一运行下列 cmdlet：

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
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
> 若想更改但不进行确认，请在步骤 5 中改用此 cmdlet：New-DlpEdmSchema -FileData $edmSchemaXml

> [!NOTE]
> 为 EDMSchema 更新新增内容可能需要10-60 分钟。 更新必须完成，然后才能执行使用这些新增操作的步骤。

#### <a name="set-up-a-rule-package"></a>设置规则包

1. 按 XML 格式创建一个规则包（采用 Unicode 编码），如下例类似。 （可复制、修改和使用我们的示例。）

      设置规则包时，请确保正确引用 .csv 或 .tsv **edm.xml文件。** 可复制、修改和使用我们的示例。 在此示例 xml 中，需要对以下字段进行自定义，以创建 EDM 敏感类型：

      - **RulePack id & ExactMatch id**：使用 [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) 生成 GUID。

      - **数据存储**：此字段指定要使用的 EDM 查找数据存储。 提供已配置的 EDM 架构的数据源名称。

      - **idMatch**：此字段指向 EDM 的主要元素。
        - 匹配：指定要在精确查找中使用的字段。 在数据存储的 EDM 架构中提供可搜索的字段名称。
        - 分类：此字段指定触发 EDM 查找的敏感类型匹配。 可提供现有内建或自定义敏感信息类型的名称或 GUID。 请注意，与所提供敏感信息类型相匹配的任何字符串将进行哈希处理，并与敏感信息表中的每个条目相比较。 为避免导致性能问题，如果将自定义敏感信息类型用作 EDM 中的分类元素，请通过添加辅助关键词或在自定义分类敏感信息类型定义中包含格式的方法，避免使用与较大百分比内容（如“任何数字”或“任何五个字母的单词”）相匹配的类型。

      - **匹配：** 此字段指向邻近 idMatch 找到的其他证据。
        - 匹配：在数据存储的 EDM 架构中提供任何字段名称。
      - **资源：** 此部分在多个区域设置中指定敏感类型的名称和说明。
        - idRef：提供 ExactMatch ID 的 GUID。
        - 名称和说明：按需自定义。

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

2. 通过逐一运行下列 PowerShell cmdlet 来上传规则包：

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

此时，你已设置基于 EDM 的分类。 下一步是为敏感数据创建哈希，然后上传哈希以便编制索引。

回想一下，在前面的过程中我们的 PatientRecords 架构将 5 个文件定义为可搜索的项：*PatientID*、*MRN*、*SSN*、*Phone* 和 *DOB*。 我们的示例规则包中有这些字段并引用数据库架构文件 (**edm.xml**)，其中每个可搜索的字段具有一个 *ExactMatch* 项目。 请考虑以下 ExactMatch 项目：

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

在此示例中，请注意：

- dataStore 名称引用了我们之前创建的 .csv 文件：**dataStore = "PatientRecords"**。

- idMatch 值引用了数据库架构文件中列出的可搜索字段： **idMatch matches = "SSN"**。

- 分类值引用了现有或自定义敏感信息类型：**classification = "U.S. Social Security Number (SSN)"**。 （在此情况下，我们使用美国社会保障号的现有敏感信息类型。）

> [!NOTE]
> 为 EDMSchema 更新新增内容可能需要10-60 分钟。 更新必须完成，然后才能执行使用这些新增操作的步骤。

导入带有 EDM 敏感信息类型的规则包并导入敏感数据表后，可以使用合规中心的 EDM 向导中的 **测试** 功能测试新创建的类型。 有关使用此功能的说明，请参阅[使用精确数据匹配架构和敏感信息类型向导](sit-edm-wizard.md)。

#### <a name="editing-the-schema-for-edm-based-classification"></a>编辑基于 EDM 的分类的架构

如果想要更改 **edm.xml** 文件，例如更改要对基于 EDM 的分类使用的字段，请按照以下步骤操作：

> [!TIP]
> 可更改 EDM 架构和数据文件以利用 **可配置匹配项**。 配置后，EDM 在对某个项目进行求值时将忽略大小写差异和某些分隔符。 这使你能够更轻松地定义 xml 架构和敏感数据文件。 若要了解详细信息，请参阅[修改精确数据匹配架构，以使用可配置匹配项](sit-modify-edm-schema-configurable-match.md)。

1. 编辑 **edm.mxl** 文件（即本文的 [定义架构](#define-the-schema-for-your-database-of-sensitive-information)部分中讨论的文件）。

2. 使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。

3. 要更新数据库架构，请逐一运行下列 cmdlet：

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      系统将提示你进行确认，如下所示：

      > 确认
      >
      > 是否确实要执行此操作？
      >
      > 将更新数据存储“patientrecords”的 EDM 架构。
      >
      > \[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：

      > [!TIP]
      > 若想更改但不进行确认，请在步骤 3 中改用此 cmdlet：Set-DlpEdmSchema -FileData $edmSchemaXml

      > [!NOTE]
      > 为 EDMSchema 更新新增内容可能需要10-60 分钟。 更新必须完成，然后才能执行使用这些新增操作的步骤。

#### <a name="removing-the-schema-for-edm-based-classification"></a>删除基于 EDM 的分类的架构

（根据需要）若想删除正在对基于 EDM 的分类使用的架构，请按照以下步骤操作：

1. 使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。

2. 运行下列 PowerShell cmdlet，用“patient records”的数据存储名称替换要删除的名称：

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      系统将提示你进行确认：

      > 确认
      >
      > 是否确实要执行此操作？
      >
      > 将删除数据存储“patientrecords”的 EDM 架构。
      >
      > \[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：

      > [!TIP]
      >  若想更改但不进行确认，请在步骤 2 中改用此 cmdlet：Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false

### <a name="part-2-hash-and-upload-the-sensitive-data"></a>第 2 部分：为敏感数据创建哈希并上传

在此阶段，你将设置自定义安全组和用户帐户，并设置 EDM 上传代理工具。 然后，使用此工具为敏感数据创建带随机混淆值的哈希并上传。

可使用一台计算机完成哈希创建和上传，也可以将哈希创建步骤与上传步骤分离，以实现更高的安全性。

如果想要在一台计算机上创建哈希并上传，则需要在可直接连接到 Microsoft 365 租户的计算机上执行此操作。 这要求计算机上需要具备明文敏感数据文件以便创建哈希。

如果不希望公开明文敏感数据文件，可在计算机的安全位置上为其创建哈希，然后将哈希文件和随机混淆值文件复制到可直接连接到 Microsoft 365 租户的计算机以进行上传。在这种情况下，两台计算机上都需要 EDMUploadAgent。

> [!IMPORTANT]
> 如果你使用"精确数据匹配"架构和敏感信息类型向导来创建你的架构和模式文件， ***必须*** 此过程的架构。

> [!NOTE]
> 如果你的组织为租户级别的Microsoft 365[](customer-key-overview.md)密钥，精确数据匹配将自动使用其加密功能。 这仅适用于商业云中 E5 许可的租户。

#### <a name="prerequisites"></a>先决条件

- 要添加到 **EDM \_ DataUploaders** Microsoft 365组的工作或学校帐户。
- 一Windows 10 .NET Windows Server 2016 4.6.2 版本的计算机，用于运行 EDMUploadAgent。
- 用于上传的计算机上应含有以下内容的目录：
  - EDMUploadAgent。
  - 您的敏感项目文件.csv .tsv 格式，PatientRecords.csv **示例中所示** 。
  - 输出哈希和 salt 文件。
  - 数据存储区文件中 **edm.xml名称;** 对于此示例，它是 `PatientRecords` 。
- 如果使用了精确 [数据匹配架构和敏感信息类型向导](sit-edm-wizard.md)***，则必须下载*** 它。

#### <a name="set-up-the-security-group-and-user-account"></a>设置安全组和用户帐户

1. 作为全局管理员，使用相应的 [订阅链接](#portal-links-for-your-subscription)转到管理中心并 [创建安全组](/office365/admin/email/create-edit-or-delete-a-security-group)，名为 **EDM\_DataUploaders**。

2. 将一个或多个用户添加到 **EDM\_DataUploaders** 安全组。 （这些用户将管理敏感信息的数据库。）

#### <a name="hash-and-upload-from-one-computer"></a>从一台计算机上创建哈希并上传

此计算机必须对你的 Microsoft 365 租户拥有直接访问权限。

> [!NOTE]
>
> 在开始此过程之前，请确保你是 **EDM\_DataUploaders** 安全组的成员。
>
> （可选）您可以通过运行：在.csv对文件或 .tsv 文件运行验证：
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> 有关 EdmUploadAgent.exe 支持的所有参数的详细信息，请运行
>
> `EdmUploadAgent.exe /?`

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a>按订阅类型链接到 EDM 上传代理

- [商用 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 商业客户应使用此文件
- [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 这是专为高安全性政府云订阅者提供的
- [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 这是专为美国国防部云客户提供的

1. 创建 EDMUploadAgent 要使用的工作目录。 例如，**C:\EDM\Data**。 将 **PatientRecords .csv** 文件放入该目录中。

2. 下载并将适合你的订阅的 [EDM 上传代理](#links-to-edm-upload-agent-by-subscription-type)安装到步骤 1 创建的目录中。

   > [!NOTE]
   > 上述链接中的 EDMUploadAgent 已更新，可自动将随机混淆值添加到哈希数据。 或者，你可以提供自己的随机混淆值。 使用此版本后，你将不能使用 EDMUploadAgent 的先前版本。
   >
   > 每天只能使用 EDMUploadAgent 上传数据到任何给定的数据存储空间两次。

   > [!TIP]
   > 要获取受支持命令参数的列表，请运行无代理参数。例如“EdmUploadAgent.exe”。

3. 授权 “EDM 上传代理”，打开命令提示符窗口（以管理员身份），切换到 **C:\EDM\Data** 目录，然后运行以下命令：

   `EdmUploadAgent.exe /Authorize`

4. 使用添加到 EDM_DataUploaders 安全组的 Microsoft 365 工作或学校帐户登录。 将从用户帐户提取你的租户信息以建立连接。

   可选：如使用精确数据匹配架构和敏感信息类型向导创建架构和模式文件，请在命令提示符窗口中运行以下命令：

   ```console
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. 若要为敏感数据创建哈希并上传，请在命令提示符窗口中运行以下命令：

   ```console
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"] /AllowedBadLinesPercentage [value]
   ```

   示例 **：EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C：\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5**

   敏感数据文件的默认格式是逗号分隔的值。 可以通过使用 /ColumnSeparator 参数指示"{Tab}"选项来指定以制表符分隔的文件，或者通过指示"|"选项来指定管道分隔的文件。
   如果您的敏感信息表包含一些格式不正确的值，但您希望在忽略无效行的同时导入剩余数据，可以在命令中使用 **/AllowedBadLinesPercentage** 参数。 上面的示例指定 5% 阈值。 这意味着，即使多达 5% 的行无效，该工具也将哈希并上载敏感信息表。 在支持此参数的工具版本中，默认阈值为 0%。 因此，任何错误行都将导致错误。 
   此命令将自动将随机生成的 salt 值添加到哈希中，以增强安全性。 或者，如果你想要使用自己的随机混淆值，请将 **/Salt <saltvalue>** 值添加到命令中。 该值的长度必须为 64 个字符，并且只能包含 a-z 的字符和 0-9 的数字。

6. 运行以下命令，检查“上传”状态：

   ```console
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   示例：**EdmUploadAgent/GetSession/DataStoreName PatientRecords**

   在 **ProcessingInProgress** 中查找状态。 每隔几分钟再次检查，直到状态更改为“**已完成**”。 在状态为已完成后，即可使用 EDM 数据。

#### <a name="separate-hash-and-upload"></a>将哈希与上传分开操作

在处于安全环境中的计算机上执行哈希。

可选：如使用精确数据匹配架构和敏感信息类型向导创建架构和模式文件，请在命令提示符窗口中运行以下命令：

```console
EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
````

1. 在命令提示符窗口中运行以下命令：

   ```console
   EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /AllowedBadLinesPercentage [value]
   ```

   例如：

   ```console
   EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5
   ```

   如果没有指定“**/Salt \<saltvalue\>**”选项，这将会输出具有以下扩展名的哈希文件和随机混淆值文件：

   - .EdmHash
   - .EdmSalt

2. 以安全的方式将这些文件复制到计算机，以将敏感项目.csv或 .tsv 文件 (PatientRecords) 租户。

   若要上传哈希数据，请在 Windows 命令提示符中运行以下命令：

   ```console
   EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>
   ```

   例如：

   ```console
   EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**
   ```

   若要验证是否已上传敏感数据，请在“命令提示符”窗口中运行以下命令：

   ```console
   EdmUploadAgent.exe /GetDataStore
   ```

   你将看到数据存储区列表以及上次更新时间。

   如果要查看所有数据上载到特定存储的信息，请在 Windows 命令提示符下运行以下命令：

   ```console
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```

   继续设置[刷新敏感信息数据库](#refreshing-your-sensitive-information-database)的流程和计划。

此时，你已准备好将基于 EDM 的分类与 Microsoft 云服务一起使用。 例如，你可以[使用基于 EDM 的分类设置 DLP 策略](#to-create-a-dlp-policy-with-edm)。

#### <a name="refreshing-your-sensitive-information-database"></a>刷新敏感信息数据库

可以每天刷新敏感信息数据库，EDM 上传工具会重新为敏感数据创建索引，然后重新上传索引数据。

1. 确定刷新敏感信息数据库的流程和频率（每天或每周）。

2. 将敏感数据重新导出到应用程序（如 Microsoft Excel）并保存为 .csv .tsv 格式的文件。 在按照[为敏感数据创建哈希并上传](#part-2-hash-and-upload-the-sensitive-data)中所述的步骤执行操作时，让所使用的文件名和位置保持不变。

    > [!NOTE]
    > 如果 (或 .tsv 文件的结构 (字段名) .csv，则刷新数据时无需对数据库架构文件进行任何更改。 但是，如果必须进行更改，请确保相应地编辑数据库架和规则包。

3. 使用[任务计划程序](/windows/desktop/TaskSchd/task-scheduler-start-page)自动执行[创建哈希并上载敏感数据](#part-2-hash-and-upload-the-sensitive-data)流程中的步骤 2 和 3。 你可以使用多种方法来计划任务：

   |方法|需执行的操作|
   |---|---|
   |Windows PowerShell|请参阅本文中的[计划任务](/powershell/module/scheduledtasks/)文档和[示例 PowerShell 脚本](#example-powershell-script-for-task-scheduler)|
   |任务计划程序 API|请参阅[任务计划程序](/windows/desktop/TaskSchd/using-the-task-scheduler)文档|
   |Windows 用户界面|在 Windows 中单击“**开始**”，然后键入 Task Scheduler。 然后，在结果列表中，右键单击“**任务计划程序**”，然后选择“**以管理员身份运行**”。|

#### <a name="example-powershell-script-for-task-scheduler"></a>任务计划程序的示例 PowerShell 脚本

此部分包含一个示例 PowerShell 脚本，你可以使用该脚本来计划为数据创建哈希并上传哈希数据的任务：

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a>在合并步骤中计划哈希和上传

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a>将计划哈希和上传作为单独的步骤

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a>第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用

这些位置支持 EDM 敏感信息类型：

- 针对 Exchange Online 的 DLP（电子邮件）
- OneDrive for Business（文件）
- Microsoft Teams（对话）
- 针对 SharePoint 的 DLP（文件）
- Microsoft Cloud App Security DLP 策略
- 服务器端自动标记策略 - 适用于商业云客户和政府云客户
- 客户端自动标记策略 - 适用于政府云客户  

#### <a name="to-create-a-dlp-policy-with-edm"></a>使用 EDM 创建 DLP 策略

1. 使用相应的[订阅链接](#portal-links-for-your-subscription)转到安全与合规中心。

2. 选择 **数据丢失防护** \> **策略**。

3. 选择 **创建策略** \> **自定义** \> "**下一步**"。

4. 在“**命名策略**”选项卡上，指定名称和说明，然后选择“**下一步**”。

5. 在“**选择位置**”选项卡上，选择“**允许选择特定位置**”，然后选择“**下一步**”。

6. 在“**状态**”列中，选择“**Exchange 电子邮件、OneDrive 帐户、团队聊天和频道邮件**”，然后选择“**下一步**”。

7. 在“**策略设置**”选项卡上，选择“**使用高级设置**”，然后选择“**下一步**”。

8. 选择“**+ 新建规则**”。

9. 在“**名称**”部分中，指定规则的名称和说明。

10. 在“**条件**”部分的“**+ 添加条件**”列表中，选择“**内容包含敏感类型**”。

    ![内容包含敏感信息类型。](../media/edm-dlp-newrule-conditions.png)

11. 搜索你在设置规则包时创建的敏感信息类型，然后选择“**+ 添加**”。
    然后选择“**完成**”。

12. 完成为规则选择相关选项，例如“**用户通知**”、“**用户覆盖**”、“**事件报告**”等，然后选择“**保存**”。

13. 在“**策略设置**”选项卡上，查看你的规则，然后选择“**下一步**”。

14. 指定是立即打开策略、测试它还是保持关闭。 然后选择“**下一步**”。

15. 在“**查看你的设置**”选项卡上，查看你的策略。 执行任何必要的更改。 准备好后，选择“**创建**”。

> [!NOTE]
> 新 DLP 策略大约需要一个小时才能通过你的数据中心。

## <a name="related-articles"></a>相关文章

- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [了解敏感信息类型](sensitive-information-type-learn-about.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)
- [修改精确数据匹配架构，以使用可配置匹配项](sit-modify-edm-schema-configurable-match.md)
