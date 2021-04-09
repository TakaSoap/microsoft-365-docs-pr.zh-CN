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
description: 了解 Microsoft 365 E5 或 Microsoft 365 E5 安全中心中的安全文档。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1186c7856d0b979c483cf6dd1c0a010ab582e2ce
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644748"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 中的安全文档

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

安全文档是 Microsoft 365 E5 或 Microsoft 365 E5 安全中心中的一项功能，它使用 Microsoft [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) [Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)扫描在受保护的视图或 Office 应用程序防护中打开的文档[和文件](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全文档仅适用于拥有 *Microsoft 365 E5* 或 *Microsoft 365 E5 安全许可证* 的用户。 这些许可证不包含在 Microsoft Defender for Office 365 计划中。

- 安全文档在 Microsoft 365 企业应用版中 (以前称为 Office 365 专业增强) 版本 2004 或更高版本。

- 安全与合规中心的打开网址为 <https://protection.office.com>。 若要直接转到 **ATP 安全附件页面，** 请打开 <https://protection.office.com/safeattachmentv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要配置安全文档设置，您必须是组织管理或安全 **管理员角色****组** 的成员。
  - 若要对安全文档设置进行只读访问，你需要是全局读者或安全读者 **角色组的成员**。 

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft 如何处理你的数据？

为了保护你，安全文档将文件发送到 [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 云进行分析。 有关 Microsoft Defender for Endpoint 如何处理你的数据的详细信息，请参阅 [：Microsoft Defender for Endpoint 数据存储和隐私](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

安全文档发送的文件不会在 Defender 中保留超过分析 (，通常不超过 24 小时) 。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>使用安全&中心配置安全文档

1. 在安全与&中心中，转到"**威胁** 管理策略 \>  \> **ATP 安全附件**"，然后单击"全局 **设置"。**

2. 在出现的 **"全局** 设置"飞出中，配置以下设置：

   - **打开 Office 客户端的安全** 文档：将切换开关向右移动，以打开功能：打开 ![ 切换 ](../../media/scc-toggle-on.png) 。

   - 即使 **安全** 文档将文件标识为恶意文件，也允许用户单击"受保护的视图"：建议关闭此选项， (将开关向左切换：关闭 ![ ](../../media/scc-toggle-off.png)) 。

   完成后，单击“**保存**”。

   ![选择"安全附件"页上的"全局设置"后的安全文档设置。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 配置安全文档

使用以下语法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ 参数为整个组织启用或禁用安全文档。
- _AllowSafeDocsOpen_ 参数允许或阻止用户离开受保护的视图 (也就是说，如果文档被标识为恶意) 则打开文档。

本示例为整个组织启用安全文档，并阻止用户打开从受保护的视图中标识为恶意的文档。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>载入 Microsoft Defender for Endpoint Service 以启用审核功能

若要部署 Microsoft Defender for Endpoint，你需要完成部署的各个阶段。 载入后，可以在安全与合规中心&审核功能。

若要了解更多信息，请参阅 [载入到 Microsoft Defender for Endpoint 服务](/microsoft-365/security/defender-endpoint/onboarding)。 如果你需要其他帮助，请参阅疑难解答 [Microsoft Defender 终结点载入问题](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。

### <a name="how-do-i-know-this-worked"></a>我如何知道这有效？

若要验证是否已启用和配置安全文档，请执行下列任一步骤：

- 在安全&合规中心，转到"威胁管理策略 \>  \> **ATP** 安全附件"，单击"全局设置"，并验证"为 Office 客户端启用安全文档"和"允许用户通过受保护的视图"（即使安全文档将文件标识为恶意设置）进行单击。

- 在 Exchange Online PowerShell 中运行以下命令并验证属性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 以下文件可用于测试安全文档保护。 这些文档类似于EICAR.TXT反恶意软件和防病毒解决方案的文档文件。 这些文件没有危害，但它们将触发安全文档保护。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
