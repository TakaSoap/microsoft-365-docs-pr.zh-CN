---
title: 开始使用攻击模拟培训
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用攻击模拟培训在 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 组织中运行模拟网络钓鱼和密码攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6b8a10432c63a12f4d81e67f580f11b4f8b35ed
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701199"
---
# <a name="get-started-using-attack-simulation-training-in-defender-for-office-365"></a>在 Defender for Office 365 中开始使用攻击模拟Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于 Microsoft** [Defender for Office 365计划 2](defender-for-office-365.md)

如果你的组织拥有 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2（[](office-365-ti.md)包括威胁调查和响应功能），可以在 Microsoft 365 Defender 门户中使用攻击模拟培训在组织中运行真实的攻击方案。 这些模拟攻击可以帮助你在真实攻击影响你的最后一线之前识别和查找易受攻击的用户。 阅读本文可了解更多信息。

> [!NOTE]
> 攻击模拟培训取代了在安全与合规中心（位于威胁管理攻击模拟器或 ）&提供的旧 \> **攻击** 模拟器 v1 体验 <https://protection.office.com/attacksimulator> 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Microsoft 365 Defender 门户，请转到 <https://security.microsoft.com>。 攻击模拟培训位于电子邮件和 **协作** \> **攻击模拟培训中**。 若要直接转到攻击模拟培训，请打开 <https://security.microsoft.com/attacksimulator> 。

- 有关跨不同订阅提供攻击模拟培训Microsoft 365，请参阅 Microsoft Defender for Office 365 [service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

- 您需在Azure Active Directory权限，然后才能执行本文中的过程。 具体来说，你需要是以下角色之一的成员：
  - **组织管理**
  - **安全管理员**
  - **攻击模拟管理员** <sup>\*</sup> ：创建和管理攻击模拟市场活动的各个方面。
  - **攻击有效负载作者** <sup>\*</sup> ：创建管理员稍后可以启动的攻击负载。

  <sup>\*</sup>当前不支持将用户添加到 Microsoft 365 Defender门户中的此角色。

  有关详细信息，请参阅管理门户[中的权限Microsoft 365 Defender或](permissions-microsoft-365-security-center.md)[关于管理员角色](../../admin/add-users/about-admin-roles.md)。

- 没有用于攻击模拟培训的相应 PowerShell cmdlet。

- 攻击模拟和培训相关的数据与其他客户数据一起存储，Microsoft 365服务。 有关详细信息，请参阅[Microsoft 365位置](../../enterprise/o365-data-locations.md)。 攻击模拟可用于以下区域：NAM、APC、EUR、IND、CAN、AUS、FRA、GBR、JPN、EUR、BRA、BRA、CHE、NOR、ZAF、ARE 和 DEU。

  > [!NOTE]
  > NOR、ZAF、ARE 和 DEU 是最新的新增功能。 除报告的电子邮件遥测之外的所有功能将在这些区域可用。 我们正在努力启用此功能，并会在报告的电子邮件遥测可用后立即通知我们的客户。 

- 自 2021 年 6 月 15 日起，攻击模拟GCC。 如果你的组织拥有 Office 365 G5 GCC 或 Microsoft Defender for Office 365 (计划 2) 政府版，可以使用 Microsoft 365 Defender 门户中的攻击模拟培训在组织中运行实际攻击方案，如本文所述。 攻击模拟培训尚未在高GCC DoD 环境中提供。

> [!NOTE]
> 攻击模拟培训将一部分功能作为试用版向 E3 客户提供。 试用版包含使用凭据获取有效负载的能力，以及选择"ISA 网络钓鱼"或"批量市场网络钓鱼"培训体验的能力。 E3 试用版产品/服务中没有任何其他功能。

## <a name="simulations"></a>模拟

*网络钓鱼* 是电子邮件攻击的一个通用术语，它尝试窃取看起来来自合法或受信任的发件人的邮件中的敏感信息。 *网络钓鱼* 是分类为社交工程的技术子集 _的一部分_。

在攻击模拟培训中，提供了多种类型的社交工程技术：

- **凭据获取**：攻击者向收件人发送包含 URL 的邮件。 当收件人单击 URL 时，他们会被带至一个网站，该网站通常显示一个对话框，要求用户输入用户名和密码。 通常，目标页面以表示已知网站为标题，以在用户中建立信任。

- **恶意软件** 附件：攻击者向收件人发送包含附件的邮件。 当收件人打开附件时， (代码，例如，) 用户设备上运行一个宏，以帮助攻击者安装其他代码或进一步自我编写代码。

- **附件中的链接**：这是凭据获取的混合。 攻击者向收件人发送一封邮件，其中包含附件内的 URL。 当收件人打开附件并单击该 URL 时，他们会访问一个网站，该网站通常显示一个对话框，要求用户输入用户名和密码。 通常，目标页面以表示已知网站为标题，以在用户中建立信任。

- **链接到恶意软件**：攻击者向收件人发送一封邮件，其中包含指向已知文件共享网站上附件的链接 (例如，SharePoint Online 或 Dropbox) 。 当收件人单击 URL 时，附件将打开 (任意代码（例如，宏) 将在用户设备上运行，以帮助攻击者安装其他代码或进一步编写代码）。

- **按 URL 驱动器**：攻击者向收件人发送包含 URL 的邮件。 当收件人单击 URL 时，他们会被带至尝试运行后台代码的网站。 此后台代码尝试收集有关收件人的信息或在设备上部署任意代码。 通常，目标网站是已遭到入侵的已知网站或已知网站的克隆。 熟悉网站有助于让用户确信链接可安全单击。 此技术也称为水 _洞攻击_。

> [!NOTE]
> 在网络钓鱼活动中使用该 URL 之前，请检查支持的 Web 浏览器中模拟网络钓鱼 URL 的可用性。 虽然我们与许多 URL 信誉供应商合作以始终允许这些模拟 URL，但我们并不总是具有完全覆盖范围 (例如，Google 保险箱浏览) 。 大多数供应商提供的指导允许你始终允许特定 URL (例如 <https://support.google.com/chrome/a/answer/7532419> ，) 。

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

有关如何创建和发送新模拟的分步说明，请参阅 [模拟网络钓鱼攻击](attack-simulation-training.md)。

### <a name="create-a-payload"></a>创建有效负载

有关如何创建负载以用于模拟的分步说明，请参阅为 [攻击模拟培训创建自定义负载](attack-simulation-training-payloads.md)。

### <a name="gaining-insights"></a>获取见解

有关如何通过报告获取见解的分步说明，请参阅通过 [攻击模拟培训获取见解](attack-simulation-training-insights.md)。

> [!NOTE]
> 攻击模拟器使用 保险箱 Links in Defender for Office 365 安全跟踪发送给网络钓鱼活动的目标收件人的有效负载邮件中 URL 的单击数据，即使 保险箱 链接策略中已打开"不跟踪用户单击"设置。
