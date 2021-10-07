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
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 管理员可以了解如何为 SharePoint、OneDrive 和 Microsoft Teams 启用 保险箱 附件，包括如何为检测到的文件设置警报。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 546c714d76807f828845b3c0ef0c8fe3ef94169c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211881"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>为 SharePoint、OneDrive 和 Microsoft Teams 启用安全附件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for Office 365 for SharePoint、OneDrive 和 Microsoft Teams 可保护你的组织避免意外共享恶意文件。 有关详细信息，请参阅 保险箱[Attachments for SharePoint， OneDrive， and Microsoft Teams](mdo-for-spo-odb-and-teams.md)。

本文包含为 保险箱、SharePoint 和 OneDrive 启用和配置Microsoft Teams。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到"附件 **保险箱，** 请打开 <https://security.microsoft.com/safeattachmentv2> 。

- 若要为 SharePoint、OneDrive 和 Microsoft Teams 启用 保险箱 附件，你需要是 Microsoft 365 Defender 门户中组织管理或安全管理员角色组的成员。   有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

- 若要SharePoint Online PowerShell 阻止用户下载恶意文件，你需要是 Azure AD 中全局管理员[](/azure/active-directory/roles/permissions-reference#global-administrator)或 SharePoint[管理员](/azure/active-directory/roles/permissions-reference#sharepoint-administrator)角色的成员。

- 验证是否为组织启用了审核日志记录。 有关详细信息，请参阅 [打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

- 设置最多允许 30 分钟生效。

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>步骤 1：使用Microsoft 365 Defender门户打开保险箱、SharePoint和OneDrive附件Microsoft Teams

1. 在Microsoft 365 Defender门户中，转到"附件"& \>  \> 策略"部分保险箱 \> **策略"。**

2. 在 **"保险箱"页上**，单击"**全局设置"。**

3. 在出现的 **"全局设置**"飞出中，转到"保护 **SharePoint、OneDrive** 和Microsoft Teams文件"部分。

   将"**打开 Defender for Office 365 for SharePoint、OneDrive** 和 Microsoft Teams"开关移动到右 ![ "切换"打开。](../../media/scc-toggle-on.png) 可打开保险箱、SharePoint、OneDrive和Microsoft Teams的"附件"。

   完成时，请单击“保存”。

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>使用 Exchange Online PowerShell 为 保险箱、SharePoint 和 OneDrive 启用Microsoft Teams

如果你希望使用 PowerShell 打开 保险箱 Attachments for SharePoint、OneDrive 和 Microsoft Teams，请连接到[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)并运行以下命令：

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>步骤 2： (推荐) 使用 SharePoint Online PowerShell 阻止用户下载恶意文件

默认情况下，用户无法打开、移动、复制或共享 保险箱 Attachments 检测到的恶意文件SharePoint、OneDrive和 <sup>\*</sup> Microsoft Teams。 但是，他们可以删除和下载恶意文件。

<sup>\*</sup>如果用户转到"**管理访问权限"，"****共享**"选项仍然可用。

若要阻止用户下载恶意文件，请连接到[SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)并运行以下命令：

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**注意**:

- 此设置同时影响用户和管理员。
- 用户仍可以删除恶意文件。

有关语法和参数的详细信息，请参阅 [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)。

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>步骤 3 (推荐) 使用 Microsoft 365 Defender 门户为检测到的文件创建警报策略

你可以创建一个警报策略，当 SharePoint、OneDrive 和 Microsoft Teams 附件检测到恶意文件时保险箱通知你和其他管理员。 若要了解有关警报的更多信息，请参阅 [警报策略](../../compliance/alert-policies.md)。

1. 在 Microsoft 365 Defender门户中，转到策略 **&规则** \> **警报策略或** 打开 <https://security.microsoft.com/alertpolicies> 。

2. 在"**警报策略"** 页上，单击"**新建警报策略"。**

3. " **新建警报策略"** 向导将随即打开。在" **命名警报"** 页上，配置以下设置：
   - **名称**：键入唯一的描述性名称。 例如，库中的恶意文件。
   - **说明**：键入可选说明。 例如，当在 SharePoint Online、OneDrive 或 Microsoft Teams 中检测到恶意文件时，通知管理员。
   - **严重性：** 从 **下拉列表中选择"** 低 **、中"** 或"高"。 
   - **类别**： **从下拉列表中选择** 威胁管理。

   完成后，单击“**下一步**”。

4. 在" **创建警报设置"** 页上，配置以下设置：
   - **要提醒什么？** section \> **Activity is** \> Select Detected malware in **file** from the drop down list.
   - **您希望如何触发警报？** section：每次活动匹配规则 **时保留默认值** 。

   完成后，单击“**下一步**”。

5. 在 **"设置收件人"** 页上，配置以下设置：
   - 验证 **是否选择了"发送电子邮件** 通知"。 在" **电子邮件收件人** "框中，选择一个或多个在检测到恶意文件时应收到通知的全局管理员、安全管理员或安全读者。
   - **每日通知限制**：保留默认值 **"没有限制"。**

   完成后，单击“**下一步**”。

6. 在" **查看设置"** 页上，查看设置。 可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   在 **"是否想要马上** 打开策略？"部分中，保留默认值"是， **将其打开"保持选中** 状态。

   完成后，单击"完成 **"。**

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>使用安全&合规性 PowerShell 为检测到的文件创建警报策略

如果您更希望使用 PowerShell 创建与上一节中描述的相同的警报策略，请连接到安全与合规中心 [& PowerShell](/powershell/exchange/connect-to-scc-powershell) 并运行以下命令：

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**注意**：默认 _严重性值为_ Low。 若要指定 Medium 或 High，在命令中包括 _Severity_ 参数和值。

有关语法和参数的详细信息，请参阅 [New-ActivityAlert](/powershell/module/exchange/new-activityalert)。

### <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

- 若要验证是否成功为 SharePoint、OneDrive 和 Microsoft Teams 启用保险箱"附件"，请执行以下步骤之一：

  - 在 Microsoft 365 Defender 门户中，转到策略 **& 规则** 威胁策略部分 保险箱 附件，选择全局设置，然后验证启用 Office 365 \>  \>  \> for  **SharePoint、OneDrive 和 Defender 的值Microsoft Teams** 设置。

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
  - 在 Microsoft 365 Defender 门户中，转到策略 **&** \> **规则 警报策略** \> 选择警报策略，并验证设置。
  - 在Microsoft 365 Defender PowerShell 中，将 替换为警报策略的名称 \<AlertPolicyName\> ，运行以下命令并验证属性值：

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    有关语法和参数的详细信息，请参阅 [Get-ActivityAlert](/powershell/module/exchange/get-activityalert)。

- 使用[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)查看有关已检测到的文件在SharePoint、OneDrive和Microsoft Teams。 具体来说，您可以使用"查看 **数据者：内容恶意软件 \> "** 视图。
