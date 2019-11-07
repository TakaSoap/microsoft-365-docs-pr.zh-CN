---
title: 将应用程序部署到设备
description: 将应用添加到 Microsoft 托管桌面设备并将其部署到的信息。
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、应用程序、业务线应用程序、LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5f1e2bd2440b5c38c958d3182684e87643f2e853
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012023"
---
# <a name="deploy-apps-to-devices"></a>将应用程序部署到设备
Microsoft 托管桌面的加入部分包括向用户设备添加应用程序并将其部署到用户设备。 在使用 Microsoft 托管桌面门户后，可以添加和部署应用。 

整个过程如下所示：
1. [向 Microsoft 托管桌面门户添加应用](#1)程序-它可以是现有业务线（LOB）应用程序，也可以是 microsoft Store for business 中已与 Intune 同步的应用。 
2. [为应用分配创建 Azure Active Directory （AD）组](#2)-你将使用这些组来管理应用分配。
3. [将应用程序分配给用户](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>步骤1：向 Microsoft 托管桌面门户添加应用程序
你可以将[Win32 （或基于 WINDOWS MSI 的应用](#lob-apps)）或[Microsoft Store for Business 应用](#msfb-apps)添加到 microsoft 托管桌面，然后将其部署到 microsoft 托管桌面设备。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Microsoft 托管桌面的基于 Win32 或 Windows MSI 的应用程序

你可以将业务线（LOB）应用添加到 Microsoft 托管桌面门户。 有关安装在 Microsoft 托管桌面设备上的应用程序的要求的信息，请参阅[Microsoft 托管桌面应用程序要求](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)。

在此过程中，您将选择要添加的应用程序类型，然后配置和上载应用程序源。 

**将 LOB 应用程序或 Windows 应用添加到 Microsoft 托管桌面门户**

你可以登录到 Microsoft 托管桌面门户，或登录到 Intune，然后搜索 Microsoft 托管桌面。 我们将显示登录到 Microsoft 托管桌面门户。 

1.  登录到[Microsoft 托管桌面管理门户](https://aka.ms/mmdportal)。 
2.  在 "**清单**" 下，选择 "**应用**"。
3.  在 "应用工作负荷" 中，选择 "**添加**"。
4.  在 "**添加应用程序**" 中，选择 "**业务线应用程序**" 或 " **Windows 应用程序（Win32）**"。
    - 如果选择了 "**业务线应用程序**"，请参阅[向 Microsoft Intune 添加 Windows 业务线应用程序](https://docs.microsoft.com/intune/lob-apps-windows)，以了解有关添加和配置业务线应用程序的说明。
    - 如果选择了 " **windows 应用程序（Win32）**"，请参阅[Win32 应用程序管理](https://docs.microsoft.com/intune/apps-win32-app-management)以了解有关添加和配置 Windows 应用的说明。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store for Business 应用
如果你尚未注册 Microsoft Store for Business，你可以在购买应用时进行注册。 拥有你的应用程序后，可以使用 Microsoft 托管桌面同步这些应用。 

**从适用于企业的 Microsoft Store 购买应用程序**

1. 使用 Microsoft Store for Business Administration account 登录[Microsoft store For business](https://businessstore.microsoft.com) 。
2. 选择 **"为我的组购买"**。
3. 使用 "搜索" 查找所需的应用程序，并选择该应用程序。
4. 在 "产品详细信息" 中，选择 **"获取应用程序**"。 Microsoft Store 将应用程序添加到组织的**产品 & 服务**。

**在 Intune 和 Microsoft Store for Business 之间强制进行同步**
1. 以 Intune 管理员身份登录到[Azure 门户](https://portal.azure.com/)或为你的租户登录全局管理员
2. 选择 "**所有服务" > Intune**。 Intune 位于 "监控 + 管理" 部分。
3. 在 Intune 窗格中，选择 "**客户端应用程序**"，然后选择 " **Microsoft Store for Business**"。
4. 选择 "**启用**" 以使用 Intune 同步 Microsoft Store for Business 应用。
    - 如果尚未安装，请使用 Intune 注册并关联 Microsoft Store for Business 帐户
    - 选择在 Intune 控制台中显示 Microsoft Store for Business 中的应用程序将在其中显示的语言
    - 选择 "**同步**" 以使用 Intune 同步 Microsoft Store for Business 应用。
    - 验证 Microsoft Store for Business 和 Intune 之间的同步是否处于活动状态（下一步）。 

**验证 Intune 与 Microsoft Store for Business 之间的同步是否处于活动状态**
1. 使用 Microsoft Store for Business Administration account 登录[Microsoft store For business](https://businessstore.microsoft.com) 。
2. 选择 "**管理**"。
3. 选择 "**设置**"，然后选择 "**分发**"。
4. 在 "**管理工具**" 下，验证是否列出了 Intune 以及状态是否为 "**活动**"。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>步骤2：创建 Azure AD 组

为每个应用程序创建三个 Azure AD 组。 此表概述了您需要的组（可用、必需和卸载）。 

应用程序分配类型 |   组使用   | 示例 Azure AD 名称
--- | --- | ---
可用 |  该应用程序将从公司门户应用程序或网站提供。 | MMD –*应用程序名称*–可用
必需 |  应用程序安装在所选组中的设备上。 | MMD –*应用程序名称*–必需
Uninstall |  将从所选组中的设备中卸载应用程序。 | MMD –*应用程序名称*–卸载

将您的用户添加到这些组，以使应用程序 availabe、安装应用程序或从其 Microsoft 托管桌面设备中删除该应用程序。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>步骤3：将应用程序分配给用户

**将应用程序分配给用户**

1. 登录到[Microsoft 托管桌面管理门户](https://aka.ms/mmdportal)。
2. 在 "托管桌面" 窗格中，选择 "**应用程序**"。
3. 在 "应用程序工作负荷" 中，选择要向其分配用户的应用，然后选择 "**分配用户组**"。
4. 对于特定应用程序，选择 "分配类型" （可用、必需、卸载）并分配适当的组。
5. 在 "分配应用程序" 窗格中，选择 **"确定"**。


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft 托管桌面入门步骤

1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)
2. [调整条件访问](conditional-access.md)
3. [分配许可证](assign-licenses.md)
4. [部署 Intune 公司门户](company-portal.md)
5. [启用企业状态漫游](enterprise-state-roaming.md)
6. [设置设备](set-up-devices.md)
7. [让用户做好使用设备的准备](get-started-devices.md)
8. 部署应用程序（本主题）


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
