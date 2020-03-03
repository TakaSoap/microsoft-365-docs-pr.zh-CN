---
title: 以 Office 365 中的通讯组列表形式发送电子邮件
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: 了解如何在 Office 365 中以通讯组列表的身份发送电子邮件。
ms.openlocfilehash: 076405b54f2a1521e0d9a1fc54c734b172eb82e8
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361737"
---
# <a name="send-email-as-a-distribution-list-in-office-365"></a>以 Office 365 中的通讯组列表形式发送电子邮件

在 Office 365 中，可以将电子邮件作为通讯组列表发送。 当通讯组列表的成员答复发送到通讯组列表的邮件时，该电子邮件似乎来自通讯组列表，而不是来自单个用户。 本主题介绍如何执行此操作。
  
## <a name="send-email-as-a-distribution-list"></a>以通讯组列表的形式发送电子邮件

在执行这些步骤之前，请确保已将其添加到 Office 365 通讯组列表，并且已向您授予 "代理发送" 权限。
  
 **管理员**：确保已按照 "[向列表中添加 Office 365 用户或联系人](../email/add-user-or-contact-to-distribution-list.md)" 中的步骤操作，并[允许成员以 Office 365 组主题的形式发送电子邮件](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)，并向通讯组列表添加了正确的人员。
  
1. 打开 web 上的 Outlook 并转到 "收件箱"。 
    
2. 打开发送到通讯组列表的邮件。 
    
3. 选择 "**答复**"。 
    
4. 在邮件底部，选择 "**更多** \> **显示来自**"。<br/> ![选择 "更多"，然后选择 "显示来源"](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. 右键单击 "发件人地址-例如`Ina@weewalter.me` -"，然后选择 "**删除**"。<br/> ![删除 FROM 别名](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. 然后键入通讯组列表地址，如 support@contoso.com，并发送邮件。 下次从通讯组列表中答复时，其地址将显示为 "**发件**人" 列表中的一个选项。<br/>![共享邮箱的别名显示](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)
  

