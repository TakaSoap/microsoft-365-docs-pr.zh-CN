---
title: 使用Microsoft Defender 防病毒配置Microsoft Endpoint Manager
description: 使用Microsoft Endpoint Manager和Microsoft Intune配置Microsoft Defender 防病毒Endpoint Protection
keywords: scep， intune， 终结点保护， 配置
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: 1eb126481cc9872c42906e0311d1c771da44c693
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560179"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>使用Microsoft Endpoint Manager配置和管理Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

可以使用自定义[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)配置Microsoft Defender 防病毒扫描。 [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和 Configuration [Manager](/mem/configmgr/core/understand/introduction)现在属于Endpoint Manager。

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>在Microsoft Defender 防病毒中配置Endpoint Manager

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () ，然后登录。

2. 导航到 **终结点安全性**。

3. 在 **"管理"** 下，**选择"防病毒"。**

4. 选择你的Microsoft Defender 防病毒策略。

5. 在“**管理**”下，选择“**属性**”。

6. 选择“**配置设置**”旁的“**编辑**”。

   > [!IMPORTANT]
   > AllowOnAccessProtection 和 AllowIntrusionPreventionSystem 防病毒设置已正式弃用，因此无法配置。 

7. 展开扫描 **部分** ，然后查看或编辑扫描设置。

8. 选择 **"审阅 + 保存"。**

> [!TIP]
> 需要帮助？ 请参阅[管理终结点安全Microsoft Intune。](/mem/intune/protect/endpoint-security)

## <a name="related-articles"></a>相关文章

- [有关管理和配置工具的参考文章](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
