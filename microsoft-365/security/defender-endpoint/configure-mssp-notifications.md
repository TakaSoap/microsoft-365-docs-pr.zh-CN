---
title: 配置发送给 MSSP 的警报通知
description: 配置发送给 MSSP 的警报通知
keywords: 托管安全服务提供程序， mssp， 配置， 集成
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 03d33f89ad4edc34ebc7aa6783442100c52fea87fd3681a0b752f521d40a9280
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53857671"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>配置发送给 MSSP 的警报通知 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)。


>[!NOTE]
>此步骤可通过 MSSP 客户或 MSSP 完成。 MSSP 必须被授予适当的权限，才能代表 MSSP 客户进行配置。

授予门户访问权限后，可创建通知通知规则，以便创建与租户关联的警报并满足设置条件时，向 MSSP 发送电子邮件。

 
有关详细信息，请参阅创建 [警报通知的规则](configure-email-notifications.md#create-rules-for-alert-notifications)。
 

必须选中以下复选框：
- **包含组织** 名称 - 客户名称将添加到电子邮件通知中
- **包含租户特定的门户链接** - 警报链接 URL 将具有租户特定参数 (tid=target_tenant_id) ，以允许直接访问目标租户门户


## <a name="related-topics"></a>相关主题
- [授予 MSSP 对门户的访问权限](grant-mssp-access.md)
- [访问 MSSP 客户门户](access-mssp-portal.md)
- [从客户租户获取警报](fetch-alerts-mssp.md)
