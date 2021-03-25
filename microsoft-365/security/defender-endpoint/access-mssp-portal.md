---
title: 访问 Microsoft Defender 安全中心 MSSP 客户门户
description: 访问 Microsoft Defender 安全中心 MSSP 客户门户
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164853"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a>访问 Microsoft Defender 安全中心 MSSP 客户门户

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>这些步骤集面向 MSSP。 

默认情况下，MSSP 客户通过以下 URL 访问其 Microsoft Defender 安全中心租户 `https://securitycenter.windows.com` ：。
 

但是，MSSP 将需要使用以下格式的特定于租户的 URL：  `https://securitycenter.windows.com?tid=customer_tenant_id` 访问 MSSP 客户门户。 

通常，需要将 MSSP 添加到其打算管理的每个 MSSP 客户的 Azure AD。


使用以下步骤获取 MSSP 客户租户 ID，然后使用该 ID 访问租户特定的 URL：

1. 作为 MSSP，使用凭据登录到 Azure AD。 

2. 将目录切换到 MSSP 客户的租户。

3.  选择 **"Azure Active Directory >属性"。** 你将在"目录 ID"字段中找到租户 ID。 

4. 通过替换以下 URL 中的值访问 MSSP `customer_tenant_id` 客户门户 `https://securitycenter.windows.com?tid=customer_tenant_id` ：。


## <a name="related-topics"></a>相关主题
- [授予对门户的 MSSP 访问权限](grant-mssp-access.md)
- [配置警报通知](configure-mssp-notifications.md)
- [从客户租户提取警报](fetch-alerts-mssp.md)
