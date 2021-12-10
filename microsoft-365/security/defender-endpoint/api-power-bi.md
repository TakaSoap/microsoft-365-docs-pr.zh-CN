---
title: Microsoft Defender for Endpoint API 与 Power BI
ms.reviewer: ''
description: 在 Microsoft Defender for Endpoint API (Power Business Intelligence) BI 报告。
keywords: api， 受支持的 api， Power BI， 报告
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 765af5e4a2e880aa9b6c1208495537ad8cf5f26b
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165110"
---
# <a name="create-custom-reports-using-power-bi"></a>使用自定义报告Power BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

在此部分中，你将了解在 Defender Power BI API 顶部创建一个报告。

第一个示例演示如何将Power BI高级搜寻 API，第二个示例演示了与 OData API（如计算机操作或警报）的连接。

## <a name="connect-power-bi-to-advanced-hunting-api"></a>连接 Power BI高级搜寻 API

- 打开 Microsoft Power BI

- 单击 **"获取** \> **数据空白查询"**

  ![创建空白查询的图像。](images/power-bi-create-blank-query.png)

- 单击 **"高级编辑器"**

  ![打开的高级编辑器的图像。](images/power-bi-open-advanced-editor.png)

- 复制以下内容并将其粘贴到编辑器中：

```
    let
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table
```

- 单击 **完成**

- 单击 **"编辑凭据"**

    ![编辑凭据 0 的图像。](images/power-bi-edit-credentials.png)

- 选择 **"组织** \> **帐户""登录"**

    ![set credentials1 的图像。](images/power-bi-set-credentials-organizational.png)

- 输入凭据并等待登录

- 单击 **连接**

    ![set credentials2 的图像。](images/power-bi-set-credentials-organizational-cont.png)

- 现在，查询结果将显示为表格，你可以开始在它上面生成可视化效果！

- 你可以复制此表、重命名该表并编辑内部的高级搜寻查询，以获取任何你想获取的数据。

## <a name="connect-power-bi-to-odata-apis"></a>连接 Power BI OData API

- 与上述示例的唯一区别是编辑器内的查询。

- 复制以下内容并将其粘贴到编辑器中以拉取 **组织** 的所有计算机操作：

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source
```

- 你可以对警报和 **计算机** 执行相同的 **操作**。
- 您还可以将 OData 查询用于查询筛选器，请参阅使用 [OData 查询](exposed-apis-odata-samples.md)

## <a name="power-bi-dashboard-samples-in-github"></a>Power BI仪表板GitHub

有关详细信息，请参阅Power BI[模板](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)。

## <a name="sample-reports"></a>示例报告

查看 Microsoft Defender for Endpoint Power BI报告示例。 有关详细信息，请参阅浏览 [代码示例](/samples/browse/?products=mdatp)。

## <a name="related-topics"></a>相关主题

- [适用于终结点的 Defender API](apis-intro.md)
- [高级搜寻 API](run-advanced-query-api.md)
- [使用 OData 查询](exposed-apis-odata-samples.md)
