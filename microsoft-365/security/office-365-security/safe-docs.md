---
title: Office 365 ATP 中的安全文档
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解 Office 365 ATP 中的安全文档。
ms.openlocfilehash: b70c7013ce038a3934b7ea5e62d1d0530f12e4e6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634312"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Office 365 中的安全文档高级威胁防护

安全文档是 Office 365 高级威胁防护（ATP）中的一项功能，它使用[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)来扫描在[受保护视图](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中打开的文档和文件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 此功能仅适用于使用 Microsoft 365 E5 或 Microsoft 365 E5 安全许可证的用户。

- 安全文档当前可供公共预览使用，在 "每月频道（定向）" 上的[Office 预览体验计划](https://insider.office.com/en-us/join)中，用户可使用 office 版本2002（12527.20092）或更高版本的用户。 此功能在默认情况下处于禁用状态，将需要由安全管理员启用。

- 仅支持美国区域的兼容文件处理（所有文件都将传送到美国区域进行扫描）。 对英国/欧盟地区的支持计划在将来的更新中。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要连接到 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 在执行本主题中的过程之前，您需要分配权限。 若要启用和配置安全文档，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。 有关安全 & 合规中心中的角色组的详细信息，请参阅[security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>使用安全 & 合规中心配置安全文档

1. 在上<https://protection.office.com>打开安全 & 合规性中心。

2. 转到 "**威胁管理** \> **策略** \> **ATP 安全附件**"。

3. 在 "**信任文件以在 Office 应用程序中打开外部受保护的视图**" 部分中，在 "帮助用户保持安全" 中，配置以下任一设置：

   - **打开 Office 客户端的安全文档（文件也将发送到 Microsoft 云进行深入分析）**

   - **允许用户在受保护的视图中单击，即使安全文档将文件标识为恶意文件**也是如此：我们建议您不要启用此选项。

4. 完成后，单击 **“保存”**。

![ATP 安全附件页面](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 配置安全文档

使用以下语法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- _EnableSafeDocs_参数为整个组织启用或禁用安全文档。

- _AllowSafeDocsOpen_参数允许或禁止用户在文档被标识为恶意时离开受保护的视图（即打开文档）。

本示例为整个组织启用安全文档，并阻止用户打开已被 "受保护的视图" 识别为恶意的文档。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

有关语法和参数的详细信息，请参阅[AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365)。

### <a name="how-do-i-know-this-worked"></a>我如何知道这有效？

若要验证是否已启用并配置安全文档，请执行以下任一步骤：

- 在安全 & 合规性中心转到**威胁管理** \> **策略** \> **ATP 安全附件**，并验证在**信任文件以在 Office 应用程序中打开受保护视图外部时帮助**中的选择是否保持安全。

- 在 Exchange Online PowerShell 中运行以下命令，并验证属性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
