---
title: 在 Defender for Office 365 中配置安全链接设置的全局设置
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何查看和配置全局设置 (阻止以下 URL"列表和保护 Office 365 应用) for Safe Links in Microsoft Defender for Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3466f515458b05a5c00053a30fad8f5a84802fd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906560"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for Office 365 中配置安全链接的全局设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender for Office 365](office-365-atp.md)的企业客户。 如果您是一位家庭用户，正在查找有关 Outlook 中安全链接的信息，请参阅高级安全 Outlook.com [信息](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全链接是 Microsoft [Defender for Office 365](office-365-atp.md) 中的一项功能，它提供对邮件流中入站电子邮件的 URL 扫描，以及电子邮件和其他位置中 URL 和链接的单击验证时间。 有关详细信息，请参阅 [Microsoft Defender for Office 365 中的安全链接](atp-safe-links.md)。

您可以在安全链接策略中配置大多数安全链接设置。 有关说明，请参阅在 [Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md)中设置安全链接策略。

但是，安全链接还使用适用于任何活动安全链接策略中包含的所有用户的全局设置。 这些全局设置区域：

- " **阻止以下 URL"** 列表。 有关详细信息，请参阅安全链接的"阻止以下 [URL"列表](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Office 365 应用的安全链接保护。 有关详细信息，请参阅 Office [365 应用的安全链接设置](atp-safe-links.md#safe-links-settings-for-office-365-apps)。

您可以在安全与合规中心或 PowerShell (& Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置全局安全链接设置;适用于没有 Exchange Online 邮箱，但具有 Microsoft Defender for Office 365 附加订阅的组织的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全链接的全局设置提供的功能仅适用于活动安全链接策略中包含的用户。 没有内置或默认安全链接策略，因此您需要创建至少一个安全链接策略，以便这些全局设置处于活动状态。 有关说明，请参阅在 [Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md)中设置安全链接策略。

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到安全 **链接页面** ，请使用 <https://protection.office.com/safelinksv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要配置安全链接的全局设置，您必须是组织管理或 **安全管理员角色组** 的成员。 
  - 若要对安全链接的全局设置进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：

  - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关安全链接的全局设置的建议值，请参阅 [安全链接设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)。

- 最多允许应用新策略或更新策略 30 分钟。

- [新功能不断添加到 Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)中。 添加新功能时，可能需要对现有安全链接策略进行调整。

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>在安全与合规中心中配置"阻止& URL"列表

" **阻止以下 URL"** 列表标识应始终被支持应用中的安全链接扫描阻止的链接。 有关详细信息，请参阅安全链接的"阻止 [以下 URL"列表](atp-safe-links.md#block-the-following-urls-list-for-safe-links)。

1. 在安全与&中心，转到"威胁管理策略 \>  \> **ATP 安全** 链接"，然后单击"全局 **设置"。**

2. 在出现的 **"组织的安全链接** 策略"飞出中，转到" **阻止以下 URL"** 框。

3. 配置一个或多个条目，如"阻止以下 URL"列表的条目 [语法中所述](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

   完成后，单击“**保存**”。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>在 PowerShell 中配置"阻止以下 URL"列表

有关条目语法的详细信息，请参阅"阻止以下 [URL"列表的条目语法](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

您可以使用 **Get-AtpPolicyForO365** cmdlet 查看 _BlockURLs_ 属性中的现有条目。

- 若要添加将替换任何现有条目的值，请使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的以下语法：

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  本示例向列表中添加以下条目：

  - 阻止域、子域和域 fabrikam.com。
  - 阻止子域研究，但不能阻止子域中的父域或其他子 tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- 若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法：

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  本示例为 adatum.com 一个新条目，并删除 fabrikam.com。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>在安全与合规中心为 Office 365 &安全链接保护

Office 365 应用的安全链接保护适用于受支持的 Office 桌面、移动和 Web 应用中的文档。 有关详细信息，请参阅 Office [365 应用的安全链接设置](atp-safe-links.md#safe-links-settings-for-office-365-apps)。

1. 在安全与&中心，转到"威胁管理策略 \>  \> **ATP 安全** 链接"，然后单击"全局 **设置"。**

2. 在出现的"组织 **的安全** 链接策略"飞出中，在"设置"中配置应用于电子邮件 **以外的内容的以下** 设置：

   - **Office 365 应用程序**：验证切换是否位于右侧，为受支持的 Office 365 应用启用安全 ![ 链接：切换为打开 ](../../media/scc-toggle-on.png) 。

   - **Do not track when users click Safe Links**： Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps： Toggle off ![ ](../../media/scc-toggle-off.png) .

   - **不允许用户单击"** 指向原始 URL 的安全链接"：验证切换是否位于右侧，以防止用户单击到受支持的 Office 365 应用中的原始阻止 URL： ![ 切换为打开 ](../../media/scc-toggle-on.png) 。

   完成后，单击“**保存**”。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>在 PowerShell 中为 Office 365 应用配置安全链接保护

如果你希望使用 PowerShell 为 Office 365 应用配置安全链接保护，请使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的以下语法：

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

此示例为 Office 365 应用中的安全链接保护配置以下设置：

- Office 365 应用的安全链接 (我们未使用 _EnableSafeLinksForO365Clients_ 参数，默认值为 $true) 。
- 将跟踪与受支持的 Office 365 应用中阻止的 URL 相关的用户单击次数。
- 不允许用户单击访问受支持的 Office 365 应用中阻止的原始 URL (我们未使用 _AllowClickThrough_ 参数，默认值为 $false) 。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功配置安全链接的全局设置 (阻止以下 **URL** 列表和 Office 365 应用保护设置) ，请执行下列任一步骤：

- 在安全&中心，转到"威胁管理策略ATP 安全链接"，单击"全局设置"，然后验证出现的飞出屏幕 \>  \> 中的设置。 

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，运行以下命令并验证设置：

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  有关语法和参数的详细信息，请参阅 [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。