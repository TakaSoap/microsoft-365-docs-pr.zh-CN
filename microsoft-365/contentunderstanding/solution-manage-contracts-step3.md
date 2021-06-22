---
title: 第 3 步。 使用 Power Automate 创建处理合同的流程
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
description: 了解如何使用Power Automate解决方案来创建流程以处理Microsoft 365合同。
ms.openlocfilehash: e6c1d1e53363f996241efb2394189853d840c6c2
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054475"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a><span data-ttu-id="00aea-104">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="00aea-104">Step 3.</span></span> <span data-ttu-id="00aea-105">使用 Power Automate 创建处理合同的流程</span><span class="sxs-lookup"><span data-stu-id="00aea-105">Use Power Automate to create your flow to process your contracts</span></span>

<span data-ttu-id="00aea-106">已创建合同管理通道，并附加了SharePoint文档库。</span><span class="sxs-lookup"><span data-stu-id="00aea-106">You've created your Contract Management channel and have attached your SharePoint document library.</span></span> <span data-ttu-id="00aea-107">下一步是创建一个Power Automate流，以处理您的SharePoint Syntex标识和分类的合同。</span><span class="sxs-lookup"><span data-stu-id="00aea-107">The next step is to create a Power Automate flow to process your contracts that your SharePoint Syntex model identifies and classifies.</span></span> <span data-ttu-id="00aea-108">可以通过在文档库中创建Power Automate流[SharePoint此步骤](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)。</span><span class="sxs-lookup"><span data-stu-id="00aea-108">You can do this step by [creating a Power Automate flow in your SharePoint document library](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01).</span></span>

<span data-ttu-id="00aea-109">对于合同管理解决方案，您需要创建一个Power Automate流以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="00aea-109">For your contracts management solution, you want to create a Power Automate flow to do the following actions:</span></span>

-  <span data-ttu-id="00aea-110">在合同已按你的SharePoint Syntex分类后，将合同状态更改为 **"正在审阅"。**</span><span class="sxs-lookup"><span data-stu-id="00aea-110">After a contract has been classified by your SharePoint Syntex model, change the contract status to **In review**.</span></span>
- <span data-ttu-id="00aea-111">然后，将审核该合同，并批准或拒绝该合同。</span><span class="sxs-lookup"><span data-stu-id="00aea-111">The contract is then reviewed and is either approved or rejected.</span></span>
- <span data-ttu-id="00aea-112">对于已批准合同，合同信息将张贴到一个选项卡上，用于付款处理。</span><span class="sxs-lookup"><span data-stu-id="00aea-112">For approved contracts, the contract information is posted to a tab for payment processing.</span></span>
- <span data-ttu-id="00aea-113">对于被拒绝的合同，将通知团队进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="00aea-113">For rejected contracts, the team is notified for further analysis.</span></span> 

<span data-ttu-id="00aea-114">下图显示了Power Automate管理解决方案的工作流程。</span><span class="sxs-lookup"><span data-stu-id="00aea-114">The following diagram shows the Power Automate flow for the contract management solution.</span></span>

