---
title: Microsoft Defender for Business 中的教程和模拟
description: 了解可帮助你开始使用 Defender for Business 的一些教程
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: cfb98e3276025fbd9c75466de3c82339243e2f3b
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374867"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business"></a>Microsoft Defender for Business 中的教程和模拟

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向联机内容的链接，这些链接可能介绍 Microsoft Defender for Business 预览版中未包含 (一些) 。

如果你刚刚完成 Microsoft Defender for Business 的设置，你可能想知道从何处开始了解 Defender for Business 的工作原理。 本文介绍了要试用的预览方案，以及适用于 Defender for Business 的几个教程和模拟。 这些资源旨在帮助你了解 Defender for Business 如何为公司工作。

## <a name="try-these-preview-scenarios"></a>尝试这些预览方案

下表总结了在预览 Defender for Business 期间要尝试的几个方案。 
<br/><br/>


| 应用场景  | 说明  |
|---------|---------|
| 使用本地脚本载入设备     | 在 Defender for Business 中，Windows 10在每台设备上下载并运行的脚本载入设备和 11 台设备。 该脚本创建与 Azure Active Directory (Azure AD) 的信任，并注册设备Microsoft Intune。 若要了解更多信息，请参阅 [在 Defender for Business 中使用本地脚本载入设备](mdb-onboard-devices.md#onboard-a-device-using-a-local-script-in-defender-for-business)。         |
| 使用移动设备载入Microsoft Intune     | 如果你已在使用 Microsoft Intune Defender for Endpoint 之前，可以使用 Microsoft Intune载入设备。 请尝试将 macOS、iOS、Linux 和 Android 设备与 Microsoft Intune。 若要了解更多信息，请参阅设备[注册Microsoft Intune。](/mem/intune/enrollment/device-enrollment)        |
| 编辑安全策略和设置     | 如果你在 Defender for Business 中管理安全策略和设置，请使用设备配置 **页面查看** 和编辑策略。 若要了解更多信息，请参阅 [在 Microsoft Defender for Business 中查看或编辑策略](mdb-view-edit-policies.md)。        |
| 执行模拟攻击   | Defender for Business 中提供了多个教程和模拟。 这些教程和模拟旨在展示 Defender for Business 的威胁防护功能如何适用于你的公司。 若要试用一个或多个教程，请参阅适用于 Microsoft [Defender for Business 的推荐教程](#recommended-tutorials-for-defender-for-business)。         |
| 查看事件Microsoft 365 Lighthouse     | 如果你是使用 Microsoft 365 Lighthouse 的 Microsoft 合作伙伴，可以在客户门户中查看客户租户Microsoft 365 Lighthouse事件。 若要了解更多信息，请参阅[Microsoft 365 Lighthouse 和 Microsoft Defender for Business。](mdb-lighthouse-integration.md)       |


## <a name="recommended-tutorials-for-defender-for-business"></a>适用于 Defender for Business 的推荐教程

下表介绍了针对 Defender for Business 客户的建议教程：
<br/><br/>


| 教程  | 说明  |
|---------|---------|
| **文档删除后门**     | 模拟在测试设备上引入基于文件的恶意软件的攻击。 本教程介绍如何获取和使用模拟文件，以及要监视的模拟Microsoft 365 Defender内容。 <br/><br/>本教程要求Microsoft Word安装在测试设备上。   |
| **实时响应教程**     | 了解如何将基本和高级命令与实时响应一同使用。 了解如何查找可疑文件、修正该文件以及收集设备上的信息。   |
| **威胁&漏洞管理 (核心方案)**     | 了解危险和漏洞管理三种方案： <br/><br/>1. 减少组织的威胁和漏洞暴露。 <br/>2. 请求修正。 <br/>3. 创建安全建议例外。 <br/><br/> 威胁漏洞管理对终结点漏洞和错误配置的发现、优先顺序和修正使用基于风险的方法。      |

每个教程都包括一个演练文档，该文档介绍了方案、工作方式和操作方法。

> [!TIP]
> 你将在演练文档中看到对 Microsoft Defender for Endpoint 的引用。 本文中列出的教程可以与 Defender for Endpoint 或 Defender for Business 一同使用。

## <a name="how-to-access-the-tutorials"></a>如何访问教程

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 并登录。

2. 在导航窗格中的"终结点 **"下**，选择 **"教程"。**

3. 选择以下教程之一：

   - **文档删除后门**
   - **实时响应教程**
   - **威胁&漏洞管理 (核心方案)**

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Business 中管理设备](mdb-manage-devices.md)

- [在 Microsoft Defender for Business 中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解 Microsoft Defender for Business 中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)