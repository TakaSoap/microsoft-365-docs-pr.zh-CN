---
title: 启用 Office 365 ATP-SharePoint、OneDrive、& 团队
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 了解如何为 SharePoint、OneDrive 和团队打开 ATP，包括如何为检测到的文件设置通知。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cd345ae74b81c23f92b9e9b7d712efa8b875503
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326897"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Office 365 高级威胁防护 (适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP) 保护您的组织不会在无意中共享恶意文件。 有关详细信息，请参阅 [适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)。

本文包含为 SharePoint、OneDrive 和 Microsoft 团队启用和配置 ATP 的步骤。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com>。 若要直接转到 " **ATP 安全附件** " 页面，请打开 <https://protection.office.com/safeattachmentv2> 。

- 若要打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP，您需要是安全 & 合规性中心中的 " **组织管理** " 或 " **安全管理员** " 角色组的成员。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

- 若要使用 SharePoint Online PowerShell 阻止用户下载恶意文件，您必须是 Azure AD 中 [全局管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 或 [SharePoint 管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) 角色的成员。

- 验证是否已为您的组织启用审核日志记录。 有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

- 允许最长30分钟的设置生效。

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>步骤1：使用安全 & 合规中心打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"，然后单击 " **全局设置**"。

2. 在 " **全局设置** " 飞出时，转到 " **启用 SharePoint、OneDrive 和 MICROSOFT 团队的 ATP** " 设置。 将切换切换到右侧 ![ 切换，以 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP。

   完成时，请单击“保存”****。

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>使用 Exchange Online PowerShell 打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP

如果你更愿意使用 PowerShell 打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP，请 [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 并运行以下命令：

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>步骤2：建议 () 使用 SharePoint Online PowerShell 以防止用户下载恶意文件

默认情况下，用户无法打开、移动、复制或共享由 ATP 检测到的恶意文件。 但是，他们可以删除和下载恶意文件。

若要阻止用户下载恶意文件，请 [连接到 SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 并运行以下命令：

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**注意**：

- 此设置会影响用户和管理员。
- 用户仍可以删除恶意文件。

有关语法和参数的详细信息，请参阅 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>建议的步骤 3 () 使用安全 & 合规中心为检测到的文件创建通知策略

当 SharePoint、OneDrive 和 Microsoft 团队的 ATP 检测到恶意文件时，可以创建通知您和其他管理员的通知策略。 若要了解有关通知的详细信息，请参阅 [在安全 & 合规性中心中创建活动通知](../../compliance/create-activity-alerts.md)。

1. 在 [安全 & 合规性中心](https://protection.office.com)中，转到 " **通知**" "通知 \> **策略** " 或 "打开" <https://protection.office.com/alertpolicies> 。

2. 在 " **通知策略** " 页上，单击 " **新建通知策略**"。

3. " **新建通知策略** " 向导将在飞出时打开。在 "将 **通知命名** 为" 页上，配置以下设置：

   - **名称**：键入唯一的描述性名称。 例如，库中的恶意文件。
   - **说明**：键入可选的说明。 例如，当在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到恶意文件时，会通知管理员。
   - **严重性**：保持选定的默认值为 " **低** "，或选择 " **中** " 或 " **高**"。
   - **选择一个类别**：选择 **威胁管理**。

   完成后，单击“下一步”****。

4. 在 " **创建通知设置** " 页上，配置以下设置：

   - **你希望在什么情况上提醒？：活动为**：在 **文件中选择检测到的恶意软件**。
   - **您希望如何触发警报？**： **每次活动匹配选定的规则时** ，保留默认值。

   完成后，单击“下一步”****。

5. 在 " **设置收件人** " 页上，配置以下设置：

   - **发送电子邮件通知**：确认已选中此设置。 在 " **电子邮件收件人** " 框中，选择一个或多个全局管理员、安全管理员或在检测到恶意文件时应收到通知的安全阅读者。
   - **每日通知限制**：保留默认值 " **无限制** " 处于选中状态。

   完成后，单击“下一步”****。

6. 在 " **查看您的设置** " 页上，查看设置，然后单击任何部分中的 " **编辑** " 以进行更改。

   在 " **是否要立即启用策略？** " 部分，保留默认值 **"是"，然后将其立即打开** 。

   完成后，单击 " **完成**"。

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>使用 Security & 合规性 PowerShell 为检测到的文件创建通知策略

如果您希望使用 PowerShell 创建与上一节中所述相同的警报策略，请 [连接到 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) ，并运行以下命令：

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**注意**：默认 _严重性_ 值为 "低"。 若要指定 "中" 或 "高"，请在命令中包含 _严重性_ 参数和值。

有关语法和参数的详细信息，请参阅 [set-activityalert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)。

### <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

- 若要验证是否成功启用了 SharePoint、OneDrive 和 Microsoft 团队的 ATP，请使用以下步骤之一：

  - 在 " [安全性 & 合规性中心](https://protection.office.com)" 中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"，选择 " **全局设置**"，然后验证 " **启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP** 的值" 设置的值。

  - 在 Exchange Online PowerShell 中，运行以下命令以验证属性设置：

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)。

- 若要验证是否已成功阻止用户下载恶意文件，请打开 SharePoint Online PowerShell，然后运行以下命令来验证属性值：

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  有关语法和参数的详细信息，请参阅 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。

- 若要验证是否已成功为检测到的文件配置了通知策略，请执行以下任一步骤：

  - 在安全 & 合规性中心中，转到 " **通知** \> " "通知 **策略**"， \> 选择 "通知策略" 并验证设置。

  - 在安全 & 合规性中心 PowerShell 中，将替换 \<AlertPolicyName\> 为警报策略的名称，运行以下命令，并验证属性值：

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    有关语法和参数的详细信息，请参阅 [set-activityalert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)。

- 使用 " [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report) " 查看 SharePoint、OneDrive 和 Microsoft 团队中检测到的文件的相关信息。 具体来说，可以使用 " **查看数据的方式：内容 \> 恶意软件** " 视图。