![Flow显示整个解决方案的图表。](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a><span data-ttu-id="00aea-116">准备合同进行审阅</span><span class="sxs-lookup"><span data-stu-id="00aea-116">Prepare your contract for review</span></span>

<span data-ttu-id="00aea-117">当合同由文档理解SharePoint Syntex和分类时，Power Automate流将首先将状态更改为 **"正在审阅"。**</span><span class="sxs-lookup"><span data-stu-id="00aea-117">When a contract is identified and classified by your SharePoint Syntex document understanding model, the Power Automate flow will first change the status to **In review**.</span></span>

![更新状态。](../media/content-understanding/flow-overview.png)

<span data-ttu-id="00aea-119">签出文件后，将状态值更改为 **"正在审阅"。**</span><span class="sxs-lookup"><span data-stu-id="00aea-119">After checking out the file, change the status value to **In review**.</span></span>

![正在审阅状态。](../media/content-understanding/in-review.png)

<span data-ttu-id="00aea-121">下一步是创建自适应卡片，指出合同正在等待审阅，并发布到合同管理频道。</span><span class="sxs-lookup"><span data-stu-id="00aea-121">The next step is to create an adaptive card stating that the contract is waiting for review and posting it to the Contract Management channel.</span></span>

![合同审阅帖子。](../media/content-understanding/contract-approval-post.png)


![创建用于查看的自适应卡片。](../media/content-understanding/adaptive-card.png)

<span data-ttu-id="00aea-124">以下代码是项目流中用于此步骤Power Automate JSON。</span><span class="sxs-lookup"><span data-stu-id="00aea-124">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional-context"></a><span data-ttu-id="00aea-125">条件上下文</span><span class="sxs-lookup"><span data-stu-id="00aea-125">Conditional context</span></span>

<span data-ttu-id="00aea-126">在流中，接下来需要创建一个条件，在条件中，您的合同将被[批准](#if-the-contract-is-approved)或拒绝[。](#if-the-contract-is-rejected)</span><span class="sxs-lookup"><span data-stu-id="00aea-126">In your flow, next you need to create a condition in which your contract will be either  [approved](#if-the-contract-is-approved) or [rejected](#if-the-contract-is-rejected).</span></span>

![条件。](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a><span data-ttu-id="00aea-128">如果合同得到批准</span><span class="sxs-lookup"><span data-stu-id="00aea-128">If the contract is approved</span></span>

<span data-ttu-id="00aea-129">合同获得批准后，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="00aea-129">When a contract has been approved, the following things occur:</span></span>

- <span data-ttu-id="00aea-130">在 **"合同"** 选项卡上，合同卡中的状态将更改为"已批准 **"。**</span><span class="sxs-lookup"><span data-stu-id="00aea-130">On the **Contracts** tab, the status in the contract card will change to **Approved**.</span></span>

   ![卡片状态为已批准。](../media/content-understanding/approved-contracts-tab.png)

- <span data-ttu-id="00aea-132">在流中，状态更改为"已批准 **"。**</span><span class="sxs-lookup"><span data-stu-id="00aea-132">In your flow, the status is changed to **Approved**.</span></span>

   ![Flow状态为已批准。](../media/content-understanding/status-approved.png)

- <span data-ttu-id="00aea-134">在此解决方案中，合同数据将添加到" **付款** "选项卡，以便可以管理付款。</span><span class="sxs-lookup"><span data-stu-id="00aea-134">In this solution, the contract data will be added to the **For Payout** tab so that the payouts can be managed.</span></span> <span data-ttu-id="00aea-135">可以扩展此过程 (，以允许流程提交合同，供第三方财务应用程序（例如，Dynamics CRM) ）付款。</span><span class="sxs-lookup"><span data-stu-id="00aea-135">This process can be extended to allow the flow to submit the contracts for payment by a third-party financial application (for example, Dynamics CRM).</span></span>

   ![合同已移至"付款"。](../media/content-understanding/for-payout.png)

- <span data-ttu-id="00aea-137">在流中，创建以下项以将已批准合同移动到" **付款"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="00aea-137">In the flow, you create the following item to move approved contracts to the **For Payout** tab.</span></span>

   ![Flow项目移动到"支付"。](../media/content-understanding/ready-for-payout.png)

    <span data-ttu-id="00aea-139">若要从卡片获取所需信息的表达式Teams，请使用下表中显示的值。</span><span class="sxs-lookup"><span data-stu-id="00aea-139">To get the expressions for the information needed from the Teams card, use the values shown in the following table.</span></span>
 
    |<span data-ttu-id="00aea-140">名称</span><span class="sxs-lookup"><span data-stu-id="00aea-140">Name</span></span>     |<span data-ttu-id="00aea-141">Expression</span><span class="sxs-lookup"><span data-stu-id="00aea-141">Expression</span></span> |
    |---------|-----------|
    | <span data-ttu-id="00aea-142">审批状态</span><span class="sxs-lookup"><span data-stu-id="00aea-142">Approval state</span></span>  | <span data-ttu-id="00aea-143">body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response') ？['submitActionId']</span><span class="sxs-lookup"><span data-stu-id="00aea-143">body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['submitActionId']</span></span>         |
    | <span data-ttu-id="00aea-144">批准者</span><span class="sxs-lookup"><span data-stu-id="00aea-144">Approved by</span></span>     | <span data-ttu-id="00aea-145">body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response') ？['responder']['displayName']</span><span class="sxs-lookup"><span data-stu-id="00aea-145">body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']</span></span>        |
    | <span data-ttu-id="00aea-146">审批日期</span><span class="sxs-lookup"><span data-stu-id="00aea-146">Approval date</span></span>     | <span data-ttu-id="00aea-147">body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response') ？['responseTime']</span><span class="sxs-lookup"><span data-stu-id="00aea-147">body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']</span></span>         |
    | <span data-ttu-id="00aea-148">评论</span><span class="sxs-lookup"><span data-stu-id="00aea-148">Comment</span></span>     | <span data-ttu-id="00aea-149">body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response') ？['data']['acComments']</span><span class="sxs-lookup"><span data-stu-id="00aea-149">body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']</span></span>         |
    
    <span data-ttu-id="00aea-150">以下示例演示如何使用公式框中的 Power Automate编写表达式。</span><span class="sxs-lookup"><span data-stu-id="00aea-150">The following example shows how to use the formula box in Power Automate to write an expression.</span></span>

   ![显示表达式Power Automate的屏幕截图。](../media/content-understanding/expression-formula-power-automate.png)    

