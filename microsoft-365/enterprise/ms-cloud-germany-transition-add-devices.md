---
title: 从德国 Microsoft 云迁移的其他设备信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从德国 Microsoft 云迁移到新的德国数据中心 (Microsoft 云) Office 365服务的其他设备信息。
ms.openlocfilehash: 16c2e1f33e66f9b7d710a867c5c4467053e03c67
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166822"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云迁移的其他设备信息

连接到德国 Microsoft 云的已加入和注册的 Azure AD 设备必须在第 9 阶段之后和阶段 10 之前进行迁移。 设备的迁移取决于设备类型、操作系统和 Azure AD 关系。

## <a name="azure-ad-joined-windows-10-devices"></a>加入 Azure AD Windows 10设备
如果Windows 10已加入 Azure AD，则它必须与 Azure AD 断开连接，并且必须再次连接。

[![Azure AD 设备Re-Join Flow。 ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


如果用户是设备管理员，Windows 10 Azure AD 取消注册设备，然后通过三个步骤重新加入该设备。

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>步骤 1：确定设备是否加入 Azure ID

1. 使用你的工作帐户登录。
2. 转到设置  >    >  **帐户访问工作或学校**。
3. 在列表中查找连接到 **[...]的帐户s Azure AD**.
4. 如果存在已连接的帐户，请继续执行步骤 2。

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>步骤 2：断开设备与 Azure AD 连接

1. 单击 **已连接** 的工作或学校帐户上的"断开连接"。
2. 确认断开连接两次。
3. 输入本地管理员用户名和密码。 设备已断开连接。
4. 重新启动设备。

### <a name="step-3-join-the-device-to-azure-ad"></a>步骤 3：将设备加入 Azure AD

1. 使用本地管理员的凭据登录。
2. 转到设置  >    >  **帐户访问工作或学校**。
3. 单击“**连接**”。
4. **重要** 提示：单击 **加入 Azure AD**。
5. 输入工作帐户的电子邮件地址和密码。 设备已连接。
6. 重新启动设备。
7. 使用你的工作帐户的电子邮件地址和密码登录。

如果用户不是设备的管理员 **，Azure AD DC** 管理员、云 **应用程序** 管理员或 **全局** 管理员可以按照此配置路径在设备上创建本地管理员帐户，并取消加入设备：

*设置 >帐户>其他>凭据未知> Microsoft 帐户添加用户*

有关详细信息，请参阅 [关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles?)。

对于重新加入，此步骤中可以使用组织的任何工作帐户的凭据。

请考虑用于加入设备的工作帐户将自动提升为设备的管理员。
组织中的其他任何工作帐户都可以登录到设备，但没有管理员权限。

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a>Azure AD 注册 (工作区) Windows 10设备

如果Windows 10已注册 Azure AD，需要从 Azure AD 断开连接，然后重新连接。

[![Azure AD 设备Re-Registration Flow。 ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a>步骤 1：确定设备是否注册了 Azure ID

1. 使用你的用户登录。
2. 转到设置  >    >  **帐户访问工作或学校**。
3. 在列表中发现你的工作帐户并检查它是否 **连接到 [...]'s Azure AD**.

    如果你的工作帐户在列表中，但没有连接到 Azure AD，请继续执行步骤 2。

    否则，你的设备是加入 Azure AD 的设备，你必须参考加入[Azure AD Windows 10设备](#azure-ad-joined-windows-10-devices)。

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>步骤 2：断开设备与 Azure AD 连接

1. 单击你的工作帐户。 将显示" *信息"* 和" *断开连接"* 按钮。
2. 单击 **断开连接**。
3. 通过单击"是"确认从设备删除 **帐户**。

### <a name="step-3-connect-the-device-to-azure-ad"></a>步骤 3：连接设备连接到 Azure AD

1. 单击“**连接**”。
2. 输入你的工作帐户的电子邮件地址，然后单击下一 **步**。
3. 输入工作帐户的密码，然后单击"**登录"。**
4. 通过单击"完成 **"确认**。 你的工作帐户将再次列出。

## <a name="android"></a>Android

对于 Android，用户需要注销并重新注册其设备。 这可以通过 Microsoft Authenticator 或 公司门户 应用完成。

- 从Microsoft Authenticator应用，用户可以转到"设置 >**注册"。** 在这里，用户可以注销和重新注册其设备。

- 从公司门户，用户可以转到"**设备**"选项卡并删除设备。 此后，使用"设置"公司门户。

- 用户还可以注销和重新注册，从帐户设置页删除帐户，然后读取工作帐户。

若要使用应用注销和重新注册 Android 上的设备，Microsoft Authenticator应用：

1. 打开Microsoft Authenticator应用，然后转到 **"设置"。**
2. 选择 **"设备注册"。**
3. 通过选择"注销"取消 **注册设备**。
4. 对于 **设备注册**，请通过键入你的电子邮件地址重新注册设备，**然后选择注册。**

若要注销 Android 设备并重新注册 Android 设置页面：

1. 打开 **设备设置****转到帐户**。
2. 选择要重新注册的工作帐户，然后选择"删除 **帐户"。**
3. 删除帐户后，从"帐户"**页面选择"** 添加帐户>**工作帐户"。**
4. 对于 **Workplace Join，** 键入你的电子邮件地址，然后选择 **加入** 以完成设备注册。

若要从 Android 上注销和重新注册设备，公司门户：

1. 启动公司门户并转到 **设备** 选项卡。
2. 选择设备以查看设备详细信息。
3. From theellipses (three dots) menu， select **Remove Device**， and complete the removal by confirming in the dialog.
4. 你现在应该已注销公司门户应用。 选择 **"登录** "以重新注册设备。

有关此工作负载的迁移阶段需要执行的任何操作或对管理或使用情况的影响，请参阅从德国 Microsoft 云迁移的其他[Azure AD](ms-cloud-germany-transition-azure-ad.md)信息中有关 Azure Active Directory (Azure AD) 的信息。

## <a name="ios"></a>iOS

在 iOS 设备上，用户需要手动从 Microsoft Authenticator 中删除任何缓存的帐户、注销设备以及从设备上的任何本机应用注销。

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>步骤 1：如果存在，请从应用中删除Microsoft Authenticator帐户

1. 点击"登录"应用中Microsoft Authenticator帐户。
2. 点击 **设置** 右上角的"页面"图标。 如果未看到"设置"图标，则可能不会使用最新版本的 Microsoft Authenticator。
3. 点击" **删除帐户"** 按钮。
4. 点击 **此设备上的所有应用**。

### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>步骤 2：从应用注销Microsoft Authenticator设备

1. 点击右上角的菜单图标。
2. 依次 **设置"** 设备 **注册"。**
3. If your account is shown， tap **Unregister device** and **Continue** in the dialog. 此后应该看不到任何帐户。

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>步骤 3：如有必要从个别应用注销

用户可以转到单个应用（如 Outlook、Teams 和 OneDrive）并从这些应用中删除帐户。

## <a name="frequently-asked-questions"></a>常见问题解答

**如何判断我的组织是否受到影响？**

管理员应检查 `https://portal.microsoftazure.de` 以确定他们是否有已注册的 Azure AD 或加入 Azure AD 的设备。 如果你的组织已注册 Azure AD 或加入 Azure AD 的设备，则你的组织必须遵循此页面上的说明。

**我的用户何时重新注册其设备？**

阶段 [9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 完成后仅注销和重新注册设备，这一点对于成功至关重要。 你必须在阶段 10 启动之前完成重新注册，否则你可能会失去对设备的访问权限。

**我如何知道我的所有设备都注册到公共云中？**

若要检查你的设备是否已在公有云中注册，你应该将设备列表从 Azure AD 门户导出并下载到 Excel 电子表格。 然后，使用 registeredTime (在组织通过迁移过程的第 [9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)阶段) 使用 _registeredTime_ 列筛选注册的设备。

**是否仍需要按照使用基于 DNS 的 DNS 为 Microsoft 创建 DNS 记录Windows [DNS 名称](/microsoft-365/admin/dns/create-dns-records-using-windows-based-dns?#add-two-cname-records-for-mobile-device-management-mdm-for-microsoft)？**

重新注册设备不再需要此 DNS 条目。 

## <a name="additional-considerations"></a>其他注意事项

> [!IMPORTANT]
> Intune 服务主体将在迁移过程的第 [3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)阶段之后启用，这意味着激活 Azure AD 设备注册。 如果在迁移之前阻止了 Azure AD 设备注册，则必须使用 PowerShell 禁用 Intune 服务主体，以再次禁用 Azure AD 门户的 Azure AD 设备注册。 可以使用 PowerShell for Azure Active Directory 模块中的此命令禁用 Intune Graph主体。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到Office 365新的德国数据中心区域部署服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他前期工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 迁移计划信息](/power-bi/admin/service-admin-migrate-data-germany)
- [开始 Microsoft Teams 升级](/microsoftteams/upgrade-start-here)
