---
title: 解决 Windows 365 商业版云电脑设置问题
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
description: 了解如何解决 Windows 365 商业版云电脑的安装问题。
ms.date: 08/13/2021
ms.openlocfilehash: 701d1ce3ae97836d6687050e16a176aad85e2995
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59171490"
---
# <a name="troubleshoot-windows-365-business-cloud-pc-setup-issues"></a>解决 Windows 365 商业版云电脑设置问题

如果用户收到"安装失败"错误，或者如果安装程序在为其分配许可证后需要花费 90 分钟以上的时间，请使用本文中的步骤解决问题。

> [!IMPORTANT]
> 你必须是全局管理员才能执行本文中所述的多数任务。 如果其他管理员角色可用于特定过程，则这些角色将在过程之前进行说明。 如果你没有登录或访问 Azure 门户部分的权限，请联系你的 IT 管理员。有关 Azure 规则详细信息，请参阅 [Azure AD 内置角色](/azure/active-directory/roles/permissions-reference)。 若要了解有关 Azure 门户的信息，请参阅 [Azure 门户概述](/azure/azure-portal/azure-portal-overview)。

## <a name="step-1-verify-azure-ad-device-settings"></a>步骤 1. 验证 Azure AD 设备设置

确保 **用户可以将设备加入 Azure AD** 设置为"全部 **"。**

