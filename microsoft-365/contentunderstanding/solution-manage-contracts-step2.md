---
title: 步骤 2. 使用Microsoft Teams创建合同管理通道
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: 了解如何使用Microsoft Teams解决方案创建合同管理Microsoft 365渠道。
ms.openlocfilehash: 073ef1651ea5470594bfce0ffce65e849f9e063a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841170"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a><span data-ttu-id="16e82-104">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="16e82-104">Step 2.</span></span> <span data-ttu-id="16e82-105">使用Microsoft Teams创建合同管理通道</span><span class="sxs-lookup"><span data-stu-id="16e82-105">Use Microsoft Teams to create your contract management channel</span></span>

<span data-ttu-id="16e82-106">当组织设置合同管理解决方案时，您需要一个中央位置，利益干系人可在其中审阅和管理合同。</span><span class="sxs-lookup"><span data-stu-id="16e82-106">When your organization sets up a contracts management solution, you need a central location in which stakeholders can review and manage contracts.</span></span> <span data-ttu-id="16e82-107">为此，可以使用Microsoft Teams设置Teams通道[](/microsoftteams/)，并使用 Teams 中的功能：</span><span class="sxs-lookup"><span data-stu-id="16e82-107">For this purpose, you can use [Microsoft Teams](/microsoftteams/) to set up a Teams channel and use the features in Teams to:</span></span>

- <span data-ttu-id="16e82-108">**为利益干系人创建一个位置，以轻松查看需要操作的所有合同。**</span><span class="sxs-lookup"><span data-stu-id="16e82-108">**Create a location for stakeholders to easily see all contracts that require action.**</span></span> <span data-ttu-id="16e82-109">例如，在Teams可以在"合同管理"频道中创建"合同"选项卡，成员可以在其中查看需要审批的所有合同的有用图块视图。</span><span class="sxs-lookup"><span data-stu-id="16e82-109">For example, in Teams you can create a **Contracts** tab in the Contract Management channel in which members can see a useful tile view of all contracts that need approval.</span></span> <span data-ttu-id="16e82-110">还可以配置视图，以便每个"卡"列出你关注的重要数据 (如客户、承包商和费用金额) 。   </span><span class="sxs-lookup"><span data-stu-id="16e82-110">You can also configure the view so that each "card" lists the important data you care about (such as *Client*, *Contractor*, and *Fee amount*).</span></span>

     !["合同"选项卡。](../media/content-understanding/tile-view.png)

- <span data-ttu-id="16e82-112">**为成员提供相互交互并查看重要事件的位置。**</span><span class="sxs-lookup"><span data-stu-id="16e82-112">**Have a location for members to interact with each other and see important events.**</span></span> <span data-ttu-id="16e82-113">例如，在Teams中，"帖子"选项卡可用于进行对话、获取更新以及查看 (，例如拒绝合同) 。</span><span class="sxs-lookup"><span data-stu-id="16e82-113">For example, in Teams, the **Posts** tab can be used to have conversations, get updates, and see actions (such as a member rejecting a contract).</span></span> <span data-ttu-id="16e82-114">当发生某些 (如提交审批的新合同) ，"帖子"选项卡不仅可用于声明它，还可用于记录它。</span><span class="sxs-lookup"><span data-stu-id="16e82-114">When something has happened (such as a new contract submitted for approval), the **Posts** tab can be used not only to announce it, but also to keep a record of it.</span></span> <span data-ttu-id="16e82-115">如果成员订阅通知，则每当有更新时，他们将收到通知。</span><span class="sxs-lookup"><span data-stu-id="16e82-115">And if members subscribe to notifications, they'll get notified whenever there's an update.</span></span>

     !["帖子"选项卡。](../media/content-understanding/posts.png)

- <span data-ttu-id="16e82-117">**为成员提供一个位置来查看批准的合同，了解何时可以提交这些合同进行付款。**</span><span class="sxs-lookup"><span data-stu-id="16e82-117">**Have a location for members to see approved contracts to know when they can be submitted for payment.**</span></span> <span data-ttu-id="16e82-118">In Teams， you can create a **For Payment** channel that will list all contracts that will need to be submitted to payment.</span><span class="sxs-lookup"><span data-stu-id="16e82-118">In Teams, you can create a **For Payment** channel that will list all contracts that will need to be submitted to payment.</span></span> <span data-ttu-id="16e82-119">可以轻松扩展此解决方案，将此信息直接写入第三方财务应用程序， (Dynamics CRM) 。</span><span class="sxs-lookup"><span data-stu-id="16e82-119">You can easily extend this solution to instead write this information directly to a third-party financial application (for example, Dynamics CRM).</span></span>

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a><span data-ttu-id="16e82-120">将SharePoint文档库附加到"合同"选项卡</span><span class="sxs-lookup"><span data-stu-id="16e82-120">Attach your SharePoint document library to the Contracts tab</span></span>

