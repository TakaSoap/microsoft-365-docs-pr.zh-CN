---
title: 在 Microsoft Defender for Business 中查看和编辑安全设置
description: 在 Microsoft Defender for Business 中配置安全策略
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: c943841a89acb7052f63ba76898e9b23e5dc3b4c
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2022
ms.locfileid: "63449494"
---
# <a name="view-and-edit-your-security-policies-and-settings-in-microsoft-defender-for-business"></a>在 Microsoft Defender for Business 中查看和编辑安全策略和设置

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

## <a name="overview"></a>概述

将组织的设备载入 Microsoft Defender for Business 后，下一步是查看安全策略和设置，并在必要时编辑安全策略和设置。 安全策略包括：

- **[下一代保护](#view-or-edit-your-next-generation-protection-policies)** 策略，可确定组织的设备的防病毒和反恶意软件保护
- **[防火墙保护和规则](#view-or-edit-your-firewall-policies-and-custom-rules)**，用于确定允许哪些网络流量流入或流出组织设备
- **[Web 内容筛选](#set-up-web-content-filtering)**，可阻止用户访问某些网站 (基于) 的 URL，例如成人内容或法律责任。

在 Defender for Business 中，安全策略通过设备组 [应用于设备](mdb-create-edit-device-groups.md#what-is-a-device-group)。 

除了安全策略之外，还可以查看和编辑设置，[](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)例如，在 Microsoft 365 Defender 门户 ([https://security.microsoft.com](https://security.microsoft.com)) 中要使用哪个时区，以及是否在预览功能可用时接收它们。

使用本文作为管理安全策略和设置的指南。

## <a name="what-to-do"></a>需执行的操作

1. [选择管理安全策略和设备的地方](#choose-where-to-manage-security-policies-and-devices)。

2. [查看或编辑下一代保护策略](#view-or-edit-your-next-generation-protection-policies)。

3. [查看或编辑防火墙策略和自定义规则](#view-or-edit-your-firewall-policies-and-custom-rules)。

4. [设置 Web 内容筛选](#set-up-web-content-filtering)。

5. [查看和编辑应用门户Microsoft 365 Defender设置](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)。 

6. [继续执行下一步](#next-steps)。

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="choose-where-to-manage-security-policies-and-devices"></a>选择在何处管理安全策略和设备

Defender for Business 采用 [简化的配置过程，](mdb-simplified-configuration.md) 有助于简化安装和配置过程。 如果选择简化的配置过程，[https://security.microsoft.com/](https://security.microsoft.com/)可以在 Microsoft 365 Defender 门户中查看和管理 () 。 但是，您不限于此选项。 如果你一直在使用包括Microsoft Endpoint Manager (的 Microsoft Intune) ，可以一直使用Endpoint Manager。

下表可帮助你选择管理安全策略和设备的地方。 <br/><br/>

| 选项 | 说明 |
|:---|:---|
| **使用Microsoft 365 Defender门户 (***建议)* | Microsoft 365 Defender门户 ([https://security.microsoft.com/](https://security.microsoft.com/)) 管理组织设备、安全策略和安全设置的一站式商店。 你可以访问安全策略和设置，使用威胁&[漏洞](mdb-view-tvm-dashboard.md)管理仪表板，在一个地方查看和管理所有事件。[](mdb-view-manage-incidents.md)  |
| **使用Microsoft Endpoint Manager** | 如果你的组织已在使用 Endpoint Manager (，Microsoft Intune) 管理安全策略，你可以继续使用 Endpoint Manager 来管理设备和安全策略。 若要了解更多信息，请参阅使用 Microsoft Intune [中的终结点安全策略管理设备安全](/mem/intune/protect/endpoint-security-policy)。 <br/><br/>如果你决定切换到 [Defender for Business](mdb-simplified-configuration.md) 中的简化配置过程以改用 Microsoft 365 Defender 门户，系统将提示你删除 Endpoint Manager 中任何现有的安全策略，以避免以后出现[策略冲突。](mdb-troubleshooting.yml) |

> [!NOTE]
> 如果要在安全门户中管理Microsoft 365 Defender策略，可以在"安全Endpoint Manager中查看这些策略，列为"防病毒"或"防火墙策略"。 当你在防火墙策略中查看Endpoint Manager，你将看到两个策略列出：一个策略用于防火墙保护，另一个策略用于自定义规则。

## <a name="view-or-edit-your-next-generation-protection-policies"></a>查看或编辑下一代保护策略

根据是使用应用门户Microsoft 365 Defender还是Microsoft Endpoint Manager管理下一代保护策略，请使用下表中的过程之一： <br/><br/>

| 门户 | Procedure |
|:---|:---|
| Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com))  | 1. 转到 Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。 <br/><br/>2. 在导航窗格中，选择" **设备配置"**。 策略按操作系统和策略类型进行组织。<br/><br/>3. 选择操作系统选项卡 (，Windows **客户端)**。<br/><br/>4. 展开 **下一代保护** 以查看策略列表。<br/><br/>5. 选择一个策略以查看有关该策略的更多详细信息。 若要进行更改或了解有关策略设置的信息，请参阅以下文章： <br/>- [查看或编辑设备策略](mdb-view-edit-policies.md)<br/>- [了解下一代配置设置](mdb-next-gen-configuration-settings.md)  |
| Microsoft Endpoint Manager管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))  | 1。转到 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。 现在，你已Microsoft Endpoint Manager管理中心。<br/><br/>2. 选择 **终结点安全性**。<br/><br/>3. **选择"防病毒** "以查看该类别中的策略。 <br/><br/>若要获取有关管理环境中安全设置Microsoft Endpoint Manager，请从管理 Microsoft Intune [中的终结点安全开始](/mem/intune/protect/endpoint-security)。 |

## <a name="view-or-edit-your-firewall-policies-and-custom-rules"></a>查看或编辑防火墙策略和自定义规则

根据是使用防火墙Microsoft 365 Defender还是Microsoft Endpoint Manager管理防火墙保护，请使用下表中的过程之一： <br/><br/>

| 门户 | Procedure |
|:---|:---|
| Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com))  | 1. 转到 Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。 <br/><br/>2. 在导航窗格中，选择" **设备配置"**。 策略按操作系统和策略类型进行组织。<br/><br/>3. 选择操作系统选项卡 (，Windows **客户端)**。<br/><br/>4. 展开 **防火墙** 以查看策略列表。<br/><br/>5. 选择一个策略以查看有关该策略的更多详细信息。 若要进行更改或了解有关策略设置的信息，请参阅以下文章： <br/>- [查看或编辑设备策略](mdb-view-edit-policies.md)<br/>- [防火墙设置](mdb-firewall.md)<br/>- [管理防火墙策略的自定义规则](mdb-custom-rules-firewall.md)  |
| Microsoft Endpoint Manager管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))  | 1。转到 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。 现在，你已Microsoft Endpoint Manager管理中心。<br/><br/>2. 选择 **终结点安全性**。<br/><br/>3. 选择 **"防火墙** "以查看该类别中的策略。 为防火墙保护定义的自定义规则作为单独的策略列出。<br/><br/>若要获取有关管理环境中安全设置Microsoft Endpoint Manager，请从管理 Microsoft Intune [中的终结点安全开始](/mem/intune/protect/endpoint-security)。 |

## <a name="set-up-web-content-filtering"></a>设置 Web 内容筛选

Web 内容筛选使安全团队能够根据网站的内容类别跟踪和监管对网站的访问，例如：

- 成人内容：与性生活、犯罪、暴力、色情、制造明确材料或暴力相关的网站
- 高带宽：下载站点、图像共享网站或对等主机
- 法律责任：包括儿童滥用图像、宣传非法活动、培养教师或学校欺诈或宣传有害的活动的网站
- 网站：提供基于 Web 的聊天室、在线游戏、基于 Web 的电子邮件或社交网络的网站
- 未分类：没有内容或新注册的网站

并非所有这些类别中的网站都是恶意网站，但由于合规性法规、带宽使用情况或其他问题，它们对于组织可能存在问题。 此外，可以创建仅审核策略，以更好地了解安全团队是否应该阻止任何网站类别。

Web 内容筛选在主要 Web 浏览器上可用，其中包含由 Windows Defender SmartScreen (Microsoft Edge) 和网络保护 (Chrome、Firefox、Filtering 和 Opera) 执行) 。 有关详细信息，请参阅 [Web 内容筛选的先决条件](../defender-endpoint/web-content-filtering.md#prerequisites)。

### <a name="to-set-up-web-content-filtering"></a>设置 Web 内容筛选

1. 在"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，设置 **"Web** >  内容 **筛选** > **+ 添加策略"**。

2. 为策略指定名称和说明。

3. 选择要阻止的类别。 使用展开图标完全展开每个父类别并选择特定的 Web 内容类别。

   若要设置不阻止任何网站的仅审核策略，请不要选择任何类别。

   不要选择 **"未分类"**。

4. 通过选择要应用策略的设备组来指定策略作用域。 将仅阻止所选设备组中设备访问所选类别中的网站。

5. 查看摘要并保存策略。 策略刷新可能需要 2 个小时才能应用到所选设备。

> [!TIP]
> 若要了解有关 Web 内容筛选的信息，请参阅 [Web 内容筛选](../defender-endpoint/web-content-filtering.md)。

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>查看和编辑 Microsoft 365 Defender 门户中的其他设置

除了应用于设备的安全策略之外，还可以在 Defender for Business 中查看和编辑其他设置。 例如，你指定使用的时区，并且你可以载入 (或) 设备。 

> [!NOTE]
> 你可能会在租户中看到比本文中列出的更多的设置。 本文重点介绍了应在 Defender for Business 中查看的最重要的设置。

### <a name="settings-to-review-for-defender-for-business"></a>设置查看 Defender for Business

下表介绍了用于查看 (的设置，如有必要，) Defender for Business 中的编辑权限。

<br/><br/>

| 类别 | Setting | 说明 |
|:---|:---|:---|
| **安全中心** | **时区** | 选择要用于事件中显示的日期和时间的时区、检测到的威胁以及自动调查和&修正。 可以使用 UTC 或本地时区， (*推荐)* 。  |
| **Microsoft 365 Defender** | **Account** | 查看详细信息，例如存储数据的位置、租户 ID 和组织 (组织) ID。 |
| **Microsoft 365 Defender**  | **预览功能**  | 打开预览功能以试用即将推出的功能和新功能。 你可以成为第一批预览新功能并提供反馈的人。 |
| **终结点**  | **电子邮件通知** | 设置或编辑电子邮件通知规则。 检测到漏洞或创建警报时，电子邮件通知规则中指定的收件人将收到一封电子邮件。 [详细了解电子邮件通知](mdb-email-notifications.md)。 |
| **终结点**   | **设备管理** > **载入** | 使用可下载脚本将设备载入 Defender for Business。 若要了解更多信息，请参阅 [将设备载入 Microsoft Defender for Business](mdb-onboard-devices.md)。   |  
| **终结点**  |  **设备管理** > **载出** | 从 defender () 删除设备。 当你离开设备时，它不再将数据发送到 Defender for Business，但在载出之前收到的数据将保留。 若要了解更多信息，请参阅 [将设备载出](mdb-onboard-devices.md#offboarding-a-device)。  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>在门户中Microsoft 365 Defender设置

1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com/](https://security.microsoft.com/) ，然后登录。

2. 选择 **设置**，然后选择一个类别 (，如安全中心、**Microsoft 365 Defender或终结点**) 。

3. 在设置列表中，选择要查看或编辑的项。


## <a name="next-steps"></a>后续步骤

继续执行以下一个或多个任务：

- [开始使用 Microsoft Defender for Business](mdb-get-started.md)

- [在 Microsoft Defender for Business 中管理设备](mdb-manage-devices.md)

- [在 Microsoft Defender for Business 中查看和管理事件](mdb-view-manage-incidents.md)

- [在 Microsoft Defender for Business 中查看或编辑策略](mdb-view-edit-policies.md)
