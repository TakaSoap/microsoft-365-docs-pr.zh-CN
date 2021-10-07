---
title: 使用 Microsoft 365 解决方案管理合同
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- m365solution-managecontracts
- m365solution-overview
search.appverid: ''
ms.localizationpriority: medium
ROBOTS: ''
description: 了解如何使用 SharePoint Syntex、SharePoint 列表、Microsoft Teams 和 Power Automate 的 Microsoft 365 解决方案管理Power Automate。
ms.openlocfilehash: 86ccbeef283b165e178b12debd3ae99f982afc04
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189233"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>使用 Microsoft 365 解决方案管理合同

本文介绍如何使用 SharePoint Syntex 和 Microsoft 365 的组件为组织创建合同管理解决方案。 它提供了一个框架，可帮助你计划和创建满足你独特业务需求的解决方案。 即使此解决方案讨论合同管理，也可以调整它以创建其他文档管理解决方案，如工作单或发票。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWJUR0]

</br>

## <a name="identify-the-business-problem"></a>确定业务问题

规划合同管理系统的第一步是了解您尝试解决的问题。 对于此解决方案，需要解决四个关键问题：

- **确定合同**。 你的组织处理许多文档，如发票、合同、工作表等。  一些是通过电子邮件发送的数字资产，一些是通过传统邮件发送的纸张资产。 您需要一种方法来识别所有其他文档中的所有客户合同，然后对这些合同进行分类。

- **跟踪合同审批的历史记录**。 贵组织需要一种可靠的方法，以查找合同是否已获得批准或拒绝，以及是否已处理付款。 

- **用于管理合同审批的网站**。 组织需要建立一个协作网站，所有必需的利益干系人都可以在该网站中轻松审阅合同。 利益干系人应能根据需要查看整个合同，但主要考虑查看每个合同 (例如客户名称、PO 编号和总成本) 。 利益干系人应该能够轻松批准或拒绝传入合同。

- **路由已审阅合同**。 需要通过特定工作流传送已批准和已拒绝合同。 批准的合同需要传送给第三方应用程序进行付款处理。 必须传送被拒绝的合同进行其他审阅。

## <a name="overview-of-the-solution"></a>解决方案概述

  ![使用列表、列表SharePoint Syntex列表SharePoint列表Teams解决方案Power Automate。](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

此合同管理解决方案指南包括以下四个Microsoft 365：

- **Microsoft SharePoint Syntex：** 创建模型以标识和分类合同文件，然后从中提取适当的数据。

- **Microsoft SharePoint列表**：使用新式SharePoint中提供的格式以业务友好格式显示合同。

- **Microsoft Teams：** 使用 Teams 和关联选项卡的功能，让利益干系人能够审阅和管理合同。

- **Power Automate：** 使用流指导合同完成审批流程，然后引导到第三方应用程序进行付款。

### <a name="how-it-all-works"></a>一切如何工作

  ![显示工作流的解决方案图表，该工作流用于上载文档、提取数据、通知利益干系人以及批准或拒绝合同。](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. 将文档上载到SharePoint库。 一SharePoint Syntex文档理解模型已应用于文档库。 它检查每个文件，以查看是否与经过训练要查找的"合同"内容类型匹配。 如果找到匹配项，它会将文件分类为"协定"，并更新文档的内容类型。

2. 模型还会从利益干系人感兴趣的每个合同文件中提取特定数据，如客户、承包商 *和费用金额*。  

    以下页面是模型经过训练以识别的一个合同示例。

      ![合同示例。](../media/content-understanding/contract.png)

3. 在Microsoft Teams中，所有利益干系人都是安全Teams通道的成员，在通道中，文档库中的所有合同都可以看到批准或拒绝。 通过使用Teams功能，当需要审阅新合同时，将通知所有利益干系人。

4. 通过使用Power Automate，合同将经过审批流程在 Teams 通道中移动。 当成员批准合同时，合同状态更改为已批准，通过 Teams 帖子通知所有成员，并创建一个行项目以显示合同已准备好付款。 此过程可以扩展为直接写入第三方财务应用程序进行支付。

5. 当成员拒绝合同时，状态将更改为"已拒绝"，并且将通过一条帖子通知所有成员Teams通知。

6. 此解决方案的最终结果是业务流程自动化部署。 员工可以轻松使用自定义磁贴视图Teams启动和监视文档的审批工作流。 

     !["合同"选项卡。](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a>许可要求

此解决方案依赖于以下功能，这些功能均作为 Microsoft 365 企业版 (E1、E3、E5、F3) 或 Business (Basic、Standard 或 高级版) 许可证的一部分提供：

- Microsoft SharePoint Syntex
- Microsoft Teams
- Power Automate

### <a name="learn-how-to-use-sharepoint-syntex"></a>了解如何使用SharePoint Syntex

新SharePoint Syntex？ 了解如何使用 ai SharePoint Syntex管理内容。

入门[SharePoint Syntex](/learn/paths/syntex-get-started)学习路径将指导您如何使用文档理解模型和表单处理模型对文档进行分类、提取文本和标记文档以便快速轻松地进行知识管理。

## <a name="create-the-solution"></a>创建解决方案

以下各节将详细介绍如何配置合同管理解决方案。 它分为三个步骤：

- [步骤 1.使用SharePoint Syntex标识合同文件并提取数据](solution-manage-contracts-step1.md)
- [步骤 2.使用 Microsoft Teams 创建合同管理通道](solution-manage-contracts-step2.md)
- [步骤 3.使用 Power Automate 创建流程以处理合同](solution-manage-contracts-step3.md)
