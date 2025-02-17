---
title: Microsoft Defender for Endpoint API 与 Power BI
ms.reviewer: ''
description: 在 Microsoft Defender for Endpoint API (BI) 报告。
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
ms.openlocfilehash: 4cad6fd5188745773ce561d1db697989598a1dc5
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472146"
---
# <a name="create-custom-reports-using-power-bi"></a>使用自定义报告Power BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

在此部分中，你将了解如何在 Defender for Endpoint API Power BI创建一个报告。

第一个示例演示如何将Power BI高级搜寻 API，第二个示例演示了与 OData API（如计算机操作或警报）的连接。

## <a name="connect-power-bi-to-advanced-hunting-api"></a>连接 Power BI高级搜寻 API

- 打开 Microsoft Power BI。

- 单击 **"获取数据** \> **空白查询"**。

  :::image type="content" source="images/power-bi-create-blank-query.png" alt-text="&quot;获取数据&quot;菜单项下的&quot;空白查询&quot;选项" lightbox="images/power-bi-create-blank-query.png":::

- 单击 **"高级编辑器"**。

  :::image type="content" source="images/power-bi-open-advanced-editor.png" alt-text="高级编辑器菜单项" lightbox="images/power-bi-open-advanced-editor.png":::

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

- 单击“**完成**”。

- 单击 **"编辑凭据"**。

    :::image type="content" source="images/power-bi-edit-credentials.png" alt-text="&quot;编辑凭据&quot;菜单项" lightbox="images/power-bi-edit-credentials.png":::
    

- 选择 **"组织帐户** \> **登录"**。

    :::image type="content" source="images/power-bi-set-credentials-organizational.png" alt-text="&quot;组织帐户&quot;菜单项中的&quot;登录&quot;选项" lightbox="images/power-bi-set-credentials-organizational.png":::

- 输入凭据并等待登录。

- 单击“**连接**”。

    :::image type="content" source="images/power-bi-set-credentials-organizational-cont.png" alt-text="&quot;组织帐户&quot;菜单项中的登录确认消息" lightbox="images/power-bi-set-credentials-organizational-cont.png":::

- 现在，查询结果将显示为表格，你可以开始在表格顶部生成可视化效果！

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

- 你可以对警报和 **计算机执行** 相同的 **操作**。
- 您还可以将 OData 查询用于查询筛选器，请参阅使用 [OData 查询](exposed-apis-odata-samples.md)。

## <a name="power-bi-dashboard-samples-in-github"></a>Power BI仪表板GitHub

有关详细信息，请参阅Power BI[模板](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)。

## <a name="sample-reports"></a>示例报告

查看 Microsoft Defender for Endpoint Power BI报告示例。 有关详细信息，请参阅浏览 [代码示例](/samples/browse/?products=mdatp)。

## <a name="related-topics"></a>相关主题

- [适用于终结点的 Defender API](apis-intro.md)
- [高级搜寻 API](run-advanced-query-api.md)
- [使用 OData 查询](exposed-apis-odata-samples.md)
