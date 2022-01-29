---
title: 创建基于精确数据匹配的敏感信息类型/规则包
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
description: 创建基于精确数据匹配的敏感信息类型/规则包
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b28669a2791685d172889bf6486b89b9d971e36
ms.sourcegitcommit: 99067d5eb1fa7b094e7cdb1f7be65acaaa235a54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2022
ms.locfileid: "62271918"
---
# <a name="create-exact-data-match-sensitive-information-typerule-package"></a>创建基于精确数据匹配的敏感信息类型/规则包

可以使用合规性中心中的 [EDM](#use-the-edm-schema-and-sit-wizard) 架构和 SIT 向导创建精确数据匹配 (EDM) 敏感信息类型 (SIT) 或手动创建规则包 XML [文件](#create-a-rule-package-manually)。 您还可以使用一种方法创建架构，然后使用另一种方法编辑架构，以组合这两种方法。

如果你不熟悉基于 EDM 的 SITS 或他们的实现，你应该熟悉：

- [了解敏感信息类型](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [基于精确数据匹配的敏感信息类型入门](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

## <a name="use-the-edm-schema-and-sit-wizard"></a>使用 EDM 架构和 SIT 向导

可以使用此向导在 SIT 文件 (敏感信息类型) 以帮助简化此过程。

EDM 敏感信息类型由一个或多个模式组成。 每个模式都描述一组证据 (架构中的字段) ，这些字段将用于标识文档或电子邮件中的敏感内容。

## <a name="pre-requisites"></a>先决条件

执行以下文章中的步骤：

1. [为基于精确数据匹配的敏感信息类型导出源数据](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
2. [为基于精确数据匹配的敏感信息类型创建架构](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)
3. [为基于精确数据匹配的敏感信息类型哈希并上传敏感信息源表](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)

- 无论是使用向导创建 EDM 敏感信息类型，还是通过 PowerShell 创建规则包 XML 文件，都必须具有全局管理员或合规性管理员权限，才能通过 UI 创建、测试和部署自定义敏感信息类型。 请参阅[关于管理员角色Office 365](/office365/admin/add-users/about-admin-roles)。
- 确定要用作主要元素敏感信息类型的内置 TS 之一。
  - 如果任何内置敏感信息类型与所选列中的数据都不匹配，则你必须创建一个自定义的敏感信息类型。
  - 如果你为架构中的主元素列选择了"忽略的分隔符"选项，请确保你创建的自定义 SIT 将匹配带和不带选定分隔符的数据。
  - 如果使用内置的 SIT，请确保它将准确检测要选择的字符串，并且不包括任何周围字符或排除存储在敏感信息表中的字符串的任何有效部分。

请参阅 [敏感信息类型实体定义](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) 和 [自定义敏感信息类型入门](create-a-custom-sensitive-information-type.md#get-started-with-custom-sensitive-information-types)。

### <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>使用精确数据匹配架构和敏感信息类型模式向导

1. 在 Microsoft 365 合规中心为租户转到 **数据分类** > **精确数据匹配**。

2. 选择 **EDM 敏感信息类型** 和 **创建 EDM 敏感信息类型** 以打开敏感信息类型配置向导。

3. Choose **Choose an existing EDM schema** and choose the schema you created in [Create the schema for exact data match based sensitive information types](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types).

4. 选择 **下一步**，然后选择 **创建模式**。

5. 选择 **可信度** 和 **主元素**。 若要了解有关可信度详细信息，请参阅 [了解敏感信息类型](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)。

6. 选择要 **与 Primary 元素** 关联的敏感信息类型，以定义将文档中的文本与主元素字段中的所有值进行比较。 若要了解可用敏感信息类型的详细信息，请参阅[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)。

   > [!IMPORTANT]
   > 选择与要查找的内容的格式紧密匹配的敏感信息类型。 选择与不必要的内容匹配的敏感信息类型（如匹配所有文本字符串的敏感信息类型）或所有数字都可能导致系统负载过大，这可能会导致敏感信息丢失。 有关选择要在此处使用的敏感信息类型的建议，请参阅本文档中精确数据匹配简介文章中的最佳实践部分。

7. 选择支持 **元素和** 匹配选项。

8. 选择 **"完成"** 和"下一 **步"**。

9. 选择所需的 **可信度和字符邻近度**。 这将是整个 EDM 敏感信息类型的默认值。

10. 如果要 **为** EDM 敏感信息类型创建其他模式，请选择"创建模式"。

11. 选择 **下一步** 并填写 **名称** 和 **面向管理员的说明**。

12. 查看并选择 **提交**。

### <a name="edit-or-delete-the-sensitive-information-type-pattern"></a>编辑或删除敏感信息类型模式

1. Open **Compliance centerData** >  **classificationExact** >  **数据匹配**。

2. 选择 **"EDM 敏感信息类型"**。

3. 选择要编辑的 EDM SIT。

4. 从 **飞出控件选择"编辑 EDM** 敏感信息类型"或"删除 **EDM** 敏感信息类型"。

## <a name="create-a-rule-package-manually"></a>手动创建规则包

此过程演示如何使用 Unicode 编码)  (创建名为规则包 (的 XML 格式的文件，然后使用合规性中心 PowerShell cmdlet 将其上载到 Microsoft 365 中。

> [!NOTE]
> 如果你映射到的 SIT 可以检测多词确证性证据，则你在手动创建的规则包中定义的辅助元素可以映射到 SIT。 `John Smith` `John Smith` `Smith` `John`例如，如果确定证据字段未映射到可检测到该模式的 SIT，那么该名称将不会作为辅助元素匹配，因为我们会将内容中的内容与其中一个字段上载的术语分开比较和发现。
>
> 一个租户中限制为 10 个规则Microsoft 365包。 由于规则包可以包含任意数量的敏感信息类型，因此，您可以避免每次想要使用此方法定义新的敏感信息类型时创建新规则包，而应导出现有规则包，在重新上载之前将敏感信息类型添加到 XML 中。

1. 按 XML 格式创建一个规则包（采用 Unicode 编码），如下例类似。 （可复制、修改和使用我们的示例。）

   在设置规则包时，请确保正确引用您的.csv、.tsv 或管道 (|) 分隔的敏感信息源表 **文件和edm.xml架构** 文件。 可复制、修改和使用我们的示例。 在此示例 xml 中，需要自定义以下字段以创建 EDM 敏感类型：

   - **RulePack id & ExactMatch id**：使用 [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) 生成 GUID。

   - **数据存储**：此字段指定要使用的 EDM 查找数据存储。 提供配置的 EDM 架构的数据源名称。

   - **idMatch**：此字段指向 EDM 的主要元素。
   - **匹配**：指定要用于精确查找的字段。 在数据存储的 EDM 架构中提供可搜索的字段名称。
   - **分类**：此字段指定触发 EDM 查找的敏感信息类型匹配。 可以使用现有内置或自定义敏感信息类型的名称或 GUID。

   > [!NOTE]
   > 请注意，与提供的 SIT 匹配的任何字符串都将进行哈希处理，并与敏感信息源表中的每个条目进行比较。 若要避免性能问题（如果选择分类元素的自定义 SIT，请勿使用与大部分内容匹配的自定义 SIT）。 例如，一个匹配"任意数字"或"任何五个字母的单词"。 您可以通过添加支持关键字或在自定义分类 SIT 的定义中添加格式来区分它。

   - **Match**：此字段指向在 idMatch 邻近感应中发现的其他证据。
   - **匹配：** 在 EDM Schema 中为 DataStore 提供任何字段名称。
   - **Resource idRef：** 此部分指定多个区域设置中敏感类型的名称和说明
     - 为 ExactMatch ID 提供 GUID。
     - **名称** & **description**：根据需要自定义。

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

2. Upload运行以下 PowerShell 命令来更新规则包：

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('.\\rulepack.xml'))
   ```

> [!NOTE]
> 规则包文件的语法与其他敏感信息类型的语法相同。 有关规则包文件的语法和其他配置选项的完整详细信息，以及有关使用 PowerShell 修改和删除敏感信息类型的说明，请参阅 [使用 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md#create-a-custom-sensitive-information-type-using-powershell)。

## <a name="next-step"></a>后续步骤

- [测试基于精确数据匹配的敏感信息类型](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)
