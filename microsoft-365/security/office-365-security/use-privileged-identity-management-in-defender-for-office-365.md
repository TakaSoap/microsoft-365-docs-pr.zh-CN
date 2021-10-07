---
title: 使用 Microsoft Defender for Office 365 中的 Azure Privileged Identity Management (PIM) 来限制管理员对网络安全工具的访问。
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/03/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 了解如何集成 Azure PIM，以便向用户授予即时、限时访问权限以在 Microsoft Defender for Office 365 中执行已提升特权任务，从而降低数据风险。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ea618a24c14aa49973ae05287a65cbb756f5467
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196281"
---
<!--A-->
# <a name="privileged-identity-management-pim-and-why-to-use-it-with-microsoft-defender-for-office-365"></a>Privileged Identity Management (PIM) 以及将其与 Microsoft Defender for Office 365 配合使用的原因

Privileged Identity Management (PIM) 为 Azure 功能，设置后，用户便可在有限的时间段(有时称为时间框时间段)内访问数据，从而完成特定任务。 此访问权限为执行所需操作的‘即时’权限，之后会被撤销。 PIM 限制了用户对敏感数据的访问权限和时间，与具有对数据和其他设置的长期访问权限的特权管理帐户相比，PIM 降低了曝光风险。 那么，如何将此功能(PIM)与 Microsoft Defender for Office 365 结合使用?

> [!TIP]
> PIM 访问权限仅限于角色和标识级别，且允许完成多个任务。 其不会与仅限于任务级别的 Privileged Access Management (PAM)混淆。

## <a name="steps-to-use-pim-to-grant-just-in-time-access-to-defender-for-office-365-related-tasks"></a>使用 PIM 授予对 Defender for Office 365 相关任务的即时访问权限的步骤

通过将 PIM 设置为与 Defender for Office 365 配合使用，管理员会创建流程，以便用户请求访问权限以执行所需操作。用户必须 *证明* 提升其特权的必要性。

在此示例中，我们将为 Alex 进行配置，他是我们安全团队的成员，在 Office 365 中没有永久访问权限，但可以提升为日常操作所需的角色，例如[威胁搜寻](threat-hunting-in-threat-explorer.md) ，然后在不太频繁但敏感的操作中可以提升特权级别， 例如，需要[修正恶意传递的电子邮件](remediate-malicious-email-delivered-office-365.md)。

> [!NOTE]
> 这将指导你完成为安全分析师设置 PIM 所需的步骤，该分析师需能够在 Microsoft Defender for Office 365 中使用威胁资源管理器清除电子邮件。相同步骤可用于安全与合规门户中的其他 RBAC 角色。 例如，此流程适用于信息工作者，其需要日常访问电子数据展示以执行搜索和案例工作，但偶尔只需已提升权限以从租户中导出数据。

***步骤 1***：在订阅的 Azure PIM 控制台中，将用户(Alex)添加到 Azure 安全信息读取者角色，并配置与激活相关的安全设置。

