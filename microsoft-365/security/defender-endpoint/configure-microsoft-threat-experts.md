---
title: 配置和管理 Microsoft 威胁专家功能
ms.reviewer: ''
description: 注册到 Microsoft 威胁专家，以在日常安全操作和安全管理工作中配置、管理和使用它。
keywords: Microsoft 威胁专家， 托管威胁搜寻服务， MTE， Microsoft 托管搜寻服务
search.product: Windows 10
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 152c0c54138841d9159c7230fc043307979e4546
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471816"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities"></a>配置和管理 Microsoft 威胁专家功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

## <a name="before-you-begin"></a>准备工作

> [!NOTE]
> 在适用于目标攻击通知托管威胁搜寻服务之前，Microsoft 威胁专家 Microsoft 技术服务提供商和帐户团队讨论资格要求。

确保在你的环境中部署了 Defender for Endpoint 并注册了设备，而不只是在实验室设置上。

如果你是适用于终结点的 Defender 客户，则需要申请 **Microsoft 威胁专家 -** 目标攻击通知，获取特殊的见解和分析，以帮助识别最重要的威胁，以便你可以快速响应它们。 联系你的客户团队或 Microsoft 代表，订阅 Microsoft 威胁专家 **-** 专家按需咨询我们的威胁专家，了解相关检测和对手。

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>适用于 Microsoft 威胁专家 - 目标攻击通知服务

如果你已经是适用于终结点的 Defender 客户，可以通过应用中心门户Microsoft 365 Defender应用。

1. 从导航窗格中，转到"常规设置 >**高级> - > Microsoft 威胁专家攻击通知"**。

2. 单击“**应用**”。

   :::image type="content" source="images/mte-collaboratewithmte.png" alt-text="Microsoft 威胁专家设置" lightbox="images/mte-collaboratewithmte.png":::

3. 输入你的姓名和电子邮件地址，以便 Microsoft 可以在你的应用程序上返回给你。

   :::image type="content" source="images/mte-apply.png" alt-text="&quot;应用程序&quot;页上Microsoft 威胁专家&quot;字段" lightbox="images/mte-apply.png":::

