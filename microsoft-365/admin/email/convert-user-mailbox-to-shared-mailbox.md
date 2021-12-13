---
title: 将用户邮箱转换为共享邮箱
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '了解如何将专用邮箱转换为多个人员（而不是一个人）可以访问的共享邮箱。 '
ms.openlocfilehash: 45ed21e1638bfee2d13ee59193a542bd4f70e05b
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61422263"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>将用户邮箱转换为共享邮箱

将用户的邮箱转换为共享邮箱时，将保留所有现有电子邮件和日历。 现在，它才在一个共享邮箱中，多个人员将能够访问它，而不是一个人。 稍后，可以将共享邮箱转换回专用 (用户) 邮箱。

## <a name="before-you-begin"></a>准备工作

**以下是您需要了解的一些非常重要的事情：**

- 要转换的用户邮箱需要分配有许可证，然后才能将其转换为共享邮箱。 否则，将看不到用于转换邮箱的选项。 如果已删除许可证，请重新添加它，以便转换邮箱。 将邮箱转换为共享邮箱后，可以从用户帐户中删除许可证。

- 共享邮箱可以具有多达 50 GB 的数据，而无需为其分配许可证。 要保留的数据超过此限制，需要为其分配许可证。 你可能需要删除一大 (电子邮件，例如，从共享邮箱) 包含附件的电子邮件，以便缩小邮箱大小，以便可以删除许可证。

- 不要删除旧用户帐户。 这是定位共享邮箱所需的。 如果已删除用户帐户，请参阅转换已删除 [用户的邮箱](#convert-the-mailbox-of-a-deleted-user)。

- 将邮箱转换为共享邮箱后，这些规则将保持不变。

## <a name="use-the-classic-exchange-admin-center-to-convert-a-mailbox"></a>使用经典Exchange管理中心转换邮箱
 
1. 转到经典<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理中心</a>。

2. 选择 **"收件人** \> **""邮箱"。**

3. 选择用户邮箱。 在 **"转换为共享邮箱"下，** 选择"**转换"。**

4. 如果邮箱小于 50 GB，可以从用户中删除许可证，[](../manage/remove-licenses-from-users.md)并停止付费。 不要删除用户帐户。 共享邮箱需要它作为定位标记。 如果要转换离开组织的员工的邮箱，应执行其他步骤以确保他们不再登录。 有关详细信息，请参阅从公司[中删除以前的Microsoft 365。](../add-users/remove-former-employee.md)
    
> [!NOTE]
> 无需在邮箱转换期间重置用户密码。 但是，如果未重置密码，则 **完成** 邮箱转换后，原始用户名和密码将继续工作。

有关有关共享邮箱的一切其他信息，请参阅关于 [共享](about-shared-mailboxes.md) 邮箱和 [创建共享邮箱](create-a-shared-mailbox.md)。

> [!NOTE]
> 共享邮箱不需要单独的许可证。 但是，如果你想要启用就地存档或将就地保留或诉讼保留置于共享邮箱，则必须向邮箱分配带有 Exchange Online Archiving 的 Exchange Online 计划 1 或 Exchange Online 计划 2 许可证。

## <a name="use-the-new-exchange-admin-center-to-convert-a-mailbox"></a>使用新建Exchange管理中心转换邮箱

1. 转到管理<a href="https://admin.exchange.microsoft.com/#/homepage" target="_blank">Exchange中心</a>。

2. 选择 **"收件人** \> **""邮箱"。**

3. 选择用户邮箱。 在"**邮箱"** 选项卡的"更多 **操作"下**，选择 **"转换为共享邮箱"。**

4. 如果邮箱小于 50 GB，可以从用户中删除许可证，[](../manage/remove-licenses-from-users.md)并停止付费。 不要删除用户帐户。 共享邮箱需要它作为定位标记。 如果要转换离开组织的员工的邮箱，应执行其他步骤以确保他们不再登录。 请参阅从[公司中删除以前的Microsoft 365。](../add-users/remove-former-employee.md)
    
> [!NOTE]
> 无需在邮箱转换期间重置用户密码。 但是，如果未重置密码，则 **完成** 邮箱转换后，原始用户名和密码将继续工作。

有关有关共享邮箱的一切其他信息，请参阅关于 [共享](about-shared-mailboxes.md) 邮箱和 [创建共享邮箱](create-a-shared-mailbox.md)。

> [!NOTE]
> 共享邮箱不需要单独的许可证。 但是，如果你想要启用就地存档或将就地保留或诉讼保留置于共享邮箱，则必须向邮箱分配带有 Exchange Online Archiving 的 Exchange Online 计划 1 或 Exchange Online 计划 2 许可证。

## <a name="convert-the-mailbox-of-a-deleted-user"></a>转换已删除用户的邮箱

删除用户帐户后，请按照以下步骤将其旧邮箱转换为共享邮箱：

1. [还原用户帐户](../add-users/restore-user.md)。

2. 请确保已Microsoft 365许可证。

3. 重置用户密码。
    
4. 等待 20-30 分钟，以重新创建其邮箱。
      
6. 在邮箱被重新创建后，从用户的邮箱中删除许可证。 不要删除用户的旧邮箱。 共享邮箱需要它作为定位标记。
    
7. 将成员添加到共享邮箱。

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>将共享邮箱转换回用户的专用 () 邮箱

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。
   
2. 选择 **"收件人** \> **""共享"。**

3. 选择共享邮箱。 在 **"转换为常规邮箱"下，** 选择"**转换"。**

4. 返回到管理中心。 在 **"用户**"下，选择与旧共享邮箱关联的用户帐户。 将许可证分配给帐户，然后重置密码。

   设置邮箱需要几分钟时间，但之后，打算使用该帐户的人就可以了。 登录后，他们会看到共享邮箱中过去的电子邮件和日历项目。

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>在混合环境中转换用户邮箱

有关将用户邮箱转换为混合环境中共享邮箱Exchange，请参阅：

 - [在内部部署部署环境中创建或修改远程共享邮箱Exchange Cmdlet](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [在混合部署中运行目录同步后，共享邮箱Exchange转换为用户邮箱](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> 如果你是组织管理或收件人管理角色组的成员，可以使用 Exchange 命令行管理程序将用户邮箱更改为本地共享邮箱。 例如，`Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`。

## <a name="related-content"></a>相关内容

[关于共享邮箱](about-shared-mailboxes.md)（文章）\
[Create a shared mailbox (](create-a-shared-mailbox.md) article) \
[配置共享邮箱](configure-a-shared-mailbox.md)（文章）\
[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)（文章）\
[解决共享邮箱相关问题](resolve-issues-with-shared-mailboxes.md)（文章）
