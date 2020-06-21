---
title: 电子邮件协作
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- MOW150
- OWE150
- OWP150
- SPO160
- BSA160
- SPB160
ms.assetid: eb3e840f-ed60-4461-81f5-12381c132b89
description: 了解各种类型的组以及如何将它们与 Microsoft 365 的各种协作功能一起使用。
ms.openlocfilehash: d48f92380715153a28553f959f402faa7ae77f4c
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780225"
---
# <a name="email-collaboration"></a>电子邮件协作

Microsoft 365 鼓励通过 Outlook 中的组、通讯组列表（也称为通讯组）、共享邮箱和公用文件夹进行协作。 上述每个选项都有不同的用途、用户体验和功能集。 应使用哪个选项要取决于用户需要执行的操作，以及您的组织提供的工具。
  
## <a name="summary-of-collaboration-options"></a>协作选项摘要
<a name="BKMK_SUMMARYOFCOLLABORATIONOPTIONS"> </a>

此表介绍了可供您使用的各种协作选项。
  


|**协作工具**|**说明**|
|:-----|:-----|
|Outlook 中的组  <br/> |在 Microsoft 365 中的所有应用程序中工作的共享工作区。 包括共享收件箱、日历和用于存储文件的 OneDrive for Business 网站。 用户可以从其电子邮件或日历中创建、查找和加入 Outlook 中的组。 使用 Exchange Online 或 Microsoft 365 订阅的新用户和现有用户可以使用 Outlook 中的组。  <br/> |
|共享邮箱  <br/> |A mailbox for select users to read and send email messages and share a common calendar. Shared mailboxes also can serve as a generic email address (such as info@contoso.com or sales@contoso.com) that customers can use to inquire about your company. When the Send As permission is enabled on the shared mailbox, email sent from the mailbox will use the generic address (e.g., sales@contoso.com).  <br/> |
|通讯列表（也称为通讯组）  <br/> |Used to distribute email messages to two or more people at the same time. Distribution groups are also known as mail-enabled distribution groups. A variant of the distribution group, called the dynamic distribution group, is a mail-enabled Active Directory group object used to send email to a large and evolving group of recipients. The exact recipients are determined by filters and conditions that you specify, such as all members of a particular locale or all full-time employees.   <br/><br/> Outlook 中的 Microsoft 365 组提供了比通讯组更强大的协作解决方案。 若要了解详细信息，请参阅[为什么应将通讯组列表升级到 Outlook 中的组](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)，并将[通讯组列表迁移到 Microsoft 365 组](../manage/upgrade-distribution-lists.md)。  <br/> |
|公用文件夹  <br/> |为共享访问而设计，公用文件夹提供了一种简单有效的方式来收集、整理和与组织中的其他人共享信息。 公用文件夹按易于浏览并且在 Outlook 文件夹视图中始终可见的深入层次结构组织内容。 公用文件夹可以启用邮件并添加为通讯组的成员。 发送到通讯组的电子邮件将自动添加到公用文件夹以便存档或以后参考。 当您没有 SharePoint Online 订阅时，公用文件夹还提供简单的文档共享。  <br/> |
   
## <a name="which-collaboration-tool-to-use"></a>应该使用哪种协作工具？
<a name="BKMK_SUMMARYOFCOLLABORATIONOPTIONS"> </a>

下表提供了各种类型的组的快速浏览，并说明了何时以及如何将它们用于各种协作功能。
  

||**Outlook 中的组**|**通讯组列表**|**共享邮箱**|**公用文件夹**|
|:-----|:-----|:-----|:-----|:-----|
|**供谁使用？** <br/> |希望工作组邮件、文件和日历的协作工作区与已使用的服务集成的用户（Outlook Web App、OneDrive for Business）  <br/> |需要向有共同兴趣或特征的收件人组发送电子邮件的用户。  <br/> |共享邮箱是处理客户电子邮件问题的一种非常好的方法，因为组织中的若干人可以分担监视邮箱和响应查询的责任。 您的客户问题会获得更快的答案，相关电子邮件全部存储在一个邮箱中。  <br/><br/> Delegates working on behalf of a virtual identity, such as support@contoso.com. Delgates can respond to email as that shared mailbox identity.  <br/> |With the proper permissions, everyone in your organization can access and search public folders. They are ideal for email archiving or for sharing documents.  <br/> |
|**理想的组大小** <br/> |任何  <br/> |大型  <br/> |小  <br/> |大型  <br/> |
|**访问** <br/> |Exchange Online 和用户  <br/> |对于通讯组，必须手动添加成员。 对于动态通讯组，成员添加基于筛选条件。  <br/> |Users can be granted Full Access and/or Send As permissions. If granted Full Access permissions, users must also add the shared mailbox to their Outlook profile to access the shared mailbox.  <br/> |您的组织中的任何人都可以访问  <br/> |
|**共享的日历** <br/> |是  <br/> |否  <br/> |可访问  <br/> |是  <br/> |
|**电子邮件是否会送达用户的个人收件箱？** <br/> |No. Users can subscribe to a group and then forward all Group messages to their inbox  <br/> |Yes. Email arrives in the inbox of all distribution group members.  <br/> |No. Email arrives in the Inbox of the shared mailbox.  <br/> |No. Email arrives in the public folder.  <br/> |
|**支持的客户端** <br/> | Outlook 2016  <br/>  Outlook 2013（订阅后转发）  <br/>  Outlook Web App  <br/>  Outlook 2010（订阅后转发）  <br/>  Outlook 2007（订阅后转发）  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> |

  
## <a name="related-articles"></a>相关文章

[管理通讯组](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)
    
[使用 Microsoft 365 组而不是网站邮箱](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)
    
[在 Microsoft 365 中创建共享邮箱](create-a-shared-mailbox.md)
    
[Microsoft 365 和 Exchange Online 中的公用文件夹](https://technet.microsoft.com/library/jj200758%28v=exchg.150%29.aspx)
    