1. 在 登录 Microsoft Azure 门户 [https://portal.azure.com/](https://go.microsoft.com/fwlink/p/?linkid=516942) 。
2. 在 **"管理Azure Active Directory"** 下，选择"**查看"。**
3. 在左侧导航中的"管理 **"下**，选择 **"设备"，** 然后选择"**设备设置"。**
4. 如果用户 **可能将设备加入 Azure AD** 未设置为"全部"，请选择"全部"，然后选择"保存 **"。**
5. 转到步骤[2。验证 Windows 365 BPRT 永久用户帐户是否处于活动状态](#step-2-verify-that-the-windows-365-bprt-permanent-user-system-account-is-active)。

## <a name="step-2-verify-that-the-windows-365-bprt-permanent-user-system-account-is-active"></a>步骤 2. 验证 Windows 365 BPRT 永久用户帐户是否处于活动状态

首次在Windows分配 Windows 365 许可证时，将在 Azure AD 中自动创建名为 **Windows 365 BPRT 永久用户的** 系统帐户。 请勿删除此帐户或更改该帐户 (例如更改名称或 UPN) 。 如果修改或删除系统帐户，则安装将失败。 此系统帐户可确保顺利设置过程，并且除 Windows 365 商业版的范围服务功能外，其他任何写入功能或对组织的访问权限。 如果删除或修改此系统帐户，则必须使用具有 Windows 365 商业版许可证的任何帐户登录到 windows365.microsoft.com，并等待 12 小时以刷新令牌。

若要确保 Windows 365 BPRT 永久用户帐户在 Azure AD 中处于活动状态，请使用以下步骤。

1. 在 Azure 门户中，转到<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">"Azure Active Directory概述</a>"页。
2. 在左侧导航中的"管理 **"下，** 选择"**用户"。**
3. 在搜索框中，键入 **Windows 365 BPRT 永久用户**，然后按 **Enter。**
4. 如果存在 Windows 365 BPRT 永久用户帐户，请转到步骤[3。验证基于设备的 MFA 是否已关闭](#step-3-verify-that-device-based-mfa-is-turned-off)。
5. 如果 Windows 365 BPRT 永久用户帐户缺失或进行了任何更改，请通过分配了 Windows 365 商业版许可证的任何帐户登录到 windows365.microsoft.com。 将在 12 Windows生成新的 365 BPRT 永久用户。 重新生成令牌后，直接转到步骤 [6。重置云电脑](#step-6-reset-your-cloud-pcs)。

## <a name="step-3-verify-that-device-based-mfa-is-turned-off"></a>步骤 3. 验证基于设备的 MFA 是否已关闭

可以配置你的组织，以便使用 Azure AD (MFA) 多重身份验证。 如果是这样，则必须关闭此设置。 若要确保"要求 **多重身份验证以向 Azure AD** 注册或加入设备"设置为"否"，请使用以下步骤。

1. 在 Azure 门户中，转到<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">"Azure Active Directory概述</a>"页。
2. 在左侧导航中的"管理 **"下**，选择 **"设备"，** 然后选择"**设备设置"。**
3. If **Require Multi-factor Authentication to register or join devices with Azure AD** is set to **Yes**， select **No**， then select **Save**.
4. 转到步骤 [4。确保 MFA 不会阻止安装](#step-4-make-sure-that-mfa-doesnt-block-setup)。

## <a name="step-4-make-sure-that-mfa-doesnt-block-setup"></a>步骤 4. 确保 MFA 不会阻止安装

如果你没有包含条件访问Azure AD Premium P1许可证，请转到步骤[5。确保 MDM 颁发机构配置已正确设置](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)。 如果不知道订阅是否包含Azure AD Premium P1，请参阅我[拥有哪些订阅？](../admin-overview/what-subscription-do-i-have.md)

如果你有包含条件访问的 Azure AD Premium P1 许可证，请在完成本文中的其余步骤后选择一个用户作为第一个登录到 Windows 365 主页 [https://windows365.microsoft.com](https://windows365.microsoft.com) 的用户。 确保第一个用户没有 MFA 条件访问策略。 在任何设置尝试过程中，MFA 必须保持关闭状态。 在整个组织中成功设置所有云电脑后，你可以为此用户启用 MFA。 若要了解有关条件访问策略的更多信息，请参阅什么是条件访问[Azure Active Directory？。](/azure/active-directory/conditional-access/overview)

若要检查条件访问策略，请使用以下步骤。

1. 在 Azure 门户中，转到" <a href="https://go.microsoft.com/fwlink/p/?linkid=2169290" target="_blank">条件访问策略"</a> 页。
2. 如果未列出任何策略，请继续执行步骤 [5。确保 MDM 颁发机构配置已正确设置](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)。
3. 如果页面上列出了任何策略，请选择策略名称。
4. 在"**访问控制"****部分中的"** 授予"下，如果显示"已选择 0 个控件"，则返回到策略列表并选择下一个策略。 否则，继续执行步骤 5。
5. 在" **访问控制"** 部分中的" **授予"** 下，如果显示选中了多个控件，请选择 **_"n_ 个控件"所选** 链接。
6. 在右侧窗格中 **，如果选中** 了"需要多重身份验证"，请清除该复选框，然后选择"选择 **"** 按钮。
   > [!TIP]
   > 或者，你可以从策略中排除第一个用户。 若要了解如何这样做，请参阅管理从 [条件访问策略中排除的用户](/azure/active-directory/governance/conditional-access-exclusion)。
7. 重复步骤 3 至 6，直到删除了所有条件访问策略的 MFA。
8. 转到步骤 [5。确保 MDM 颁发机构配置已正确设置](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)。

## <a name="step-5-make-sure-mdm-authority-configuration-is-set-up-correctly"></a>步骤 5. 确保 MDM 颁发机构配置已正确设置

如果根据本文前面步骤 1-4 进行了更改，则现在可以解决根本原因。 若要验证该问题是否得到解决，请转到步骤 [6。重置云电脑](#step-6-reset-your-cloud-pcs)。

如果未对步骤 1-4 进行更改，则设置失败可能是由环境中 MDM 颁发机构配置导致的。 如果是这样，则有两个途径可遵循，具体取决于你是否计划Microsoft Intune管理云电脑。

- 如果你使用或计划将 Microsoft Intune 用于云电脑，请按照路径[A：确保](#path-a-use-microsoft-intune-to-manage-your-cloud-pcs)已正确配置移动 (MDM 和 MAM) 中的步骤操作。
- 如果你不计划使用 Microsoft Intune 管理云电脑，请按照路径[B： 关闭自动 MDM](#path-b-turn-off-automatic-mdm-enrollment)注册 中的步骤操作。

### <a name="path-a-use-microsoft-intune-to-manage-your-cloud-pcs"></a>路径 A。Microsoft Intune管理云电脑

如果你已使用 Microsoft Intune，或计划使用它管理 Windows 365 云电脑，请确保 Azure AD 中的移动 (MDM 和 **MAM)** 设置已正确配置。

1. 在 Azure 门户中，转到<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">"Azure Active Directory概述</a>"页。
2. 在左侧导航导航 **中的"管理**"下，选择"移动性 (MDM 和 **MAM) "，** 然后选择 **"Microsoft Intune"。**
3. 在"**配置"** 页面上 **，在 MDM** 用户作用域旁边，选择 **"部分**"或"**全部**"，然后选择"保存 **"。**
4. 在左侧导航中 **，在"** 管理"下，选择"移动性 (MDM 和 **MAM) "，** 选择"Microsoft Intune **注册**"，然后重复步骤 3。

分配有云电脑的用户必须分配有 Intune 许可证。 CloudPCBPRT 系统帐户无需分配 Intune 许可证。

> [!IMPORTANT]
> 若要分配许可证，你必须是全局管理员或许可管理员，或者具有许可权限的角色。

1. In the [Microsoft Endpoint Manager admin center，](https://go.microsoft.com/fwlink/p/?linkid=2169290)select **Users**  >  **All Users**.
2. 在" **所有用户"** 列表中，选择一个用户。
3. 在"用户配置文件 **"页上**，选择"许可证 **"。**
4. 在"**许可证"页上**，选择"分配 **"。**
5. 查找 **Intune**，选中复选框，然后选择 **保存**。 用户帐户现在具有使用服务和注册设备所需的权限。
6. 转到步骤 [6。重置云电脑](#step-6-reset-your-cloud-pcs)。

### <a name="path-b-turn-off-automatic-mdm-enrollment"></a>路径 B。关闭自动 MDM 注册

如果你不计划将 Microsoft Intune用于云电脑管理，则必须关闭自动 MDM 注册。

> [!IMPORTANT]
> 如果你不是 MDM 管理员，请不要在未咨询 IT 管理员的情况下使用以下任一过程。仅在未设置云电脑时遵循这些过程。 任何配置更改都可能会影响管理环境。 如果需要帮助，请联系 [Intune 支持](/mem/get-support)人员。

#### <a name="use-the-azure-ad-portal-to-turn-off-automatic-intune-enrollment"></a>使用 Azure AD 门户关闭自动 Intune 注册

1. 在 Azure 门户中，转到<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">"Azure Active Directory概述</a>"页。
2. 在左侧导航导航 **中的"管理**"下，选择"移动性 (MDM 和 **MAM) "，** 然后选择 **"Microsoft Intune"。**
3. 在 **"配置** "页上，你将看到两个操作之一。 如果你有一个Azure AD Premium，请选择 MDM **用户作用域** 旁边的"无"，然后选择"保存 **"。** 如果没有订阅，请选择Azure AD Premium禁用 **"。**
4. 在左侧导航中 **，在"** 管理"下，选择"移动性 (MDM 和 **MAM) "，** 选择"Microsoft Intune **注册**"，然后重复步骤 3。
5. 转到步骤 [6。重置云电脑](#step-6-reset-your-cloud-pcs)。


## <a name="step-6-reset-your-cloud-pcs"></a>步骤 6. 重置云电脑

完成本文中的疑难解答步骤后，用户必须重新启动其云电脑设置。 

如果您刚刚完成了步骤 [3。确认基于设备的 MFA](#step-3-verify-that-device-based-mfa-is-turned-off)已关闭，请至少等待 10 分钟，更改才能生效，然后再继续。 确保从 MFA 中排除的用户是第一个登录到[Windows 365 主页的用户](https://windows365.microsoft.com)。

告诉所有看到"安装程序失败"错误的云电脑用户，使用以下步骤重置其云电脑。

1. On the [Windows 365 home page，](https://windows365.microsoft.com)select the gear icon for any Cloud PC that has the "Setup failed" status， then select **Reset**. 此操作将重新启动安装过程。
2. 重置后，如果"安装程序失败"错误仍显示，并且您跳过了步骤 [5。确保 MDM 颁发机构配置设置正确，](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)完成此步骤，然后再次重置 CloudPC。 否则，在左侧导航中，选择" **新建支持请求** "以打开支持票证。
