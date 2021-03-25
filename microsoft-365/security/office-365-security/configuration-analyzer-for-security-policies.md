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
description: 管理员可以了解如何使用配置分析器查找和修复低于"标准保护"和"严格保护"预设安全策略的安全策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fd67c93711dc847a25be485b4b016af55e4a31
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203184"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP 和 Microsoft Defender for Office 365 中的保护策略的配置分析器

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

安全与&中心中的配置分析器提供了一个中心位置，用于查找和修复安全策略，其中设置位于预设安全策略中的"标准保护"和"严格保护配置文件" [设置下方](preset-security-policies.md)。

配置分析器分析以下类型的策略：

- **Exchange Online Protection (EOP)** 策略：这包括具有 Exchange Online 邮箱的 Microsoft 365 组织和没有 Exchange Online 邮箱的独立 EOP 组织：

  - [反垃圾邮件策略](configure-your-spam-filter-policies.md)。
  - [反恶意软件策略](configure-anti-malware-policies.md)。
  - [EOP 防钓鱼策略](set-up-anti-phishing-policies.md#spoof-settings)。

- **Microsoft Defender for Office 365 策略**：这包括具有 Microsoft 365 E5 或适用于 Office 365 的 Defender 附加订阅的组织：

  - Microsoft Defender for Office 365 中的防钓鱼策略，其中包括：

    - EOP [防钓鱼](set-up-anti-phishing-policies.md#spoof-settings) 策略中可用的相同欺骗设置。
    - [模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [安全链接策略](set-up-safe-links-policies.md)。

  - [安全附件策略](set-up-safe-attachments-policies.md)。

用作 **基线****的标准** 和严格策略设置值在 EOP 和 [Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md)安全推荐设置中进行了介绍。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到配置 **分析器页面** ，请使用 <https://protection.office.com/configurationAnalyzer> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要使用 **配置分析器** 并更新安全策略，您必须是组织管理或安全 **管理员角色****组** 的成员。
  - 若要对配置分析器进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  > [!NOTE]
  >  
  > - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>使用安全与合规中心&分析器

在安全与&中心，转到"**威胁管理** \> **策略** \> **配置分析器"。**

!["威胁管理策略"页上的配置分析 \> 器小组件](../../media/configuration-analyzer-widget.png)

配置分析器有两个主要选项卡：

- **设置和建议**：选择"标准"或"严格"，并将这些设置与现有的安全策略进行比较。 在结果中，可以调整设置的值，使它们达到与 Standard 或 Strict 相同的级别。

- **配置偏移分析和历史记录**：此视图允许你随着时间的推移跟踪策略更改。

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>配置分析器中的"设置和建议"选项卡

默认情况下，选项卡在与标准保护配置文件的比较中打开。 可以通过单击查看严格建议切换到严格保护 **配置文件的比较**。 若要切换回，请选择 **"查看标准建议"。**

![配置分析器中的设置和建议视图](../../media/configuration-analyzer-settings-and-recommendations-view.png)

默认情况下，" **策略组/** 设置名称"列包含不同类型的安全策略的折叠视图以及需要改进的设置 (（如果有) ）。 策略类型为：

- **反垃圾邮件**
- **防钓鱼**
- **反恶意软件**
- **如果订阅包含** Microsoft Defender for Office 365 (，ATP 安全附件) 
- **如果你的订阅** 包含 Microsoft Defender for Office 365 (，ATP 安全链接) 

在默认视图中，所有内容都折叠。 在每个策略旁边，有一个策略 (的比较结果摘要，您可以修改) 以及标准或严格保护配置文件 (其中不能修改) 的相应策略中的设置。 你将看到要进行比较的保护配置文件的以下信息：

- **绿色**：所有现有策略的所有设置都至少与保护配置文件一样安全。
- **Amber：** 现有策略中的少量设置没有保护配置文件安全。
- **红色**：现有策略中的大量设置没有保护配置文件安全。 这可能是许多策略中的一些设置或一个策略中的许多设置。

For favorable comparisons， you'll see the text： **All settings follow** \<**Standard** or **Strict**\> **recommendations**. 否则，你将看到要更改的建议设置数。

如果展开" **策略组/设置** 名称"，将显示每个需要关注的特定策略中所有策略和相关设置。 或者，您可以扩展特定类型的策略 (例如，"反垃圾邮件) 查看那些需要您注意的策略类型中的设置。

如果比较没有针对绿色策略 (建议) ，则扩展策略不会显示任何结果。 如果存在任何数量的有关改进建议 (或红色) ，则说明需要注意的设置，并且以下列中显示了相应的信息：

- 需要你注意的设置的名称。 例如，在上一个屏幕截图中，它是反垃圾邮件策略中的批量电子邮件阈值。

- **策略**：包含设置的受影响策略的名称。

- **应用于**：应用了受影响策略的用户数。

- **当前配置**：设置的当前值。

- **上次修改** 时间：上次修改策略的日期。

- **建议**：Standard 或 Strict 保护配置文件中的设置的值。 若要更改策略中的设置值以匹配保护配置文件中的推荐值，请单击"采用 **"。** 如果更改成功，你将看到消息："**建议已成功采用"。** 单击 **"** 刷新"查看建议数量减少以及从结果删除特定设置/策略行。

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>配置分析器中的"配置偏移分析和历史记录"选项卡

此选项卡允许你跟踪对自定义安全策略所做的更改。 默认情况下，将显示以下信息：

- **上次修改时间**
- **修改者**
- **设置名称**
- **策略**
- **类型**

若要筛选结果，请单击“筛选器”。 在出现的 **"** 筛选器"飞出中，可以从以下筛选器中选择：

- **开始时间和****结束 (** 日期) 
- **标准保护** 或 **严格保护**

若要将结果导出到 .csv 文件，请单击"导出 **"。**

![配置分析器中的配置偏移分析和历史记录视图](../../media/configuration-analyzer-configuration-drift-analysis-view.png)