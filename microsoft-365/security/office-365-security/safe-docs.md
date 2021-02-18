---
title: Microsoft Defender for Office 365 中的安全文档
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解 Microsoft 365 E5 或 Microsoft 365 E5 安全版中的安全文档。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288581"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 中的安全文档

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

安全文档是 Microsoft 365 E5 或 Microsoft 365 E5 安全版中的一项功能，它使用 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 扫描受保护的视图中打开 [的文档和文件](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全文档仅适用于拥有 *Microsoft 365 E5* 或 *Microsoft 365 E5 安全许可证的用户* 。 这些许可证不包含在 Microsoft Defender for Office 365 计划中。

- Microsoft 365 企业应用版支持安全文档 (以前称为 Office 365 专业增强版) 版本 2004 或更高版本。

- 安全与合规中心的打开网址为 <https://protection.office.com>。 若要直接转到 **ATP 安全附件页，** 请打开 <https://protection.office.com/safeattachmentv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要配置安全文档设置，您必须是组织管理或 **安全管理员** 角色组的成员。
  - 若要对安全文档设置进行只读访问，你需要是全局读者或安全读者 **角色组的成员**。 

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  > [!NOTE]
  >
  > - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft 如何处理你的数据？

为了保护你，安全文档将文件发送到 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 云进行分析。 可在以下位置找到有关 Microsoft Defender for Endpoint 如何处理你的数据 [的详细信息：Microsoft Defender for Endpoint 数据存储和隐私](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

安全文档发送的文件不会在 Defender 中保留超过分析 (，通常不超过 24 小时) 。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>使用安全&合规中心配置安全文档

1. 在安全&，转到 **"威胁管理** 策略 \>  \> **ATP 安全附件**"，然后单击"**全局设置"。**

2. 在 **出现的全局设置** 飞出中，配置以下设置：

   - **打开 Office 客户端的安全文档**：将开关向右移动以打开功能： ![ 打开 ](../../media/scc-toggle-on.png) 。

   - 即使安全文档将文件标识为恶意文件，也允许用户单击"受保护的视图"：建议将此选项保持关闭状态， (将切换保持为左侧 ![ ：) 。 ](../../media/scc-toggle-off.png)

   完成时，请单击“保存”。

   ![在"安全附件"页上选择全局设置后的安全文档设置。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 配置安全文档

使用以下语法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ 参数为整个组织启用或禁用安全文档。
- _AllowSafeDocsOpen_ 参数允许或阻止用户离开受保护的视图 (，即打开文档) 如果文档被标识为恶意视图。

本示例为整个组织启用安全文档，并阻止用户打开受保护的视图中已标识为恶意的文档。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

有关语法和参数的详细信息，请参阅[Set-AtpPolicyForO365。](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

### <a name="how-do-i-know-this-worked"></a>我如何知道这有效？

若要验证是否已启用和配置安全文档，请执行下列任一步骤：

- 在安全&合规中心，转到"威胁管理策略 \>  \> **ATP** 安全附件"，单击"全局设置"，并验证"为 **Office** 客户端启用安全文档"，并允许用户单击"受保护的视图"，即使安全文档将文件标识为恶意设置。

- 在 Exchange Online PowerShell 中运行以下命令并验证属性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 以下文件可用于测试安全文档保护。 这些文档类似于用于EICAR.TXT反恶意软件和防病毒解决方案的文档文件。 这些文件没有危害，但它们将触发安全文档保护。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
