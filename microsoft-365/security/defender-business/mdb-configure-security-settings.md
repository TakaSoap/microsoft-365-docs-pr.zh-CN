---
title: 在 Microsoft Defender for Business 中配置安全设置
description: 在 Microsoft Defender for Business 中配置安全设置和策略
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 18b259278f7f6053cdd7629eea114c3f61c82bb0
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2021
ms.locfileid: "61508343"
---
# <a name="configure-your-security-settings-and-policies-in-microsoft-defender-for-business-preview"></a>在 Microsoft Defender for Business 预览版中配置 (和) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求[](https://aka.ms/mdb-preview)它的客户和 IT 合作伙伴推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

将公司设备载入 Microsoft Defender for Business (预览版) 后，下一步是查看并编辑安全设置和策略（如有必要）。 

## <a name="what-to-do"></a>需执行的操作

1. [选择管理安全设置和策略的地方](#choose-where-to-manage-security-settings-and-policies)。

2. [查看安全设置和策略](#view-your-security-settings-and-policies)。 

3. [继续执行下一步](#next-steps)。

## <a name="choose-where-to-manage-security-settings-and-policies"></a>选择在何处管理安全设置和策略

在管理安全设置和策略时，可以从多个选项中进行选择，如下表所述： <br/><br/>

| 选项 | 说明 |
|:---|:---|
| **使用应用门户中的默认安全设置Microsoft 365 Defender策略 (***推荐)* | Defender for Business (预览) 专为忙碌的中小型企业设计。 Defender for Business 中的默认安全设置和策略旨在保护公司设备，自第一天起。<br/><br/>可以使用 Microsoft 365 Defender门户 () 查看 [https://security.microsoft.com/](https://security.microsoft.com/) 和管理安全设置和策略。<br/><br/>若要了解更多信息，请参阅 [查看或编辑设备策略](mdb-view-edit-policies.md)。 |
| **使用Microsoft Endpoint Manager** | 如果你的公司使用 Microsoft Endpoint Manager 来管理安全设置和策略，你可以继续使用 Endpoint Manager，将安全策略和设置应用于某些或所有设备。 若要了解更多信息，请参阅使用 Microsoft Intune[中的终结点安全策略管理设备Microsoft Intune。](/mem/intune/protect/endpoint-security-policy) <br/><br/>请考虑在 [Defender for Business 中切换到简化的配置过程](mdb-simplified-configuration.md)。 如果进行了切换，系统将提示你删除 Microsoft Endpoint Manager 中现有的安全策略，然后再继续 Defender for Business 中的简化配置过程。 在策略中删除Microsoft Endpoint Manager有助于避免以后出现策略冲突。 |

> [!TIP]
> 如果你想要注册 Microsoft Defender for Business 预览计划，请访问 [https://aka.ms/MDB-Preview](https://aka.ms/MDB-Preview) 。 若要了解的详细信息，请参阅获取[Microsoft Defender for Business (预览) 。 ](get-defender-business.md)

## <a name="view-your-security-settings-and-policies"></a>查看安全设置和策略

若要查看安全设置和策略，请使用下表中的过程之一：
<br/><br/>

| 门户 | Procedure |
|:---|:---|
| Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) ()  | 1. 转到 Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () ，然后登录。 <br/><br/>2. 在导航窗格中，选择"设备 **配置"。** 策略按操作系统和策略类型进行组织。<br/><br/>3. 选择操作系统选项卡 (，Windows **客户端) 。**<br/><br/>4. 展开类别 (下一代保护或 **防火墙) 查看** 策略列表。<br/><br/>5. 选择一个策略以查看有关该策略的更多详细信息。 若要进行更改或了解有关策略设置的信息，请参阅以下文章： <br/>- [查看或编辑设备策略](mdb-view-edit-policies.md)<br/>- [了解下一代配置设置](mdb-next-gen-configuration-settings.md)<br/>- [防火墙设置](mdb-firewall.md)  |
| Microsoft Endpoint Manager管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ()  | 1。转到 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。 现在，你已Microsoft Endpoint Manager管理中心。<br/><br/>2. 选择 **"终结点安全"。**<br/><br/>3. 选择一个类别，如 **防病毒**、**防火墙**、终结点检测和响应或攻击面减少，以查看该类别中的策略。 <br/><br/>若要获取有关管理 Microsoft Endpoint Manager 中的安全设置的帮助，请从管理 Microsoft Intune[中的终结点安全开始](/mem/intune/protect/endpoint-security)。 |

## <a name="next-steps"></a>后续步骤

继续执行以下一个或多个任务：

- [开始使用 Microsoft Defender for Business (预览) ](mdb-get-started.md)

- [在 Microsoft Defender for Business 预览版中 (设备) ](mdb-manage-devices.md)

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)

- [在 Microsoft Defender for Business 预览版中查看 (编辑) ](mdb-view-edit-policies.md)

