---
title: 通过管理Microsoft 威胁专家配置和管理Microsoft 365 Defender
description: 通过安全中心Microsoft 365 Defender Microsoft 威胁专家，以在日常安全操作和安全管理工作中配置、管理和使用它。
keywords: Microsoft 威胁专家， 托管威胁搜寻服务， MTE， Microsoft 托管搜寻服务
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
ms.openlocfilehash: 8a8de691ff08b50b56c34ed9e779cc97d48c5fcd
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63755822"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>通过管理Microsoft 威胁专家配置和管理Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>开始之前

> [!IMPORTANT]
> 在应用之前，请务必与 Microsoft 技术服务提供商和帐户团队讨论 Microsoft 威胁专家 - 目标攻击通知托管威胁搜寻服务的资格要求。

若要接收目标攻击通知，你需要已注册Microsoft 365 Defender部署目标攻击通知。 然后，通过 M365 门户提交应用程序，Microsoft 威胁专家 - 目标攻击通知。

联系你的帐户团队或 Microsoft 代表，以订阅 Microsoft 威胁专家 - 专家按需。 按需专家让你可以咨询我们的威胁专家，了解如何保护你的组织免受相关检测和攻击。

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>适用于 Microsoft 威胁专家 - 目标攻击通知服务

如果你已拥有适用于终结点和 Microsoft 365 Defender 的 Microsoft Defender，可以通过Microsoft 威胁专家应用目标攻击Microsoft 365 Defender通知。  目标攻击通知可让你获得特殊的见解和分析，以帮助识别组织面临的最关键威胁，以便你可以快速响应它们。

1. 从导航窗格中，转到"设置 >终结点">">高级> Microsoft 威胁专家 **- 目标攻击通知"**。

2. 选择“**应用**”。

    :::image type="content" source="../../media/mte/mte-collaboratewithmte.png" alt-text="Microsoft 威胁专家门户中的&quot;Microsoft 365 Defender设置&quot;页" lightbox="../../media/mte/mte-collaboratewithmte.png":::

3. 输入你的姓名和电子邮件地址，以便 Microsoft 可以就你的应用程序联系你。

    :::image type="content" source="../../media/mte/mte-apply.png" alt-text="Microsoft 威胁专家门户中的&quot;Microsoft 365 Defender应用程序&quot;页" lightbox="../../media/mte/mte-apply.png":::
  
