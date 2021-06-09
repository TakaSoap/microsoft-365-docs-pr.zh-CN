---
title: Microsoft Defender for Endpoint API 到 Power BI
ms.reviewer: ''
description: 在 Microsoft Defender for Endpoint API (BI) 报告。
keywords: api， 受支持的 api， Power BI， 报告
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0ddb38e713f08c101639976b9f2c8c1ee32e63a3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843778"
---
# <a name="create-custom-reports-using-power-bi"></a><span data-ttu-id="b1476-104">使用自定义报告Power BI</span><span class="sxs-lookup"><span data-stu-id="b1476-104">Create custom reports using Power BI</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1476-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b1476-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1476-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b1476-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b1476-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1476-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="b1476-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b1476-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b1476-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b1476-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b1476-110">在此部分中，你将了解在 Defender for Endpoint API Power BI创建一个报告。</span><span class="sxs-lookup"><span data-stu-id="b1476-110">In this section you will learn create a Power BI report on top of Defender for Endpoint APIs.</span></span>

<span data-ttu-id="b1476-111">第一个示例演示如何将Power BI高级搜寻 API，第二个示例演示了与 OData API（如计算机操作或警报）的连接。</span><span class="sxs-lookup"><span data-stu-id="b1476-111">The first example demonstrates how to connect Power BI to Advanced Hunting API and the second example demonstrates a connection to our OData APIs, such as Machine Actions or Alerts.</span></span>

## <a name="connect-power-bi-to-advanced-hunting-api"></a><span data-ttu-id="b1476-112">连接 Power BI高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="b1476-112">Connect Power BI to Advanced Hunting API</span></span>

- <span data-ttu-id="b1476-113">打开 Microsoft Power BI</span><span class="sxs-lookup"><span data-stu-id="b1476-113">Open Microsoft Power BI</span></span>

- <span data-ttu-id="b1476-114">单击 **"获取**  >  **数据空白查询"**</span><span class="sxs-lookup"><span data-stu-id="b1476-114">Click **Get Data** > **Blank Query**</span></span>

    ![创建空白查询的图像](images/power-bi-create-blank-query.png)

- <span data-ttu-id="b1476-116">单击 **"高级编辑器"**</span><span class="sxs-lookup"><span data-stu-id="b1476-116">Click **Advanced Editor**</span></span>

    ![打开的高级编辑器的图像](images/power-bi-open-advanced-editor.png)

- <span data-ttu-id="b1476-118">复制以下内容并将其粘贴到编辑器中：</span><span class="sxs-lookup"><span data-stu-id="b1476-118">Copy the below and paste it in the editor:</span></span>

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

- <span data-ttu-id="b1476-119">单击 **完成**</span><span class="sxs-lookup"><span data-stu-id="b1476-119">Click **Done**</span></span>

- <span data-ttu-id="b1476-120">单击 **"编辑凭据"**</span><span class="sxs-lookup"><span data-stu-id="b1476-120">Click **Edit Credentials**</span></span>

    ![编辑凭据的图像0](images/power-bi-edit-credentials.png)

- <span data-ttu-id="b1476-122">选择 **"组织**  >  **帐户""登录"**</span><span class="sxs-lookup"><span data-stu-id="b1476-122">Select **Organizational account** > **Sign in**</span></span>

    ![集凭据的图像1](images/power-bi-set-credentials-organizational.png)

- <span data-ttu-id="b1476-124">输入凭据并等待登录</span><span class="sxs-lookup"><span data-stu-id="b1476-124">Enter your credentials and wait to be signed in</span></span>

- <span data-ttu-id="b1476-125">单击 **连接**</span><span class="sxs-lookup"><span data-stu-id="b1476-125">Click **Connect**</span></span>

    ![集凭据的图像2](images/power-bi-set-credentials-organizational-cont.png)

- <span data-ttu-id="b1476-127">现在，查询结果将显示为表格，你可以开始在它上面生成可视化效果！</span><span class="sxs-lookup"><span data-stu-id="b1476-127">Now the results of your query will appear as table and you can start build visualizations on top of it!</span></span>

- <span data-ttu-id="b1476-128">你可以复制此表、重命名该表并编辑内部的高级搜寻查询，以获取任何你想获取的数据。</span><span class="sxs-lookup"><span data-stu-id="b1476-128">You can duplicate this table, rename it and edit the Advanced Hunting query inside to get any data you would like.</span></span>

## <a name="connect-power-bi-to-odata-apis"></a><span data-ttu-id="b1476-129">连接 Power BI OData API</span><span class="sxs-lookup"><span data-stu-id="b1476-129">Connect Power BI to OData APIs</span></span>

- <span data-ttu-id="b1476-130">与上述示例的唯一区别是编辑器内的查询。</span><span class="sxs-lookup"><span data-stu-id="b1476-130">The only difference from the above example is the query inside the editor.</span></span> 

- <span data-ttu-id="b1476-131">复制以下内容并将其粘贴到编辑器中以拉取 **组织** 的所有计算机操作：</span><span class="sxs-lookup"><span data-stu-id="b1476-131">Copy the below and paste it in the editor to pull all **Machine Actions** from your organization:</span></span>

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- <span data-ttu-id="b1476-132">你可以对警报和 **计算机** 执行相同的 **操作**。</span><span class="sxs-lookup"><span data-stu-id="b1476-132">You can do the same for **Alerts** and **Machines**.</span></span>

- <span data-ttu-id="b1476-133">您还可以将 OData 查询用于查询筛选器，请参阅使用 [OData 查询](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="b1476-133">You also can use OData queries for queries filters, see [Using OData Queries](exposed-apis-odata-samples.md)</span></span>


## <a name="power-bi-dashboard-samples-in-github"></a><span data-ttu-id="b1476-134">Power BI仪表板GitHub</span><span class="sxs-lookup"><span data-stu-id="b1476-134">Power BI dashboard samples in GitHub</span></span>
<span data-ttu-id="b1476-135">有关详细信息，请参阅Power BI[模板](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)。</span><span class="sxs-lookup"><span data-stu-id="b1476-135">For more information see the [Power BI report templates](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span></span>

## <a name="sample-reports"></a><span data-ttu-id="b1476-136">示例报告</span><span class="sxs-lookup"><span data-stu-id="b1476-136">Sample reports</span></span>
<span data-ttu-id="b1476-137">查看 Microsoft Defender for Endpoint Power BI报告示例。</span><span class="sxs-lookup"><span data-stu-id="b1476-137">View the Microsoft Defender for Endpoint Power BI report samples.</span></span> <span data-ttu-id="b1476-138">有关详细信息，请参阅浏览 [代码示例](/samples/browse/?products=mdatp)。</span><span class="sxs-lookup"><span data-stu-id="b1476-138">For more information, see [Browse code samples](/samples/browse/?products=mdatp).</span></span>


## <a name="related-topic"></a><span data-ttu-id="b1476-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="b1476-139">Related topic</span></span>
- [<span data-ttu-id="b1476-140">适用于终结点的 Defender API</span><span class="sxs-lookup"><span data-stu-id="b1476-140">Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="b1476-141">高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="b1476-141">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="b1476-142">使用 OData 查询</span><span class="sxs-lookup"><span data-stu-id="b1476-142">Using OData Queries</span></span>](exposed-apis-odata-samples.md)
