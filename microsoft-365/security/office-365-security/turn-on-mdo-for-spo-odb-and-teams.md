---
title: 为 SharePoint、OneDrive 和 Microsoft Teams 启用安全附件
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 管理员可以了解如何为 保险箱、OneDrive 和 Microsoft Teams 启用 SharePoint 附件，包括如何为检测到的文件设置警报。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 374e67626eab07cc8ab89a52554658a31e661eec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929943"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>为 SharePoint、OneDrive 和 Microsoft Teams 启用安全附件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for Office 365 for SharePoint、OneDrive 和 Microsoft Teams可保护你的组织避免意外共享恶意文件。 有关详细信息，请参阅 保险箱[Attachments for SharePoint， OneDrive， and Microsoft Teams](mdo-for-spo-odb-and-teams.md)。

本文包含为用户、保险箱和SharePoint OneDrive和Microsoft Teams。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到"附件 **保险箱"页**，请打开 <https://security.microsoft.com/safeattachmentv2> 。

- 若要为 SharePoint、OneDrive 和 Microsoft Teams 启用 保险箱 附件，你需要是 Microsoft 365 Defender 门户中组织管理或安全管理员角色组的成员。  有关详细信息，请参阅 Defender 门户[中Microsoft 365权限](permissions-in-the-security-and-compliance-center.md)。

- 若要SharePoint Online PowerShell 阻止用户下载恶意文件，你需要是 Azure AD 中全局管理员[](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)或 SharePoint[管理员](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)角色的成员。

- 验证是否为组织启用了审核日志记录。 有关详细信息，请参阅 [打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

- 设置最多允许 30 分钟生效。

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>步骤 1：使用 Microsoft 365 Defender 门户为 保险箱、SharePoint 和 OneDrive 启用Microsoft Teams

1. In the Microsoft 365 Defender portal， go to **Policies & rules** Threat \> **policies** \> **保险箱 attachments**， and click Global **settings**.

2. In the **Global settings** fly out that appears， go to the Turn on Defender for Office 365 **for SharePoint， OneDrive， and Microsoft Teams** setting. 将切换开关向右 ![ 切换 ](../../media/scc-toggle-on.png) ，以保险箱"附件SharePoint、OneDrive和Microsoft Teams。

   完成时，请单击“保存”。

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>使用 Exchange Online PowerShell 为保险箱、SharePoint、OneDrive和Microsoft Teams

如果更希望使用 PowerShell 打开 保险箱 Attachments for SharePoint、OneDrive 和 Microsoft Teams，请连接到[Exchange Online PowerShell 并](/powershell/exchange/connect-to-exchange-online-powershell)运行以下命令：

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>步骤 2： (推荐) 使用 SharePoint Online PowerShell 阻止用户下载恶意文件

默认情况下，用户无法打开、移动、复制或共享 ATP 检测到的恶意文件。 但是，他们可以删除和下载恶意文件。

若要阻止用户下载恶意文件，请连接到[SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)并运行以下命令：

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**注意**：

- 此设置同时影响用户和管理员。
- 用户仍可以删除恶意文件。

有关语法和参数的详细信息，请参阅 [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)。

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>步骤 3 (推荐) 使用 Microsoft 365 Defender 门户为检测到的文件创建警报策略

你可以创建一个警报策略，当 保险箱 附件SharePoint、OneDrive和Microsoft Teams检测到恶意文件时Microsoft Teams通知你和其他管理员。 若要了解有关警报的信息，请参阅在 defender 门户Microsoft 365[活动警报](../../compliance/create-activity-alerts.md)。

1. 在 Microsoft 365 [Defender 门户](https://security.microsoft.com)中，转到策略 **&规则** \> **警报策略或** 打开 <https://security.microsoft.com/alertpolicies> 。

2. 在"**警报策略"** 页上，单击"**新建警报策略"。**

3. " **新建警报策略"** 向导将随即打开。在" **命名警报"** 页上，配置以下设置：

   - **名称**：键入唯一的描述性名称。 例如，库中的恶意文件。
   - **说明**：键入可选说明。 例如，当在 SharePoint Online、OneDrive 或 Microsoft Teams 中检测到恶意文件时，通知管理员。
   - **严重性：保留** 默认值"低 **"** 为选中状态，或 **选择"** 中等"或"高 **"。**
   - **类别**：选择 **威胁管理**。

   完成后，单击“**下一步**”。

4. 在" **创建警报设置"** 页上，配置以下设置：

   - **要针对什么发出警报？：活动是**：在文件中选择 **检测到的恶意软件**。
   - **您希望如何触发警报？：** 每次活动匹配规则时，保留 **默认值** 。

   完成后，单击“**下一步**”。

5. 在 **"设置收件人"** 页上，配置以下设置：

   - **发送电子邮件通知**：验证此设置是否被选中。 在" **电子邮件收件人** "框中，选择一个或多个在检测到恶意文件时应收到通知的全局管理员、安全管理员或安全读者。
   - **每日通知限制**：保留默认值 **"没有限制"。**

   完成后，单击“**下一步**”。

6. 在"**查看设置"** 页上，查看设置，并单击任何部分中的"编辑"进行更改。

   在 **"是否想要马上** 打开策略？"部分中，保留默认值"是， **将其打开"保持选中** 状态。

   完成后，单击"完成 **"。**

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>使用安全&合规性 PowerShell 为检测到的文件创建警报策略

如果您更希望使用 PowerShell 创建与上一节中描述的相同的警报策略，请连接到安全& [合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 并运行以下命令：

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**注意**：默认 _严重性值为_ Low。 若要指定 Medium 或 High，在命令中包括 _Severity_ 参数和值。

有关语法和参数的详细信息，请参阅 [New-ActivityAlert](/powershell/module/exchange/new-activityalert)。

### <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

- 若要验证是否成功为 保险箱、SharePoint、OneDrive 和 Microsoft Teams 启用Microsoft Teams，请执行下列任一步骤：

  - 在 [Microsoft 365 Defender](https://security.microsoft.com)门户中，转到策略 **& 规则** 威胁策略 保险箱 附件，选择全局设置，并验证启用 Office 365 for \>  \>   **SharePoint、OneDrive** 和 Microsoft Teams 设置的 Defender 的值。

  - 在 Exchange Online PowerShell 中，运行以下命令来验证属性设置：

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    有关语法和参数的详细信息，请参阅 [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。

- 若要验证您是否已成功阻止用户下载恶意文件，请打开 SharePoint Online PowerShell，然后运行以下命令来验证属性值：

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  有关语法和参数的详细信息，请参阅 [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)。

- 若要验证是否成功为检测到的文件配置了警报策略，请使用以下任一步骤：

  - 在 Microsoft 365 Defender 门户中，转到策略 **&** \> **规则 警报策略** 选择警报策略， \> 并验证设置。

  - 在Microsoft 365 Defender 门户 PowerShell 中，将 替换为警报策略的名称 \<AlertPolicyName\> ，运行以下命令并验证属性值：

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    有关语法和参数的详细信息，请参阅 [Get-ActivityAlert](/powershell/module/exchange/get-activityalert)。

- 使用[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)查看有关已检测到的文件在SharePoint、OneDrive和Microsoft Teams。 具体来说，您可以使用"查看 **数据者：内容恶意软件 \> "** 视图。