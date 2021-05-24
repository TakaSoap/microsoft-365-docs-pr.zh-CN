---
title: 以通讯组列表方式发送电子邮件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: 将电子邮件作为通讯组列表Microsoft 365以便当成员回复邮件时，邮件看起来好像来自通讯组列表。
ms.openlocfilehash: 01bff7e1d2515670c5a6faa199355e7de591f1fb
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624533"
---
# <a name="send-email-as-a-distribution-list"></a>以通讯组列表方式发送电子邮件

在Microsoft 365中，你可以以通讯组列表方式发送电子邮件。 当通讯组列表成员答复发送到通讯组列表的邮件时，电子邮件看起来好像来自通讯组列表，而不是来自单个用户。 本主题演示如何执行此工作。
  
## <a name="before-you-begin"></a>准备工作

执行这些步骤之前，请确保你已添加到Microsoft 365通讯组列表，并且你已被授予以发送方式发送权限。
  
 **管理员**：确保你已按照将 [Microsoft 365](../email/add-user-or-contact-to-distribution-list.md)用户或联系人添加到列表和允许成员以 [Microsoft 365 组](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)组方式发送电子邮件主题中的步骤操作，并将正确的人员添加到通讯组列表。
  
## <a name="outlook-on-the-web"></a>Outlook 网页版

1. 打开Outlook"，然后转到收件箱。 
    
2. 打开发送到通讯组列表的邮件。 
    
3. 选择 **"答复"。** 
    
4. 在邮件底部，从 中选择 **"** \> **更多显示"。**<br/> ![选择"更多"，然后选择"显示自"](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. 右键单击"From"地址（如 ） `Ina@weewalter.me` 并选择"删除 **"。**<br/> ![删除 FROM 别名](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. 然后键入通讯组列表地址（如 support@contoso.com 地址）并发送邮件。 下次您从通讯组列表答复时，其地址将显示为"自"列表中的 **一** 个选项。<br/>![显示共享邮箱的别名](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)

## <a name="outlook"></a>Outlook

1. 打开Outlook桌面客户端。

2. 撰写新电子邮件。 单击"**自"** 字段，然后选择 **"其他电子邮件地址"。** 如果看不到"自"字段，请导航到 **"选项** "，然后选择" **显示** 字段"部分中的"自"。

3. 从全局 **地址列表中选择** 通讯组列表地址。

4. 发送电子邮件。

## <a name="related-content"></a>相关内容

[在管理中心创建、编辑](../email/create-edit-or-delete-a-security-group.md)或删除Microsoft 365安全 (，) \
[电子邮件协作](../email/email-collaboration.md) (文章) \
[向通讯组添加用户或联系人](../email/add-user-or-contact-to-distribution-list.md)