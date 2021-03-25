---
title: 检测和修正非法同意授予
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何识别和修正 365 中的非法同意授予Microsoft Office攻击。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a9b3ff11acb32a4b3038cc18922f8e22fda0b4c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203662"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>检测和修正非法同意授予

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**摘要**  了解如何识别和修正 Office 365 中的非法许可授予攻击。

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Office 365 中的非法许可授予攻击是什么？

在非法许可授予攻击中，攻击者创建 Azure 注册的应用程序，请求访问联系人信息、电子邮件或文档等数据。 攻击者随后会通过网络钓鱼攻击或将非法代码注入受信任的网站，来欺骗最终用户授予该应用程序访问其数据的同意。 在非法应用程序获得同意后，它无需组织帐户即可对数据进行帐户级访问。 正常修正步骤（如重置泄露帐户的密码或要求帐户使用多重身份验证 (MFA) ）无法抵御此类攻击，因为此类攻击是第三方应用程序且位于组织外部。

这些攻击利用一个交互模型，该模型认为调用信息的实体是自动化的，而不是人为的。

> [!IMPORTANT]
> 你是否怀疑目前遇到来自应用的非法许可问题？ Microsoft Cloud App Security (MCAS) 提供了用于检测、调查和修正 OAuth 应用的工具。 本 MCAS 文章包含一个教程，概述了如何调查 [有风险的 OAuth 应用](/cloud-app-security/investigate-risky-oauth)。 还可以设置 [OAuth](/cloud-app-security/app-permission-policy) 应用策略以调查应用请求的权限（用户正在授权这些应用的权限）并广泛批准或禁止这些权限请求。

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>非法许可授予攻击在 Office 365 中的外观如何？

你需要搜索安全审核日志，也称为"泄露指示器" (IOC) 攻击。 对于具有许多 Azure 注册应用程序和大型用户群的组织，最佳做法是每周查看一次组织同意授予。

### <a name="steps-for-finding-signs-of-this-attack"></a>查找此攻击的迹象的步骤

1. 在 **打开安全&合规中心** <https://protection.office.com> 。

2. 导航到 **"搜索"，** 然后选择"**审核日志搜索"。**

3. 搜索 (所有活动和所有用户) 并输入开始日期和结束日期（如果需要）然后单击"搜索 **"。**

4. 单击 **"筛选结果** "，在"活动"字段中输入"同意 **应用程序** "。

5. 单击结果以查看活动的详细信息。 单击 **"详细信息** "获取活动的详细信息。 检查 IsAdminContent 是否设置为 True。

