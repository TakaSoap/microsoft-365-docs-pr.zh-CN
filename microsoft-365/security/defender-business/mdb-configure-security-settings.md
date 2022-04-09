---
title: 在Microsoft Defender 商业版中查看和编辑安全设置
description: 在Microsoft Defender 商业版中配置安全策略
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 3d6ef3a7bc3ae9b7556041cedc88df354421f885
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64746483"
---
# <a name="view-and-edit-your-security-policies-and-settings-in-microsoft-defender-for-business"></a>在Microsoft Defender 商业版中查看和编辑安全策略和设置

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

## <a name="overview"></a>概述

将公司的设备载入到Microsoft Defender 商业版后，下一步是查看安全策略和设置（如有必要）。 要配置的安全策略包括：

- **[下一代保护策略](#view-or-edit-your-next-generation-protection-policies)**，用于确定公司设备的防病毒和反恶意软件保护
- **[防火墙保护和规则](#view-or-edit-your-firewall-policies-and-custom-rules)**，确定允许流向或流出公司设备的网络流量
- **[Web 内容筛选](#set-up-web-content-filtering)**，防止用户访问某些网站 (URL) 基于类别，如成人内容或法律责任。

在 Defender for Business 中，安全策略通过 [设备组应用于设备](mdb-create-edit-device-groups.md#what-is-a-device-group)。 

除了安全策略之外，还可以[查看和编辑设置](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)，例如要在Microsoft 365 Defender门户中使用的时区 ([https://security.microsoft.com](https://security.microsoft.com)) ，以及是否在功能可用时接收预览功能。

使用本文作为管理安全策略和设置的指南。

## <a name="what-to-do"></a>需执行的操作

1. [选择管理安全策略和设备的位置](#choose-where-to-manage-security-policies-and-devices)。

2. [查看或编辑下一代保护策略](#view-or-edit-your-next-generation-protection-policies)。

3. [查看或编辑防火墙策略和自定义规则](#view-or-edit-your-firewall-policies-and-custom-rules)。

4. [设置 Web 内容筛选](#set-up-web-content-filtering)。

5. [在Microsoft 365 Defender门户中查看和编辑其他设置](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)。 

6. [继续执行后续步骤](#next-steps)。

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="choose-where-to-manage-security-policies-and-devices"></a>选择管理安全策略和设备的位置

Defender for Business 采用 [简化的配置过程](mdb-simplified-configuration.md) ，有助于简化设置和配置过程。 如果选择简化的配置过程，则可以在Microsoft 365 Defender门户中查看和管理安全策略 ([https://security.microsoft.com/](https://security.microsoft.com/)) 。 但是，不限于此选项。 如果一直在使用包含Microsoft Intune) 的Microsoft Endpoint Manager (，则可以继续使用Endpoint Manager。

下表可帮助你选择在何处管理安全策略和设备。 <br/><br/>

| 选项 | 说明 |
|:---|:---|
| **使用Microsoft 365 Defender门户** (*建议* 的)  | Microsoft 365 Defender门户 ([https://security.microsoft.com/](https://security.microsoft.com/)) 可以是管理公司设备、安全策略和安全设置的一站式商店。 可以访问安全策略和设置，使用 [威胁&漏洞管理仪表板](mdb-view-tvm-dashboard.md)，并在一个位置 [查看和管理所有事件](mdb-view-manage-incidents.md) 。 <br/><br/>如果使用Microsoft Endpoint Manager，则载入 Defender for Business 的设备和安全策略在Endpoint Manager中可见。 若要了解详细信息，请参阅以下文章：<br/><br/>- [Defender for Business 默认设置和Microsoft Endpoint Manager](mdb-next-gen-configuration-settings.md#defender-for-business-default-settings-and-microsoft-endpoint-manager)<br/><br/>- [Microsoft Defender 商业版中的防火墙](mdb-firewall.md)   |
| **使用Microsoft Endpoint Manager** | 如果你的公司已经在使用Endpoint Manager (（包括管理安全策略的Microsoft Intune) ），则可以继续使用Endpoint Manager来管理设备和安全策略。 若要了解详细信息，请参阅[Microsoft Intune中使用终结点安全策略管理设备安全](/mem/intune/protect/endpoint-security-policy)性。 <br/><br/>如果决定[在 Defender for Business 中切换到简化的配置过程](mdb-simplified-configuration.md)，系统会提示你删除Endpoint Manager中的任何现有安全策略，以避免以后[出现策略冲突](mdb-troubleshooting.yml)。 |

> [!IMPORTANT]
> 如果在Microsoft 365 Defender门户中管理安全策略，则可以在Endpoint Manager中 *查看* 这些策略，这些策略被列为防病毒策略或防火墙策略。 在Endpoint Manager中查看防火墙策略时，会看到列出了两个策略：一个策略用于防火墙保护，另一个策略用于自定义规则。

## <a name="view-or-edit-your-next-generation-protection-policies"></a>查看或编辑下一代保护策略

根据是使用Microsoft 365 Defender门户还是Microsoft Endpoint Manager来管理下一代保护策略，请使用下表中的其中一个过程： <br/><br/>

| 门户 | Procedure |
|:---|:---|
| Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) | 1. 转到Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) ，然后登录。 <br/><br/>2. 在导航窗格中，选择 **“设备配置**”。 策略按操作系统和策略类型进行组织。<br/><br/>3.选择操作系统选项卡 (，例如 **Windows客户** 端) 。<br/><br/>4. 展开 **下一代保护** 以查看策略列表。<br/><br/>5. 选择策略以查看有关策略的更多详细信息。 若要进行更改或详细了解策略设置，请参阅以下文章： <br/>- [查看或编辑设备策略](mdb-view-edit-policies.md)<br/>- [了解下一代配置设置](mdb-next-gen-configuration-settings.md)  |
| Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) | 1. 转到 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。 你现在在Microsoft Endpoint Manager管理中心。<br/><br/>2.选择 **终结点安全性**。<br/><br/>3. 选择 **防病毒以** 查看此类别中的策略。 <br/><br/>若要在Microsoft Endpoint Manager中获取管理安全设置的帮助，请从[Microsoft Intune中的管理终结点安全](/mem/intune/protect/endpoint-security)性开始。 |

## <a name="view-or-edit-your-firewall-policies-and-custom-rules"></a>查看或编辑防火墙策略和自定义规则

根据是使用Microsoft 365 Defender门户还是Microsoft Endpoint Manager来管理防火墙保护，请使用下表中的其中一个过程： <br/><br/>

| 门户 | Procedure |
|:---|:---|
| Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) | 1. 转到Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) ，然后登录。 <br/><br/>2. 在导航窗格中，选择 **“设备配置**”。 策略按操作系统和策略类型进行组织。<br/><br/>3.选择操作系统选项卡 (，例如 **Windows客户** 端) 。<br/><br/>4. 展开 **防火墙** 以查看策略列表。<br/><br/>5. 选择策略以查看有关策略的更多详细信息。 若要进行更改或详细了解策略设置，请参阅以下文章： <br/>- [查看或编辑设备策略](mdb-view-edit-policies.md)<br/>- [防火墙设置](mdb-firewall.md)<br/>- [管理防火墙策略的自定义规则](mdb-custom-rules-firewall.md)  |
| Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) | 1. 转到 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。 你现在在Microsoft Endpoint Manager管理中心。<br/><br/>2.选择 **终结点安全性**。<br/><br/>3.选择 **防火墙** 以查看此类别中的策略。 为防火墙保护定义的自定义规则将作为单独的策略列出。<br/><br/>若要在Microsoft Endpoint Manager中获取管理安全设置的帮助，请从[Microsoft Intune中的管理终结点安全](/mem/intune/protect/endpoint-security)性开始。 |

## <a name="set-up-web-content-filtering"></a>设置 Web 内容筛选

通过 Web 内容筛选，安全团队可以根据网站的内容类别跟踪和规范对网站的访问，例如：

- 成人内容：与邪教、赌博、裸体、色情、色情、色情材料或暴力相关的网站

- 高带宽：下载网站、图像共享网站或对等主机

- 法律责任：包括虐待儿童图像、促进非法活动、助长抄袭或学校作弊或助长有害活动的网站

- 休闲：提供基于 Web 的聊天室、在线游戏、基于 Web 的电子邮件或社交网络的网站

- 未分类：没有内容或新注册的网站

并非这些类别中的所有网站都是恶意的，但由于合规性法规、带宽使用或其他问题，这些网站可能会对公司造成问题。 此外，还可以创建仅审核策略，以便更好地了解安全团队是否应阻止任何网站类别。

Web 内容筛选在主要 Web 浏览器上可用，其中包含由 Windows Defender SmartScreen (Microsoft Edge) 和网络保护 (Chrome、Firefox、Brave 和 Opera) 执行的块。 有关详细信息，请参阅 [Web 内容筛选的先决条件](../defender-endpoint/web-content-filtering.md#prerequisites)。

### <a name="to-set-up-web-content-filtering"></a>设置 Web 内容筛选

1. 在Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) 中，选择 **设置** > **Web 内容筛选** > **+ 添加策略**。

2. 为策略指定名称和说明。

3. 选择要阻止的类别。 使用展开图标完全展开每个父类别，并选择特定的 Web 内容类别。

   若要设置不阻止任何网站的仅审核策略，请不要选择任何类别。

   请勿选择 **“未分类**”。

4. 通过选择要应用策略的设备组来指定策略范围。 将只阻止所选设备组中的设备访问所选类别中的网站。

5. 查看摘要并保存策略。 策略刷新可能需要长达 2 小时才能应用于所选设备。

> [!TIP]
> 若要了解有关 Web 内容筛选的详细信息，请参阅 [Web 内容筛选](../defender-endpoint/web-content-filtering.md)。

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>在Microsoft 365 Defender门户中查看和编辑其他设置

除了应用于设备的安全策略外，还可以在 Defender for Business 中查看和编辑其他设置。 例如，指定要使用的时区，并且可以载入 (或离载) 设备。 

> [!NOTE]
> 与本文中列出的设置相比，租户中的设置可能更多。 本文重点介绍在 Defender for Business 中应查看的最重要设置。

### <a name="settings-to-review-for-defender-for-business"></a>设置查看 Defender for Business

下表介绍了查看 (的设置，如有必要，请在 Defender for Business 中编辑) 。

<br/><br/>

| 类别 | 设置 | 说明 |
|:---|:---|:---|
| **安全中心** | **时区** | 选择要用于事件中显示的日期和时间、检测到的威胁和自动调查&修正的时区。 可以使用 UTC 或本地时区 (*建议* 的) 。  |
| **Microsoft 365 Defender** | **Account** | 查看详细信息，例如存储数据的位置、租户 ID 和组织 (组织) ID。 |
| **Microsoft 365 Defender**  | **预览功能**  | 打开预览版功能，尝试即将推出的功能和新功能。 你可以成为最早预览新功能并提供反馈的人之一。 |
| **终结点**  | **电子邮件通知** | 设置或编辑电子邮件通知规则。 检测到漏洞或创建警报时，电子邮件通知规则中指定的收件人将收到电子邮件。 [详细了解电子邮件通知](mdb-email-notifications.md)。 |
| **终结点**   | **设备管理** > **载入** | 使用可下载脚本将设备载入 Defender for Business。 若要了解详细信息，请参阅[载入设备以Microsoft Defender 商业版](mdb-onboard-devices.md)。   |  
| **终结点**  |  **设备管理** > **卸载** | 从 Defender for Business 中 (删除) 设备。 当你离开设备时，它将不再将数据发送到 Defender for Business，但会保留在卸载之前收到的数据。 若要了解详细信息，请参阅 [“载入设备](mdb-onboard-devices.md#offboarding-a-device)”。  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>在Microsoft 365 Defender门户中访问设置

1. 转到Microsoft 365 Defender门户 ([https://security.microsoft.com/](https://security.microsoft.com/)) ，然后登录。

2. 选择 **设置**，然后选择一个类别 (，例如 **安全中心**、**Microsoft 365 Defender** 或 **终结点**) 。

3. 在设置列表中，选择要查看或编辑的项。


## <a name="next-steps"></a>后续步骤

继续执行以下一个或多个任务：

- [使用Microsoft Defender 商业版开始](mdb-get-started.md)
- [在Microsoft Defender 商业版中管理设备](mdb-manage-devices.md)
- [在Microsoft Defender 商业版中查看和管理事件](mdb-view-manage-incidents.md)
- [在Microsoft Defender 商业版中查看或编辑策略](mdb-view-edit-policies.md)