4. 阅读 [隐私声明，](https://privacy.microsoft.com/privacystatement)**完成后单击提交**。 应用程序获得批准后，您将收到欢迎电子邮件。

   :::image type="content" source="images/mte-applicationconfirmation.png" alt-text="应用程序Microsoft 威胁专家确认消息" lightbox="images/mte-applicationconfirmation.png":::

接受后，你将收到欢迎电子邮件，并且你将看到"应用"按钮更改为"打开"的切换。 如果你希望将自己从目标攻击通知服务中退出，请滑动切换"关闭"，然后单击页面底部的"保存首选项"。

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>你将在什么位置看到来自你的目标攻击Microsoft 威胁专家

可以通过以下媒体从 Microsoft 威胁专家接收目标攻击通知：

- 终结点门户的 Defender **事件** 页面
- Defender for Endpoint 门户 **的警报** 仪表板
- OData 警报 [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) 和 [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [高级搜寻中的 DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) 表
- 您的电子邮件（如果选择进行配置）

若要通过电子邮件接收目标攻击通知，请创建电子邮件通知规则。

### <a name="create-an-email-notification-rule"></a>创建电子邮件通知规则

可以创建规则来发送通知收件人的电子邮件通知。 有关详细信息  [，请参阅配置警报](configure-email-notifications.md) 通知以创建、编辑、删除或解决电子邮件通知问题。

## <a name="view-the-targeted-attack-notification"></a>查看目标攻击通知

在将系统配置为接收电子邮件通知后，Microsoft 威胁专家电子邮件中收到目标攻击通知。

1. 单击电子邮件中的链接，转到使用威胁专家标记的仪表板中的相应 **警报上下文**。

2. 从仪表板中，选择与从电子邮件获得相同的警报主题，以查看详细信息。

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>订阅 Microsoft 威胁专家 - 专家按需

这作为订阅服务提供。 如果你已经是适用于 Endpoint 的 Defender 客户，你可以联系 Microsoft 代表，以订阅 Microsoft 威胁专家 - 专家按需。

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>咨询 Microsoft 威胁专家，了解组织中可疑的网络安全活动

你可以与可以直接在 Microsoft 威胁专家 门户中参与的管理员合作Microsoft 365 Defender及时准确的响应。 专家提供见解，以更好地了解复杂的威胁、你收到的定向攻击通知，或者如果你需要有关警报、可能受到威胁的设备或你在门户仪表板上看到的威胁智能上下文的更多信息。

> [!NOTE]
>
> - 目前不支持与组织的自定义威胁情报数据相关的警报查询。 有关详细信息，请咨询安全运营或事件响应团队。
> - 你需要在安全门户中拥有Microsoft 365 Defender安全设置"权限，才能提交"咨询威胁专家"查询。

1. 导航到包含要调查的相关信息的门户页面，例如"事件 **"** 页面。 发送调查请求之前，请确保相关警报或设备的页面已查看。

2. 从右上角的菜单中，单击 **" ？"** 图标。 然后，选择 **"咨询威胁专家"**。

    :::image type="content" source="images/mte-eod-menu.png" alt-text="&quot;Microsoft 威胁专家专家按需&quot;菜单项" lightbox="images/mte-eod-menu.png":::

    将打开一个飞出屏幕。 以下屏幕显示你何时使用试用版订阅。

    :::image type="content" source="images/mte-eod.png" alt-text="按需Microsoft 威胁专家专家页面" lightbox="images/mte-eod.png":::

    以下屏幕显示你何时使用完整Microsoft 威胁专家专家按需订阅。

    :::image type="content" source="images/mte-eod-fullsubscription.png" alt-text="按需Microsoft 威胁专家专家完整订阅页面" lightbox="images/mte-eod-fullsubscription.png":::

    " **查询"** 主题字段预填充了指向调查请求的相关页面的链接。 例如，指向发出请求时所访问的事件、警报或设备详细信息页面的链接。

3. In the next field， provide enough information to give the Microsoft 威胁专家 enough context to start the investigation.

4. 输入要用于与电子邮件地址对应的电子邮件地址Microsoft 威胁专家。

> [!NOTE]
> 如果要通过 Microsoft 服务中心跟踪专家按需案例的状态，请联系客户成功客户经理。

观看此视频，快速概览 Microsoft 服务中心。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics-that-you-can-consult-with-microsoft-threat-experts---experts-on-demand"></a>可以咨询的样本调查主题-Microsoft 威胁专家 - 专家按需

### <a name="alert-information"></a>警报信息

- 我们会看到一种针对陆地外活动二进制文件的新警报类型：[AlertID]。 能否告诉我们有关此警报以及我们可以如何进一步调查的更多信息？
- 我们观察到两个类似的攻击，它们尝试执行恶意 PowerShell 脚本，但生成不同的警报。 一种是"可疑 PowerShell 命令行"，另一种是"根据 O365 提供的指示检测到恶意文件"。 区别是什么？
- 今天，我收到一个有关高配置文件用户设备登录失败异常数量的奇数警报。 我找不到有关这些登录尝试的任何进一步证据。 Defender for Endpoint 如何查看这些尝试？ 正在监视哪种类型的登录？
- 能否提供关于此警报的更多上下文或见解："已观察到系统实用工具的可疑行为"。

### <a name="possible-machine-compromise"></a>可能的机器入侵

- 能否帮助回答我们为何看到"观察到的未知进程？" 此消息或警报在许多设备上经常看到。 感谢你的任何输入来阐明此消息或警报是否与恶意活动相关。
- 是否有助于验证以下系统在 [date] 上可能遭到入侵，其行为与[月]内同一系统上之前的 [恶意软件名称] 恶意软件检测行为类似？

### <a name="threat-intelligence-details"></a>威胁情报详细信息

- 我们检测到一封钓鱼电子邮件，该电子邮件向用户传递了恶意 Word 文档。 恶意 Word 文档引发了一系列可疑事件，触发了针对 [恶意软件名称] 恶意软件的多个 Defender for Endpoint 警报。 你是否有关于此恶意软件的信息？ 如果是，可以向我发送链接吗？
- 我最近看到[社交媒体参考，例如 Twitter 或博客]文章，关于面向我的行业的威胁。 你可以帮助我了解针对此威胁参与者的 Defender 提供什么保护？

### <a name="microsoft-threat-experts-alert-communications"></a>Microsoft 威胁专家警报通信

- 事件响应团队能否帮助我们处理我们得到的目标攻击通知？
- 我收到了来自该邮件的此目标Microsoft 威胁专家。 我们还没有自己的事件响应团队。 现在，我们可以做什么，如何包含事件？
- 我收到了来自用户的攻击Microsoft 威胁专家。 您可以向我们提供哪些数据，我们可以将这些数据传递给事件响应团队？

  > [!NOTE]
  > Microsoft 威胁专家托管网络安全搜寻服务，而不是事件响应服务。 但是，您可以与自己的事件响应团队合作，以解决需要事件响应的问题。 如果你没有自己的事件响应团队，并且希望获得 Microsoft 的帮助，你可以与 CIRT (CSS 网络安全事件响应) 。 他们可以打开票证来帮助解决你的查询问题。

## <a name="scenario"></a>应用场景

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>接收有关托管搜寻查询的进度报告

来自你的Microsoft 威胁专家因你的查询而异。 他们将在两天内通过电子邮件将关于咨询威胁专家查询的进度报告通过电子邮件发送给你，以传达以下类别的调查状态：

- 需要更多信息才能继续执行调查
- 需要一个或多个文件示例来确定技术上下文
- 调查需要更多时间
- 初始信息足以结束调查

快速响应以保持调查的运行至关重要。

## <a name="related-topic"></a>相关主题

- [Microsoft 威胁专家概述](microsoft-threat-experts.md)
- [Microsoft 威胁专家概述Microsoft 365](/microsoft-365/security/mtp/microsoft-threat-experts)
