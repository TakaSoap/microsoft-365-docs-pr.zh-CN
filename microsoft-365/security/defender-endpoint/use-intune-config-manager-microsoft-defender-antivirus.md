---
title: 使用Microsoft Endpoint Manager配置Microsoft Defender 防病毒
description: 使用Microsoft Endpoint Manager和Microsoft Intune配置Microsoft Defender 防病毒和Endpoint Protection
keywords: scep，intune，终结点保护，配置
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
ms.openlocfilehash: b25e57ee28ae0ef3f219a9adda1ff3f860d063db
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789285"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>使用Microsoft Endpoint Manager配置和管理Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

可以使用[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)配置Microsoft Defender 防病毒扫描。 [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和[Configuration Manager](/mem/configmgr/core/understand/introduction)现在是Endpoint Manager的一部分。

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>在Endpoint Manager中配置Microsoft Defender 防病毒扫描

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ，然后登录。

2. 导航到 **Endpoint Security**。

3. 在 **“管理”** 下，选择 **“防病毒”。**

4. 选择Microsoft Defender 防病毒策略。

5. 在“**管理**”下，选择“**属性**”。

6. 选择“**配置设置**”旁的“**编辑**”。

   > [!IMPORTANT]
   > AllowOnAccessProtection 和 AllowIntrusionPreventionSystem 防病毒设置已正式弃用，因此无法配置。 

7. 展开 **“扫描** ”部分，查看或编辑扫描设置。

8. 选择 **“审阅 + 保存**”。

> [!TIP]
> 需要帮助？ 请参阅[Microsoft Intune中的管理终结点安全](/mem/intune/protect/endpoint-security)性。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-articles"></a>相关文章

- [有关管理和配置工具的参考文章](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
