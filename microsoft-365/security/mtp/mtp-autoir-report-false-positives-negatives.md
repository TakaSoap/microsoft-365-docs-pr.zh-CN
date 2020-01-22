---
title: 如何在 Microsoft 威胁防护中报告空气中的误报或虚假否定
description: 无线在 Microsoft 威胁防护中是否已错过或错误地检测到了什么？ 了解如何向 Microsoft 提交误报或漏报以进行分析。
keywords: 自动化、调查、警报、触发器、操作、修正、误报、假负
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260190"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何报告自动调查和响应功能中的误报/否定

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

在 Microsoft 威胁防护中是否进行了[自动化调查和响应功能](mtp-autoir.md)丢失或错误地检测到了什么？ 你可以将其报告给 Microsoft 或调整你的通知（如果需要）。 使用下表作为指南： 


|Item  |检测人  |如何报告  |
|---------|---------|---------|
|电子邮件 <br/>电子邮件附件 <br/>电子邮件或 Office 文件中的 URL      |[Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[将可疑的垃圾邮件、网络钓鱼、Url 和文件提交到 Microsoft for Office 365 扫描](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|设备上的文件或应用    |[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection)         |[将文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)         |
|由合法使用触发的警报 <br/>警报不准确    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> 或 <br/>[Azure 高级威胁检测](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[在云应用安全门户中管理通知](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a>后续步骤

- [批准或拒绝与自动调查和响应相关的操作](mtp-autoir-actions.md)
- [详细了解操作中心](mtp-action-center.md)
- [通过 Microsoft 威胁防护中的高级搜寻主动搜寻威胁](advanced-hunting-overview.md)
