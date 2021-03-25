---
title: 通过自动调查和响应处理遭到入侵的用户帐户
keywords: AIR， autoIR， ATP， 自动化， 调查， 响应， 修正， 威胁， 高级， 威胁， 保护， 受到威胁
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: 了解如何在 Microsoft Defender for Office 365 计划 2 中通过自动调查和响应功能加快检测和解决遭到入侵的用户帐户的过程。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2428cc2c1f82b4f2b881433fde991dd04b268d6e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203879"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>通过自动调查和响应处理遭到入侵的用户帐户

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[Microsoft Defender for Office 365 计划 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)包括强大的自动调查和响应 (AIR) 功能。 [](office-365-air.md) 此类功能可以节省安全运营团队处理威胁的时间和精力。 Microsoft 继续改进安全性功能。 最近，AIR 功能得到增强，包括当前处于预览版 (用户安全) 。 阅读本文，详细了解遭到入侵的用户安全手册。 有关其他详细信息，请参阅博客文章使用 [Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) 加快检测和响应用户泄露的时间并限制泄露范围。

![针对受损用户的自动调查](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

利用受损的用户安全手册，组织的安全团队可以：

- 加快检测遭到入侵的用户帐户;

- 在帐户泄露时限制泄露范围;和

- 更有效地响应受损用户。

## <a name="compromised-user-alerts"></a>遭到入侵的用户警报

当用户帐户受到威胁时，会发生异常或异常行为。 例如，网络钓鱼和垃圾邮件可能从受信任的用户帐户内部发送。 Defender for Office 365 可以检测 Office 365 中电子邮件模式和协作活动中的此类异常。 发生这种情况时，将触发警报，并开始威胁缓解过程。

例如，下面是由于可疑电子邮件发送而触发的警报：

![由于可疑电子邮件发送而触发的警报](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

下面是在达到用户的发送限制时触发的警报示例：

![通过达到发送限制触发的警报](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>调查和响应遭到入侵的用户

用户帐户泄露时，将触发警报。 在某些情况下，该用户帐户将被阻止并阻止发送任何进一步的电子邮件，直到组织的安全运营团队解决该问题为止。 在其他情况下，将开始自动调查，这可能会导致安全团队采取建议的操作。

- [查看和调查受限用户](#view-and-investigate-restricted-users)

- [查看有关自动调查的详细信息](#view-details-about-automated-investigations)

> [!IMPORTANT]
> 您必须具有适当的权限才能执行以下任务。 请参阅 [使用 AIR 功能所需的权限](office-365-air.md#required-permissions-to-use-air-capabilities)。

### <a name="view-and-investigate-restricted-users"></a>查看和调查受限用户

有几个选项可以导航到受限用户列表。 例如，在安全与&中心，可以转到"威胁管理"" \> **审阅受限** \> **用户"。** 以下过程介绍使用 **警报** 仪表板的导航，这是查看可能触发的各种警报的一个好方法。

1. 转到 <https://protection.office.com> 并登录。

2. 在导航窗格中，选择 **警报** \> **仪表板**。

3. 在"**其他警报"小** 组件中，选择"**受限用户"。**

   ![其他警报小组件](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   这将打开受限用户的列表。

   ![Office 365 中的受限用户](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. 在列表中选择用户帐户以查看详细信息并采取措施，例如 [释放受限制的用户](removing-user-from-restricted-users-portal-after-spam.md)。

### <a name="view-details-about-automated-investigations"></a>查看有关自动调查的详细信息

开始自动调查后，可以在安全与合规中心内查看&结果。 转到 **"威胁管理** \> **调查"，** 然后选择调查以查看其详细信息。

若要了解详细信息，请参阅 [查看调查的详细信息](air-view-investigation-results.md)。

## <a name="keep-the-following-points-in-mind"></a>请记住以下几点

- **随时了解警报**。 正如你所知，未发现泄露的时间越长，对组织、客户和合作伙伴造成广泛影响和成本的可能性越大。 提前检测和及时响应对于缓解威胁至关重要，尤其是在用户帐户受到威胁时。

- **自动化可帮助（但不替换）安全运营团队**。 自动调查和响应功能可以尽早检测到受到威胁的用户，但安全运营团队可能需要参与并执行一些调查和修正。 需要一些帮助吗？ 请参阅 [审阅和批准操作](air-review-approve-pending-completed-actions.md)。

- **不要依赖可疑登录警报作为唯一指示器**。 当用户帐户受到威胁时，它可能会或可能不会触发可疑的登录警报。 有时，是在帐户泄露后发生的一系列活动触发警报。 想要了解有关警报的更多信息？ 请参阅 [警报策略](../../compliance/alert-policies.md)。

## <a name="next-steps"></a>后续步骤

- [查看使用 AIR 功能所需的权限](office-365-air.md#required-permissions-to-use-air-capabilities)

- [在 Office 365 中查找并调查恶意电子邮件](investigate-malicious-email-that-was-delivered.md)

- [了解 Microsoft Defender for Endpoint 中的 AIR](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [访问 Microsoft 365 路线图，了解即将推出和即将推出哪些功能](https://www.microsoft.com/microsoft-365/roadmap?filters=)