---
title: 从共享邮箱删除许可证
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: sinakassaw, nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- commerce_licensing
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: '从共享邮箱中删除许可证，以将其分配给其他用户或返回许可证，以便不支付许可证费用。 '
ms.date: 05/11/2021
ms.openlocfilehash: 6de6f213cc0df7a216122d55ef07e270586aea12
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314793"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>从共享邮箱中删除许可证

共享邮箱通常不需要许可证。 按照以下说明从共享邮箱中删除许可证，以便你可以将其分配给用户或返回许可证，以便无需为不需要的许可证付费。

> [!NOTE]
>
> 以下Exchange Online需要计划 2 许可证：
>
> - 共享邮箱使用的存储空间超过 50 GB。
> - 共享邮箱使用就地存档。
> - 共享邮箱置于诉讼保留状态。
> - 共享邮箱分配有Microsoft 365 Defender许可证。
> 
> 有关如何分配许可证的分步说明，请参阅 [向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。 


## <a name="remove-the-license"></a>删除许可证

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

::: moniker-end

   > [!NOTE]
   > 您需要从"活动用户"页中删除许可证。 无法从"共享邮箱"页面删除许可证，因为许可证是用户设置。
  
2. 选择共享邮箱。

3. 在" **许可证和应用"** 选项卡中，展开 **"许可证** "并取消选中要删除的许可证的框。

4. 选择“**保存更改**”。

5. 返回到" **活动用户"** 页时，共享邮箱的状态将为 **"未授权"**。

6. 你仍然支付许可证费用。 若要停止付费， [请从订阅中删除许可证](../../commerce/licenses/buy-licenses.md)。

## <a name="related-content"></a>相关内容

[关于共享邮箱](about-shared-mailboxes.md)（文章）\
[Create a shared mailbox (](create-a-shared-mailbox.md) article) \
[配置共享邮箱](configure-a-shared-mailbox.md)（文章）\
[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)（文章）\
[解决共享邮箱相关问题](resolve-issues-with-shared-mailboxes.md)（文章）
