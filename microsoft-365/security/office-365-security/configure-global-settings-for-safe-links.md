---
title: 在适用于 Office 365 的 Defender 中配置安全链接设置的全局设置
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for Office 365 中查看和配置全局设置 ("阻止以下 Url" 列表和 Office 365 应用程序的保护) 用于安全链接。
ms.openlocfilehash: 655fba35bf3675bfd571c8e4923a00fbeba85304
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842424"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for Office 365 中配置安全链接的全局设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender For Office 365](office-365-atp.md)的商业客户。 如果您是在 Outlook 中查找有关 Safelinks 的信息的家庭用户，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全链接是 [Microsoft Defender For Office 365](office-365-atp.md) 中的一项功能，用于在邮件流中提供入站电子邮件的 URL 扫描，以及单击电子邮件中的 url 和链接以及在其他位置中进行验证的时间。 有关详细信息，请参阅 [Microsoft Defender For Office 365 中的安全链接](atp-safe-links.md)。

在安全链接策略中配置最安全的链接设置。 有关说明，请参阅 [在 Microsoft Defender For Office 365 中设置安全链接策略](set-up-atp-safe-links-policies.md)。

但是，安全链接还使用适用于所有活动安全链接策略中包含的所有用户的全局设置。 以下全局设置区域：

- **阻止以下 url** 列表。 有关详细信息，请参阅 [安全链接的 "阻止以下 url" 列表](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Office 365 应用的安全链接保护。 有关详细信息，请参阅 [Office 365 应用程序的安全链接设置](atp-safe-links.md#safe-links-settings-for-office-365-apps)。

您可以使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中配置全局安全链接设置，以获取符合 Exchange Online 中邮箱的符合条件的 Microsoft 365 组织;独立 EOP PowerShell for 不含 Exchange Online 邮箱的组织，但使用 Microsoft Defender for Office 365 附加订阅) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全链接的全局设置提供的功能仅适用于包含在活动安全链接策略中的用户。 没有内置的或默认的安全链接策略，因此您需要至少创建一个安全链接策略，以便这些全局设置处于活动状态。 有关说明，请参阅 [在 Microsoft Defender For Office 365 中设置安全链接策略](set-up-atp-safe-links-policies.md)。

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 " **安全链接** " 页面，请使用 <https://protection.office.com/safelinksv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 若要查看和配置安全链接的全局设置，您必须是下列角色组之一的成员：

  - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“ **组织管理** ”或“ **安全管理员** ”。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 **组织管理** 。

- 有关安全链接的全局设置的建议值，请参阅 [安全链接设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)。

- 允许使用最长30分钟的时间来应用新的或更新的策略。

- [新功能将不断添加到 Microsoft Defender For Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)中。 添加新功能时，您可能需要对现有安全链接策略进行调整。

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>在安全 & 合规性中心中配置 "阻止以下 Url" 列表

**Block：以下 url** 列表标识了应始终被受支持的应用程序中的安全链接扫描所阻止的链接。 有关详细信息，请参阅 [安全链接的 "阻止以下 url" 列表](atp-safe-links.md#block-the-following-urls-list-for-safe-links)。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "，然后单击 " **全局设置** "。

2. 在您的组织的 " **安全链接策略** " 飞出时，请转到 " **阻止以下 url** " 框。

3. 配置一个或多个条目，如 ["阻止以下 url 的条目语法" 列表](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)中所述。

   完成时，请单击“保存”。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>在 PowerShell 中配置 "阻止以下 Url" 列表

有关输入语法的详细信息，请参阅 ["阻止以下 url 的条目语法" 列表](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

您可以使用 **AtpPolicyForO365** Cmdlet 查看 _BlockURLs_ 属性中的现有条目。

- 若要添加将替换任何现有条目的值，请在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中使用以下语法：

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  本示例将以下项添加到列表中：

  - 阻止 fabrikam.com 的域、子域和路径。
  - 阻止子域搜索，但不阻止父域或 tailspintoys.com 中的其他子域

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- 若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法：

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  本示例为 adatum.com 添加一个新条目，并删除 fabrikam.com 的条目。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>在安全 & 合规中心中为 Office 365 应用程序配置安全链接保护

Office 365 应用程序的安全链接保护适用于受支持的 Office 桌面、移动设备和 web 应用程序中的文档。 有关详细信息，请参阅 [Office 365 应用程序的安全链接设置](atp-safe-links.md#safe-links-settings-for-office-365-apps)。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "，然后单击 " **全局设置** "。

2. 在您的组织的 " **安全链接策略** " 飞出时，将在 "应用于以下内容的设置" 部分中配置以下设置： " **电子邮件除电子邮件** " 部分：

   - **Office 365 应用程序** ：验证是否右侧的切换为支持的 Office 365 应用程序启用安全链接： ![ 开启 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。

   - **在用户单击安全链接时不进行跟踪** ：将切换向左移动，以跟踪与受支持的 Office 365 应用程序中的阻止 url 相关的用户单击： ![ 关闭 ](../../media/scc-toggle-off.png) 。

   - **不允许用户单击到原始 URL 的安全链接** ：验证切换是否向右以阻止用户在受支持的 Office 365 应用程序中单击原始阻止的 URL： ![ 开启 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。

   完成时，请单击“保存”。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>为 PowerShell 中的 Office 365 应用程序配置安全链接保护

如果您更愿意使用 PowerShell 为 Office 365 应用程序配置安全链接保护，请在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中使用以下语法：

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

此示例为 Office 365 应用中的安全链接保护配置以下设置：

- Office 365 应用的安全链接已打开 (我们不使用 _EnableSafeLinksForO365Clients_ 参数，默认值为) $true。
- 跟踪与受支持的 Office 365 应用程序中的阻止 Url 相关的用户单击。
- 不允许用户在受支持的 Office 365 应用程序中点击到原始阻止的 URL (我们不使用 _AllowClickThrough_ 参数，默认值为 $false) 。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否已成功配置安全链接的全局设置 ( **阻止以下 url** 列表和 Office 365 应用保护设置) ，请执行以下任一步骤：

- 在 "安全性 & 合规性中心" 中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "，单击 " **全局设置** "，然后验证出现的 "飞出" 中的设置。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，运行以下命令并验证设置：

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)。
