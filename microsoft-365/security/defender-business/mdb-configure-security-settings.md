---
title: 在 Microsoft Defender for Business 中配置安全设置
description: 在 Microsoft Defender for Business 中配置安全设置和策略
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/29/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 06fa057455c506fe1cd467ab1fc780e5f5801e87
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61645880"
---
# <a name="configure-your-security-settings-and-policies-in-microsoft-defender-for-business-preview"></a>在 Microsoft Defender for Business 预览版中配置 (和) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求[](https://aka.ms/mdb-preview)它的客户和 IT 合作伙伴推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

将公司设备载入 Microsoft Defender for Business (预览版) 后，下一步是查看并编辑安全设置和策略（如有必要）。 在 Defender for Business (预览) 中，安全设置通过策略应用于设备。 这些策略适用于 [设备组](mdb-create-edit-device-groups.md#what-is-a-device-group)。 

还可以在 Defender for Business 预览版中配置 (其他) 设置。 这些设置包括时区、是否接收预览功能等。

## <a name="what-to-do"></a>需执行的操作

1. [快速概览 Defender for Business 中的默认安全策略](#default-policies-in-defender-for-business)

2. [选择管理安全策略和设备的地方](#choose-where-to-manage-security-policies-and-devices)。

3. [查看安全策略](#view-your-security-policies)。

4. [查看和编辑应用程序门户Microsoft 365 Defender设置](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal) 

5. [继续执行下一步](#next-steps)。

## <a name="default-policies-in-defender-for-business"></a>Defender for Business 中的默认策略

Defender for Business (预览) 包括使用推荐设置的默认策略。 这些策略包括：

- [下一代保护设置](mdb-next-gen-configuration-settings.md)，用于确定Microsoft Defender 防病毒和其他威胁防护功能的配置方式;以及 
- [确定](mdb-firewall.md)允许哪些网络流量流入和流出公司的客户端设备的防火墙Windows设置。

可以在初始设置过程中将默认Windows应用到客户端设备。 还可以定义新策略并编辑现有策略以满足业务需求。 

## <a name="choose-where-to-manage-security-policies-and-devices"></a>选择在何处管理安全策略和设备

Defender for Business (预览) 简化了配置过程，有助于[](mdb-simplified-configuration.md)简化安装和配置过程。 如果选择简化的配置过程，可以在 Microsoft 365 Defender 门户中查看和管理 [https://security.microsoft.com/](https://security.microsoft.com/) () 。 但是，您不限于此选项。 如果你一直在使用 Microsoft Endpoint Manager (（包括 Microsoft Intune) ）或非 Microsoft 生产力解决方案来管理安全策略和设备，可以一直使用当前解决方案。

下表可帮助你选择管理安全策略和设备的地方。 <br/><br/>

| 选项 | 说明 |
|:---|:---|
| **使用应用门户中的默认安全设置Microsoft 365 Defender策略 (***推荐)* | Defender for Business (预览) 专为忙碌的中小型企业设计。 Defender for Business 中的默认安全设置和策略旨在保护公司设备，自第一天起。<br/><br/>可以使用 Microsoft 365 Defender 门户 () 查看 [https://security.microsoft.com/](https://security.microsoft.com/) 和管理安全设置和策略。<br/><br/>若要了解更多信息，请参阅 [查看或编辑设备策略](mdb-view-edit-policies.md)。 |
| **使用Microsoft Endpoint Manager** | 如果你的公司使用 Microsoft Endpoint Manager来管理安全设置和策略，你可以继续使用 Endpoint Manager，将安全策略和设置应用于某些或所有设备。 若要了解更多信息，请参阅使用 Microsoft Intune[中的终结点安全策略管理设备Microsoft Intune。](/mem/intune/protect/endpoint-security-policy) <br/><br/>请考虑在 [Defender for Business 中切换到简化的配置过程](mdb-simplified-configuration.md)。 如果你进行了切换，系统将提示你删除 Microsoft Endpoint Manager 中现有的安全策略，然后再在 Defender for Business 中执行简化的配置过程。 在策略中删除Microsoft Endpoint Manager有助于避免以后出现策略冲突。 |

> [!TIP]
> 如果你想要注册 Microsoft Defender for Business 预览计划，请访问 [https://aka.ms/MDB-Preview](https://aka.ms/MDB-Preview) 。 若要了解的详细信息，请参阅获取[Microsoft Defender for Business (预览) 。 ](get-defender-business.md)

## <a name="view-your-security-policies"></a>查看安全策略

若要查看安全策略列表，请使用下表中的过程之一：
<br/><br/>

| 门户 | Procedure |
|:---|:---|
| Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) ()  | 1. 转到 Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () ，然后登录。 <br/><br/>2. 在导航窗格中，选择"设备 **配置"。** 策略按操作系统和策略类型进行组织。<br/><br/>3. 选择操作系统选项卡 (如Windows **客户端**) 。<br/><br/>4. 展开类别 (下一代保护或防火墙) 查看策略列表。<br/><br/>5. 选择一个策略以查看有关该策略的更多详细信息。 若要进行更改或了解有关策略设置的信息，请参阅以下文章： <br/>- [查看或编辑设备策略](mdb-view-edit-policies.md)<br/>- [了解下一代配置设置](mdb-next-gen-configuration-settings.md)<br/>- [防火墙设置](mdb-firewall.md)  |
| Microsoft Endpoint Manager管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ()  | 1。转到 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。 现在，你已Microsoft Endpoint Manager管理中心。<br/><br/>2. 选择 **"终结点安全"。**<br/><br/>3. 选择一个类别，如 **防病毒**、**防火墙**、终结点检测和响应或攻击面减少，以查看该类别中的策略。 <br/><br/>若要获取有关管理 Microsoft Endpoint Manager 中的安全设置的帮助，请从管理 Microsoft Intune[中的终结点安全开始](/mem/intune/protect/endpoint-security)。 |

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>查看和编辑应用程序门户Microsoft 365 Defender设置

除了应用于设备的安全策略之外，还可以在 Defender for Business 预览版中查看和编辑 (设置) 。 例如，你指定使用的时区，并且你可以载入 (或) 设备。 

> [!NOTE]
> 你可能会在租户中看到比本文中列出的更多的设置。 我们重点介绍了应在 Defender for Business 预览版中查看 (的设置) 。

### <a name="settings-to-review-for-defender-for-business"></a>设置查看 Defender for Business

下表介绍了用于查看 (的设置，如有必要，) Defender for Business 预览版 (编辑) 。

<br/><br/>

| 类别 | 设置 | 说明 |
|:---|:---|:---|
| **安全中心** | **时区** | 选择要用于事件中显示的日期和时间的时区、检测到的威胁以及自动调查和&修正。 可以使用 UTC 或本地时区， (*推荐) 。*  |
| **Microsoft 365 Defender** | **Account** | 查看详细信息，例如数据存储位置、租户 ID 和公司 (组织) ID。 |
| **Microsoft 365 Defender**  | **预览功能**  | 打开预览功能以试用即将推出的功能和新功能。 你可以成为第一批预览新功能并提供反馈的人。 |
| **终结点**  | **电子邮件通知** | 设置或编辑电子邮件通知规则。 检测到漏洞或创建警报时，电子邮件通知规则中指定的收件人将收到一封电子邮件。 [了解有关电子邮件通知的更多信息](mdb-email-notifications.md)。 |
| **终结点**   | **设备管理**  > **载入** | 使用可下载脚本将设备载入 Defender for Business。 若要了解更多信息，请参阅 [在 Defender for Business 中使用本地脚本载入设备](mdb-onboard-devices.md#onboard-a-device-using-a-local-script-in-defender-for-business)。   |  
| **终结点**  |  **设备管理**  > **载出** | 从 defender (预览) 从 Defender for Business (中删除) 。 当你离开设备时，它不再将数据发送到 Defender for Business (预览版) ，但在载出之前收到的数据将保留。 若要了解更多信息，请参阅 [载出设备](mdb-onboard-devices.md#what-if-i-want-to-offboard-a-device)。  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>在门户中Microsoft 365 Defender设置

1. 转到 Microsoft 365 Defender门户 [https://security.microsoft.com/](https://security.microsoft.com/) () ，然后登录。

2. 选择 **设置"，** 然后选择一个 (，如安全中心、Microsoft 365 Defender或 **终结点) 。** 

3. 在设置列表中，选择要查看或编辑的项。


## <a name="next-steps"></a>后续步骤

继续执行以下一个或多个任务：

- [开始使用 Microsoft Defender for Business (预览) ](mdb-get-started.md)

- [在 Microsoft Defender for Business 预览版中 (设备) ](mdb-manage-devices.md)

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)

- [在 Microsoft Defender for Business 预览版中查看 (编辑) ](mdb-view-edit-policies.md)