1. 登录 [Azure AD 管理中心](https://aad.portal.azure.com/)，然后选择 **Azure Active Directory** > **角色和管理员**。
2. 在角色列表中选择 **安全信息读取者**，然后选择 **设置** > **编辑**
3. 将“**激活最长持续时间(小时)**”设置为正常工作日，并将“激活时”设置为需要 **Azure MFA**。
4. 由于这是 Alex 日常操作的正常特权级别，我们将取消选中 **需要激活的理由**'> **更新**。
5. 选择 **添加分配** > **未选择成员** > 选择或键入名称以搜索正确成员。
6. 点击 **选择** 按钮以选择需要为 PIM 特权添加的成员 > 点击 **下一步** >在“添加分配”页面不执行任何更改(分配类型 *符合条件* 和持续时间 *符合条件* 将为默认值)和 **分配**。

用户名称(此处为 'Alex') 将显示在下一页的“符合条件”分配下，这意味着其能够使用之前配置的设置 PIM 到角色中。

> [!NOTE]
> 有关 Privileged Identity Management 的快速回顾，请参阅 [此视频](https://www.youtube.com/watch?v=VQMAg0sa_lE)。

:::image type="content" source="../../media/pim-mdo-role-setting-details-for-security-reader-show-8-hr-duration.png" alt-text="请确保在 Privileged Access Management 中审查安全信息读取者角色的设置。此处，你将看到 PIM 激活的最长持续时间为 8 小时。":::

***步骤 2***：为其他任务创建所需的第二个(已提升)权限组并分配资格。

使用[特权访问组](/azure/active-directory/privileged-identity-management/groups-features)，我们现在可以创建自己的自定义组并在需要时合并权限或增加粒度以满足组织做法和需求。

### <a name="create-a-role-group-requiring-the-permissions-we-need"></a>创建需要所需权限的角色组

在安全门户中，创建包含所需权限的自定义角色组。

1. 浏览到 Microsoft 365 Defender 门户(https://security.microsoft.com) > **权限与角色** > 选择“电子邮件与协作”下的 **角色** > **创建**。
2. 命名组以反映其用途，例如‘搜索并清除 PIM’。
3. 不要添加成员，只需保存组并转到下一部分!

### <a name="create-the-security-group-in-azure-ad-for-elevated-permissions"></a>在 Azure AD 中为已提升权限创建安全组

1. 浏览回 [Azure AD 管理中心](https://aad.portal.azure.com/) 并导航到 **Azure AD** > **组** > **新组**。
2. 命名 AAD 组以反映其用途，当前 **无需任何所有者或成员**。
3. 将 **Azure AD 角色可分配给组** 设置为 **是**。
4. 不要添加任何角色、成员或所有者，请创建组。
5. 返回刚刚创建的组，然后选择 **特权访问** > **启用特权访问**。
6. 在组中，选择 **符合条件的分配** > **添加分配** > 将需要“搜索并清除”的用户添加为 **成员** 角色。
7. 在组的“特权访问”窗格中配置 **设置**。 选择以 **编辑****成员** 角色的设置。
8. 更改激活时间以适用于组织。 在此示例中，选择 **更新** 之前需要 *Azure MFA*、 *理由* 以及 *票证信息*。

### <a name="nest-the-newly-created-security-group-into-the-role-group"></a>将新创建的安全组嵌套进角色组。

1. [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 并运行以下内容:

    `Add-RoleGroupMember "<<Role Group Name>>" -Member "<<Azure Security Group>>"`

## <a name="test-your-configuration-of-pim-with-defender-for-office-365"></a>使用 Defender for Office 365 测试 PIM 的配置

1. 使用测试用户 (Alex) 登录，此时该测试用户不应具有 [Microsoft 365 Defender 门户](/microsoft-365/security/defender/overview-security-center)中的管理访问权限。
2. 导航到 PIM，用户可以在其中激活其日常安全信息读取者角色。
3. 如果你尝试使用威胁资源管理器清除电子邮件，则会收到错误提示，指出需要其他权限。
4. 第二次 PIM 到已提升角色。在短暂延迟后，现在应该能够清除电子邮件，且不会出现问题。

   :::image type="content" source="../../media/pim-mdo-add-the-search-and-purge-role-assignment-to-this-pim-role.PNG" alt-text="如果我们通过安全信息读取者 PIM 角色添加的用户 (Alex)尝试删除可疑电子邮件，则其将收到一条消息，指出‘你需要‘搜索并清除’角色才可对此电子邮件执行操作。请联系管理员以获取角色分配或将此电子邮件添加到事件。":::

管理角色和权限（如“搜索并清除角色”）的永久分配不适用于零信任安全计划，但如你所见，PIM 可用于授予对所需工具集的实时访问权限。

*感谢客户工程师 Ben Harris 提供访问博客文章的权限和用于此内容的资源。*

<!--A-->