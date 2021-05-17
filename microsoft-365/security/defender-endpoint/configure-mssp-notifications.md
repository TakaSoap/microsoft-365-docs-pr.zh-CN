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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166049"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>配置发送给 MSSP 的警报通知 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


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
