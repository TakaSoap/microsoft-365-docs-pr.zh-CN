---
title: 使用自动调查和响应解决已损坏的用户帐户
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护、已泄露
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: 了解如何使用 Microsoft Defender for Office 365 计划2中的自动调查和响应功能，以加快检测和解决受危害的用户帐户的过程。
ms.openlocfilehash: 0da065bea17796d09de771a767991804afb5335b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844592"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>使用自动调查和响应解决已损坏的用户帐户

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender For Office 365 计划 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) 包括功能强大的 [自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (空中) 功能。 此类功能可以将安全操作团队保存大量时间和处理威胁的工作。 Microsoft 继续改进安全功能。 最近，空中功能已得到增强，可在当前预览) 中 (的用户安全行动手册。 阅读本文，了解有关已损坏用户安全行动手册的详细信息。 通过 Microsoft Defender for Office 365，了解更多详细信息，了解博客文章 [加快了检查和响应用户泄露和限制泄露范围的时间](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) 。

![对受损用户的自动调查](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

已损坏的用户安全行动手册使贵组织的安全团队能够：

- 加速对已泄露用户帐户的检测;

- 在帐户受到威胁时限制泄露的范围;并

- 更有效地响应已损坏的用户。

## <a name="compromised-user-alerts"></a>已损坏的用户通知

当用户帐户受到威胁时，将发生反常或反常行为。 例如，网络钓鱼和垃圾邮件可能会从受信任的用户帐户内部发送。 适用于 Office 的 Defender 365 可以检测到 Office 365 中的电子邮件模式和协作活动中的此类异常。 发生这种情况时，将触发警报，并开始威胁缓解过程。

例如，以下是由于可疑电子邮件发送而触发的警报：

![因可疑电子邮件发送而触发的警报](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

下面的示例展示了用户达到发送限制时触发的警报：

![已达到发送限制触发的警报](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>调查已损坏的用户并对其做出响应

当用户帐户受到威胁时，将触发警报。 在某些情况下，该用户帐户将被阻止，并阻止发送任何其他电子邮件，直到组织的安全操作团队解决该问题。 在其他情况下，自动调查开始时可能导致安全团队应采取的建议操作。

- [查看和调查受限制的用户](#view-and-investigate-restricted-users)

- [查看有关自动调查的详细信息](#view-details-about-automated-investigations)

> [!IMPORTANT]
> 您必须具有适当的权限才能执行以下任务。 查看 [使用空中功能所需的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)。

### <a name="view-and-investigate-restricted-users"></a>查看和调查受限制的用户

有几个选项可用于导航到受限制的用户列表。 例如，在安全 & 合规性中心中，可以转到 " **威胁管理** "  >  **查看**  >  **受限制的用户** 。 下面的过程介绍了如何使用 " **通知** " 仪表板进行导航，这是查看可能已触发的各种警报的一种有效方式。

1. 转到 [https://protection.office.com](https://protection.office.com) 并登录。

2. 在导航窗格中，选择 " **通知**  >  **仪表板** "。

3. 在 " **其他通知** " 小组件中，选择 " **受限用户** "。

   ![其他通知小组件](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   这将打开受限制的用户的列表。<br/>![Office 365 中的受限用户](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. 选择列表中的用户帐户以查看详细信息并执行操作，例如， [释放受限制的用户](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam)。

### <a name="view-details-about-automated-investigations"></a>查看有关自动调查的详细信息

自动调查开始后，您可以在安全 & 合规性中心中看到其详细信息和结果。 转到 " **威胁管理**  >  **调查** "，然后选择调查以查看其详细信息。

若要了解详细信息，请参阅 [查看调查的详细信息](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results)。

## <a name="keep-the-following-points-in-mind"></a>请记住以下几点

- **停留在通知的最前面** 。 正如您所知，发现泄露的时间越长，组织、客户和合作伙伴可能会带来广泛的影响和成本。 早期检测和及时响应是缓解威胁的关键，尤其是在用户的帐户受到威胁时。

- **自动化可协助您的安全操作团队，但不能取代** 。 自动化调查和响应功能可以在早期检测到已损坏的用户，但您的安全操作团队可能需要参与并执行一些调查和修正。 需要有关这方面的一些帮助吗？ 请参阅 [审阅和批准操作](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions)。

- **不要依赖可疑登录通知作为唯一的指示器** 。 当用户帐户受到威胁时，它可能会（也可能不触发）可疑登录警报。 有时，它是在帐户泄露后发生的一系列活动，触发警报。 想要了解有关通知的详细信息吗？ 请参阅 [警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。

## <a name="next-steps"></a>后续步骤

- [查看使用 AIR 功能所需的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [查找和调查 Office 365 中的恶意电子邮件](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [了解 Microsoft Defender for Endpoint 中的空气](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [访问 Microsoft 365 路线图以了解即将推出和推出的内容](https://www.microsoft.com/microsoft-365/roadmap?filters=)

