---
title: 在管理中心管理组
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: 了解如何管理 Microsoft 365 组，包括添加删除组的成员、编辑电子邮件地址、组名称或说明，以及自定义组的工作方式。
ms.openlocfilehash: 3ba3dd36ed3929e956ce6359e678d6b684f64bb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908706"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心管理组

创建 Microsoft [365](create-groups.md) 组并添加组的成员后，可以配置组。 您可以编辑组名称或说明、管理所有者或成员，并指定外部发件人是否可以向组发送电子邮件以及是否将组对话的副本发送给成员。

转到 Microsoft 365 管理中心，位于 [https://admin.microsoft.com](https://admin.microsoft.com) 。

## <a name="edit-the-group-name-or-description"></a>编辑组名称或说明

1. 在管理中心中，展开 **"组"，** 然后单击"组 **"。**

2. 选择要编辑的组，然后单击"编辑 **名称和说明"。**

3. 更新名称和说明，然后选择"保存 **"。**

## <a name="manage-group-owners-and-members"></a>管理组所有者和成员

1. 在管理中心中，展开 **"组"，** 然后单击"组 **"。**

2. 单击要管理的组的名称以打开设置窗格。

3. 在" **成员** "选项卡上，选择是否要管理所有者或成员。

4. 选择 **"添加** "添加某人，或单击 **"X"** 删除某人。

5. 单击“**关闭**”。

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>将对话副本发送到组成员的收件箱
  
使用管理中心创建组时，默认情况下，用户不会获得发送到其收件箱的组电子邮件和会议邀请的副本。 他们需要转到组以查看对话和会议。 可以在管理中心更改此设置。

启用此设置后，组成员将获取发送到其 Outlook 收件箱的组电子邮件和会议邀请的副本。 他们可以阅读并删除该电子邮件的副本，不影响任何人。 在"组"收件箱中，电子邮件的副本仍然存在。

通过选择在 Outlook 中停止跟踪组，组的成员可以选择不接收这些电子邮件。

1. 在管理中心中，展开 **"组"，** 然后单击"组 **"。**

2. 单击要管理的组的名称以打开设置窗格。

3. 如果您希望 **成员** 在其自己的收件箱中接收组邮件和日历项目的副本，请在"设置"选项卡上，选择"将组对话和事件的副本发送给组成员"。

4. 选择“**保存**”。

## <a name="let-people-outside-the-organization-email-the-group"></a>让组织外部人员向组发送电子邮件

如果你想要拥有公司电子邮件地址（如公司电子邮件地址，info@contoso.com。
 
1. 在管理中心中，展开 **"组"，** 然后单击"组 **"。**

2. 单击要管理的组的名称以打开设置窗格。

3. 在管理中心组列表中，选择要更改的组的名称，然后在"设置"选项卡上，选择"允许外部发件人 **向此组发送电子邮件"。**
    
4. 选择“**保存**”。

## <a name="permanently-delete-a-microsoft-365-group"></a>永久删除 Microsoft 365 组

有时，你可能想要永久清除组，而无需等待 30 天的软删除期到期。 若要执行此操作，启动 PowerShell 并运行此命令，获取组的对象 ID：
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

记下要永久删除的一个或多个组的对象 ID。
  
> [!CAUTION]
> 清除组后可永久删除该组及其数据。 
  
若要清除组，请在 PowerShell 中运行此命令：

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

若要确认是否成功清除该组，请再次运行  *Get-AzureADMSDeletedGroup*  cmdlet 以确认该组不再出现在软删除的组列表中。某些情况下，要永久删除该组及其所有数据可能需要长达 24 小时。 
  
## <a name="related-articles"></a>相关文章

[创建 Microsoft 365 组](create-groups.md)

[管理对 Microsoft 365 组的来宾访问](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[选择创建 Microsoft 365 组时使用的域](../../solutions/choose-domain-to-create-groups.md)

[允许成员以 Microsoft 365 组的名义发送或发送](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[将通讯组列表升级到 Microsoft 365 组](../manage/upgrade-distribution-lists.md)

[使用 PowerShell 管理 Microsoft 365 组](../../enterprise/manage-microsoft-365-groups-with-powershell.md)