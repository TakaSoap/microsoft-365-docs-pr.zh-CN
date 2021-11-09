---
title: 使用Microsoft Defender 防病毒配置Microsoft Endpoint Manager
description: 使用 Microsoft Endpoint Manager 和 Microsoft Intune 配置Microsoft Defender 防病毒Endpoint Protection
keywords: scep， intune， 终结点保护， 配置
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: eed1b0d19efe21d4bb1ba81dfb36964c6d80894c
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881699"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>使用Microsoft Endpoint Manager配置和管理Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用[Microsoft Endpoint Manager配置](/mem/endpoint-manager-overview)Microsoft Defender 防病毒扫描。 [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和 Configuration [Manager](/mem/configmgr/core/understand/introduction)现在属于Endpoint Manager。

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>在Microsoft Defender 防病毒中配置Endpoint Manager

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () ，然后登录。

2. 导航到 **终结点安全性**。

3. 在 **"管理"** 下，**选择"防病毒"。**

4. 选择你的Microsoft Defender 防病毒策略。

5. 在“**管理**”下，选择“**属性**”。

6. 选择“**配置设置**”旁的“**编辑**”。

7. 展开扫描 **部分** ，然后查看或编辑扫描设置。

8. 选择 **"审阅 + 保存"**

> [!TIP]
> 需要帮助？ 请参阅[管理终结点安全Microsoft Intune。](/mem/intune/protect/endpoint-security)

## <a name="related-articles"></a>相关文章

- [有关管理和配置工具的参考文章](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
