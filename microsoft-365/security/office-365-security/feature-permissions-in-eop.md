---
title: EOP 中的功能权限
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 执行管理 Microsoft Exchange Online Protection (EOP) 的任务所需的权限根据正在管理的功能的不同而不同。
ms.openlocfilehash: 2129df7faaa977d59f8af8082291520d33bc9cc7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599309"
---
# <a name="feature-permissions-in-eop"></a>EOP 中的功能权限

执行管理 Exchange Online Protection （EOP）的任务所需的权限视所管理的功能而变化。

您必须是 Office 365 全局管理员或 Exchange 公司管理员（组织管理角色组），才能设置 EOP。

## <a name="exchange-online-protection-permissions"></a>Exchange Online Protection 权限

要找到管理 EOP 功能所需的权限，请参考下表：如果某个功能列出多个角色组，则您只需要被分配到其中一个角色组就可以使用此功能。

|**功能**|**所需的权限**|
|:-----|:-----|
|反恶意软件|组织管理 <br/><br/> 安全管理|
|反垃圾邮件|组织管理 <br/><br/> 安全管理|
|邮件流规则|组织管理 <br/><br/> 记录管理|
|域|组织管理 <br/><br/> 仅查看组织管理|
|高级威胁防护 (ATP)|组织管理 <br/><br/> 安全管理|
|Office 365 连接器|组织管理|
|Message trace|组织管理 <br/><br/> 仅查看组织管理|
|组织配置|组织管理|
|Quarantine|组织管理 <br/><br/> 仅查看组织管理 <br/><br/> 安全管理|
|用户、联系人和角色组|组织管理 <br/><br/> 仅查看组织管理 <br/><br/> 安全管理|
|通讯组和安全组|组织管理 <br/><br/> 仅查看组织管理 <br/><br/> 安全管理|
|查看报告|组织管理：访问邮件保护报告。 <br/><br/> 仅查看收件人：访问邮件保护报告。  <br/><br/> 合规性管理：访问邮件保护报告和数据丢失防护（DLP）报告（如果你的订阅具有 DLP 功能）。|
