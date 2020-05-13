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
ms.openlocfilehash: 11c2736edee3dd1fcbc2560d5fa574def05a8f6e
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213112"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Office 365 高级威胁防护安全文档

安全文档是 Office 365 高级威胁防护（Office 365 ATP）中的一项功能，它使用[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)来扫描在[受保护视图](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中打开的文档和文件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 此功能仅适用于使用 Microsoft 365 E5 或 Microsoft 365 E5 安全许可证的用户。

- 安全文档当前可供公共预览使用，在 "每月频道（定向）" 上的[Office 预览体验计划](https://insider.office.com/en-us/join)中，用户可使用 office 版本2002（12527.20092）或更高版本的用户。 此功能在默认情况下处于禁用状态，将需要由安全管理员启用。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 在执行本主题中的过程之前，您需要分配权限。 若要启用和配置安全文档，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。 若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="how-does-microsoft-handle-your-data"></a>Microsoft 如何处理您的数据？

为了使你受到保护，安全文档会将文件发送到[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)云进行分析。

- 可在[此处](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)找到关于 Microsoft Defender 高级线程保护处理数据的方式的详细信息
- 除了上述准则之外，通过安全文档发送的文件不会在进行分析所需的时间（通常少于24小时）的情况下保留在 Defender 中。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>使用安全 & 合规中心配置安全文档

1. 在上打开安全 & 合规性中心 <https://protection.office.com> 。

2. 转到 "**威胁管理** \> **策略** \> **ATP 安全附件**"。

3. 在 "**信任文件以在 Office 应用程序中打开外部受保护的视图**" 部分中，在 "帮助用户保持安全" 中，配置以下任一设置：

   - **打开 Office 客户端的安全文档（文件也将发送到 Microsoft 云进行深入分析）**

   - **允许用户在受保护的视图中单击，即使安全文档将文件标识为恶意文件**也是如此：我们建议您不要启用此选项。

4. 完成时，请单击“保存”****。

![ATP 安全附件页面](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全文档

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