<span data-ttu-id="16e82-121">在 **"合同管理**"频道中创建"合同"选项卡后，需要将SharePoint [文档库附加到该选项卡。](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)</span><span class="sxs-lookup"><span data-stu-id="16e82-121">After you create a **Contracts** tab in your Contracts Management channel, you need to [attach your SharePoint document library to it](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).</span></span> <span data-ttu-id="16e82-122">要SharePoint的文档库是上一节中应用SharePoint文档理解模型的文档库。</span><span class="sxs-lookup"><span data-stu-id="16e82-122">The SharePoint document library you want to attach is the one in which you applied your SharePoint Syntex document understanding model to in the previous section.</span></span>

<span data-ttu-id="16e82-123">附加文档SharePoint后，您将能够通过默认列表视图查看任何已分类合同。</span><span class="sxs-lookup"><span data-stu-id="16e82-123">After you attach the SharePoint document library, you'll be able to view any classified contracts through a default list view.</span></span>

   ![列表视图。](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a><span data-ttu-id="16e82-125">自定义"合同"选项卡磁贴视图</span><span class="sxs-lookup"><span data-stu-id="16e82-125">Customize your Contracts tab tile view</span></span>

> [!NOTE]
> <span data-ttu-id="16e82-126">本节引用合同管理解决方案资产存储库中包含的ContractTileFormatting.js[ on](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 文件中包含的代码 [示例](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)。</span><span class="sxs-lookup"><span data-stu-id="16e82-126">This section references code examples that are contained in the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file that is included in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span>

<span data-ttu-id="16e82-127">虽然Teams可以在磁贴视图中查看你的合同，但你可能希望对其进行自定义以查看想要在合同卡中可见的合同数据。</span><span class="sxs-lookup"><span data-stu-id="16e82-127">While Teams lets you view your contracts in a tile view, you might want to customize it to view the contract data you want to make visible in the contract card.</span></span> <span data-ttu-id="16e82-128">例如，对于" **合同** "选项卡，成员在合同卡上查看客户、承包商和费用金额非常重要。</span><span class="sxs-lookup"><span data-stu-id="16e82-128">For example, for the **Contracts** tab, it is important for members to see the client, contractor, and fee amount on the contract card.</span></span> <span data-ttu-id="16e82-129">所有这些字段都是通过应用到文档库的SharePoint提取自每个协定的。</span><span class="sxs-lookup"><span data-stu-id="16e82-129">All of these fields were extracted from each contract through your SharePoint Syntex model that was applied to your document library.</span></span> <span data-ttu-id="16e82-130">你还希望能够针对每个状态将磁贴标题栏更改为不同的颜色，以便成员可以轻松查看合同在审批过程中的情况。</span><span class="sxs-lookup"><span data-stu-id="16e82-130">You also want to be able to change the tile header bar to different colors for each status so that members can easily see where the contract is in the approval process.</span></span> <span data-ttu-id="16e82-131">例如，所有批准的合同都将有一个蓝色标题栏。</span><span class="sxs-lookup"><span data-stu-id="16e82-131">For example, all approved contracts will have a blue header bar.</span></span>

   ![列表视图。](../media/content-understanding/tile.png)

<span data-ttu-id="16e82-133">你使用的自定义磁贴视图要求你更改用于设置当前磁贴视图格式的 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="16e82-133">The custom tile view you use requires you to make changes to the JSON file used to format the current tile view.</span></span> <span data-ttu-id="16e82-134">你可以参考 JSON 文件，该文件用于通过查看 onContractTileFormatting.js[ 创建卡片](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 视图。</span><span class="sxs-lookup"><span data-stu-id="16e82-134">You can reference the JSON file used to create the card view by looking at the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file.</span></span> <span data-ttu-id="16e82-135">在下列部分中，你将看到代码的特定部分，这些代码适用于合同卡中的功能。</span><span class="sxs-lookup"><span data-stu-id="16e82-135">In the following sections, you'll see specific sections of the code for features that are in the contract cards.</span></span>

<span data-ttu-id="16e82-136">如果要在 Teams 频道中查看或更改视图的 JSON 代码，请在 Teams 频道中，选择视图下拉菜单，然后选择"设置当前视图的格式 **"。**</span><span class="sxs-lookup"><span data-stu-id="16e82-136">If you want to see or make changes to the JSON code for your view in your Teams channel, in the Teams channel, select the view drop-down menu, and then select **Format current view**.</span></span>

   ![json 格式。](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a><span data-ttu-id="16e82-138">卡片大小和形状</span><span class="sxs-lookup"><span data-stu-id="16e82-138">Card size and shape</span></span>

<span data-ttu-id="16e82-139">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file， look at the following section to see the code for how the size and shape of the card is formatted.</span><span class="sxs-lookup"><span data-stu-id="16e82-139">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the following section to see the code for how the size and shape of the card is formatted.</span></span>

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```

## <a name="contract-status"></a><span data-ttu-id="16e82-140">合同状态</span><span class="sxs-lookup"><span data-stu-id="16e82-140">Contract status</span></span>

<span data-ttu-id="16e82-141">以下代码允许你定义每个标题卡的状态。</span><span class="sxs-lookup"><span data-stu-id="16e82-141">The following code lets you define the status of each title card.</span></span> <span data-ttu-id="16e82-142">请注意，"新建 ("、"正在审阅"、"已批准"和"已拒绝) 值将为每个状态值显示不同的颜色代码。  </span><span class="sxs-lookup"><span data-stu-id="16e82-142">Note that each status value (*New*, *In review*, *Approved*, and *Rejected*) will display a different color code for each.</span></span> <span data-ttu-id="16e82-143">在 [ContractTileFormatting.js](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 中，查看定义状态的部分。</span><span class="sxs-lookup"><span data-stu-id="16e82-143">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the section that defines the status.</span></span>

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```

## <a name="extracted-fields"></a><span data-ttu-id="16e82-144">提取的字段</span><span class="sxs-lookup"><span data-stu-id="16e82-144">Extracted fields</span></span>

<span data-ttu-id="16e82-145">每个合同卡将显示针对每个合同提取的三个字段 (*客户端*、承包商和费用) 。  </span><span class="sxs-lookup"><span data-stu-id="16e82-145">Each contract card will display three fields that were extracted for each contract (*Client*, *Contractor*, and *Fee Amount*).</span></span> <span data-ttu-id="16e82-146">此外，你还希望显示文件由用于标识它的SharePoint分类的时间/日期。</span><span class="sxs-lookup"><span data-stu-id="16e82-146">Additionally, you also want to display the time/date that the file was classified by the SharePoint Syntex model used to identify it.</span></span>

<span data-ttu-id="16e82-147">在 [ContractTileFormatting.js](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 中，以下各节定义了其中每一部分。</span><span class="sxs-lookup"><span data-stu-id="16e82-147">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, the following sections define each of these.</span></span>

### <a name="client"></a><span data-ttu-id="16e82-148">客户端</span><span class="sxs-lookup"><span data-stu-id="16e82-148">Client</span></span>

<span data-ttu-id="16e82-149">此部分定义"客户端"在卡片上的显示方式，并使用特定合约的值。</span><span class="sxs-lookup"><span data-stu-id="16e82-149">This section defines how "Client" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a><span data-ttu-id="16e82-150">承包商</span><span class="sxs-lookup"><span data-stu-id="16e82-150">Contractor</span></span>

<span data-ttu-id="16e82-151">本节定义"承包商"在卡片上的显示方式，并使用特定合同的值。</span><span class="sxs-lookup"><span data-stu-id="16e82-151">This section defines how the "Contractor" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
},
```

### <a name="fee-amount"></a><span data-ttu-id="16e82-152">费用金额</span><span class="sxs-lookup"><span data-stu-id="16e82-152">Fee Amount</span></span>

<span data-ttu-id="16e82-153">此部分定义"费用金额"在卡上的显示方式，并使用特定合同的值。</span><span class="sxs-lookup"><span data-stu-id="16e82-153">This section defines how the "Fee Amount" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```

### <a name="classification-date"></a><span data-ttu-id="16e82-154">分类日期</span><span class="sxs-lookup"><span data-stu-id="16e82-154">Classification date</span></span>

<span data-ttu-id="16e82-155">此部分定义"分类"在卡片上的显示方式，并使用特定合约的值。</span><span class="sxs-lookup"><span data-stu-id="16e82-155">This section defines how "Classification" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a><span data-ttu-id="16e82-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="16e82-156">Next step</span></span>

[<span data-ttu-id="16e82-157">步骤 3.使用 Power Automate 创建处理合同的流程</span><span class="sxs-lookup"><span data-stu-id="16e82-157">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
