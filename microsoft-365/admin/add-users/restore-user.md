---
title: 还原用户
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 删除用户帐户后 30 天内，可以还原该帐户以及所有数据，并且用户可以使用同一帐户登录。
ms.openlocfilehash: fc011f9589d789a7eb2faa332a104ef670cf6590
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074482"
---
# <a name="restore-a-user"></a>还原用户
   
如果在删除用户帐户后 30 天内还原用户帐户，则该用户帐户及其关联的所有数据都将还原。用户可使用相同的 工作或学校帐户 进行登录。其邮箱将完全还原。如果需要了解某个特定用户帐户还有多长时间便无法再还原，请[联系我们](../../business-video/get-help-support.md)。
  
下面是一些提示︰
  
- 确保许可证可用于分配给帐户。
    
- 如果您的企业使用 Active Directory，有关还原用户帐户的说明，请参阅如何在 Office 365 中对已删除[的用户帐户进行疑难解答](/office365/troubleshoot/active-directory/restore-deleted-user-accounts)。 
    
## <a name="restore-one-or-more-user-accounts"></a>还原一个或多个用户帐户

你必须是全局Microsoft 365管理员或用户管理管理员才能执行这些步骤。 

1. 在管理中心，转到"用户 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">""已删除用户"</a>页面。

2. 在 **"已删除用户"** 页上，选择要还原的用户的名称，然后选择"还原 **"。**
    
3. 按照提示设置其密码，然后选择"还原 **"。**
    
4. 如果成功还原用户，请选择" **发送电子邮件"并关闭**。 如果遇到名称冲突或代理地址冲突，请参阅下述说明获取还原这些帐户的方法。
    
还原用户后，请确保通知他们其密码已更改，然后跟进。
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>还原用户名有冲突的用户

当删除用户帐户后，又创建了与该用户名相同的新用户帐户（为同一用户或具有相似名称的另一个用户），那么当稍后尝试还原已删除的帐户时会出现用户名冲突。
  
若要解决此问题，可以将活动的用户帐户替换为要还原的用户帐户，或者为要还原的帐户分配不同的用户名，这样就不会有两个用户名相同的帐户。步骤如下。

1. 在管理中心，转到"用户 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">""已删除用户"</a>页面。
  
2. 在 **"已删除用户"** 页上，选择要还原的用户的名称，然后选择"还原 **"。**
    
    > [!NOTE]
    > 如果两个或更多个用户还原失败，则会有错误消息告诉您一些用户的还原操作失败。查看日志以看看哪些用户未还原，然后逐个还原失败的帐户。 
  
3. 按照提示设置密码，然后选择"还原 **"。**
    
4. 会弹出一条消息告诉你还原帐户时遇到问题。执行下列操作之一：
    
     - 取消还原并重命名当前活动用户。然后再次尝试还原。
    
     - 或者，键入用户的新主电子邮件地址，然后选择"还原 **"。**
    
5. 查看结果，然后选择" **关闭**"。
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>恢复具有代理地址冲突的用户

删除包含代理地址的用户帐户后，又将相同的代理地址分配给另一个帐户，那么当你尝试还原已删除的帐户时会出现代理地址冲突。请按照以下步骤操作以修复此问题。
  
为此，[你必须拥有](about-admin-roles.md)Microsoft 365权限。 

1. 在管理中心，转到"用户 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">""已删除用户"</a>页面。

2. 在" **已删除的用户**"页上，选择要还原的用户，然后选择" **还原**"。 
    
3. 在"**还原**"页上，按照说明设置密码，然后选择"还原 **"。** 将从要还原的用户自动删除任何冲突的代理地址。
    
4. 查看结果，然后选择" **关闭**"。

## <a name="related-content"></a>相关内容

[删除用户 (](delete-a-user.md) 文章) \
[将管理员角色 (](assign-admin-roles.md) 视频) \
[向用户分配许可证](../manage/assign-licenses-to-users.md) (本文) 
