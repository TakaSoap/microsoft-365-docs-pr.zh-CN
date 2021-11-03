---
title: 在 Defender for 保险箱 中配置链接设置的全局Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何查看和配置全局设置， (Microsoft Defender for Office 365 中的 Office 365 应用) 保险箱阻止以下 URL"列表和保护。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4386f0f1b6dee2b877790b3ae715d1fb1e5f535a
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701509"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for 保险箱 中配置链接的全局Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。 如果你是一位家庭用户，正在查找有关 Outlook 中的安全链接的信息，请参阅 Advanced [Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

保险箱链接是 Microsoft [Defender for Office 365](defender-for-office-365.md)中的一项功能，它提供对邮件流中入站电子邮件的 URL 扫描，以及电子邮件和其他位置中 URL 和链接的单击验证时间。 有关详细信息，请参阅 Microsoft Defender for[保险箱 中的链接Office 365。](safe-links.md)

您可以在"链接保险箱中配置大多数保险箱链接设置。 有关说明，请参阅在[Microsoft Defender 保险箱设置链接策略Office 365。](set-up-safe-links-policies.md)

但是，保险箱链接也使用在链接策略本身之外配置的保险箱全局设置：

- " **阻止以下 URL"** 列表。 此设置适用于任何活动"链接"策略中包含的保险箱用户。 有关详细信息，请参阅[链接的"阻止以下 URL"保险箱列表](safe-links.md#block-the-following-urls-list-for-safe-links)
- 保险箱链接应用Office 365保护。 这些设置适用于组织中获得 Defender for Office 365 许可的所有用户，而不管用户是否包含在活动的 保险箱 链接策略中。 有关详细信息，请参阅保险箱[应用的链接Office 365设置](safe-links.md#safe-links-settings-for-office-365-apps)。

您可以在 保险箱 Microsoft 365 Defender 门户中或在 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置全局 Microsoft 365 链接Exchange Online;适用于没有邮箱且Exchange Online Microsoft Defender for Office 365 加载项订阅的组织的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 尽管没有默认的 保险箱 链接策略，但内置保护预设安全策略为未在自定义 保险箱 链接策略) 中定义的所有收件人 (提供 保险箱 (链接保护。 有关详细信息，请参阅[Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md)。 您还可以创建一保险箱链接策略，以应用于特定用户、组或域。 有关说明，请参阅在[Microsoft Defender 保险箱设置链接策略Office 365。](set-up-safe-links-policies.md)

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到"链接 **保险箱，** 请使用 <https://security.microsoft.com/safelinksv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要为链接保险箱全局设置，您必须是组织管理或 **安全管理员角色组** 的成员。 
  - 若要对链接的全局设置进行只读保险箱，您需要是全局读取 **者** 或安全读者 **角色组的成员**。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：

  - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的权限。有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关我们推荐的用于链接的全局保险箱值，请参阅保险箱[链接设置。](recommended-settings-for-eop-and-office365.md#safe-links-settings)

- 最多允许应用新策略或更新策略 30 分钟。

- [新功能不断添加到 Microsoft Defender for Office 365。](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) 添加新功能时，可能需要对现有"链接"策略保险箱调整。

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a>配置网站门户中的"阻止以下 URL"Microsoft 365 Defender列表

"**阻止以下 URL"** 列表标识应始终被支持应用中的"链接保险箱阻止的链接。 有关详细信息，请参阅链接[的"阻止以下 URL"保险箱列表](safe-links.md#block-the-following-urls-list-for-safe-links)。

1. 在 Microsoft 365 Defender 门户中，转到"策略"部分中的"电子邮件&协作策略&规则威胁保险箱链接 \>  \>  \> " 。 

2. 在 **"保险箱"页上**，单击"**全局设置"。** In the **保险箱 Links policy for your organization** fly out that appears， go to the Block the following **URLs** box.

3. 配置一个或多个条目，如"阻止以下 URL"列表的条目 [语法中所述](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

   完成后，单击“**保存**”。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>在 PowerShell 中配置"阻止以下 URL"列表

有关条目语法的详细信息，请参阅"阻止以下 [URL"列表的条目语法](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

您可以使用 **Get-AtpPolicyForO365** cmdlet 查看 _BlockURLs_ 属性中的现有条目。

- 若要添加将替换任何现有条目的值，请使用 PowerShell 或 PowerShell Exchange Online中的Exchange Online Protection语法：

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  本示例向列表中添加以下条目：

  - 阻止域、子域和路径的 fabrikam.com。
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

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a>在 保险箱 门户中为 Office 365 应用配置 Microsoft 365 Defender 链接保护

保险箱适用于应用Office 365的链接保护适用于支持的文档Office桌面、移动和 Web 应用中的文档。 有关详细信息，请参阅保险箱[应用的链接Office 365设置](safe-links.md#safe-links-settings-for-office-365-apps)。

1. 在 Microsoft 365 Defender 门户中，转到"策略"部分中的"电子邮件&协作策略&规则威胁保险箱链接 \>  \>  \> " 。 

2. 在 **"保险箱"页上**，单击"**全局设置"。** 在 **保险箱"** 组织的链接策略"飞出部分，配置 设置 中适用于受支持的 Office 365 **应用中的内容的设置**：

   - **Use 保险箱 Links in Office 365 apps**： Verify the toggle is to the right to enable 保险箱 Links for supported Office 365 apps： Toggle ![ ](../../media/scc-toggle-on.png) on.

   - **Do not track when users click protected links in Office 365 apps**： Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps： Toggle ![ off. ](../../media/scc-toggle-off.png) .

   - **请勿让用户** 单击到 Office 365 应用中的原始 URL：验证切换是否位于右侧，以防止用户单击到受支持的 Office 365 应用中的原始阻止的 URL： ![ 打开 ](../../media/scc-toggle-on.png) 。

   完成后，单击“**保存**”。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>在 PowerShell 保险箱为 Office 365 应用配置链接保护

如果你希望使用 PowerShell 为 Office 365 应用配置 保险箱 链接保护，请使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的以下语法：

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

此示例配置以下设置，用于保险箱应用中的链接Office 365保护：

- 保险箱我们Office 365 _EnableSafeLinksForO365Clients_ 参数时， (应用的链接将打开，默认值为 $true) 。
- 跟踪受支持应用中与阻止的 URL Office 365用户单击。
- 如果用户未使用 _AllowClickThrough_ 参数 (则不允许用户单击访问受支持的 Office 365 应用中阻止的原始 URL，默认值为 $false) 。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否成功配置了 保险箱 链接的全局设置 (阻止以下 **URL** 列表和 Office 365 应用保护设置) ，请执行下列任一步骤：

- 在 Microsoft 365 Defender 门户中，转到"策略"部分中的"电子邮件&协作策略"&"规则威胁策略 \>  \>  \> **保险箱** 链接 \> "，单击"全局设置"，然后验证显示在飞出中的设置。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，运行以下命令并验证设置：

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  有关语法和参数的详细信息，请参阅 [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。
