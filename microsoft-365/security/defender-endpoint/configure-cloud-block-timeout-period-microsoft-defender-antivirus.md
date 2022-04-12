---
title: 配置Microsoft Defender 防病毒云块超时期
description: 可以配置Microsoft Defender 防病毒在等待云确定时阻止文件运行多长时间。
keywords: Microsoft Defender 防病毒、反恶意软件、安全性、Defender、云、超时、块、句点、秒
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 9669bb17b8e970427fb9c35c5f24d35e247b720b
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790561"
---
# <a name="configure-the-cloud-block-timeout-period"></a>配置云块超时时间段

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

当Microsoft Defender 防病毒发现可疑文件时，它可以阻止文件在查询[Microsoft Defender 防病毒云服务](cloud-protection-microsoft-defender-antivirus.md)时运行。

[阻止](configure-block-at-first-sight-microsoft-defender-antivirus.md)文件的默认时间段为 10 秒。 如果你是安全管理员，则可以在允许文件运行之前指定更多等待时间。 延长云块超时期有助于确保有足够的时间从Microsoft Defender 防病毒云服务获得适当的确定。

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>使用扩展云块超时的先决条件

必须[先看到阻止](configure-block-at-first-sight-microsoft-defender-antivirus.md)并启用其先决条件，然后才能指定延长超时期。

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>使用Microsoft Endpoint Manager指定延长超时期

可以在[Microsoft Endpoint Manager中使用终结点安全策略](/mem/intune/protect/endpoint-security-policy)指定云块超时期。

1. 转到Endpoint Manager管理中心 () [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) 并登录。

2. 选择 **“终结点安全** 性”，然后在 **“管理”** 下选择 **“防病毒”。**

3. 选择 (或创建) 防病毒策略。

4. 在“ **配置设置”** 部分中，展开 **云保护**。 然后，在 **Microsoft Defender 防病毒“延长超时（以秒** 为单位）”框中，指定从 1 秒到 50 秒的时间（以秒为单位）。 指定的任何内容都会添加到默认 10 秒。

5.  (此步骤是可选的) 对防病毒策略进行任何其他更改。  (需要帮助？ 请参阅 [Microsoft Intune.) 中有关Microsoft Defender 防病毒](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)策略的设置

6. 选择 **“下一步**”，完成策略配置。

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>使用组策略指定延长超时期

可以使用组策略指定云检查的延长超时时间。

1. 在组策略管理计算机上，打开[组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. 右键单击要配置的组策略对象，然后选择 **“编辑**”。

3. 在 **组策略管理编辑器** 中，转到 **“计算机配置**”，然后选择 **“管理模板**”。

3. 将树展开为 **mpEngine** **Microsoft Defender 防病毒Windows** \> **组件**\>。

4. 双击“ **配置扩展云检查** ”并确保已启用该选项。 

   指定额外的时间，以防止文件在等待云确定时运行。 指定从 1 秒到 50 秒的额外时间（以秒为单位）。 指定的任何内容都会添加到默认 10 秒。

5. 选择“确定”。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md) 
