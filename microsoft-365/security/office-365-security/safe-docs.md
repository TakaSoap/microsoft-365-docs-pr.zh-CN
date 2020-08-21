---
title: Office 365 ATP 中的安全文档
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
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
description: 了解 Microsoft 365 E5 或 Microsoft 365 E5 安全中心中的安全文档。
ms.openlocfilehash: cd689099fc6a6caa1e0e649c3f152f1de123bf12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827465"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 安全文档

安全文档是 Microsoft 365 E5 或 Microsoft 365 E5 安全中的一项功能，它 [使用 Microsoft Defender 高级威胁](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 防护扫描在受保护视图中 [打开的文档和文件](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 现在，拥有 Office 2004 版 Office 2004 或更高 (版本的用户现在已经有) 安全文档！ 此功能默认处于关闭状态，需要由安全管理员启用。

- 此功能仅适用于 Office *365* ATP 计划计划中未附带 *的 (365 E5* 或 Microsoft 365 E5 安全) 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必须先拥有权限，然后才能执行本主题中的过程。 若要启用和配置安全文档，您需要是组织**管理或安全****管理员**角色组的成员。 若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="how-does-microsoft-handle-your-data"></a>Microsoft 如何处理你的数据？

为确保你受保护，安全文档将文件发送至 [Microsoft Defender 高级威胁防护云进行](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 分析。

- 有关 Microsoft Defender 高级威胁防护如何处理你的数据的详细信息，可以从 [此处查看](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- 除了上述指南以外，安全文档发送的文件不会在 Defender 中保留超过分析所需的时间，通常会少于 24 小时

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>使用安全与&合规中心配置安全文档

1. 打开"&安全与合规中心 <https://protection.office.com> "。

2. 转到威 **胁管理** \> **策略** \> **ATP 安全附件**。

3. 在帮助 **用户信任文件在 Office 应用程序部分的"受保护视图"之外打开时，帮助** 人员可安全运行，配置以下设置之一：

   - **为 Office 客户端启用安全文档**

   - **是否允许用户单击受保护视图，即使安全**文档将文件标识为恶意文件也是如此：我们建议您不要启用此选项。

4. 完成时，请单击“保存”****。

![ATP 安全附件页面](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全文档

使用以下语法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_参数启用或禁用整个组织的安全文档。

- _AllowSafeDocsOpen_参数允许或阻止用户离开受保护的视图 (即如果文档被识别为恶意文档) 打开该文档。

本示例为整个组织启用安全文档，并阻止用户打开已被恶意的受保护的视图的文档。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

有关语法和参数的详细信息，请参阅[Set-AtpPolicyForO365。](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

### <a name="how-do-i-know-this-worked"></a>我如何知道这有效？

若要验证是否已启用和配置安全文档，请执行以下任一步骤：

- 在安全 & 合规中心转至 **威胁管理** \> **策略** \> **ATP 安全附件**，并验证信任 **在 Office** 应用程序部分的"受保护视图外部打开"的文件时帮助用户中的选择都保持安全。

- 在 Exchange Online PowerShell 中运行以下命令并验证属性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
