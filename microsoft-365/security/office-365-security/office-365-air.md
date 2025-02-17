---
title: Microsoft Defender for Office 365
keywords: AIR， autoIR， Microsoft Defender for Endpoint， 自动化， 调查， 响应， 修正， 威胁， 高级， 威胁， 保护
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 开始使用 Microsoft Defender for Office 365 中的自动调查和响应Office 365。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e9cd2388d3551ccc0c180d20a92ec0c513472797
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473664"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender for (AIR) 的自动调查和Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)包括强大的自动调查和响应 (AIR) 功能，可节省安全操作团队的时间和精力。 触发警报时，由安全运营团队来审阅、确定警报优先级并响应这些警报。 保持传入警报的量可能会很不知所措。 自动执行其中一些任务可能会有所帮助。

AIR 使安全运营团队可以更高效地操作。 AIR 功能包括自动调查流程，以响应当今存在的已知威胁。 适当的修正操作等待审批，使安全运营团队能够有效响应检测到的威胁。 使用 AIR，安全运营团队可以专注于优先级较高的任务，而不会忽略触发的重要警报。

本文内容：

- [AIR 的整体流](#the-overall-flow-of-air);
- [如何获取 AIR](#how-to-get-air);和
- [配置或使用](#required-permissions-to-use-air-capabilities) AIR 功能所需的权限。
- 即将对应用门户Microsoft 365 Defender更改

本文还包括 [用于了解更多信息](#next-steps)的以下步骤和资源。

## <a name="the-overall-flow-of-air"></a>AIR 的整体流

将触发警报，并且安全手册将启动自动调查，从而产生结果和推荐操作。 下面是 AIR 的整体流程，分步说明：

1. 自动调查以下列方式之一启动：
   - 警报 [由](#which-alert-policies-trigger-automated-investigations) 电子邮件中的可疑内容触发 (例如邮件、附件、URL 或遭到入侵的用户帐户) 。 创建事件，并开始自动调查;或
   - 安全分析师 [在使用资源管理器时启动](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 自动 [调查](threat-explorer.md)。
2. 当自动调查运行时，它会收集有关相关电子邮件和与电子邮件相关的实体的数据。 此类实体可以包括文件、URL 和收件人。 随着新警报和相关警报的触发，调查的范围可能会增加。
3. 在自动调查期间和之后 [，可以查看](air-view-investigation-results.md) 详细信息和结果。 结果 [包括可](air-remediation-actions.md) 采取的建议操作，以响应和修正发现的任何威胁。
4. 安全运营团队会审核 [测试结果和建议](air-view-investigation-results.md)，并 [批准或拒绝修正操作](air-review-approve-pending-completed-actions.md)。
5. 随着批准或拒绝的修正 (，) 自动调查完成。

在 Microsoft Defender for Office 365中，不会自动执行任何修正操作。 只有在组织的安全团队批准后，才会执行修正操作。 AIR 功能通过确定修正操作并提供做出明智决定所需的详细信息来节省安全运营团队的时间。

在每个自动调查期间和之后，安全运营团队可以：

- [查看与调查相关的警报的详细信息](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [查看调查的结果详细信息](air-view-investigation-results.md#view-details-of-an-investigation)
- [查看和批准调查后的操作](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 有关更详细的概述，请参阅 [AIR 的工作原理](automated-investigation-response-office.md)。

## <a name="how-to-get-air"></a>如何获取 AIR

AIR 功能包含在 [Microsoft Defender for Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)，但已配置策略和警报。 需要一些帮助？ 按照防止威胁 [中的指南](protect-against-threats.md) 设置或配置以下保护设置：

- [审核日志记录](../../compliance/turn-audit-log-search-on-or-off.md) (应打开) 
- [反恶意软件保护](protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [防网络钓鱼钓鱼保护](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
- [Anti-spam protection](protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [保险箱链接和保险箱附件](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

此外，请确保 [查看组织的警报](../../compliance/alert-policies.md)策略，尤其是威胁管理类别中 [的默认策略](../../compliance/alert-policies.md#default-alert-policies)。

## <a name="which-alert-policies-trigger-automated-investigations"></a>哪些警报策略会触发自动调查？

Microsoft 365许多内置警报策略，可帮助Exchange权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。 一些 [默认警报策略](../../compliance/alert-policies.md#default-alert-policies) 可以触发自动调查。 下表介绍了触发自动调查的警报、Microsoft 365 Defender门户中的严重性以及如何生成这些警报：

|通知|Severity|警报的生成方式|
|---|---|---|
|检测到潜在恶意 URL 单击|**High**|发生以下任一情况时，将生成此警报： <ul><li>受组织链接[保险箱](safe-links.md)用户单击恶意链接</li><li>URL 裁定更改由 Microsoft Defender for Office 365</li><li>用户保险箱组织的链接 (策略覆盖"链接保险箱[页](set-up-safe-links-policies.md)。</li></ul> <p> 有关触发此警报的事件详细信息，请参阅设置链接保险箱[策略](set-up-safe-links-policies.md)。|
|电子邮件被用户报告为恶意软件或钓鱼邮件|**信息**|当贵组织的用户使用报告邮件外接程序或报告网络钓鱼外接程序将邮件报告为网络钓鱼电子邮件[时，](enable-the-report-message-add-in.md)[将生成此警报](enable-the-report-phish-add-in.md)。|
|包含恶意软件的电子邮件在传递后被删除|**信息**|当包含恶意软件的任何电子邮件传递到您组织的邮箱时，将生成此警报。 如果发生此事件，Microsoft 会使用 ZAP Exchange Online零时差自动清除从 ([受感染) ](zero-hour-auto-purge.md)。|
|包含网络钓鱼 URL 的电子邮件在传递后被删除|**信息**|当包含网络钓鱼邮件的任何邮件传递到您组织的邮箱时，将生成此警报。 如果发生此事件，Microsoft 会使用 [ZAP](zero-hour-auto-purge.md) 从Exchange Online受感染的邮件。|
|检测到可疑的电子邮件发送模式|**Medium**|当组织中有人已发送可疑电子邮件，并且存在被限制发送电子邮件的风险时，将生成此警报。 警报是行为的早期警告，可能指示帐户受到威胁，但不够严重，无法限制用户。 <p> 尽管这种情况很少见，但此策略生成的警报可能是异常情况。 但是，检查用户帐户是否遭到入侵 [是一个好主意](responding-to-a-compromised-email-account.md)。|
|用户被限制发送电子邮件|**High**|当组织中有人被限制发送出站邮件时，将生成此警报。 此警报通常在电子邮件帐户 [遭到入侵时产生](responding-to-a-compromised-email-account.md)。 <p> 有关受限用户详细信息，请参阅在 Microsoft 365 中从[受限用户门户删除阻止Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md)。|

> [!TIP]
> 若要了解有关警报策略或编辑默认设置的信息，请参阅警报策略[Microsoft 365 合规中心。](../../compliance/alert-policies.md)

## <a name="required-permissions-to-use-air-capabilities"></a>使用 AIR 功能所需的权限

权限通过某些角色授予，如下表中所述的角色：

|任务|需要 (角色) 角色|
|---|---|
|设置 AIR 功能|下列角色之一： <ul><li>全局管理员</li><li>安全管理员</li></ul> <p> 这些角色可以在 [Azure Active Directory 或 Microsoft 365 Defender](/azure/active-directory/roles/permissions-reference) [门户中分配](permissions-microsoft-365-security-center.md)。|
|启动自动调查 <p> --- 或 --- <p> 批准或拒绝建议的操作|以下角色之一，在 [Azure Active Directory 或 Microsoft 365 Defender](/azure/active-directory/roles/permissions-reference) [门户中分配](permissions-microsoft-365-security-center.md)： <ul><li>全局管理员</li><li>安全管理员</li><li>安全操作员</li><li>安全信息读取者 <br> --- 和 --- </li><li>搜索和 (此角色仅在 Microsoft 365 Defender [门户中分配](permissions-microsoft-365-security-center.md)。 你可能需要创建一个新的电子邮件& **协作** 角色组，然后向该新角色组添加搜索和清除角色。</li></ul>|

## <a name="required-licenses"></a>所需的许可证

[Microsoft Defender for Office 365 计划 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 许可证应分配给：

- 安全管理员 (包括全局管理员) 
- 组织的安全运营团队 (包括安全读者和具有"搜索和清除"角色) 
- 最终用户

## <a name="changes-are-coming-soon-in-your-microsoft-365-defender-portal"></a>即将在门户中Microsoft 365 Defender更改

如果你已在 Microsoft Defender for Office 365 中使用 AIR 功能，你将在改进的 Microsoft 365 Defender [门户中看到一些更改](../defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)。

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="统一操作中心" lightbox="../../media/m3d-action-center-unified.png":::

新的和改进的 <https://security.microsoft.com> Microsoft 365 Defender 门户将 [Microsoft Defender for Office 365](defender-for-office-365.md) 和 [Microsoft Defender for Endpoint 中的 AIR 功能汇集在一起](../defender-endpoint/automated-investigations.md)。 通过这些更新和改进，安全操作团队将能够在一处查看电子邮件、协作内容、用户帐户和设备中的自动调查和修正操作的详细信息。

> [!TIP]
> 新的Microsoft 365 Defender门户取代了以下管理中心：
>
> - 安全&合规中心 (<https://protection.office.com>) 
> - <https://security.microsoft.com> Microsoft 365 Defender () 
>
> 除了更改 URL 之外，还有一种新的外观，旨在为安全团队提供更简化的体验，同时在一个地方查看更多威胁检测。

### <a name="what-to-expect"></a>预期结果

下表列出了 Microsoft Defender for Office 365 中的 AIR 即将Office 365。

|Item|更改了哪些方面？|
|---|---|
|**"调查"** 页|更新 **后的调查** 页面更符合 [你在 Microsoft Defender for Endpoint 中看到的内容](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)。 你将看到一些与新的统一调查视图一致的常规格式和 **样式** 设置更改。 例如，调查图具有更统一的格式。|
|**"用户"** 选项卡|" **用户"** 选项卡现在是" **邮箱"** 选项卡。有关用户的详细信息列在"邮箱" **选项卡** 上。|
|**"电子邮件"** 选项卡|已删除 **"** 电子邮件"选项卡;访问 **"实体"** 选项卡以查看电子邮件和电子邮件群集项目的列表。|
|**"实体"** 选项卡|" **实体"** 选项卡具有选项卡式样式，其中包含全部摘要视图，并且能够按实体类型进行筛选。 除了 **"在** 资源管理器中打开 **"选项之外** ，"实体"选项卡现在还包括"转到 **"** 搜寻选项。 你现在可以使用[资源管理器或](threat-explorer.md)[高级搜寻](../defender-endpoint/advanced-hunting-overview.md)来查找实体和威胁，并筛选结果。|
|**"操作"** 选项卡|更新后的 **"操作** "选项卡现在包括" **挂起的操作** "选项卡和" **操作历史记录"** 选项卡。可以在选择挂起 (时) 侧窗格中批准或拒绝操作。|
|**"证据"** 选项卡|新的 **"证据** "选项卡显示与操作相关的主要实体发现。 与每条证据相关的操作可以在选择 (操作时) 侧窗格中批准或拒绝。|
|**操作中心**|更新 **的操作中心** (<https://security.microsoft.com/action-center>) 跨电子邮件、设备和标识将挂起和已完成的操作汇集在一起。 若要了解更多信息，请参阅操作中心。  (若要了解更多信息，请参阅 [操作中心](../defender/m365d-action-center.md).) |
|**"事件"** 页|现在 **，"** 事件"页面将多个调查关联在一起，以提供更好的综合调查视图。  ([了解有关 Incidents.) ](../defender/incidents-overview.md)|

## <a name="next-steps"></a>后续步骤

- [查看自动调查的详细信息和结果](air-view-investigation-results.md#view-details-of-an-investigation)
- [审阅和批准挂起的操作](air-remediation-actions.md)
