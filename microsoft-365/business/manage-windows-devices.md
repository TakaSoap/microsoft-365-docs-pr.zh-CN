---
title: 启用要由 Microsoft 365 for business 管理的加入域的 Windows 10 设备
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 了解如何启用 Microsoft 365 以仅在几个步骤中保护本地的 Active Directory 加入 Windows 10 设备。
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564921"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>启用要由 Microsoft 365 商业高级版管理的加入域的 Windows 10 设备

如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业高级版设置为保护您的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。
若要设置此保护，可以实现**混合 AZURE AD 加入的设备**。 这些设备将加入本地 Active Directory 和 Azure Active Directory。

本视频介绍了有关如何针对最常见方案对此进行设置的步骤，在下面的步骤中也将对此进行详细介绍。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>在开始之前，请确保完成以下步骤：
- 使用 Azure AD Connect 将用户同步到 Azure AD。
- 完成 Azure AD Connect 组织单位（OU）同步。
- 确保您要同步的所有域用户都具有到 Microsoft 365 商业高级版的许可证。

有关步骤，请参阅[将域用户同步到 Microsoft](manage-domain-users.md) 。

## <a name="1-verify-mdm-authority-in-intune"></a>1. 在 Intune 中验证 MDM 证书颁发机构

转到 portal.azure.com，并在 Intune 页面的顶部搜索。
在 "Microsoft Intune" 页面上，选择 "**设备注册**"，并在 "**概述**" 页上确保**MDM 颁发机构**是**Intune**。

- 如果**mdm 机构**为 "**无**"，请单击**mdm 机构**将其设置为**Intune**。
- 如果**mdm 颁发机构**是**Microsoft office 365**，请转到 "**设备**  >  **注册设备**"，并使用右侧的 "**添加 mdm 颁发机构**" 对话框添加**Intune MDM**颁发机构（仅当**MDM 机构**设置为 Microsoft Office 365 时，"**添加 MDM 颁发机构**" 对话框才可用）。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. 验证 Azure AD 是否已启用加入计算机

- 转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，在**管理中心**列表中，选择 "azure active Directory （如果 Azure active directory 不可见）" 列表中的 " **azure active directory** "。 
- 在**Azure Active directory 管理中心**中，转到 " **azure active directory** "，选择 "**设备**"，然后选择 "**设备设置**"。
- 验证**用户是否可以将设备加入 AZURE AD**已启用 
    1. 若要启用所有用户，请设置为**all**。
    2. 若要启用特定用户，请将设置为 "已**选择**" 以启用特定用户组。
        - 将 Azure AD 中同步的所需域用户添加到[安全组](../admin/create-groups/create-groups.md)。
        - 选择 "**选择组**" 以为该安全组启用 MDM 用户作用域。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. 验证 Azure AD 是否已启用 MDM

- 转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然后选择 "选择**终结点 Managemen**t" （如果**终结点管理器**不可见，请选择 "**全部显示**"）
- 在**Microsoft 终结点管理器管理中心**，转到 "**设备**  >  **windows**  >  **windows 注册**  >  **自动注册**"。
- 验证 MDM 用户作用域是否已启用。

    1. 若要注册所有计算机，设置为**all** ，以便在用户向 Windows 添加工作帐户时自动注册加入 Azure AD 和新计算机的所有用户计算机。
    2. 设置为**Some**以注册特定用户组的计算机。
        -  将 Azure AD 中同步的所需域用户添加到[安全组](../admin/create-groups/create-groups.md)。
        -  选择 "**选择组**" 以为该安全组启用 MDM 用户作用域。

## <a name="4-set-up-service-connection-point-scp"></a>4. 设置服务连接点（SCP）

可通过[配置混合 AZURE AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)简化这些步骤。 若要完成使用 Azure AD Connect 和 Microsoft 365 商业高级全局管理员和 Active Directory 管理员密码所需的步骤。

1.  启动 Azure AD Connect，然后选择 "**配置**"。
2.  在 "**其他任务**" 页上，选择 "**配置设备选项**"，然后选择 "**下一步**"。
3.  在 "**概述**" 页上，选择 "**下一步**"。
4.  在 "**连接到 AZURE AD** " 页上，输入 Microsoft 365 商业高级版全局管理员的凭据。
5.  在 "**设备选项**" 页上，选择 "**配置混合 Azure AD 加入**"，然后选择 "**下一步**"。
6.  在 " **SCP** " 页面上，对于您希望 Azure AD CONNECT 配置 SCP 的每个林，请完成以下步骤，然后选择 "**下一步**"：
    - 选中林名称旁边的框。 林应为你的 AD 域名称。
    - 在 "**身份验证服务**" 列下，打开下拉列表并选择匹配的域名（只能有一个选项）。
    - 选择 "**添加**" 以输入域管理员凭据。  
7.  在 "**设备操作系统**" 页面上，选择 "Windows 10 或更高版本仅加入域" 设备。
8.  在 "**准备配置**" 页上，选择 "**配置**"。
9.  在 "**配置完成**" 页上，选择 "**退出**"。


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a>5. 为 Intune 注册创建 GPO – ADMX 方法

改用.ADMX 模板文件。

1.  登录到 AD server、搜索和打开**服务器管理器**  >  **工具**  >  **组策略管理**。
2.  选择 "**域**" 下的域名，然后右键单击 "**组策略对象**" 以选择 "**新建**"。
3.  为新 GPO 指定名称，例如 "*Cloud_Enrollment*"，然后选择 **"确定**"。
4.  右键单击 "**组策略对象**" 下的新 GPO，然后选择 "**编辑**"。
5.  在**组策略管理编辑器**中，转到 "**计算机配置**  >  **策略**"  >  **管理模板**  >  **Windows 组件**  >  **MDM**。
6. 右键单击 "**使用默认 Azure AD 凭据启用自动 MDM 注册**"，然后选择 "**启用**  >  **" "确定"**。 关闭编辑器窗口。

> [!IMPORTANT]
> 如果您没有看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**，请参阅[获取最新的管理模板](#get-the-latest-administrative-templates)。

## <a name="6-deploy-the-group-policy"></a>6. 部署组策略

1.  在服务器管理器的 "**域**> 组策略对象" 下，选择上面步骤3中的 GPO，例如 "Cloud_Enrollment"。
2.  为 GPO 选择 "**作用域**" 选项卡。
3.  在 GPO 的 "作用域" 选项卡中，右键单击 "**链接**" 下的域链接。
4.  选择 "**强制**" 以部署 GPO，然后在确认屏幕中单击 **"确定"** 。

## <a name="get-the-latest-administrative-templates"></a>获取最新的管理模板

如果您没有看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**，可能是因为您没有为 Windows 10 版本1803、版本1809或版本1903安装 ADMX。 若要解决此问题，请执行以下步骤（注意：最新的 MDM 将向后兼容）：

1.  下载：[适用于 Windows 10 的管理模板（admx）可能为2019更新（1903）](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)。
2.  在主域控制器（PDC）上安装程序包。
3.  导航，具体取决于文件夹的版本： **C:\Program Files （x86） \Microsoft Group Policy\Windows 10 5 月 2019 Update （1903） v3**。
4.  将上述路径中的 "**策略定义**" 文件夹重命名为**PolicyDefinitions**。
5.  将**PolicyDefinitions**文件夹复制到**C:\Windows\SYSVOL\domain\Policies**。 
    -   如果计划将中央策略存储用于整个域，请在那里添加 PolicyDefinitions 的内容。
6.  重新启动主域控制器，以使策略可用。 此过程也适用于将来的任何版本。

此时，您应该能够看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**。

