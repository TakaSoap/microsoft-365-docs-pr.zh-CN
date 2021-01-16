---
title: 开始使用攻击模拟培训
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用攻击模拟培训在 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 组织中运行模拟网络钓鱼和密码攻击。
ms.openlocfilehash: 2c00fb27748887c6b8e2fa1458b10f0c3405eef7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877160"
---
# <a name="get-started-using-attack-simulation-training"></a>开始使用攻击模拟培训

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

如果你的组织拥有 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2，其中包括威胁调查和响应功能，可以使用 Microsoft 安全中心中的攻击模拟培训在组织中运行真实的攻击方案。 [](office-365-ti.md) 这些模拟攻击可以帮助你在真正的攻击影响你的最后一线之前识别和查找易受攻击的用户。 阅读本文可了解更多信息。

> [!NOTE]
> 攻击模拟培训取代了 Microsoft [Defender for Office 365](attack-simulator.md)中攻击模拟器中所述的旧攻击模拟器 v1 体验。

## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

- 若要打开 Microsoft 安全中心，请转到 <https://security.microsoft.com/> 。 攻击模拟培训在电子邮件和 **协作攻击** \> **模拟培训中提供**。 若要直接转到攻击模拟培训，请打开 <https://security.microsoft.com/attacksimulator> 。

- 有关跨不同 Microsoft 365 订阅提供攻击模拟培训详细信息，请参阅 [Microsoft Defender for Office 365 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

- 你需要在安全与合规中心& Azure Active Directory 中分配权限，然后才能执行本文中的过程。 具体来说，你需要是组织管理、**安全管理员或** 以下角色之一的成员： 
  - **攻击模拟器管理员**：创建和管理攻击模拟活动的所有方面。
  - **攻击模拟器有效负载作者**：创建管理员稍后可以启动的攻击负载。

  有关详细信息，请参阅安全与[合规中心或&管理员](permissions-in-the-security-and-compliance-center.md)[角色中的权限](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

- 没有用于攻击模拟培训的相应 PowerShell cmdlet。

- 攻击模拟和培训相关的数据存储在 Microsoft 365 服务的其他客户数据中。 有关详细信息，请参阅 [Microsoft 365 数据位置](/microsoft-365/enterprise/o365-data-locations)。 攻击模拟目前不适用于以下区域：SGP、NOR、UAE、ZAF、GER、BRA 和 CHE。

## <a name="simulations"></a>模拟

*网络钓鱼* 是电子邮件攻击的一个通用术语，它尝试窃取看起来来自合法或受信任的发件人的邮件中的敏感信息。 *网络钓鱼* 是分类为社交工程的技术子集 _的一部分_。

在攻击模拟培训中，可以使用多种社交工程技术：

- **凭据获取**：攻击者向收件人发送包含 URL 的邮件。 当收件人单击 URL 时，他们会被带至一个网站，该网站通常显示一个对话框，询问用户输入用户名和密码。 通常，目标页面以表示已知网站为标题，以在用户中建立信任。

- **恶意软件** 附件：攻击者向收件人发送包含附件的邮件。 当收件人打开附件时， (代码，例如，宏) 在用户设备上运行，以帮助攻击者安装其他代码或进一步修改自身。

- **附件中的链接**：这是凭据收集的混合。 攻击者向收件人发送包含附件内 URL 的邮件。 当收件人打开附件并单击 URL 时，他们会被带至一个网站，该网站通常显示一个对话框，询问用户输入用户名和密码。 通常，目标页面以表示已知网站为标题，以在用户中建立信任。

- 指向 **恶意软件的链接**：攻击者向收件人发送一封邮件，其中包含指向已知文件共享网站 (（例如，SharePoint Online 或 Dropbox) ）上的附件的链接。 当收件人单击 URL 时，附件将打开， (例如，宏) 在用户设备上运行，以帮助攻击者安装其他代码或进一步修改自身。

- **按 URL 驱动器**：攻击者向收件人发送包含 URL 的邮件。 当收件人单击 URL 时，他们会被带至尝试运行后台代码的网站。 此后台代码尝试收集有关收件人的信息或在设备上部署任意代码。 通常，目标网站是遭到入侵的已知网站或已知网站的克隆。 熟悉网站有助于让用户确信链接可安全单击。 此技术也称为水 _洞攻击_。

> [!NOTE]
> 在网络钓鱼活动中使用该 URL 之前，请检查受支持的 Web 浏览器中模拟网络钓鱼 URL 的可用性。 虽然我们与许多 URL 信誉供应商合作，始终允许这些模拟 URL，但我们并不总是具有完全覆盖 (例如，Google 安全浏览) 。 大多数供应商都提供指导，以便你始终允许特定 URL (例如 <https://support.google.com/chrome/a/answer/7532419> ，) 。

攻击模拟培训使用的 URL 如下列表所述：

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>创建模拟

有关如何创建和发送新模拟的分步说明，请参阅["模拟网络钓鱼攻击"。](attack-simulation-training.md)

### <a name="create-a-payload"></a>创建有效负载

有关如何创建负载以在模拟中使用的分步说明，请参阅"为攻击模拟培训创建自定义[负载"。](attack-simulation-training-payloads.md)

### <a name="gaining-insights"></a>获取见解

有关如何使用报告获取见解的分步说明，请参阅通过攻击模拟培训 [获得见解](attack-simulation-training-insights.md)。
