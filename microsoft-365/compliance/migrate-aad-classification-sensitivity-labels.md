---
title: Azure Active Directory组分类和敏感度Microsoft 365标签
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
description: 本文讨论经典分类Azure Active Directory和敏感度标签。
ms.openlocfilehash: 0a8c12d3d133000a880c58366a9f2b13ed8cbf49
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203023"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Azure Active Directory组分类和敏感度Microsoft 365标签

本文讨论经典分类Azure Active Directory和敏感度标签。

敏感度标签受这些服务 [支持](./sensitivity-labels-teams-groups-sites.md)。

有关敏感度标签的完整信息，请参阅 [了解敏感度标签](sensitivity-labels.md)。

若要了解有关网站和 Microsoft 365 组的敏感度标签及其行为Microsoft 365，请参阅使用敏感度标签来保护 Microsoft Teams、Microsoft 365 组和 SharePoint[网站中的内容](sensitivity-labels-teams-groups-sites.md)。

有关从经典 AAD 分类迁移到敏感度标签的最佳实践，请参阅以下方案。

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>方案 1：租户从未对文档和电子邮件使用经典 AAD 分类或敏感度标签

- 租户管理员通过 AAD powershell cmdlet 将租户标志"EnableMIPLabels"设置为 true，为组启用敏感度标签。
- 租户管理员在租户管理中心 创建敏感度[Microsoft 365 合规中心。](https://compliance.microsoft.com)
    - 租户管理员可以选择文件和电子邮件相关的操作，如加密和水印。
    - 租户管理员可以选择Microsoft 365组，SharePoint与 Online 网站相关的操作与敏感度标签关联。
- 租户管理员发布策略。
- **兼容的工作负载显示** 敏感度标签。 使用敏感度标签创建组。 兼容工作负载是支持敏感度标签的服务。
- **不兼容的工作负荷** 是尚不支持敏感度标签的服务。 但是，组无法通过不兼容的工作负荷与敏感度标签相关联。 若要将此类组与敏感度标签关联，租户管理员可以运行 PowerShell cmdlet。

表 1. 兼容和不兼容的工作负荷的行为 - 创建、编辑或删除组

|工作负载|用户在组窗口中看到哪些标签列表？|创建新组 |编辑组 |删除组 |
|:-------|:-------|:--------|:--------|:--------|   
|兼容   |敏感度标签。 |行为没有变化。 |行为没有变化。 |行为没有变化。 |
|不兼容 |没有敏感度标签可见。 |用户无需选择敏感度标签即可创建组。 <br><br> 请注意，管理员可以运行 cmdlet 在后台应用敏感度标签。 |**用例 1：** 之前未选择任何敏感度标签。 用户可以编辑组。<br><br> **用例 2：** 之前使用 cmdlet 在后台应用的敏感度标签。 用户可以成功编辑组，但不包括用户选择与标签有关的隐私设置无效组合的情况。 |行为没有变化。|

> [!NOTE]
> 对于 Outlook 桌面客户端 (Win 32) ，管理员在租户上启用敏感度标签，并且其用户位于较旧版本的 Outlook 桌面客户端 (Win 32) ：
>
> - 用户看到敏感度标签显示在旧版桌面客户端Outlook上。
> - 但是，当用户编辑组并保存具有敏感度标签的组时，所选隐私设置将被已应用的敏感度标签的隐私设置覆盖。
>
> 建议在旧版本的客户端上Outlook升级到较新版本。

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>方案 2：租户已在使用经典 AAD [分类](../enterprise/manage-microsoft-365-groups-with-powershell.md)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>案例 A：租户从未将敏感度标签用于文档和电子邮件

1. 在[Microsoft 365 合规中心](https://compliance.microsoft.com)中，我们建议使用与现有经典 Azure AD 标签相同的名称创建敏感度标签。
2. 使用 PowerShell cmdlet 可以使用名称映射将这些敏感度标签Microsoft 365组SharePoint网站。
3. 管理员可以选择删除经典 Azure AD 标签：
    - 兼容的工作负载显示这些敏感度标签和组通过它们创建。
    - 创建组时，不兼容的工作负荷可以正常工作，但不附加任何敏感度标签。
4. 管理员可以运行 PowerShell cmdlet，将敏感度标签应用于这些没有标签的组。
    - 或者，管理员可以选择保留经典 Azure AD 标签：
        - 兼容的工作负载显示这些敏感度标签，并使用它们创建组。 兼容工作负载是支持敏感度标签的服务。
        - 创建组和显示经典 Azure AD 标签时，不兼容的工作负载可以正常工作。 这些经典 Azure AD 标签附加到使用不兼容工作负载创建的这些组。
5. 强烈建议管理员运行 PowerShell cmdlet，将敏感度标签应用于带经典 Azure AD 标签的组。

表 2. 兼容和不兼容的工作负荷的行为 - 创建、编辑或删除组

|工作负载|用户在组窗口中看到哪些标签列表？|创建新组 |编辑组 |删除组 |
|:-------|:-------|:--------|:--------|:--------|   
|兼容   |敏感度标签。 |行为没有变化。 |行为没有变化。 |行为没有变化。 |
|不兼容 |旧的经典 AAD 标签。 |用户可以创建选择了经典 Azure AD 标签的组。 <br><br>请注意，管理员可以运行 cmdlet 在后台应用敏感度标签。 |**用例 1：** 之前未选择任何敏感度标签。 用户可以编辑组。<br><br> **用例 2：** 以前选择的经典 AAD 标签。 用户可以编辑组。<br><br> **用例 3：** 之前使用 cmdlet 在后台应用的敏感度标签。 用户应能够编辑组，但不包括用户选择与标签有关的隐私设置无效组合的一种情况。 |用户可以删除组。 |

> [!NOTE]
> 对于 Outlook 桌面客户端 (Win 32) ，管理员在租户上启用敏感度标签，并且其用户位于较旧版本的 Outlook 桌面客户端 (Win 32) ：
>
> - 用户看到敏感度标签显示在旧版桌面客户端Outlook上。
> - 但是，当用户编辑组并保存具有敏感度标签的组时，所选隐私设置将被已应用的敏感度标签的隐私设置覆盖。
>
> 建议在旧版本的客户端上Outlook升级到较新版本。

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>案例 B：租户对文档和电子邮件使用了敏感度标签

1. 管理员通过将租户标志"EnableMIPLabels"设置为 true 来启用租户上的敏感度标签功能后，就会在组/网站/团队创建和编辑对话框中显示文档和电子邮件敏感度标签。
2. 管理员可使用同一文档和电子邮件敏感度标签，通过指定相关组设置在组/网站/团队上强制实施隐私和外部用户访问：
    1. 在 ["Microsoft 365 合规中心"](https://compliance.microsoft.com)中，选择"**网站和组"** 选项卡。
    2. 编辑文档或电子邮件敏感度标签。

## <a name="sample-script"></a>示例脚本

有关将带经典 AAD 标签的组迁移到敏感度标签的示例脚本，请参阅 [经典 Azure AD 组分类](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification)。