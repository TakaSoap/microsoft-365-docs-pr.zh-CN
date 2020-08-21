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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用配置分析器，查找并修复安全策略，其中包含标准保护和严格保护预设安全策略下的设置。
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825769"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a>EOP 和 Office 365 ATP 中保护策略的配置分析器

> [!NOTE]
> 本主题中所述的功能在预览中，并不是在所有组织中可用，可能会发生更改。

安全 & 合规中心中的配置分析器提供了一个中央位置，用于查找并修复任何安全策略，这些策略包含预设安全策略中标准保护和严格保护 [配置文件设置下方的设置](preset-security-policies.md)。

配置分析器分析了以下类型的策略：

- **Exchange Online Protection (EOP) 策略**：包括具有 Exchange Online 邮箱的 Microsoft 365 组织和独立的 EOP 组织，无需 Exchange Online 邮箱：
  
  - [反垃圾邮件策略](configure-your-spam-filter-policies.md)。
  - [反恶意软件策略](configure-anti-malware-policies.md)。
  - [EOP 反网络钓鱼策略](set-up-anti-phishing-policies.md#spoof-settings)。

- **Office 365 高级威胁防 (ATP) 策略**：其中包括订阅有 Microsoft 365 E5 或 Office 365 ATP 的组织：

  - ATP 防钓鱼策略，包括：

    - EOP [反网络](set-up-anti-phishing-policies.md#spoof-settings) 钓鱼策略中提供的相同欺骗设置。
    - [模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [安全链接策略](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)。

  - [安全附件策略](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)。

EOP **和** **Office** 365 ATP 安全的推荐设置中介绍了用作基线的标准和 [严格策略设置值](recommended-settings-for-eop-and-office365-atp.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 要直接转到"配置 **分析器"** 页面，请使用 <https://protection.office.com/configurationAnalyzer> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 若要使用配置分析 **器** 并对安全策略进行更新，您需要是以下角色组的成员之一：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 对于对配置分析器的只读访问权限，您需要是以下角色组的成员之一：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>使用安全与合规中心中的&器

在安全与 &合规中心内，转到 **威胁** \> **管理** \> **策略配置分析器**。

!["威胁管理策略"页上的"配置分析器 \> "小组件](../../media/configuration-analyzer-widget.png)

配置分析器有两个主要选项卡：

- **设置和建议**：你可以选取"标准"或"严格"，并将这些设置与现有安全策略进行比较。 在结果中，你可以调整设置的值以使其与标准或严格级别相同。

- **配置摘要分析和历史记录**：此视图允许根据配置分析器在一段时间内所做的更改，跟踪您已对策略所做的更改。

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>配置分析器中的设置和建议选项卡

默认情况下，此选项卡将打开与标准保护配置文件的比较。 单击"视图严格"建议可切换到严 **格保护配置文件比较**。 要切换回来，**请选择"查看标准建议"。**

![配置分析器中的设置和建议视图](../../media/configuration-analyzer-settings-and-recommendations-view.png)

默认情况下，" **策略组/设置名称** "列包含不同类型的安全策略以及需要改善 (（如果有）的策略中的设置数量的折叠) 。 策略类型为：

- **反垃圾邮件**
- **防钓鱼**
- **反恶意软件**
- **如果你的订阅包括 ATP** (管理者，则 ATP 安全) 
- **如果订阅包括 ATP** (，则 ATP 安全链接) 

在默认视图中，所有内容都已折叠。 在每个策略旁边，会显示来自策略 (的比较结果摘要，可以修改) 以及无法修改严格的标准或严格保护配置文件 (的相应) 策略中的设置。 你将看到以下信息：

- **绿色**：所有现有策略中的全部设置至少与要比较的保护配置文件一安全。
- **Amber：** 现有策略中的一少设置不如你正在比较的保护配置文件一捷。
- **红**色：现有策略中的大量设置不如你正比较的保护配置文件一安全。 在许多策略中，这可能是许多策略中的几个设置，也可以是一个策略中的许多设置。

对于可采用的比较，你将看到文本：遵 **循建议的所有** \<**Standard** or **Strict**\> **设置**。 否则，你将看到建议更改的设置的数量。

如果展开 **策略组/设置名称**，则会显示需要注意的每个特定策略中的所有策略和关联设置。 或者，你可以展开特定类型的策略 (例如， **反垃圾邮件** 垃圾邮件) ，查看那些需要你关注的策略类型中的设置。

如果比较针对的改进未提供 (建议，) ，则展开策略会显示"nothing"。 如果以下各列中显示任意 (改善建议) ，则显示需要注意的设置，且以下列中显示相应的信息：

- 需要关注你的设置的名称。 例如，在上面的屏幕截图中，它是 **反垃圾邮件策略中的** 批量电子邮件阈值。

- **Policy：** 包含设置的受影响策略的名称。

- **应用于**：受影响的策略应用到的用户数量。

- **当前配置**：设置的当前值。

- **上次**修改时间：上次修改策略的日期。

- **建议：** 标准保护配置文件或严格保护配置文件中设置的值。 要更改策略中设置的值，以与保护配置文件中的建议值匹配，请单击"**采用"。** 如果更改成功，你将看到以下消息 **：建议已成功采用**。 单击 **"** 刷新"可查看建议数量减少，并从结果中删除特定设置/策略行。

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>配置分析器中的配置详细分析和历史记录选项卡

此选项卡允许您根据安全分析器中的信息跟踪已对自定义安全策略所做的更改。 默认情况下，将显示以下信息：

- **上次修改时间**
- **修改者**
- **设置名称**
- **策略**
- **类型**

若要筛选结果，请单击“筛选器”****。 在 **显示的** 筛选器浮出控件中，可以选择以下筛选器：

- **开始时间** 和 **结束时间** (日期) 
- **标准保护****或严格保护**

要将结果导出到 .csv 文件，请单击"导出 **"。**

![配置分析器中的配置详细分析和历史记录视图](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
