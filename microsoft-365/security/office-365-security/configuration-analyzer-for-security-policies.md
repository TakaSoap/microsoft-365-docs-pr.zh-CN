---
title: 安全策略的配置分析器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用配置分析器查找和修复预设安全策略中的"标准保护"和"严格保护"中的设置下面的安全策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2b732922cf0a7d9f1d44a24d3b7b6f025f3c2a27
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573423"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP 和 Microsoft Defender for Office 365 中的保护策略的配置Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender门户中的配置分析器提供了一个中心位置，用于查找和修复安全策略，其中设置位于预设安全策略中的"标准保护"和"严格保护配置文件"[设置下面](preset-security-policies.md)。

配置分析器分析以下类型的策略：

- **Exchange Online Protection (EOP)** 策略：这包括Microsoft 365邮箱的 Exchange Online 组织，以及没有邮箱Exchange Online独立 EOP 组织：
  - [反垃圾邮件策略](configure-your-spam-filter-policies.md)。
  - [反恶意软件策略](configure-anti-malware-policies.md)。
  - [EOP 防钓鱼策略](set-up-anti-phishing-policies.md#spoof-settings)。

- **Microsoft Defender for Office 365** 策略：这包括具有 Microsoft 365 E5 或 Defender for Office 365 加载项订阅的组织：
  - Microsoft Defender for Office 365中的反网络钓鱼策略，包括：
    - EOP [防钓鱼](set-up-anti-phishing-policies.md#spoof-settings) 策略中可用的相同欺骗设置。
    - [模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [保险箱链接策略](set-up-safe-links-policies.md)。
  - [保险箱附件策略](set-up-safe-attachments-policies.md)。

用作基线的标准和严格策略设置值在 EOP 和 Microsoft Defender 的推荐设置中进行了介绍[，Office 365安全](recommended-settings-for-eop-and-office365.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到配置 **分析器页面** ，请使用 <https://security.microsoft.com/configurationAnalyzer> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您需在 Microsoft 365 Defender 门户中分配权限，然后才能执行本文中的过程：
  - 若要使用 **配置分析器** 并更新安全策略，您必须是组织管理或安全 **管理员角色****组** 的成员。
  - 若要对配置分析器进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。

  有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

  > [!NOTE]
  >
  > - 将用户添加到相应的 Azure Active Directory 角色会为用户提供在 Microsoft 365 Defender _门户中_ 所需的权限，以及用户对 Microsoft 365 中其他功能Microsoft 365。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

## <a name="use-the-configuration-analyzer-in-the-microsoft-365-defender-portal"></a>使用配置门户中的Microsoft 365 Defender分析器

在 Microsoft 365 Defender 门户中，转到"**模板** 策略"部分中的"电子邮件&协作策略& \> **规则** \> **威胁策略** 配置 \> **分析** 器"。

" **配置分析器** "页包含三个主要选项卡：

- **标准建议**：将现有安全策略与标准建议进行比较。 你可以调整设置值，使它们达到与 Standard 相同的级别。
- **严格建议**：将现有安全策略与严格建议进行比较。 你可以调整设置值，使它们达到与 Strict 相同的级别。
- **配置偏移分析和历史记录**：审核和跟踪策略更改。

### <a name="standard-recommendations-and-strict-recommendations-tabs-in-the-configuration-analyzer"></a>配置分析器中的标准建议和严格建议选项卡

默认情况下，配置分析器在"标准建议 **"选项卡上** 打开。可以切换到"严格 **建议"** 选项卡。两个选项卡上的设置、布局和操作相同。

![设置配置分析器中的"配置和建议"视图。](../../media/configuration-analyzer-settings-and-recommendations-view.png)

与标准或严格保护相比，选项卡的第一部分显示每种类型的策略中需要改进的设置数。 策略类型为：

- **反垃圾邮件**
- **防钓鱼**
- **反恶意软件**
- **保险箱订阅** (Microsoft Defender for Office 365) 
- **保险箱订阅** (Microsoft Defender for Office 365) 

如果未显示策略类型和编号，则此类型的所有策略都满足标准保护或严格保护的建议设置。

选项卡的其余部分是需要达到标准或严格保护级别的设置表。 该表包含以下列：

- **推荐**：Standard 或 Strict 保护配置文件中的设置的值。
- **策略**：包含设置的受影响策略的名称。
- **策略组/设置名称**：需要你注意的设置的名称。
- **策略类型**：反垃圾邮件、反网络钓鱼、反恶意软件、保险箱链接或保险箱附件。
- **当前配置**：设置的当前值。
- **上次修改** 时间：上次修改策略的日期。
- **状态**：通常情况下，此值为 **"未启动"。**

### <a name="change-a-policy-setting-to-the-recommended-value"></a>将策略设置更改为建议的值

在配置 **分析** 器的标准保护或严格保护选项卡上，选择表中的行。 将显示以下按钮：

- **应用建议**
- **查看策略**
- **刷新**：

如果您选择一行 **并单击"** 应用建议"， (显示一个确认对话框，并会显示一个) 对话框。 如果单击 **"确定"，** 将发生以下情况：

- 该设置将更新为建议的值。
- 只有 **"刷新"** 按钮 **("应用** 建议"和"查看"策略) 。 
- 行 **的 Status** 值将更改为 **Complete**。

如果你选择一行并单击查看策略，你将在 Microsoft 365 Defender 门户中查看受影响策略的详细信息飞出，你可以手动更新该设置。

自动或手动更新设置后，单击"刷新"以查看建议数量减少以及从结果中删除更新的行。

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>配置分析器中的"配置偏移分析和历史记录"选项卡

此选项卡允许您跟踪对安全策略所做的更改，以及这些更改与"标准"或"严格"设置之间的比较情况。 默认情况下，将显示以下信息：

- **上次修改时间**
- **修改者**
- **设置名称**
- **策略**：受影响策略的名称。
- **类型**：反垃圾邮件、反网络钓鱼、反恶意软件、保险箱链接或保险箱附件。
- **配置更改**：设置的旧值和新值
- **配置偏移**：值 **Increase** 或 **Decrease，** 指示与建议的标准或严格设置相比，设置安全性增加或降低。

要筛选结果，请单击“**筛选器**”。 在出现的 **"** 筛选器"飞出中，可以从以下筛选器中选择：

- **开始时间和****结束** () ：你可以从今天返回 90 天。
- **标准保护** 或 **严格保护**

完成后，单击“**应用**”。

若要将结果导出到.csv文件，请单击"导出 **"。**

若要按特定的"修改者 **"、"****设置** 名称"或"**类型**"值筛选结果，请使用"**搜索"** 框。

![配置分析器中的配置偏移分析和历史记录视图。](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
