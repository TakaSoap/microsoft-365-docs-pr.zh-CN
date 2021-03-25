---
title: 开始使用攻击模拟培训
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
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
ms.openlocfilehash: 6e344153ef433bc13b16136e584ec4da73fcef6a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203215"
---
# <a name="get-started-using-attack-simulation-training"></a>开始使用攻击模拟培训

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

如果你的组织拥有 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2，其中包括威胁调查和响应功能，可以在 Microsoft 安全中心内使用攻击模拟培训在组织中运行真实的攻击方案。 [](office-365-ti.md) 这些模拟攻击可以帮助你在真实攻击影响你的最后一线之前识别和查找易受攻击的用户。 阅读本文可了解更多信息。

> [!NOTE]
> 攻击模拟培训取代了 Microsoft [Defender for Office 365](attack-simulator.md)中攻击模拟器中所述的旧攻击模拟器 v1 体验。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Microsoft 安全中心，请转到 <https://security.microsoft.com/> 。 攻击模拟培训位于电子邮件和 **协作** \> **攻击模拟培训中**。 若要直接转到攻击模拟培训，请打开 <https://security.microsoft.com/attacksimulator> 。

- 有关不同 Microsoft 365 订阅中攻击模拟培训的可用性详细信息，请参阅 [Microsoft Defender for Office 365 服务说明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

- 您需在安全与合规中心或 Azure Active Directory &分配权限，然后才能执行本文中的过程。 具体来说，你需要是组织管理、安全 **管理员** 或以下角色之一的成员： 
  - **攻击模拟器管理员**：创建和管理攻击模拟活动的所有方面。
  - **攻击模拟器有效负载作者**：创建管理员稍后可以启动的攻击负载。

  有关详细信息，请参阅安全[与合规中心&权限或](permissions-in-the-security-and-compliance-center.md)[关于管理员角色](../../admin/add-users/about-admin-roles.md)。

- 没有用于攻击模拟培训的相应 PowerShell cmdlet。

- 攻击模拟和培训相关的数据与 Microsoft 365 服务的其他客户数据存储在一起。 有关详细信息，请参阅 [Microsoft 365 数据位置](../../enterprise/o365-data-locations.md)。 攻击模拟可用于以下区域：NAM、APC、EUR、IND、CAN、AUS、FRA、GBR、JPN 和 EUR。

## <a name="simulations"></a>模拟

*网络钓鱼* 是电子邮件攻击的一个通用术语，它尝试窃取看起来来自合法或受信任的发件人的邮件中的敏感信息。 *网络钓鱼* 是分类为社交工程的技术子集 _的一部分_。

在攻击模拟培训中，提供了多种社交工程技术：

- **凭据获取**：攻击者向收件人发送包含 URL 的邮件。 当收件人单击 URL 时，他们会被带至一个网站，该网站通常显示一个对话框，要求用户输入用户名和密码。 通常，目标页面以表示已知网站为标题，以在用户中建立信任。

- **恶意软件** 附件：攻击者向收件人发送包含附件的邮件。 当收件人打开附件时， (代码，例如，宏) 在用户设备上运行，以帮助攻击者安装其他代码或进一步自我编写代码。

- **附件中的链接**：这是凭据获取的混合。 攻击者向收件人发送一封邮件，其中包含附件内的 URL。 当收件人打开附件并单击该 URL 时，他们会访问一个网站，该网站通常显示一个对话框，要求用户输入用户名和密码。 通常，目标页面以表示已知网站为标题，以在用户中建立信任。

- 链接到 **恶意软件**：攻击者向收件人发送一封邮件，其中包含指向已知文件共享网站 (例如，SharePoint Online 或 Dropbox) 的附件的链接。 当收件人单击 URL 时，附件将打开并任意代码 (例如，宏) 在用户设备上运行，以帮助攻击者安装其他代码或进一步安装代码。

- **按 URL 驱动器**：攻击者向收件人发送包含 URL 的邮件。 当收件人单击 URL 时，他们会被带至尝试运行后台代码的网站。 此后台代码尝试收集有关收件人的信息或在设备上部署任意代码。 通常，目标网站是已遭到入侵的已知网站或已知网站的克隆。 熟悉网站有助于让用户确信链接可安全单击。 此技术也称为水 _洞攻击_。

> [!NOTE]
> 在网络钓鱼活动中使用该 URL 之前，请检查模拟网络钓鱼 URL 在受支持的 Web 浏览器中的可用性。 虽然我们与许多 URL 信誉供应商合作，始终允许这些模拟 URL，但我们并不总是具有完全覆盖 (例如，Google 安全浏览) 。 大多数供应商提供的指导允许你始终允许特定 URL (例如 <https://support.google.com/chrome/a/answer/7532419> ，) 。

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
> 攻击模拟器使用 Defender for Office 365 中的安全链接安全跟踪发送给网络钓鱼活动的目标收件人的有效负载消息中 URL 的单击数据，即使安全链接策略中的"不跟踪用户单击"设置已打开。