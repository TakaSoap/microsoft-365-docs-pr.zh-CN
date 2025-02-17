---
title: Microsoft Defender for Office 365 中的安全文档
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解 保险箱/A5 或 Microsoft 365 E5 Microsoft 365 E5/A5 安全Microsoft 365 E5文档。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab5e35954cac20a18e34f418b5b9fcdc7f2fd007
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466336"
---
# <a name="safe-documents-in-microsoft-365-e5a5"></a>保险箱/A5 Microsoft 365 E5文档

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

保险箱文档是一项高级功能，它使用 [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 的云后端扫描受保护的视图或应用程序防护中打开的 Office [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) [文档Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)。

用户无需在本地设备上安装 Defender for Endpoint，保险箱文档保护。 如果满足保险箱所有要求，则用户会获得文档保护：

- 保险箱文档在组织中启用，如本文所述。
- 向用户分配所需许可计划中的许可证。 保险箱 文档由 **Office 365 SafeDocs** (或 **SAFEDOCS** 或 **bf6f5520-59e3-4f82-974b-7dbbc4fd27c7**) 服务计划 (也称为服务) 控制。 此服务计划适用于以下许可计划 (也称为许可证计划、Microsoft 365计划或产品) ：
  - Microsoft 365 A5教职员工
  - Microsoft 365 A5学生
  - Microsoft 365 E5
  - Microsoft 365 E5 安全版

  保险箱文档不包含在 Microsoft Defender 中Office 365许可计划。

  有关详细信息，请参阅许可 [的产品名称和服务计划标识符](/azure/active-directory/enterprise-users/licensing-service-plan-reference)。

- 他们使用的是以前Microsoft 365 企业应用版 (2004 Office 365 专业增强版) 更高版本的版本。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到"附件 **保险箱，** 请使用 <https://security.microsoft.com/safeattachmentv2>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您需要 **具有以下Exchange Online**，然后才能执行本文中的过程：
  - 若要保险箱文档设置，您必须是组织管理或 **安全管理员角色组** 的成员。
  - 若要对"文档"保险箱只读访问权限，您需要是"全局读者"或"安全读者"**角色组的成员**。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的权限。有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft 如何处理你的数据？

若要保护你，保险箱文档将文件发送到 [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 云进行分析。 有关 Microsoft Defender for Endpoint 如何处理你的数据的详细信息，请参阅： [Microsoft Defender for Endpoint 数据存储和隐私](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

通常，保险箱文档发送的文件不会保留在 Defender for Endpoint 中，超过分析 (通常不超过 24 小时) 。

## <a name="use-the-microsoft-365-defender-portal-to-configure-safe-documents"></a>使用 Microsoft 365 Defender 门户配置保险箱文档

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **保险箱 Attachments** in the **Policies** section. 若要直接转到"附件 **保险箱，** 请使用 <https://security.microsoft.com/safeattachmentv2>。

2. 在"保险箱 **"页上**，单击"**全局设置"**。

3. 在出现的 **"全局** 设置"飞出中，配置以下设置：
   - **打开保险箱客户端Office** 文档：将切换开关向右移动以打开功能：![打开。](../../media/scc-toggle-on.png)
   - **允许用户单击**"受保护的视图"，即使保险箱文档将文件标识为恶意文件：我们建议你关闭此选项 (将切换保持为左侧： ![切换为关闭。](../../media/scc-toggle-off.png)) 。

   完成后，单击“**保存**”。

   :::image type="content" source="../../media/safe-docs-global-settings.png" alt-text="在保险箱附件&quot;页上选择&quot;全局设置&quot;后，保险箱&quot;文档&quot;设置" lightbox="../../media/safe-docs-global-settings.png":::

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 配置保险箱文档

如果希望用户 PowerShell 配置文档保险箱，请使用 PowerShell 中的以下Exchange Online语法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ 参数为保险箱启用或禁用文档。
- _AllowSafeDocsOpen_ 参数允许或阻止用户离开受保护的 (，也就是说，如果文档被标识为恶意) 则打开文档。

本示例为保险箱启用文档，并阻止用户打开受保护视图中标识为恶意的文档。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

### <a name="configure-individual-access-to-safe-documents"></a>配置对文档保险箱访问

如果要有选择地允许或阻止对文档保险箱访问，请按照以下步骤操作：

1. 如本文保险箱所述，Microsoft 365 Defender或 Exchange Online PowerShell 中打开"文档"。
2. 使用 Azure AD PowerShell 为特定保险箱禁用特定许可计划的特定 Microsoft 365 服务中所述禁用[文档。](/microsoft-365/enterprise/disable-access-to-services-with-microsoft-365-powershell#disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan)

  在 PowerShell 中禁用的服务计划的名称为 **SAFEDOCS**。

有关详细信息，请参阅下列主题：

- [使用 PowerShell Microsoft 365许可证和服务](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)
- [使用 PowerShell Microsoft 365帐户许可证和服务详细信息](/microsoft-365/enterprise/view-account-license-and-service-details-with-microsoft-365-powershell)
- [许可的产品名称和服务计划标识符](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>载入 Microsoft Defender for Endpoint 服务以启用审核功能

若要启用审核功能，本地设备需要安装 Microsoft Defender for Endpoint。 若要部署 Microsoft Defender for Endpoint，你需要完成部署的各个阶段。 载入后，可以在企业门户中配置Microsoft 365 Defender功能。

若要了解更多信息，请参阅 [载入到 Microsoft Defender for Endpoint 服务](/microsoft-365/security/defender-endpoint/onboarding)。 如果需要其他帮助，请参阅 Microsoft [Defender 终结点载入问题疑难解答](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。

### <a name="how-do-i-know-this-worked"></a>我如何知道这有效？

若要验证是否已启用和配置保险箱文档，请执行下列任一步骤：

- 在 Microsoft 365 Defender  \>  \> \> 门户中，转到"策略"部分"全局设置"中的"电子邮件 & 协作策略& 规则威胁策略 **保险箱**  \> 保险箱 附件"，并验证为 **Office** **客户端和允许用户单击"受保护的视图"，即使保险箱将文件标识为恶意** 设置。

- 在 PowerShell Exchange Online以下命令并验证属性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 以下文件可用于测试文档保险箱保护。 这些文件类似于用于EICAR.TXT反恶意软件和防病毒解决方案的文件。 这些文件不有害的，但它们将触发保险箱文档保护。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
