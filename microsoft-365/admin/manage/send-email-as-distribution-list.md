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
description: 了解如何在 Microsoft 365 中以通讯组列表方式发送电子邮件。
ms.openlocfilehash: 379f2471fd38da5098bf8f2ca82f4f76ee82bd8e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915154"
---
# <a name="send-email-as-a-distribution-list"></a>以通讯组列表方式发送电子邮件

在 Microsoft 365 中，你可以以通讯组列表方式发送电子邮件。 当通讯组列表成员答复发送到通讯组列表的邮件时，电子邮件看起来好像来自通讯组列表，而不是来自单个用户。 本主题演示如何执行此工作。
  
## <a name="send-email-as-a-distribution-list"></a>以通讯组列表方式发送电子邮件

执行这些步骤之前，请确保你已添加到 Microsoft 365 通讯组列表，并且你已被授予以发送方式发送权限。
  
 **管理员**：确保你已按照将 [Microsoft 365](../email/add-user-or-contact-to-distribution-list.md) 用户或联系人添加到列表和允许成员以 Microsoft [365](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) 组组方式发送电子邮件主题中的步骤操作，并将正确的人员添加到通讯组列表。
  
1. 打开 Outlook 网页，然后转到收件箱。 
    
2. 打开发送到通讯组列表的邮件。 
    
3. 选择 **"答复"。** 
    
4. 在邮件底部，从 中选择 **"** \> **更多显示"。**<br/> ![选择"更多"，然后选择"显示自"](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. 右键单击"From"地址（如 ） `Ina@weewalter.me` 并选择"删除 **"。**<br/> ![删除 FROM 别名](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. 然后键入通讯组列表地址（如 support@contoso.com 地址）并发送邮件。 下次您从通讯组列表答复时，其地址将显示为"自"列表中的 **一** 个选项。<br/>![显示共享邮箱的别名](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)
