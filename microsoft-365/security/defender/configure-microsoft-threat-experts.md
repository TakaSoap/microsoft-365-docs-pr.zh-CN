---
title: 通过Microsoft 365 Defender配置和管理Microsoft 威胁专家功能
description: 通过Microsoft 365 Defender订阅 Microsoft 威胁专家，以便在日常安全操作和安全管理工作中配置、管理和使用它。
keywords: Microsoft 威胁专家、托管威胁搜寻服务、MTE、Microsoft 托管搜寻服务
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: cd8f7e65c409138d6404a734b098e70e6d419cbb
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667265"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>通过Microsoft 365 Defender配置和管理Microsoft 威胁专家功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>准备工作

> [!IMPORTANT]
> 在申请之前，请确保与 Microsoft 技术服务提供商和帐户团队讨论Microsoft 威胁专家 - 目标攻击通知托管威胁搜寻服务的资格要求。

若要接收目标攻击通知，需要使用已注册的设备部署Microsoft 365 Defender。 然后，通过 M365 门户提交应用程序以获取Microsoft 威胁专家 - 目标攻击通知。

联系帐户团队或 Microsoft 代表以订阅Microsoft 威胁专家 - 按需专家。 使用按需专家可以咨询我们的威胁专家，了解如何保护组织免受相关检测和攻击。

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>申请Microsoft 威胁专家 - 目标攻击通知服务

如果已有Microsoft Defender for Endpoint和Microsoft 365 Defender，则可以通过其Microsoft 365 Defender门户申请Microsoft 威胁专家 - 目标攻击通知。  有针对性的攻击通知向你提供特殊的见解和分析，以帮助识别组织面临的最严重威胁，以便快速响应这些威胁。

1. 在导航窗格中，转到 **设置 >终结点>常规>高级功能> Microsoft 威胁专家 - 目标攻击通知**。

2. 选择“**应用**”。

    :::image type="content" source="../../media/mte/mte-collaboratewithmte.png" alt-text="Microsoft 365 Defender门户中的&quot;Microsoft 威胁专家设置&quot;页" lightbox="../../media/mte/mte-collaboratewithmte.png":::

3. 输入你的姓名和电子邮件地址，以便 Microsoft 可以联系你有关应用程序的信息。

    :::image type="content" source="../../media/mte/mte-apply.png" alt-text="Microsoft 365 Defender门户中的Microsoft 威胁专家应用程序页" lightbox="../../media/mte/mte-apply.png":::
  
