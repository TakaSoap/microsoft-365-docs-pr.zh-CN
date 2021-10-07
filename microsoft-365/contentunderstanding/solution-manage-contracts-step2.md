---
title: 步骤 2. 使用 Microsoft Teams 创建合同管理通道
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
description: 了解如何使用Microsoft Teams解决方案创建合同管理Microsoft 365渠道。
ms.openlocfilehash: a5a42bedcb6acba4caf8f6f114812c63869ee92e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172115"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>步骤 2. 使用 Microsoft Teams 创建合同管理通道

当组织设置合同管理解决方案时，您需要一个中央位置，利益干系人可在其中审阅和管理合同。 为此，可以使用 Microsoft Teams 设置[](/microsoftteams/)Teams通道，并使用 Teams 中的功能：

- **为利益干系人创建一个位置，以轻松查看需要操作的所有合同。** 例如，在Teams可以在"合同管理"频道中创建"合同"选项卡，成员可以在其中查看需要审批的所有合同的有用图块视图。 还可以配置视图，以便每个"卡"列出你关注的重要数据 (如客户、承包商和费用金额) 。   

     !["合同"选项卡。](../media/content-understanding/tile-view.png)

- **为成员提供相互交互并查看重要事件的位置。** 例如，在 Teams 中，"帖子"选项卡可用于进行对话、获取更新以及查看 (，例如拒绝合同) 。 当发生 (（如提交审批的新合同) ）时，"公告"选项卡不仅可用于声明它，还可用于记录它。 如果成员订阅通知，则每当有更新时，他们将收到通知。

     !["帖子"选项卡。](../media/content-understanding/posts.png)

- **为成员提供查看已批准合同的位置，了解何时可以提交这些合同进行付款。** 在SharePoint中，你需要创建一个"付款"列表，并包括"客户端、承包商"和"费用"金额的列，选择"单行 **文本**"作为列类型。  你需要将"付款"列表添加为"合同管理"Teams中的"付款"选项卡，这类似于你将对"合同"选项卡 [执行哪些操作](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab)。"**付款**"选项卡将列出需要提交付款的所有合同。 可以轻松扩展此解决方案，将此信息直接写入第三方财务应用程序， (Dynamics CRM) 。 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>将SharePoint文档库附加到"合同"选项卡

在 **"合同管理**"频道中创建"合同"选项卡后，需要将SharePoint [文档库附加到该选项卡。](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b) 要SharePoint的文档库是上一节中SharePoint Syntex文档理解模型所应用到的文档库。

附加文档SharePoint后，您将能够通过默认列表视图查看任何已分类合同。

   ![库的列表SharePoint视图。](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a>自定义"合同"选项卡磁贴视图

> [!NOTE]
> 本节引用 [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 文件中包含的代码示例，该文件包含在 [合同管理解决方案资产存储库中](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)。

当你Teams磁贴视图中查看你的合同时，你可能希望对其进行自定义以查看想要在合同卡中可见的合同数据。 例如，对于" **合同** "选项卡，成员在合同卡上查看客户、承包商和费用金额非常重要。 所有这些字段都是通过应用到文档库SharePoint Syntex模型从每个协定中提取的。 你还希望能够针对每个状态将磁贴标题栏更改为不同的颜色，以便成员可以轻松查看合同在审批过程中的情况。 例如，所有批准的合同都将有一个蓝色标题栏。

   ![库的SharePoint视图。](../media/content-understanding/tile.png)

你使用的自定义磁贴视图要求你更改用于设置当前磁贴视图格式的 JSON 文件。 通过查看 [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 文件，可以引用用于创建卡片视图的 JSON 文件。 在下列部分中，你将看到代码的特定部分，这些代码适用于合同卡中的功能。

如果要在 Teams 频道中查看或更改视图的 JSON 代码，请在 Teams 频道中，选择视图下拉菜单，然后选择"设置当前视图的格式 **"。**

   ![频道中 json 格式Teams屏幕截图。](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a>卡片大小和形状

在 [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 文件中，查看以下部分以查看卡片大小和形状格式的代码。

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

## <a name="contract-status"></a>合同状态

以下代码允许你定义每个标题卡的状态。 请注意，"新建 ("、"正在审阅"、"已批准"和"已拒绝) 值将为每个状态值显示不同的颜色代码。   在 [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 文件中，查看定义状态的部分。

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

## <a name="extracted-fields"></a>提取的字段

每个合同卡将显示针对每个合同提取的三个字段 (*客户端*、承包商和 *费用) 。*  此外，您还需要显示文件由用于标识文件的 SharePoint Syntex分类的时间/日期。

在 [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 文件中，以下各节定义了其中每个部分。

### <a name="client"></a>客户端

此部分定义"客户端"在卡片上的显示方式，并使用特定合约的值。

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

### <a name="contractor"></a>承包商

本节定义"承包商"在卡片上的显示方式，并使用特定合同的值。

```JSON
                        {
                          "elmType": "div",
                          "txtContent": "Contractor",
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
                          "txtContent": "[$Contractor]"
                        },
```

### <a name="fee-amount"></a>费用金额

此部分定义"费用金额"在卡上的显示方式，并使用特定合同的值。

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

### <a name="classification-date"></a>分类日期

此部分定义"分类"在卡片上的显示方式，并使用特定合约的值。

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

## <a name="next-step"></a>后续步骤

[步骤 3.使用 Power Automate 创建流程以处理合同](solution-manage-contracts-step3.md)