> [!NOTE]
>
> 在事件发生后，可能需要 30 分钟到 24 小时审核日志相应的项目条目显示在搜索结果中。
>
> 审核记录在 审核日志 中保留和搜索的时间长度取决于 Microsoft 365 订阅，特别是分配给特定用户的许可证类型。 有关详细信息，请参阅审核 [日志](../../compliance/search-the-audit-log-in-security-and-compliance.md)。
>
> 如果此值为 true，则表明具有全局管理员访问权限的某人可能授予了对数据的广泛访问权。 如果这是意外情况，请采取措施 [确认攻击](#how-to-confirm-an-attack)。

## <a name="how-to-confirm-an-attack"></a>如何确认攻击

如果你有上面列出的一个或多个 ICS 实例，则需要进行进一步调查，以积极确认攻击已发生。 可以使用以下三种方法之一确认攻击：

- 使用 Azure Active Directory 门户清点应用程序及其权限。 此方法很全面，但一次只能检查一个用户，如果有许多用户要检查，则检查可能非常耗时。

- 使用 PowerShell 清点应用程序及其权限。 这是最快、最彻底的方法，开销最少。

- 让用户单独检查其应用和权限，将结果报告回管理员进行修正。

## <a name="inventory-apps-with-access-in-your-organization"></a>清点组织中具有访问权限的应用

可以使用 Azure Active Directory 门户或 PowerShell 为用户执行此操作，也可以让用户单独枚举其应用程序访问权限。

### <a name="steps-for-using-the-azure-active-directory-portal"></a>使用 Azure Active Directory 门户的步骤

可以使用 [Azure Active Directory](https://portal.azure.com/)门户查找任何单个用户已授予权限的应用程序。

1. 使用管理权限登录到 Azure 门户。

2. 选择"Azure Active Directory"边栏选项卡。

3. 选择 **用户**。

4. 选择要查看的用户。

5. 选择 **"应用程序"。**

这将显示分配给用户的应用以及应用程序具有的权限。

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>让用户枚举其应用程序访问权限的步骤

让用户转到 并 https://myapps.microsoft.com 查看自己的应用程序访问权限。 他们应该能够查看所有具有访问权限的应用、查看有关它们的详细信息 (包括访问) 的范围，并能够撤消对可疑或非法应用的权限。

### <a name="steps-for-doing-this-with-powershell"></a>使用 PowerShell 执行此操作的步骤

验证非法同意授予攻击的最简单方法就是运行 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)，这将将租户中所有用户的所有 OAuth 许可授权和 OAuth 应用转储到一个 .csv 文件中。

#### <a name="pre-requisites"></a>先决条件

- 安装的 Azure AD PowerShell 库。

- 将针对其运行脚本的租户的全局管理员权限。

- 将运行脚本的计算机上的本地管理员。

> [!IMPORTANT]
> ***强烈建议您*** 要求对管理帐户进行多重身份验证。 此脚本支持 MFA 身份验证。

1. 使用本地管理员权限登录到您将从中运行脚本的计算机。

2. 从 GitHub [ 下载Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) 脚本，或将其复制到运行脚本的文件夹。 这将是将输出"permissions.csv"文件写入的同一文件夹。

3. 以管理员角色打开 PowerShell 实例，然后打开脚本保存到的文件夹。

4. 使用 [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet 连接到目录。

5. 运行此 PowerShell 命令：

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

该脚本生成一个名为 Permissions.csv。 按照以下步骤查找非法应用程序权限授予：

1. 在 ConsentType 列 (G 列) 搜索值"AllPrinciples"。 AllPrincipals 权限允许客户端应用程序访问租赁中每个人的内容。 本机 Microsoft 365 应用程序需要此权限才能正常工作。 应仔细查看每个具有此权限的非 Microsoft 应用程序。

2. 在"权限 (列F) 查看每个委派应用程序对内容具有的权限。 查找"读取"和"写入"权限或"*"。所有"权限，并仔细查看这些权限，因为它们可能不适合。

3. 查看已授予同意的特定用户。 如果高配置文件或高影响力用户授予了不适当的同意，您应该进一步调查。

4. 在 ClientDisplayName 列 (列C#）查找看起来可疑的应用。 应仔细查看具有拼写错误的名称、超级名称或黑客攻击名称的应用。

## <a name="determine-the-scope-of-the-attack"></a>确定攻击范围

完成清点应用程序访问后，请查看 **审核日志以确定泄露** 的完整范围。 搜索受影响的用户、非法应用程序有权访问您的组织的时间范围以及应用程序具有的权限。 可以在 Microsoft 365 **安全审核日志**[中心中搜索安全中心。](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> [在攻击](../../compliance/enable-mailbox-auditing.md)[之前，必须为](../../compliance/turn-audit-log-search-on-or-off.md)管理员和用户启用邮箱审核和活动审核才能获取此信息。

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>如何停止和修正非法同意授予攻击

在标识具有非法权限的应用程序后，您具有几种删除该访问权限的方法。

- 可以通过以下方法在 Azure Active Directory 门户中撤销应用程序的权限：

  - 在"Azure Active Directory 用户"边栏 **选项卡中导航到受影响的** 用户。

  - 选择 **"应用程序"。**

  - 选择非法应用程序。

  - 在 **向下** 钻取中单击"删除"。

- 可以按照 [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)中的步骤撤销对 PowerShell 的 OAuth 许可授权。

- 你可以按照 [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)中的步骤使用 PowerShell 撤销服务应用角色分配。

- 还可以完全禁用受影响帐户的登录，进而禁用应用访问该帐户的数据。 当然，这不适合于最终用户的工作效率，但如果您正在努力快速限制影响，它可以是一个可行的短期修正。

- 您可以关闭租赁的集成应用程序。 这是一个重大步骤，禁用最终用户在租户范围内授予同意的能力。 这可以防止用户无意中授予对恶意应用程序的访问权限。 不建议这样做，因为它严重妨碍用户使用第三方应用程序提高工作效率的能力。 为此，可以按照打开或关闭集成 [应用中的步骤操作](../../admin/misc/user-consent.md)。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>像网络安全专家那样保护 Microsoft 365

你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。 使用“[Microsoft 365 安全路线图 - 前 30 天、90 天内以及之后的首要行动](security-roadmap.md)”，通过实施 Microsoft 建议的最佳做法来保护你的 Microsoft 365 租户。

- 需要在前 30 天完成的任务。 这些任务会对你的用户产生直接影响并且影响很小。

- 需要在 90 天内完成的任务。 这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。

- 90 天后。 这些增强功能基于前 90 天的工作构建。

## <a name="see-also"></a>另请参阅：

- ["我的应用程序"列表中的"](/azure/active-directory/application-access-unexpected-application) 意外应用程序"将指导管理员完成在意识到存在具有数据访问权限的意外应用程序后可能想要执行的各种操作。

- [将应用程序与 Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) 集成是同意和权限的简要概述。

- [开发我的应用程序时](/azure/active-directory/active-directory-application-dev-development-content-map) 遇到问题提供了指向各种许可相关文章的链接。

- [Azure Active Directory ](/azure/active-directory/develop/active-directory-application-objects) (Azure AD) 中的应用程序和服务主体对象概述了应用程序模型的核心应用程序和服务主体对象。

- [管理对应用](/azure/active-directory/active-directory-managing-access-to-apps) 的访问权限是管理员管理用户对应用的访问权限所必须的功能概述。