4. 阅读 [隐私声明，](https://privacy.microsoft.com/en-us/privacystatement)**然后在完成后选择** 提交。 应用程序获得批准后，您将收到欢迎电子邮件。

    :::image type="content" source="../../media/mte/mte-applicationconfirmation.png" alt-text="Microsoft 威胁专家门户中的应用程序Microsoft 365 Defender确认" lightbox="../../media/mte/mte-applicationconfirmation.png":::

5. 收到欢迎电子邮件后，将自动开始接收目标攻击通知。

6. 可以通过访问常规和高级功能设置 >终结点>**验证>状态**。 获得批准后，Microsoft 威胁专家 **- 目标攻击** 通知切换将可见并切换 **为打开**。

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>你将在什么位置看到来自你的目标攻击Microsoft 威胁专家

可以通过以下媒体从Microsoft 威胁专家接收目标攻击通知：

- Microsoft 365 Defender门户 **的事件** 页面
- Microsoft 365 Defender门户 **的警报** 仪表板
- OData 警报 [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) 和 [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [高级搜寻中的 DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) 表
- 如果你选择通过电子邮件将目标攻击通知发送给你的收件箱。 请参阅 [下面的创建电子邮件通知](#create-an-email-notification-rule) 规则。

### <a name="create-an-email-notification-rule"></a>创建电子邮件通知规则

可以创建规则来发送通知收件人的电子邮件通知。 有关完整详细信息，请参阅  [配置警报通知](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) 以创建、编辑、删除或解决电子邮件通知问题。

## <a name="view-targeted-attack-notifications"></a>查看目标攻击通知

在将系统配置为接收电子邮件通知后，Microsoft 威胁专家电子邮件中收到目标攻击通知。

1. 选择电子邮件中的链接，转到使用威胁专家标记的仪表板中的相应 **警报上下文**。

2. 从 **"警报"** 页面，选择与在电子邮件中收到的警报主题相同的警报主题，以查看详细信息。

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>订阅 Microsoft 威胁专家 - 专家按需

如果你已经是适用于 Endpoint 的 Microsoft Defender 客户，你可以联系你的 Microsoft 代表，以订阅 Microsoft 威胁专家 - 专家按需。

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>咨询 Microsoft 威胁专家，了解组织中可疑的网络安全活动

你可以从 Microsoft 威胁专家 门户内Microsoft 365 Defender联系人。 专家可以帮助你了解复杂的威胁和目标攻击通知。 与专家合作，进一步了解有关警报和事件的详细信息，或提供有关处理泄露的建议。 深入了解门户仪表板描述的威胁情报上下文。

> [!NOTE]
>
> - 目前不支持与组织的自定义威胁情报数据相关的警报查询。 有关详细信息，请咨询安全运营或事件响应团队。
> - 你需要拥有安全中心门户中的"管理安全中心中的安全设置"权限Microsoft 365 Defender"咨询威胁专家"表单 **提交查询。**

1. 导航到与要调查的信息相关的门户页面：例如，设备、**警报** 或 **事件**。  发送调查请求之前，请确保已查看与查询相关的门户页面。

2. 从顶部菜单中， **选择？咨询威胁专家**。

    :::image type="content" source="../../media/mte/incidents-action-mte-highlighted.png" alt-text="Microsoft 威胁专家门户中菜单中的按需专家Microsoft 365 Defender专家" lightbox="../../media/mte/incidents-action-mte-highlighted.png":::

    将打开一个飞出屏幕。

    标头将指示你是使用试用版订阅，还是使用完整的 Microsoft 威胁专家 - 专家按需订阅。

    :::image type="content" source="../../media/mte/mte-trial.png" alt-text="Microsoft 威胁专家门户中的按需专家试用订阅Microsoft 365 Defender屏幕" lightbox="../../media/mte/mte-trial.png":::

    " **调查** "主题字段已经填充了指向请求相关页面的链接。

3. In the next field， provide enough information to give the Microsoft 威胁专家 enough context to start the investigation.

4. 输入要用于与电子邮件地址对应的电子邮件地址Microsoft 威胁专家。

> [!NOTE]
> 如果要通过 Microsoft 服务中心跟踪专家按需案例的状态，请联系你的技术客户经理。

观看此视频，快速概览 Microsoft 服务中心。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>示例调查主题

### <a name="alert-information"></a>警报信息

- 我们看到了一种新型的针对非陆地二进制文件的警报。 我们可以提供警报 ID。 能否告诉我们有关此警报以及我们可以如何进一步调查此警报的更多信息？
- 我们观察到两个类似的攻击，它们尝试执行恶意 PowerShell 脚本，但生成不同的警报。 一种是"可疑 PowerShell 命令行"，另一种是"根据 O365 提供的指示检测到恶意文件"。 区别是什么？
- 今天，我们收到一个有关高配置文件用户设备登录失败异常数量的奇数警报。 我们找不到有关这些尝试的任何进一步证据。 如何Microsoft 365 Defender这些尝试？ 监视的登录类型是什么？
- 能否提供关于警报的更多上下文或见解，"已观察到系统实用工具的可疑行为"？
- 我观察到名为"创建转发/重定向规则"的警报。 我认为活动是良好的。 能否告诉我为什么收到警报？

### <a name="possible-machine-compromise"></a>可能的机器入侵

- 能否帮助解释我们为何在组织中很多设备上看到有关"观察到的未知进程"的消息或警报？ 感谢你的任何输入来阐明此消息或警报是否与恶意活动相关。
- 你能否帮助验证从上周开始在下列系统上可能遭到入侵？ 其行为类似于六个月之前对同一系统进行恶意软件检测的行为。

### <a name="threat-intelligence-details"></a>威胁情报详细信息

- 我们检测到一封钓鱼电子邮件，该电子邮件向用户传递了恶意 Word 文档。 文档引发了一系列可疑事件，从而触发了针对特定恶意软件系列的多个警报。 你是否有关于此恶意软件的信息？ 如果是，能否向我们发送链接？
- 我们最近看到一篇有关针对我们行业的威胁的博客文章。 你可以帮助我们了解针对此威胁Microsoft 365 Defender提供哪些保护？
- 我们最近观察到了针对我们的组织进行的网络钓鱼活动。 能否告诉我们这是专门针对我们的公司还是垂直市场？

### <a name="microsoft-threat-experts-alert-communications"></a>Microsoft 威胁专家警报通信

- 事件响应团队能否帮助我们处理我们得到的目标攻击通知？
- 我们收到了来自此攻击的此目标Microsoft 威胁专家。 我们还没有自己的事件响应团队。 现在，我们可以做什么，如何包含事件？
- 我们收到了来自用户的攻击Microsoft 威胁专家。 您可以向我们提供哪些数据，我们可以将这些数据传递给事件响应团队？

> [!NOTE]
> Microsoft 威胁专家是托管威胁搜寻服务，而不是事件响应服务。 但是，您可以与自己的事件响应团队合作，以解决需要事件响应的问题。 如果你没有自己的事件响应团队，并且希望获得 Microsoft 的帮助，你可以与 CIRT (CSS 网络安全事件响应) 。 他们可以打开票证来帮助解决你的查询问题。

## <a name="scenario"></a>应用场景

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>接收有关托管搜寻查询的进度报告

来自你的Microsoft 威胁专家根据你的查询而异。 你通常会收到以下响应之一：

- 需要更多信息才能继续执行调查
- 需要一个或多个文件示例来确定技术上下文
- 调查需要更多时间
- 初始信息足以结束调查

如果专家请求更多信息或文件示例，快速响应以保持调查的运行至关重要。

## <a name="see-also"></a>另请参阅

- [Microsoft 威胁专家概述](microsoft-threat-experts.md)
