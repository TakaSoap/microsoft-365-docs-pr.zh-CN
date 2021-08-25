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
description: 了解如何解决 Windows 365 商业云电脑的安装问题。
ms.date: 08/13/2021
ms.openlocfilehash: b639453ef55960a3526fa8354dc95efb2653f9c5
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2021
ms.locfileid: "58507336"
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
5. 转到步骤 [2。验证 CloudPCBRT 系统帐户是否处于活动状态](#step-2-verify-that-the-cloudpcbrt-system-account-is-active)。

## <a name="step-2-verify-that-the-cloudpcbrt-system-account-is-active"></a>步骤 2. 验证 CloudPCBRT 系统帐户是否处于活动状态

首次在组织中分配 Windows 365 许可证时，将在 Azure AD 中自动创建名为"CloudPCBPRT"的系统帐户。 请勿删除此帐户，也不对该帐户 (例如更改名称或 UPN) 。 如果删除系统帐户，则安装将失败。 此系统帐户可确保设置过程顺畅，并且除 Windows 365 商业版的范围服务功能外，其他任何写入功能或对组织的访问权限。 如果删除此系统帐户，则必须打开一个新的支持请求以将其还原。

若要确保 CloudPCBRT 系统帐户在 Azure AD 中处于活动状态，请使用以下步骤。

1. 在 Azure 门户中，转到<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">"Azure Active Directory概述"</a>页。
2. 在左侧导航中的"管理 **"下，** 选择"**用户"。**
3. 在搜索框中，键入 **CloudPCBRT**，然后按 **Enter。**
4. 如果存在 CloudPCBRT 系统帐户，请转到步骤 [3。验证基于设备的 MFA 是否已关闭](#step-3-verify-that-device-based-mfa-is-turned-off)。
5. 如果 CloudPCBRT 系统帐户缺失，请在左侧导航中，选择"新建支持请求"以打开支持票证。 关闭支持票证后，直接转到步骤 [6。重置云电脑](#step-6-reset-your-cloud-pcs)。

## <a name="step-3-verify-that-device-based-mfa-is-turned-off"></a>步骤 3. 验证基于设备的 MFA 是否已关闭

可以配置你的组织，以便使用 Azure AD (MFA) 多重身份验证。 如果是这样，则必须关闭此设置。 若要确保"要求 **多重身份验证以向 Azure AD** 注册或加入设备"设置为"否"，请使用以下步骤。

1. 在 Azure 门户中，转到<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">"Azure Active Directory概述"</a>页。
2. 在左侧导航中的"管理 **"下**，选择 **"设备"，** 然后选择"**设备设置"。**
3. If **Require Multi-factor Authentication to register or join devices with Azure AD** is set to **Yes**， select **No**， then select **Save**.
4. 转到步骤 [4。确保 MFA 不会阻止安装](#step-4-make-sure-that-mfa-doesnt-block-setup)。

## <a name="step-4-make-sure-that-mfa-doesnt-block-setup"></a>步骤 4. 确保 MFA 不会阻止安装

如果你没有包含条件访问Azure AD Premium P1许可证，请转到步骤[5。确保 MDM 颁发机构配置已正确设置](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)。 如果你不知道你的订阅是否包含Azure AD Premium P1，请参阅我[拥有哪些订阅？](../admin-overview/what-subscription-do-i-have.md)

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

如果未对步骤 1-4 进行更改，则设置失败可能是由环境中 MDM 颁发机构配置导致的。 如果是这样，则有两种途径可遵循，具体取决于你是否计划Microsoft Intune管理云电脑。

- 如果你使用或计划将 Microsoft Intune 用于云电脑，请按照路径[A：确保](#path-a-use-microsoft-intune-to-manage-your-cloud-pcs)已正确配置移动 (MDM 和 MAM) 设置中的步骤操作。
- 如果你不计划使用 Microsoft Intune 管理云电脑，请按照路径[B： 关闭自动 MDM 注册 中的步骤操作](#path-b-turn-off-automatic-mdm-enrollment)。

### <a name="path-a-use-microsoft-intune-to-manage-your-cloud-pcs"></a>路径 A。Microsoft Intune管理云电脑

如果你已使用 Microsoft Intune，或计划使用它来管理 Windows 365 云电脑，请确保 Azure AD 中的移动 (MDM 和 **MAM)** 设置已正确配置。

1. 在 Azure 门户中，转到<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">"Azure Active Directory概述"</a>页。
2. 在左侧导航的 **"管理"** 下，选择"移动性 (MDM 和 **MAM) "，** 然后选择 **"Microsoft Intune"。**
3. 在"**配置"** 页面上 **，在 MDM** 用户作用域旁边，选择 **"部分**"或"**全部**"，然后选择"保存 **"。**
4. 在左侧导航 **中，在**"管理"下，选择"移动性 (MDM **和 MAM**) "，Microsoft Intune **注册"，然后** 重复步骤 3。

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

#### <a name="option-1-use-the-azure-ad-portal-to-turn-off-automatic-intune-enrollment"></a>选项 1. 使用 Azure AD 门户关闭自动 Intune 注册

1. 在 Azure 门户中，转到<a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">"Azure Active Directory概述"</a>页。
2. 在左侧导航的 **"管理"** 下，选择"移动性 (MDM 和 **MAM) "，** 然后选择 **"Microsoft Intune"。**
3. 在"**配置"** 页面上，在 MDM 用户作用域旁边，选择"**无**"，然后选择"保存 **"。**
4. 在左侧导航 **中，在**"管理"下，选择"移动性 (MDM **和 MAM**) "，Microsoft Intune **注册"，然后** 重复步骤 3。
5. 转到步骤 [6。重置云电脑](#step-6-reset-your-cloud-pcs)。

#### <a name="option-2-use-microsoft-graph-to-turn-off-automatic-intune-enrollment"></a>选项 2：使用 Microsoft Graph关闭自动 Intune 注册

如果你无法根据选项 1 Microsoft Azure配置移动 (MDM 和 **MAM**) 配置 [移动功能。使用 Azure AD](#option-1-use-the-azure-ad-portal-to-turn-off-automatic-intune-enrollment)门户关闭自动 Intune 注册，你将看到一条警告，显示"自动 MDM 注册仅适用于Azure AD Premium订阅者"。 在这种情况下，你必须使用 Microsoft Graph在你的环境中关闭 MDM 策略。

1. 转到 "Graph 资源管理器 <a href="https://go.microsoft.com/fwlink/p/?linkid=2170005">https://developer.microsoft.com/graph/graph-explorer</a> "。。
2. Under **Graph Explorer，** select **Sign in to Graph Explorer**， and sign in with your Global admin account.
3. 如果看到"**请求的权限"对话框**，请选择"接受 **"。**
4. 在帐户名称旁边，选择"更多操作"按钮 (三个点) ，然后选择"**选择权限"。**
5. 在"**权限"** 窗格中，展开"**策略**"，选择 **"Policy.Read.All"** 和 **"Policy.ReadWrite.MobilityManagement"，** 然后选择"同意 **"。**
6. 如果看到"**请求的权限"对话框**，请选中"代表你的组织同意"复选框，然后选择"接受 **"。**
7. 再次 **展开"** 策略"，验证 **Policy.Read.All** 和 **Policy.ReadWrite.MobilityManagement** 的"状态"列是否显示 **"Consented"，** 然后关闭"**权限"** 窗格。
8. 从第一个下拉列表中，选择 **"GET"。**
9. 在文本框中，输入以下字符串，然后选择"**运行查询"：**  
    `https://graph.microsoft.com/beta/policies/mobileDeviceManagementPolicies`  
    此查询检索组织中设备管理策略的列表。
   "响应预览 **"** 窗格中的结果应类似于以下代码段：

    ```
    {
        "@odata.context": "https://graph.microsoft.com/beta/$metadata#mobilityManagementPolicies",
        "value": [
            {
                "id": "0000000a-0000-0000-c000-000000000000",
                "appliesTo": "all",
                "complianceUrl": null,
                "description": "Device Management Policy for Microsoft Intune",
                "discoveryUrl": null,
                "displayName": "Microsoft Intune",
                "isValid": true,
                "termsOfUseUrl": null
            },
            {
                "id": "d4ebce55-015a-49b5-a083-c84d1797ae8c",
                "appliesTo": "none",
                "complianceUrl": "https://portal.manage.microsoft.com/?portalAction",
                "description": "Device Management Policy for Microsoft Intune Enrollment",
                "discoveryUrl": "https://enrollment.manage.microsoft.com/enrollmentserver/discovery.svc",
                "displayName": "Microsoft Intune Enrollment",
                "isValid": true,
                "termsOfUseUrl": "https://portal.manage.microsoft.com/TermsofUse.aspx"
            }
        ]
    }
    ```
10. 如果 `"appliesTo"` 列出的所有策略的值为 **none，** 请转到步骤 [6。重置云电脑](#step-6-reset-your-cloud-pcs)。 否则，继续执行步骤 11。
11. 第一个下拉列表中，选择 **PATCH**。
12. 在文本框中，输入以下字符串：  
    `https://graph.microsoft.com/beta/policies/mobileDeviceManagementPolicies/0000000a-0000-0000-c000-000000000000`
13. 在"**请求正文"** 部分，输入以下代码段，然后选择"**运行查询"：**
    ```
    {
        "appliesTo": "none"
    }
    ```
14. 在文本框中，输入以下字符串：  
    `https://graph.microsoft.com/beta/policies/mobileDeviceManagementPolicies/d4ebce55-015a-49b5-a083-c84d1797ae8c`
15. 在"**请求正文**"部分，保留在步骤 13 中输入的代码段，然后选择"运行 **查询"。**
16. 第一个下拉列表中，选择 **"GET"。**
17. 清除"请求正文 **"部分的任何** 文本。
18. 在文本框中，输入以下字符串，然后选择"**运行查询"：**  
    `https://graph.microsoft.com/beta/policies/mobileDeviceManagementPolicies`

    "响应"视图 **窗格中** 的结果应类似于以下代码段。
    ```
    {
        "@odata.context": "https://graph.microsoft.com/beta/$metadata#mobilityManagementPolicies",
        "value": [
            {
                "id": "0000000a-0000-0000-c000-000000000000",
                "appliesTo": "none",
                "complianceUrl": "https://portal.manage.microsoft.com/?portalAction=Compliance",
                "description": "Device Management Policy for Microsoft Intune",
                "discoveryUrl": "https://enrollment.manage.microsoft.com/enrollmentserver/discovery.svc”,
                "displayName": "Microsoft Intune",
                "isValid": true,
                "termsOfUseUrl": "https://portal.manage.microsoft.com/TermsofUse.aspx"
            },
            {
                "id": "d4ebce55-015a-49b5-a083-c84d1797ae8c",
                "appliesTo": "none",
                "complianceUrl": "https://portal.manage.microsoft.com/?portalAction",
                "description": "Device Management Policy for Microsoft Intune Enrollment",
                "discoveryUrl": "https://enrollment.manage.microsoft.com/enrollmentserver/discovery.svc",
                "displayName": "Microsoft Intune Enrollment",
                "isValid": true,
                "termsOfUseUrl": "https://portal.manage.microsoft.com/TermsofUse.aspx"
            }
        ]
    } 
    ```

    所有 `"appliesTo"` 策略的值现在都设置为 **none**。 此查询验证作用域是否成功更改了组织中设备管理策略。
19. 转到步骤 [6。重置云电脑](#step-6-reset-your-cloud-pcs)。

## <a name="step-6-reset-your-cloud-pcs"></a>步骤 6. 重置云电脑

完成本文中的疑难解答步骤后，用户必须重新启动其云电脑设置。 

如果您刚刚完成了步骤 [3。确认基于设备的 MFA](#step-3-verify-that-device-based-mfa-is-turned-off)已关闭，请至少等待 10 分钟，更改才能生效，然后再继续。 确保从 MFA 中排除的用户是第一个登录到[Windows 365 主页的用户](https://windows365.microsoft.com)。

告诉所有看到"安装程序失败"错误的云电脑用户，使用以下步骤重置其云电脑。

1. On the [Windows 365 home page，](https://windows365.microsoft.com)select the gear icon for any Cloud PC that has the "Setup failed" status， then select **Reset**. 此操作将重新启动安装过程。
2. 重置后，如果"安装程序失败"错误仍显示，并且您跳过了步骤 [5。确保 MDM 颁发机构配置设置正确，](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)完成此步骤，然后再次重置 CloudPC。 否则，在左侧导航中，选择" **新建支持请求** "以打开支持票证。
