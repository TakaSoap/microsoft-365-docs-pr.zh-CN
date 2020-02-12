---
title: 在 EOP 中配置最终用户垃圾邮件通知
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: 您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: 95a8142b4f4687c66657cd01e1110470c8b08bc4
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957397"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a>在 EOP 中配置最终用户垃圾邮件通知
  
> [!IMPORTANT]
> 该主题适用于要保护本地邮箱的 Exchange Online Protection (EOP) 独立客户。 正在保护云托管邮箱的 Exchange Online 客户应阅读以下主题：[在 Exchange Online 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-exchange-online.md)。 
  
您可以为默认的公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。 启用最终用户垃圾邮件通知邮件，使用户可以管理其自己的隔离垃圾邮件、批量邮件和网络钓鱼邮件。 
  
最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。
  
收到通知邮件后，最终用户可以从以下选项中进行选择：

如果希望 Office 365 将发件人添加到阻止发件人列表，请**阻止发件人**。

如果邮件不是垃圾邮件，并且您希望 Office 365 将邮件发送到您的邮箱，则**释放**。

如果要执行其他操作，如预览或发布，请**查看**以导航到安全与合规中心内的隔离门户。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟
  
您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"反垃圾邮件"条目。 
  
有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>使用 EAC 配置最终用户垃圾邮件通知

1. 在 Exchange 管理中心（EAC）中，导航到 "**保护** > **垃圾邮件筛选器**"。
    
2. 选择您想要启用最终用户垃圾邮件通知（默认禁用）的内容筛选器策略。
    
3. 在显示您的策略摘要信息的右窗格中，单击“配置最终用户垃圾邮件通知”**** 链接。 
    
4. 在随后出现的对话框中，您可以配置以下选项：
    
1. **启用最终用户垃圾邮件通知**选中此复选框，以便为此策略启用最终用户垃圾邮件通知。 ） 
    
2. **每隔（天）发送最终用户垃圾邮件通知**指定发送最终用户垃圾邮件通知的频率。 默认值为 3 天。 您可以指定一个介于 1 到 15 天之间的值。 例如，如果您指定 7 天，则该通知将包括在过去 7 天内预期发送给该用户但实际发送到垃圾邮件隔离邮箱的所有邮件列表。 
    
3. **通知语言**使用下拉列表，选择为此策略编写最终用户垃圾邮件通知所使用的语言。 
    
5. 单击“保存”****。 右窗格中将显示内容筛选器策略设置的摘要，包括您的最终用户垃圾邮件通知设置。
    
> [!NOTE]
>  最终用户垃圾邮件通知只对已启用的内容筛选器策略可用。 >  每天只发送一次最终用户垃圾邮件通知。无法保证和配置任何特定客户的通知发送时间。 
  
 **提示：** 如果要在完全实现最终用户垃圾邮件通知之前将其发送给一组有限的用户，请创建自定义内容筛选器策略，为用户驻留的域启用最终用户垃圾邮件通知。 然后，在 EAC 中的 "**邮件流\>规则**" 下，创建邮件流规则（也称为传输规则），以阻止来自 quarantine@messaging.microsoft.com （发送通知的电子邮件地址）的邮件，但要接收通知的用户例外。 下图是为 Contoso.com 域中的两个用户（SaraD 和 AlexD）创建一个异常的示例： 
  
![测试最终用户垃圾邮件通知的传输规则](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>更多信息

[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  
