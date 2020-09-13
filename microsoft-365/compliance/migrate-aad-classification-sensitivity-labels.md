---
title: Microsoft 365 组的 Azure Active Directory 分类和敏感度标签
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: 本文讨论经典 Azure Active Directory 分类和敏感度标签。
ms.openlocfilehash: 2506e7f467a485878f1e26a23ee1071907b41614
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545656"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Microsoft 365 组的 Azure Active Directory 分类和敏感度标签

本文讨论经典 Azure Active Directory 分类和敏感度标签。

[这些服务](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels)支持敏感度标签。

有关敏感度标签的完整信息，请参阅 [了解敏感度标签](sensitivity-labels.md)。

若要了解有关网站和 Microsoft 365 组的敏感度标签及其行为的详细信息，请参阅 [使用敏感度标签保护 Microsoft 团队、microsoft 365 组和 SharePoint 网站中的内容](sensitivity-labels-teams-groups-sites.md)。

在从经典 AAD 分类迁移到敏感度标签时，请参阅以下方案以获得最佳实践。

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>方案1：租户从不使用经典 AAD 分类或文档和电子邮件的敏感度标签

- 租户管理员通过 AAD powershell cmdlet 将租户标志 "EnableMIPLabels" 设置为 true，从而为组启用敏感度标签。
- 租户管理员在 [Microsoft 365 合规性中心](https://compliance.microsoft.com)内创建敏感度标签。
    - 租户管理员可以选择与加密和水印等文件和电子邮件相关的操作。
    - 租户管理员可以选择与灵敏度标签相关的 Microsoft 365 组和 SharePoint Online 网站相关操作。
- 租户管理员发布该策略。
- **兼容的工作负荷** 显示敏感度标签。 使用敏感度标签可创建组。 兼容工作负荷是支持灵敏度标签的服务。
- 不**兼容的工作负荷**是指尚不支持敏感度标签的服务。 但是，可以创建组，它们不能通过不兼容的工作负荷与灵敏度标签相关联。 若要将此类组与敏感度标签相关联，租户管理员可以运行 PowerShell cmdlet。

表 1. 兼容和不兼容工作负载的行为–创建、编辑或删除组

|Workload|用户在组窗口中看到的标签列表是什么？|创建新组 |编辑组 |删除组 |
|:-------|:-------|:--------|:--------|:--------|   
|兼容   |敏感度标签。 |行为没有变化。 |行为没有变化。 |行为没有变化。 |
|不兼容 |不显示敏感度标签。 |用户可以在不选择敏感度标签的情况下创建组。 <br><br> 请注意，管理员可以在后台运行 cmdlet 以应用敏感标签。 |**案例 1**：尚未选择任何敏感度标签。 用户可以编辑组。<br><br> **示例 2**：使用 cmdlet 在背景中之前应用的敏感度标签。 用户可以成功编辑组，不包括用户在标签中选择了无效的隐私设置组合的情况。 |行为没有变化。|

> [!NOTE]
> 在 Outlook 桌面客户端 (Win 32) 中，管理员在其租户上启用灵敏度标签，并且其用户位于较旧版本的 Outlook 桌面客户端中 (Win 32) ：
>
> - 用户看到敏感度标签显示在较旧版本的 Outlook 桌面客户端上。
> - 但是，当用户编辑组，并使用敏感度标签保存组时，所选隐私设置将被应用灵敏度标签的隐私设置替代。
>
> 建议您在 Outlook 客户端的旧版本上的用户升级到较新版本。

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>方案2：租户已在使用经典 AAD [分类](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>案例 A：租户从不使用文档和电子邮件的敏感度标签

1. 在 [Microsoft 365 合规性中心](https://compliance.microsoft.com)中，我们建议使用与现有经典 Azure AD 标签相同的名称创建敏感度标签。
2. 使用 PowerShell cmdlet 将这些敏感度标签应用于现有的 Microsoft 365 组和使用名称映射的 SharePoint 网站。
3. 管理员可以选择删除经典 Azure AD 标签：
    - 兼容工作负载显示这些敏感度标签和组使用它们创建。
    - 不兼容的工作负荷在创建组时工作正常，但未附加任何敏感度标签。
4. 管理员可以运行 PowerShell cmdlet，将敏感度标签应用于这些组，而无标签。
    - 此外，管理员还可以选择保留经典 Azure AD 标签：
        - 兼容工作负荷显示这些敏感度标签，并使用它们创建组。 兼容工作负荷是支持灵敏度标签的服务。
        - 创建组时不兼容的工作负荷工作，并显示经典 Azure AD 标签。 这些经典 Azure AD 标签附加到使用不兼容的工作负荷创建的这些组。
5. 强烈建议管理员运行 PowerShell cmdlet，以将敏感度标签应用于使用经典 Azure AD 标签的这些组。

表 2. 兼容和不兼容工作负载的行为–创建、编辑或删除组

|Workload|用户在组窗口中看到的标签列表是什么？|创建新组 |编辑组 |删除组 |
|:-------|:-------|:--------|:--------|:--------|   
|兼容   |敏感度标签。 |行为没有变化。 |行为没有变化。 |行为没有变化。 |
|不兼容 |旧的经典 AAD 标签。 |用户可以使用选定的经典 Azure AD 标签创建组。 <br><br>请注意，管理员可以在后台运行 cmdlet 以应用敏感标签。 |**案例 1**：尚未选择任何敏感度标签。 用户可以编辑组。<br><br> **示例 2**：之前选择的经典 AAD 标签。 用户可以编辑组。<br><br> **示例 3**：之前使用 cmdlet 在后台应用的敏感度标签。 用户应该能够编辑组，但不包括用户在标签中选择了无效隐私设置组合的一种情况。 |用户可以删除组。 |

> [!NOTE]
> 在 Outlook 桌面客户端 (Win 32) 中，管理员在其租户上启用灵敏度标签，并且其用户位于较旧版本的 Outlook 桌面客户端中 (Win 32) ：
>
> - 用户看到敏感度标签显示在较旧版本的 Outlook 桌面客户端上。
> - 但是，当用户编辑组，并使用敏感度标签保存组时，所选隐私设置将被应用灵敏度标签的隐私设置替代。
>
> 建议您在 Outlook 客户端的旧版本上的用户升级到较新版本。

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>案例 B：针对文档和电子邮件的租户使用敏感度标签

1. 一旦管理员通过将租户标志 "EnableMIPLabels" 设置为 true，便会在 "组/站点/团队创建和编辑" 对话框中显示 "文档" 和 "电子邮件灵敏度" 标签，然后再将租户标志 "" 设置为 true。
2. 管理员可以使用相同的文档和电子邮件敏感度标签，通过指定相关组设置，在组/站点/团队上强制执行隐私和外部用户访问：
    1. 在 [Microsoft 365 合规性中心](https://compliance.microsoft.com)中，选择 " **网站和组** " 选项卡。
    2. 编辑文档或电子邮件敏感度标签。

## <a name="sample-script"></a>示例脚本

有关将具有经典 AAD 标签的组迁移到敏感度标签的示例脚本，请参阅 [经典 AZURE AD 组分类](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。
