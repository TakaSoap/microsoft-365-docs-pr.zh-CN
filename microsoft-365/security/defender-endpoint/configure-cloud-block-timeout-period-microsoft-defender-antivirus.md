---
title: 配置Microsoft Defender 防病毒阻止超时期限
description: 你可以配置在Microsoft Defender 防病毒确定时阻止文件运行的时间。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 云， 超时， 阻止， 时间段， 秒
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
ms.openlocfilehash: 1acd1a95ddc3aa679f0e5f1295e14cf33b4f97a0
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168290"
---
# <a name="configure-the-cloud-block-timeout-period"></a>配置云块超时时间段

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

当Microsoft Defender 防病毒发现可疑文件时，它会阻止该文件在查询 Microsoft Defender 防病毒[云服务时运行](cloud-protection-microsoft-defender-antivirus.md)。

文件被阻止的默认 [时间段](configure-block-at-first-sight-microsoft-defender-antivirus.md) 为 10 秒。 如果您是安全管理员，您可以指定在允许文件运行之前等待的时间。 延长云阻止超时期有助于确保有足够的时间从云云服务收到Microsoft Defender 防病毒决定。

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>使用扩展云阻止超时的先决条件

[必须先启用"首次](configure-block-at-first-sight-microsoft-defender-antivirus.md) 看到时阻止"及其先决条件，然后才能指定延长的超时期限。

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>使用规则指定延长的超时Microsoft Endpoint Manager

可以使用终结点安全策略指定云阻止超时[Microsoft Endpoint Manager。](/mem/intune/protect/endpoint-security-policy)

1. 转到管理Endpoint Manager中心 [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) () 登录。

2. 选择 **"终结点安全性"，** 然后在"管理 **"下**，选择 **"防病毒"。**

3. 选择 (或) 防病毒策略。

4. 在"**配置设置"** 部分，展开"**云保护"。** 然后，在 **"Microsoft Defender 防病毒** 超时以秒表示"框中，指定从 1 秒到 50 秒的更多时间（以秒表示）。 您指定的任何时间将添加到默认值 10 秒。

5.  (此步骤是可选的) 对防病毒策略进行任何其他更改。  (需要帮助？ 请参阅[设置 .Microsoft Defender 防病毒 中的 Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)策略) 

6. 选择 **"下** 一步"，然后完成策略配置。

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>使用组策略指定延长的超时时段

可以使用组策略指定云检查的延长超时时间。

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. 右键单击要配置的组策略对象， **然后选择编辑**。

3. 在组 **策略管理编辑器中**，转到"**计算机配置**"，然后选择"**管理模板"。**

3. 展开树以Windows  \>  \> **MpEngine** Microsoft Defender 防病毒组件。

4. 双击配置 **扩展云检查并确保** 该选项已启用。 

   指定额外时间，以在等待云确定时阻止文件运行。 指定从 1 秒到 50 秒的额外时间（秒）。 您指定的任何时间将添加到默认值 10 秒。

5. 选择“**确定**”。

 
