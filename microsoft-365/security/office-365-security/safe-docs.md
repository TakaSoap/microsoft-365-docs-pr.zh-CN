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
description: 了解 Microsoft 365 E5 或 Microsoft 365 E5 Security 中的安全文档。
ms.openlocfilehash: baa04f74388b702b42a0bdb83a7f0797ace09883
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48773945"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 中的安全文档

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


安全文档是 Microsoft 365 E5 或 Microsoft 365 E5 Security 中的一项功能，使用 [Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 来扫描在 [受保护视图](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中打开的文档和文件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全文档仅适用于使用 *Microsoft 365 e5* 或 *Microsoft 365 e5 安全* 许可证的用户。 这些许可证不包含在 Office 365 高级威胁防护 (ATP) 计划中。

- Microsoft 365 应用程序中的安全文档在以前称为 Office 365 专业增强版) 版本2004或更高版本的企业版 (中受支持。

- 安全与合规中心的打开网址为 <https://protection.office.com>。 若要直接转到 " **ATP 安全附件** " 页面，请打开 <https://protection.office.com/safeattachmentv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 在执行本主题中的过程之前，您需要分配权限。 若要启用和配置安全文档，您必须是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。 若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft 如何处理您的数据？

为了使你受到保护，安全文档会将文件发送到 [Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 云进行分析。 有关 Microsoft Defender ATP 如何处理你的数据的详细信息，请参阅此处： [Microsoft DEFENDER atp 数据存储和隐私](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

安全文档发送的文件不会在进行分析所需的时间段内保留，而不会在 (中保留（) 通常不到24小时）。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>使用安全 & 合规中心配置安全文档

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件** "，然后单击 " **全局设置** "。

2. 在显示的 **全局设置** 飞出中，配置以下设置：

   - **打开 Office 客户端的安全文档** ：将切换移到右侧以打开功能： ![ 开启 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。

   - **允许用户在受保护的视图中单击，即使安全文档将该文件标识为恶意文件** 也是如此：建议您将此选项保留为关闭状态 (保持左侧的开关： ![ ](../../media/scc-toggle-off.png)) 切换。

   完成时，请单击“保存”  。

   ![选择 "ATP 安全附件" 页面上的 "全局设置" 后的安全文档设置。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 配置安全文档

使用以下语法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ 参数为整个组织启用或禁用安全文档。
- _AllowSafeDocsOpen_ 参数允许或禁止用户将受保护的视图 (即，如果文档已被标识为恶意文档，则打开文档) 。

本示例为整个组织启用安全文档，并阻止用户打开已被 "受保护的视图" 识别为恶意的文档。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。

### <a name="how-do-i-know-this-worked"></a>我如何知道这有效？

若要验证是否已启用并配置安全文档，请执行以下任一步骤：

- 在 "安全性 & 合规性中心" 中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件** "，单击 " **全局设置** "，然后验证是否 **打开 Office 客户端的安全文档** 并 **允许用户在受保护的视图中单击，即使安全文档将该文件标识为恶意** 设置也是如此。

- 在 Exchange Online PowerShell 中运行以下命令，并验证属性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 以下文件可用于测试安全文档保护。 这些文档类似于测试反恶意软件和反病毒解决方案的 EICAR.TXT 文件。 这些文件不会造成危害，但会触发安全文档保护。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
