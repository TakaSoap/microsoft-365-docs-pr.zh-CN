---
title: 访问 MSSP Microsoft 365 Defender门户
description: 访问 MSSP Microsoft 365 Defender门户
keywords: 托管安全服务提供程序， mssp， 配置， 集成
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5a359938dbee85ea64b5f46804761410cae1f48e
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166622"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>访问 MSSP Microsoft 365 Defender门户

**适用于：**
- [ Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [ Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)。

> [!NOTE]
> 这些步骤集面向 MSSP。

默认情况下，MSSP 客户通过Microsoft 365 Defender访问其租户 `https://securitycenter.windows.com/` ：。

但是，MSSP 将需要使用以下格式的特定于租户的 URL：  `https://securitycenter.windows.com?tid=customer_tenant_id` 访问 MSSP 客户门户。

通常，需要将 MSSP 添加到其打算管理的每个 MSSP Azure AD中。

使用以下步骤获取 MSSP 客户租户 ID，然后使用该 ID 访问租户特定的 URL：

1. 作为 MSSP，登录以Azure AD凭据登录。

2. 将目录切换到 MSSP 客户的租户。

3. 选择 **Azure Active Directory >属性 "。** 你将在"目录 ID"字段中找到租户 ID。

4. 通过替换以下 URL 中的值访问 MSSP `customer_tenant_id` 客户门户 `https://securitycenter.windows.com/?tid=customer_tenant_id` ：。

## <a name="related-topics"></a>相关主题

- [授予 MSSP 对门户的访问权限](grant-mssp-access.md)
- [配置警报通知](configure-mssp-notifications.md)
- [从客户租户获取警报](fetch-alerts-mssp.md)
