---
title: 配置 Microsoft Defender 防病毒云阻止超时期限
description: 你可以配置 Microsoft Defender 防病毒在等待云确定时阻止文件运行的时间。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 云， 超时， 阻止， 时间段， 秒
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689950"
---
# <a name="configure-the-cloud-block-timeout-period"></a>配置云阻止超时时段

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

当 Microsoft Defender 防病毒发现可疑文件时，它会阻止该文件在查询 [Microsoft Defender 防病毒云服务时运行](cloud-protection-microsoft-defender-antivirus.md)。

文件将被阻止 [的默认时间段为](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10 秒。 您可以指定在允许文件运行之前要等待的一段额外时间。 这有助于确保有足够的时间从 Microsoft Defender 防病毒云服务收到正确决定。

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>使用扩展云阻止超时的先决条件

[必须先启用"首次](configure-block-at-first-sight-microsoft-defender-antivirus.md) 看到时阻止"及其先决条件，然后才能指定延长的超时期限。

## <a name="specify-the-extended-timeout-period"></a>指定延长的超时期限

可以使用组策略指定云检查的延长超时时间。

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。

3. 将树展开到 **Windows 组件> Microsoft Defender 防病毒> MpEngine**

4. 双击配置 **扩展云检查并确保** 该选项已启用。 指定在等待云确定时阻止文件运行的额外时间。 可以指定 1 秒到 50 秒的额外时间（以秒表示）。 此时将添加到默认值 10 秒。

5. 单击“**确定**”。

## <a name="related-topics"></a>相关主题

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [通过云保护使用下一代防病毒技术](cloud-protection-microsoft-defender-antivirus.md)
- [配置首次看到时阻止](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)