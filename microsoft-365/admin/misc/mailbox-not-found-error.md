---
title: 在 Outlook 网页版中遇到“邮箱未找到”错误
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
ms.custom: AdminTemplateSet
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: “**邮箱未找到**”错误意味着用来连接 Outlook 网页版的帐户没有 Exchange Online 许可证。
ms.openlocfilehash: e7808f550b41c63d0a2602f9977b86d8bf9a2b45158856298ad191a851a9b575
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53823911"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a>在 Outlook 网页版中遇到“邮箱未找到”错误？

如果你正在使用 Outlook 网页版且遇到“**邮箱未找到**”错误，那么用来连接 Outlook 网页版的帐户没有 Exchange Online 许可证，因此没有邮箱与帐户关联。 

## <a name="assign-a-license-to-your-account"></a>向帐户分配许可证

管理员按照以下步骤操作，可以向帐户分配许可证：

1. 打开“[Microsoft 365 管理中心](https://admin.microsoft.com/adminportal/home#/homepage)”，转到“**用户**”部分下的“**活动用户**”, 然后选择正在查看错误的用户。
1. 在打开的用户页面，转到“**许可证和应用**”部分，选择相应的“**位置**”值，然后分配包含 Exchange Online 的许可证（展开许可证以查看其详细信息）。 
1. 完成后，单击“**保存更改**”。

## <a name="related-content"></a>相关内容

[为用户添加另一个电子邮件别名](../email/add-another-email-alias-for-a-user.md)（文章）\
[在 Microsoft 365 中配置电子邮件转发](../email/configure-email-forwarding.md)（文章）\
[创建共享邮箱](../email/create-a-shared-mailbox.md)（文章）