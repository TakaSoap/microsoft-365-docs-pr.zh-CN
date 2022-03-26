---
title: 要求对组织外部人员进行条件访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 了解如何要求组织外部人员通过条件访问检查，如 MFA 和兼容设备。
ms.openlocfilehash: 181ee77e6b8a8d491294c9a5d3f8ec9202c9f9c1
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63715979"
---
# <a name="require-conditional-access-for-people-outside-your-organization"></a>要求对组织外部人员进行条件访问

您可以为组织外部人员要求以下条件访问选项之一：

- 多重身份验证
- 兼容设备
- 已Azure AD混合设备

使用 Azure AD B2B 直接连接（如与 Teams 中的共享通道）时，可以选择信任其他组织的条件访问设置，以使用这些选项。

## <a name="planning-considerations-for-conditional-access"></a>条件访问的规划注意事项

多重身份验证可用于任何外部帐户。 如果组织不信任来自其他组织的多重身份验证Azure AD，则来自这些组织的用户在访问组织资源时必须执行多重身份验证。 具有第三方电子邮件地址 (Microsoft) 将始终提示他们进行多重身份验证。

"要求 **设备标记为** 合规"和"要求混合 **Azure AD加入的设备** 要求设备在设备Azure AD。 如果选择启用这些选项，则组织外部人员必须使用由组织或您信任的组织管理的设备。 将阻止没有托管设备的人，包括：

- 具有第三方或消费者电子邮件地址的人
- 来自Microsoft 365 Azure AD组织或组织不管理设备的人
- 来自Microsoft 365或Azure AD组织，需要组织不信任其条件访问设置的托管设备的人。

建议在要求兼容或混合设备Azure AD谨慎，因为这将阻止许多外部协作方案。 确保你的所有合作伙伴组织管理其设备，并且你的组织信任他们的设置。

## <a name="set-up-conditional-access-requirements-for-people-outside-your-organization"></a>为组织外部人员设置条件访问要求

若要要求组织外部人员具有条件访问权限，请执行下列操作：

1. [选择要信任其他组织的条件访问设置](#choose-conditional-access-settings-to-trust-from-other-organizations)。
1. [为组织外部人员设置条件访问](#set-up-conditional-access-for-people-outside-your-organization)。

## <a name="choose-conditional-access-settings-to-trust-from-other-organizations"></a>选择条件访问设置以信任其他组织

可以选择信任来自所有其他组织或组织Microsoft 365 Azure AD或仅信任您指定的组织的条件访问设置。

> [!NOTE]
> 对跨租户访问设置所做的更改可能需要两个小时才能生效。

### <a name="trust-conditional-access-settings-from-all-azure-active-directory-organizations"></a>信任来自所有组织的条件Azure Active Directory设置

如果要信任来自所有组织的条件访问设置，请按照此过程操作。

信任来自所有组织的条件Azure Active Directory设置
1. 使用全局[Azure Active Directory](https://aad.portal.azure.com)或安全管理员帐户登录登录。
1. 选择 **"外部标识"**，然后选择"跨租户访问设置 (**预览)**。
1. 选择" **默认设置"** 选项卡。
1. 在 **"入站访问设置"** 下， **选择"编辑入站默认值"**。
1. 选择" **信任设置"** 选项卡。
1. 选择您希望条件访问策略接受其他组织的设置。
1. 选择 **"保存** "并关闭 **"默认设置"** 边栏选项卡。

### <a name="trust-conditional-access-settings-from-a-specific-organization"></a>信任来自特定组织的条件访问设置

如果要信任来自特定组织的条件访问设置，请按照此过程操作。

信任来自特定组织的条件访问设置
1. 使用全局[Azure Active Directory](https://aad.portal.azure.com)或安全管理员帐户登录登录。
1. 选择 **"外部标识"**，然后选择"跨租户访问设置 (**预览)**。
1. 选择要 **信任** 条件访问设置的组织的入站访问设置。
1. 选择" **信任设置"** 选项卡。
1. 选择" **自定义设置"** 选项。
1. 选择您希望条件访问策略接受其他组织的设置。
1. 选择 **"保存** "并关闭 **"默认设置"** 边栏选项卡。

## <a name="set-up-conditional-access-for-people-outside-your-organization"></a>为组织外部人员设置条件访问

为组织外部人员设置条件访问策略会影响以下内容：

- 使用来宾帐户的用户 (Azure AD B2B 协作) 
- B2B 直接Teams用户 (Azure AD共享频道中的外部) 

> [!IMPORTANT]
> 仅选择"要求设备标记为合规"或"要求加入混合 **Azure AD** 的设备"（如果组织外部的每个人都使用由组织或受信任的组织或 Microsoft 365 或 Azure AD 管理的设备）。

为组织外部人员设置条件访问
1. 转到 “[ Azure 条件访问策略](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)”。
1. 在“**条件访问 | 策略**”边栏选项卡上，单击“**新建策略**”。
1. 在“**名称**”字段中，输入名称。
1. 在“**分配**”下，单击“**用户和组**”。
1. 在“**用户和组**”边栏选项卡上，选择“**选择用户和组**”，然后选中“**所有来宾和外部用户**”复选框。
1. 在“**分配**”下，单击“**云应用或操作**”。
1. 在“**云应用或操作**”边栏选项卡中，选择“**包含**”选项卡上的“**所有云应用**”。
1. 在“**访问控制**”下，单击“**授予**”。
1. 在" **授予"** 边栏选项卡上，选择要为组织外部人员需要的选项，然后单击"选择 **"**。
1. 在“**新建**”边栏选项卡中的“**启用策略**”下面，单击“**打开**”，然后单击“**创建**”。

## <a name="related-topics"></a>相关主题

[教程：为 B2B 来宾强制执行多重身份验证](/azure/active-directory/external-identities/b2b-tutorial-require-mfa)
