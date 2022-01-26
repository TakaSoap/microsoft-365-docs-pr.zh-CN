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
ms.localizationpriority: medium
ROBOTS: ''
description: 了解如何使用Power Automate解决方案来创建流程以处理Microsoft 365合同。
ms.openlocfilehash: d83fb6e5ca911cbafc6f064c615ab15ae0f570c7
ms.sourcegitcommit: f3c912780bbcf5a5b47de192202adb3afbd5952b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2022
ms.locfileid: "62219001"
---
# <a name="step-3-use-power-automate-to-create-the-flow-to-process-your-contracts"></a>步骤 3. 使用 Power Automate 创建处理合同的流程

已创建合同管理通道，并附加了SharePoint文档库。 下一步是创建一个Power Automate流，以处理您的SharePoint Syntex标识和分类的合同。 可以通过在文档库中创建Power Automate[流来SharePoint此步骤](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)。

对于合同管理解决方案，您需要创建一个Power Automate流以执行以下操作：

-  在合同已按你的SharePoint Syntex分类后，将合同状态更改为 **"正在审阅"。**
- 然后，将审核该合同，并批准或拒绝该合同。
- 对于已批准合同，合同信息将张贴到一个选项卡上，用于付款处理。
- 对于被拒绝的合同，将通知团队进行进一步分析。 

下图显示了Power Automate管理解决方案的流。

![Flow显示整个解决方案的图表。](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a>准备合同进行审阅

当合同由文档理解SharePoint Syntex和分类时，Power Automate流将首先将状态更改为 **"正在审阅"。**

![更新状态。](../media/content-understanding/flow-overview.png)

签出文件后，将状态值更改为 **"正在审阅"。**

![正在审阅状态。](../media/content-understanding/in-review.png)

下一步是创建自适应卡片，指出合同正在等待审阅，并发布到合同管理频道。

![合同审阅帖子。](../media/content-understanding/contract-approval-post.png)


![创建用于查看的自适应卡片。](../media/content-understanding/adaptive-card.png)

以下代码是项目流中用于此步骤Power Automate JSON。

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


## <a name="conditional-context"></a>条件上下文

在流中，接下来需要创建一个条件，在条件中，您的合同将被[批准](#if-the-contract-is-approved)或拒绝[。](#if-the-contract-is-rejected)

![条件。](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a>如果合同得到批准

合同获得批准后，将发生以下情况：

- 在 **"合同"** 选项卡上，合同卡中的状态将更改为"已批准 **"。**

   ![卡片状态为已批准。](../media/content-understanding/approved-contracts-tab.png)

- 在流中，状态更改为"已批准 **"。**

   ![Flow状态为已批准。](../media/content-understanding/status-approved.png)

- 在此解决方案中，合同数据将添加到" **付款** "选项卡，以便可以管理付款。 可以扩展此过程，以允许流程提交合同，供第三方财务应用程序（例如，Dynamics CRM (）) 。

   ![合同已移至"付款"。](../media/content-understanding/for-payout.png)

- 在流中，创建以下项以将已批准合同移动到" **付款"** 选项卡。

   ![Flow"支付"的项。](../media/content-understanding/ready-for-payout.png)

    若要从卡片获取所需信息的表达式Teams，请使用下表中显示的值。
 
    |名称     |Expression |
    |---------|-----------|
    | 审批状态  | body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response') ？['submitActionId']         |
    | 批准者     | body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response') ？['responder']['displayName']        |
    | 审批日期     | body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response') ？['responseTime']         |
    | 备注     | body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response') ？['data']？['acComments']         |
    
    下面的示例演示如何使用公式框中的 Power Automate编写表达式。

   ![显示表达式Power Automate的屏幕截图。](../media/content-understanding/expression-formula-power-automate.png)    

- 创建一个表明合同已批准的自适应卡片，并张贴到合同管理频道。

   ![发布合同审批。](../media/content-understanding/adaptive-card-approval.png)

   ![自适应卡片审批。](../media/content-understanding/adaptive-card.png)


   以下代码是项目流中用于此步骤Power Automate JSON。

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
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']?['acComments']}"
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

## <a name="if-the-contract-is-rejected"></a>如果合同被拒绝

当合同被拒绝时，将发生以下情况：

- 在 **"合同"** 选项卡上，合同卡中的状态将更改为"已 **拒绝"。**

   ![卡状态被拒绝。](../media/content-understanding/rejected-contracts-tab.png)

- 在流中，签出合同文件，将状态更改为"已拒绝"，然后重新签入该文件。 

   ![Flow在合同文件中被拒绝。](../media/content-understanding/reject-flow.png)

- 在你的流中，创建一个自适应卡片，指出合约已被拒绝。

   ![Flow自适应卡片上显示"已拒绝"状态。](../media/content-understanding/reject-flow-item.png)

以下代码是项目流中用于此步骤Power Automate JSON。

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
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']?['acComments']}"
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

- The card is posted in the Contract Management channel.

   ![Flow要拒绝的自适应卡片。](../media/content-understanding/rejected.png)