- <span data-ttu-id="00aea-152">创建一个表明合同已批准的自适应卡片，并张贴到合同管理频道。</span><span class="sxs-lookup"><span data-stu-id="00aea-152">An adaptive card stating that the contract has been approved is created and posted to the Contract Management channel.</span></span>

   ![发布合同审批。](../media/content-understanding/adaptive-card-approval.png)

   ![自适应卡片审批。](../media/content-understanding/adaptive-card.png)


   <span data-ttu-id="00aea-155">以下代码是项目流中用于此步骤Power Automate JSON。</span><span class="sxs-lookup"><span data-stu-id="00aea-155">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a><span data-ttu-id="00aea-156">如果合同被拒绝</span><span class="sxs-lookup"><span data-stu-id="00aea-156">If the contract is rejected</span></span>

<span data-ttu-id="00aea-157">当合同被拒绝时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="00aea-157">When a contract has been rejected, the following things occur:</span></span>

- <span data-ttu-id="00aea-158">在 **"合同"** 选项卡上，合同卡中的状态将更改为"已 **拒绝"。**</span><span class="sxs-lookup"><span data-stu-id="00aea-158">On the **Contracts** tab, the status in the contract card will change to **Rejected**.</span></span>

   ![卡状态被拒绝。](../media/content-understanding/rejected-contracts-tab.png)

- <span data-ttu-id="00aea-160">在流中，签出合同文件，将状态更改为"已拒绝"，然后重新签入该文件。 </span><span class="sxs-lookup"><span data-stu-id="00aea-160">In your flow, you check out the contract file, change the status to **Rejected**, and then check the file back in.</span></span>

   ![Flow在合同文件中拒绝状态。](../media/content-understanding/reject-flow.png)

- <span data-ttu-id="00aea-162">在你的流中，创建一个自适应卡片，指出合约已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="00aea-162">In your flow, you create an adaptive card stating that the contract has been rejected.</span></span>

   ![Flow自适应卡片上显示已拒绝状态。](../media/content-understanding/reject-flow-item.png)

<span data-ttu-id="00aea-164">以下代码是项目流中用于此步骤Power Automate JSON。</span><span class="sxs-lookup"><span data-stu-id="00aea-164">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- <span data-ttu-id="00aea-165">The card is posted in the Contract Management channel.</span><span class="sxs-lookup"><span data-stu-id="00aea-165">The card is posted in the Contract Management channel.</span></span>

   ![Flow要拒绝的自适应卡片。](../media/content-understanding/rejected.png)