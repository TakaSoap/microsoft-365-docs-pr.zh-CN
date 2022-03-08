---
title: 允许企业Windows 10已加入域Microsoft 365设备
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: 了解如何启用 Microsoft 365只需几个步骤，Windows 10加入 Active-Directory 的设备。
ms.openlocfilehash: b12acbfbc9ff6e25c846d512781d8b72edf3f2fe
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327919"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>允许加入域Windows 10设备由用户Microsoft 365 商业高级版

> [!NOTE]
> 从 2022 年 3 月 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 此产品/服务为设备提供其他安全功能。 [详细了解 Defender for Business](../../security/defender-business/mdb-overview.md)。

如果你的组织在本地Windows Server Active Directory，你可以设置 Microsoft 365 商业高级版 来保护 Windows 10 设备，同时仍保留对需要本地身份验证的本地资源的访问权限。
若要设置此保护，你可以实现已加入 **Azure AD混合保护**。 这些设备已加入到本地 Active Directory 和 Azure Active Directory。

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>观看：配置混合Azure Active Directory加入

本视频介绍了如何针对最常见方案设置此方案的步骤，后续步骤中对此也进行详细介绍。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>准备工作

- 将用户与Azure AD同步Azure AD 连接。
- 完成Azure AD 连接组织单位 (OU) 同步。
- 请确保您同步的所有域用户都有Microsoft 365 商业高级版。

有关 [步骤，请参阅将域用户](manage-domain-users.md) 同步到 Microsoft。

## <a name="1-verify-mdm-authority-in-intune"></a>1. 在 Intune 中验证 MDM 颁发机构

转到"[Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)"，在"Microsoft Intune"页面上，选择"设备注册"，然后在"概述"页上，确保 **MDM 颁发机构** 为 **Intune**。

- 如果 **MDM 颁发** 机构为 **"无**"，请单击 **MDM 颁发机构** 以将它设置为 **Intune**。
- 如果 **MDM** 颁发机构Microsoft Office 365，请转到 **DevicesEnroll** >  设备并使用右侧"添加 **MDM** 颁发机构"对话框添加 **Intune MDM** 颁发机构 (只有在 **MDM** 颁发机构设置为 Microsoft Office 365) 时，"添加 **MDM** 颁发机构"对话框才可用。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. 验证Azure AD是否已启用加入计算机

- 转到管理中心，<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>然后选择"Azure Active Directory ( "管理中心"列表中Azure Active Directory") "全部 **显示"**。 
- In the **Azure Active Directory admin center**， go to **Azure Active Directory** ， choose **Devices** and then **Device settings**.
- **VerifyUsers 可能会将设备加入Azure AD** 启用状态 
    1. 若要启用所有用户，请设置为"全部 **"**。
    2. 若要启用特定用户，请设置为 **"已选择** "以启用特定的一组用户。
        - 将同步到安全组Azure AD域[用户](../../admin/create-groups/create-groups.md)。
        - 选择 **"选择组** "以启用该安全组的 MDM 用户作用域。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. 验证Azure AD是否已启用 MDM

- 转到管理中心，<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>然后选择"终结点管理"**(如果"** 终结点管理"**Endpoint Manager"全部** 显示") 
- 在管理 **Microsoft Endpoint Manager，** 转到"**设备** >  > Windows **Windows注册** > **"**。
- 验证 MDM 用户作用域是否已启用。

    1. 若要注册所有计算机，请设置为"全部"，以在用户向计算机中添加工作帐户时自动注册加入到 Azure AD 和新计算机的Windows。
    2. 设置为 **"某些** "以注册特定组用户的计算机。
        -  将同步到安全组Azure AD域[用户](../create-groups/create-groups.md)。
        -  选择 **"选择组** "以启用该安全组的 MDM 用户作用域。

## <a name="4-create-the-required-resources"></a>4. 创建所需的资源 

使用 [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 模块中的 [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet 简化了配置混合 Azure AD 联接所需的任务。[](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) 调用此 cmdlet 时，它将创建和配置所需的服务连接点和组策略。

可以通过从 PowerShell 实例调用以下内容来安装此模块：

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> 建议您在运行 Azure AD 连接 的 Windows 服务器上安装此Azure AD 连接。

若要创建所需的服务连接点和组策略，将调用  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet。 执行此任务时Microsoft 365 商业高级版全局管理员凭据。 准备好创建资源时，请调用以下内容：

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

第一个命令将建立与 Microsoft 云的连接，当系统提示时，Microsoft 365 商业高级版全局管理员凭据。

## <a name="5-link-the-group-policy"></a>5. 链接组策略

1. 在组策略管理控制台 (GPMC) 中，右键单击要链接策略的位置，然后从上下文菜单中选择"链接现有 *GPO* ..."。
2. 选择在以上步骤中创建的策略，然后单击"确定 **"**。

## <a name="get-the-latest-administrative-templates"></a>获取最新的管理模板

如果你看不到使用默认 Azure AD 凭据启用自动 **MDM** 注册的策略，这可能是因为你未为 Windows 10、版本 1803 或更高版本安装 ADMX。 若要解决此问题，请按照以下步骤操作 (注意：最新的 MDM.admx 与) ：

1. 下载：[2020 年 10 月更新 (.admx) Windows 10 2020 年 10 月 (模板](https://www.microsoft.com/download/102157)) 。
2. 在域控制器上安装程序包。
3. 根据管理模板版本导航到文件夹：**C：\Program Files (x86) \Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**。
4. 将 **上述路径中的** "策略定义"文件夹重命名为 **PolicyDefinitions**。
5. 将 **PolicyDefinitions** 文件夹复制到 SYSVOL 共享，默认位于 **C：\Windows\SYSVOL\domain\Policies**。
   - 如果计划将中央策略存储用于整个域，请在那里添加 PolicyDefinitions 的内容。
6. 如果您具有多个域控制器，请等待 SYSVOL 复制，以便策略可用。 此过程还适用于管理模板的任何未来版本。

此时，你应该能够看到策略"使用默认凭据启用 **自动 MDM 注册Azure AD可用**。

## <a name="related-content"></a>相关内容

[将域用户同步Microsoft 365](manage-domain-users.md) (文章) \
[在管理中心创建组 (](../create-groups/create-groups.md) 文章) \
[教程：Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains) (一) [Top 10 ways to secure Microsoft 365 for business plans](../security-and-compliance/secure-your-business-data.md)