4. 阅读 [隐私声明](https://privacy.microsoft.com/en-us/privacystatement)，然后在完成后选择" **提交** "。 应用程序获得批准后，你将收到一封欢迎电子邮件。

    :::image type="content" source="../../media/mte/mte-applicationconfirmation.png" alt-text="Microsoft 365 Defender门户中的Microsoft 威胁专家应用程序确认" lightbox="../../media/mte/mte-applicationconfirmation.png":::

5. 收到欢迎电子邮件后，你将自动开始接收目标攻击通知。

6. 可以通过访问 **设置 >终结点>常规>高级功能** 来验证状态。 批准后，**Microsoft 威胁专家 - 目标攻击通知** 切换将可见并 **打开**。

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>你将在其中看到来自Microsoft 威胁专家的目标攻击通知

可以通过以下媒介从Microsoft 威胁专家接收目标攻击通知：

- Microsoft 365 Defender门户的 **"事件"** 页
- Microsoft 365 Defender门户的 **警报** 仪表板
- OData 警报 [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) 和 [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- 高级搜寻中的 [DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) 表
- 如果选择通过电子邮件向你发送有针对性的攻击通知，则收件箱。 请参阅下面 [的"创建电子邮件通知规则](#create-an-email-notification-rule) "。

### <a name="create-an-email-notification-rule"></a>创建电子邮件通知规则

可以创建规则来发送通知收件人的电子邮件通知。 有关完整详细信息，请参阅  [配置警报通知](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) 以创建、编辑、删除或排查电子邮件通知问题。

## <a name="view-targeted-attack-notifications"></a>查看目标攻击通知

将系统配置为接收电子邮件通知后，你将开始收到电子邮件中Microsoft 威胁专家的目标攻击通知。

1. 选择电子邮件中的链接，转到标记有 **威胁专家** 的仪表板中的相应警报上下文。

2. 在 **"警报"** 页中，选择与电子邮件中收到的警报主题相同的警报主题，以查看更多详细信息。

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>订阅Microsoft 威胁专家 - 按需专家

如果你已经是Microsoft Defender for Endpoint客户，可以联系 Microsoft 代表订阅Microsoft 威胁专家 - 按需专家。

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>咨询 Microsoft 威胁专家，了解组织中的可疑网络安全活动

可以从Microsoft 365 Defender门户内部联系Microsoft 威胁专家。 专家可以帮助你了解复杂的威胁和有针对性的攻击通知。 与专家合作，了解有关警报和事件的更多详细信息，或有关处理入侵的建议。 深入了解门户仪表板描述的威胁智能上下文。

> [!NOTE]
>
> - 目前不支持与组织的自定义威胁情报数据相关的警报查询。 有关详细信息，请咨询安全操作或事件响应团队。
> - 需要在 **Microsoft 365 Defender门户中拥有安全中心管理安全设置** 的权限，才能通过 **"咨询威胁专家**"表单提交查询。

1. 导航到与要调查的信息相关的门户页面：例如， **设备**、 **警报** 或 **事件**。 在发送调查请求之前，请确保查看与查询相关的门户页面。

2. 在顶部菜单中，选择 **"？咨询威胁专家**。

    :::image type="content" source="../../media/mte/incidents-action-mte-highlighted.png" alt-text="Microsoft 365 Defender门户中菜单中的Microsoft 威胁专家专家点播" lightbox="../../media/mte/incidents-action-mte-highlighted.png":::

    将打开浮出控件屏幕。

    标头将指示你是在试用订阅中，还是在完整Microsoft 威胁专家 - 专家按需订阅。

    :::image type="content" source="../../media/mte/mte-trial.png" alt-text="Microsoft 365 Defender门户中的&quot;Microsoft 威胁专家专家按需&quot;试用订阅屏幕" lightbox="../../media/mte/mte-trial.png":::

    调查 **主题** 字段已填充到请求的相关页面的链接。

3. 在下一个字段中，提供足够的信息，使Microsoft 威胁专家有足够的上下文来开始调查。

4. 输入要用于与Microsoft 威胁专家对应的电子邮件地址。

> [!NOTE]
> 若要通过 Microsoft Services Hub 跟踪专家按需案例的状态，请联系技术客户经理。

观看此视频，快速了解 Microsoft Services Hub。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>示例调查主题

### <a name="alert-information"></a>警报信息

- 我们看到了一种针对陆地生活二进制文件的新型警报。 我们可以提供警报 ID。 能否告诉我们有关此警报的详细信息，以及如何进一步调查？
- 我们观察到两个类似的攻击，这两个攻击都尝试执行恶意 PowerShell 脚本，但会生成不同的警报。 一个是"可疑的 PowerShell 命令行"，另一个是"根据 O365 提供的指示检测到恶意文件"。 有什么区别？
- 我们今天收到一条奇怪的警报，询问来自高调用户设备的异常失败登录次数。 我们找不到任何进一步的证据来证明这些尝试。 Microsoft 365 Defender如何查看这些尝试？ 正在监视哪些类型的登录名？
- 是否可以提供有关警报的更多上下文或见解，"观察到系统实用工具的可疑行为"？
- 我观察到一条标题为"创建转发/重定向规则"的警报。 我相信这项活动是良性的。 你能告诉我为什么收到警报吗？

### <a name="possible-machine-compromise"></a>可能的计算机入侵

- 能否帮助解释为什么我们在组织中的许多设备上看到"观察到的未知进程"的消息或警报？ 我们理解任何输入来阐明此消息或警报是否与恶意活动相关。
- 是否可帮助验证以下系统上可能出现的妥协（从上周开始）？ 它的行为与六个月前同一系统上以前的恶意软件检测类似。

### <a name="threat-intelligence-details"></a>威胁情报详细信息

- 我们检测到一封网络钓鱼电子邮件，该电子邮件将恶意 Word 文档传递给用户。 该文档引发了一系列可疑事件，这些事件触发了特定恶意软件系列的多个警报。 你对此恶意软件有任何信息吗？ 如果是，可以向我们发送链接吗？
- 我们最近看到一篇关于针对我们行业的威胁的博客文章。 能否帮助我们了解Microsoft 365 Defender对此威胁执行组件提供哪些保护？
- 我们最近观察到针对我们的组织进行的网络钓鱼活动。 你能告诉我们这是专门针对我们公司还是垂直公司？

### <a name="microsoft-threat-experts-alert-communications"></a>Microsoft 威胁专家警报通信

- 事件响应团队能否帮助我们解决我们收到的目标攻击通知？
- 我们从Microsoft 威胁专家收到了此目标攻击通知。 我们没有我们自己的事件响应团队。 我们现在可以做什么，如何包含事件？
- 我们收到了来自Microsoft 威胁专家的目标攻击通知。 你可以向我们提供哪些数据，我们可以将这些数据传递给我们的事件响应团队？

> [!NOTE]
> Microsoft 威胁专家是托管的威胁搜寻服务，而不是事件响应服务。 但是，可以与自己的事件响应团队联系，解决需要事件响应的问题。 如果你没有自己的事件响应团队，并且希望 Microsoft 提供帮助，则可以与 CSS 网络安全事件响应团队 (CIRT) 联系。 他们可以开具票证来帮助你解决查询问题。

## <a name="scenario"></a>应用场景

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>接收有关托管搜寻查询的进度报告

Microsoft 威胁专家的响应将因查询而异。 通常会收到以下响应之一：

- 需要详细信息才能继续调查
- 需要一个文件或多个文件示例来确定技术上下文
- 调查需要更多的时间
- 初步信息足以结束调查

如果专家请求更多信息或文件示例，则快速响应以使调查继续进行至关重要。

## <a name="see-also"></a>另请参阅

- [Microsoft 威胁专家概述](microsoft-threat-experts.md)
