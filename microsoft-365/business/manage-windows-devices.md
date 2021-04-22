---
title: 允许 Microsoft 365 商业版管理加入域的 Windows 10 设备
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 了解如何通过几个步骤使 Microsoft 365 能够保护加入本地 Active-Directory 的 Windows 10 设备。
ms.openlocfilehash: c9f5a21d993200abcf9ecf1fa236879245e1c153
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939494"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>允许 Microsoft 365 商业高级版管理加入域的 Windows 10 设备

如果你的组织使用本地 Windows Server Active Directory，你可以设置 Microsoft 365 商业高级版来保护你的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。
若要设置此保护，你可以实现加入 **混合 Azure AD 的设备**。 这些设备已加入本地 Active Directory 和 Azure Active Directory。

本视频介绍了如何针对最常见方案设置此方案的步骤，后续步骤中对此也进行详细介绍。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>在开始使用之前，请确保完成以下步骤：
- 使用 Azure AD Connect 将用户同步到 Azure AD。
- 完成 Azure AD Connect 组织单位 (OU) 同步。
- 确保你同步的所有域用户都有 Microsoft 365 商业高级版许可证。

有关 [步骤，请参阅将域用户](manage-domain-users.md) 同步到 Microsoft。

## <a name="1-verify-mdm-authority-in-intune"></a>1. 在 Intune 中验证 MDM 颁发机构

转到 [终结点管理器](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)，在 Microsoft Intune 页面上，选择设备注册，然后在概述页面上，确保 **MDM 颁发机构** 是 **Intune**。

- 如果 **MDM 颁发机构** 为 **"无**"，请单击 **MDM 颁发机构** ，以将它设置为 **Intune**。
- 如果 **MDM 颁发** 机构为 Microsoft Office  **365，** 请转到设备注册设备并使用右侧添加 MDM 颁发机构对话框添加 Intune MDM 颁发机构 (只有 MDM 颁发机构设置为 Microsoft Office  >   365 ) 时，"添加 **MDM** 颁发机构"对话框才可用。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. 验证 Azure AD 是否已启用以加入计算机

- 转到 管理中心 ，然后选择 Azure Active Directory (如果 Azure Active Directory 在管理中心列表中不可见，) <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 全部显示"。  
- 在 **Azure Active Directory 管理中心** 中，转到 **"Azure Active Directory"，** 选择"**设备**"，然后选择"**设备设置"。**
- 验证 **用户是否将设备加入 Azure AD** 已启用 
    1. 若要启用所有用户，请 **设置为全部**。
    2. 若要启用特定用户，请设置为 **"已选择** "以启用特定的一组用户。
        - 将 Azure AD 中同步的所需域用户添加到 [安全组](../admin/create-groups/create-groups.md)。
        - 选择 **"选择组** "以启用该安全组的 MDM 用户作用域。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. 验证 Azure AD 是否已启用 MDM

- 转到管理中心，然后选择终结点管理 (如果终结点管理器在管理中心内不可见，请选择 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 全部)   
- 在 **Microsoft Endpoint Manager 管理中心中**，**转到设备**  >  **Windows**  >  **Windows 注册**  >  **自动注册**。
- 验证 MDM 用户作用域是否已启用。

    1. 若要注册所有计算机，请设置为"全部"，以在用户将工作帐户添加到 Windows 时自动注册已加入 Azure AD 的所有用户计算机和新计算机。
    2. 设置为 **"某些** "以注册特定组用户的计算机。
        -  将 Azure AD 中同步的所需域用户添加到 [安全组](../admin/create-groups/create-groups.md)。
        -  选择 **"选择组** "以启用该安全组的 MDM 用户作用域。

## <a name="4-create-the-required-resources"></a>4. 创建所需的资源 

使用[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 模块中的[Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet 简化了配置混合[Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)加入所需的任务。 调用此 cmdlet 时，它将创建和配置所需的服务连接点和组策略。

可以通过从 PowerShell 实例调用以下内容来安装此模块：

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> 建议在运行 Azure AD Connect 的 Windows Server 上安装此模块。

若要创建所需的服务连接点和组策略，将调用  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet。 执行此任务时，你将需要 Microsoft 365 商业高级版全局管理员凭据。 准备好创建资源时，请调用以下内容：

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

第一个命令将建立与 Microsoft 云的连接，当系统提示时，指定 Microsoft 365 商业高级版全局管理员凭据。

## <a name="5-link-the-group-policy"></a>5. 链接组策略

1. 在组策略管理控制台 (GPMC) 中，右键单击要链接策略的位置，然后从上下文菜单中选择"链接现有 *GPO..."。*
2. 选择在以上步骤中创建的策略，然后单击"确定 **"。**

## <a name="get-the-latest-administrative-templates"></a>获取最新的管理模板

如果你看不到使用默认 Azure **AD** 凭据启用自动 MDM 注册的策略，这可能是因为你未为 Windows 10 版本 1803 或更高版本安装 ADMX。 若要解决此问题，请按照以下步骤操作 (注意：最新的 MDM.admx 是向后兼容的) ：

1.  下载[：2020 年 10 ( 20H2) Windows 10 管理模板 (.admx) 。 ](https://www.microsoft.com/download/102157)
2.  在域控制器上安装程序包。
3.  根据管理模板版本导航到文件夹 **：C：\Program Files (x86) \Microsoft Group Policy\Windows 10 2020 年 10 月更新 (20H2)**。
4.  将上述 **路径中的"策略** 定义"文件夹重命名为 **PolicyDefinitions**。
5.  将 **PolicyDefinitions** 文件夹复制到 SYSVOL 共享，默认位于 **C：\Windows\SYSVOL\domain\Policies。** 
    -   如果计划将中央策略存储用于整个域，请在那里添加 PolicyDefinitions 的内容。
6.  如果您具有多个域控制器，请等待 SYSVOL 复制，以便策略可用。 此过程还适用于管理模板的任何未来版本。

此时，你应该可以看到"使用默认 **Azure AD** 凭据启用自动 MDM 注册"策略可用。

## <a name="related-content"></a>相关内容

将域用户同步到[Microsoft 365](manage-domain-users.md) (文章) 在管理[中心创建组](../admin/create-groups/create-groups.md) (文章) 教程：为托管域配置混合 Azure Active [Directory](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (文章) 