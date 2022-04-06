---
title: Microsoft Defender 商业版中的教程和模拟
description: 了解几个教程，以帮助你开始使用 Defender for Business
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 98ead4a77c275e0e4aeeab90e87e0b468a9b7bb8
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665967"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business"></a>Microsoft Defender 商业版中的教程和模拟

> [!IMPORTANT]
> Microsoft Defender 商业版现为预览版，将逐步向[注册此](https://aka.ms/mdb-preview)处的客户和 IT 合作伙伴推出以请求它。 我们将在未来几周内加入一组初始客户和合作伙伴，并将扩展预览版，直至正式发布。 请注意，预览版将使用 [一组初始方案](#try-these-preview-scenarios)启动，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

如果刚刚完成Microsoft Defender 商业版设置，你可能想知道从何处开始了解 Defender for Business 的工作原理。 本文介绍要尝试的预览方案，以及适用于 Defender for Business 的多个教程和模拟。 这些资源旨在帮助你了解 Defender for Business 如何为公司工作。

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="try-these-preview-scenarios"></a>试用这些预览方案

下表总结了几个尝试使用 Defender for Business 的方案。 
<br/><br/>


| 应用场景  | 说明  |
|---------|---------|
| 使用本地脚本载入设备 <br/> (*不用于生产部署*)      | 在 Defender for Business 中，最多可以使用在每个设备上下载和运行的脚本载入 10 Windows 10 和 11 台设备。 该脚本适用于评估 Defender for Business 在环境中的工作原理，可使用Azure Active Directory (Azure AD) 创建信任，并使用Microsoft Intune注册设备。 若要了解详细信息，请 [参阅 Defender for Business 中的本地脚本](mdb-onboard-devices.md#local-script-in-defender-for-business)。         |
| 使用Microsoft Intune载入设备     | 如果在获取 Defender for Endpoint 之前已使用Microsoft Intune，则可以继续使用Microsoft Intune载入设备。 尝试使用Microsoft Intune载入 macOS、iOS 和 Android 设备。 若要了解详细信息，请参阅[Microsoft Intune中的设备注册](/mem/intune/enrollment/device-enrollment)。        |
| 编辑安全策略     | 如果在 Defender for Business 中管理安全策略，请使用 **"设备配置** "页查看和编辑策略。 若要了解详细信息，请参阅[Microsoft Defender 商业版中的视图或编辑策略](mdb-view-edit-policies.md)。        |
| 执行模拟攻击   | Defender for Business 中提供了多个教程和模拟。 这些教程和模拟旨在向你展示 Defender for Business 的威胁防护功能如何为公司工作。 若要尝试一个或多个教程，请参阅[Microsoft Defender 商业版的建议教程](#recommended-tutorials-for-defender-for-business)。         |
| 查看Microsoft 365 Lighthouse中的事件     | 如果你是使用[Microsoft 365 Lighthouse的Microsoft 云解决方案提供商](/partner-center/enrolling-in-the-csp-program)，你将能够很快在Microsoft 365 Lighthouse门户中查看客户租户中的事件。 若要了解详细信息，请参阅[Microsoft 365 Lighthouse和Microsoft Defender 商业版](mdb-lighthouse-integration.md)。       |


## <a name="recommended-tutorials-for-defender-for-business"></a>Defender for Business 的建议教程

下表介绍了 Defender for Business 客户的建议教程：
<br/><br/>


| 教程  | 说明  |
|---------|---------|
| **文档删除后门**     | 模拟在测试设备上引入基于文件的恶意软件的攻击。 本教程介绍如何获取和使用模拟文件，以及在Microsoft 365 Defender门户中要监视的内容。 <br/><br/>本教程要求在测试设备上安装Microsoft Word。   |
| **实时响应教程**     | 了解如何将基本命令和高级命令与实时响应配合使用。 了解如何查找可疑文件、修正文件以及如何在设备上收集信息。   |
| **威胁&漏洞管理 (核心方案)**     | 通过三种方案了解危险和漏洞管理： <br/><br/>1. 减少公司的威胁和漏洞暴露。 <br/>2. 请求修正。 <br/>3. 为安全建议创建异常。 <br/><br/> 威胁和漏洞管理使用基于风险的方法来发现、确定终结点漏洞和错误配置的优先级和修正。      |

每个教程都包含一个演练文档，其中介绍了方案、工作原理和操作方法。

> [!TIP]
> 你将在演练文档中看到对Microsoft Defender for Endpoint的引用。 本文中列出的教程可用于 Defender for Endpoint 或 Defender for Business。

## <a name="how-to-access-the-tutorials"></a>如何访问教程

1. 转到Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格 **的"终结点**"下，选择 **"教程**"。

3. 选择以下教程之一：

   - **文档删除后门**
   - **实时响应教程**
   - **威胁&漏洞管理 (核心方案)**

## <a name="next-steps"></a>后续步骤

- [在Microsoft Defender 商业版中管理设备](mdb-manage-devices.md)

- [在Microsoft Defender 商业版中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解Microsoft Defender 商业版中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)