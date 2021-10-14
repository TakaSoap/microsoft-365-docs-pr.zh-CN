---
title: 将应用部署到设备
description: 有关在设备上添加和部署应用Microsoft 托管桌面的信息。
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、应用、业务线应用、LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 15b41681d94d8f33176d140ebc00cc74319e69ff
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "60334491"
---
# <a name="deploy-apps-to-devices"></a>将应用部署到设备
加入应用Microsoft 托管桌面包括向用户设备添加和部署应用。 使用应用门户Microsoft 托管桌面，可以添加和部署应用。 

整个过程如下所示：
1. [向Microsoft 托管桌面](#1)门户添加应用 - 这可以是现有业务线 (LOB) 应用，或你已与 Intune 适用于企业的 Microsoft Store同步的应用。 
2. [为Azure Active Directory (创建) AD 组](#2)- 你将使用这些组管理应用分配。
3. [将应用分配给用户](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>步骤 1：将应用添加到Microsoft 托管桌面门户
你可以添加[Win32 或Windows基于 MSI 的应用](#lob-apps)，或适用于企业的 Microsoft Store应用[Microsoft 托管桌面，](#msfb-apps)然后将它们部署到Microsoft 托管桌面设备。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>将基于 win32 Windows基于 MSI 的应用Microsoft 托管桌面

你可以向企业门户添加业务线 (LOB) 应用Microsoft 托管桌面应用。 有关在设备上安装的应用Microsoft 托管桌面的信息，请参阅Microsoft 托管桌面[要求](../service-description/mmd-app-requirements.md)。

在此过程中，选择要添加的应用程序类型，然后配置和上载应用程序源。 

**将 LOB 应用或Windows添加到Microsoft 托管桌面门户**

你可以登录到 Microsoft 托管桌面 门户，或登录到 Intune，然后搜索Microsoft 托管桌面。 我们将展示如何登录Microsoft 托管桌面门户。 

1.    登录到管理[Microsoft 托管桌面 。](https://aka.ms/mmdportal) 
2.    在 **"清单"** 下，选择 **"应用"。**
3.    在应用工作负载中 **，选择添加**。
4.    在 **"添加应用**"**中，** 选择"业务线应用"或 **Windows Win32 (应用) 。**
    - 如果你选择了 **业务线** 应用，请参阅向 Windows [](/intune/lob-apps-windows)业务线应用Microsoft Intune添加和配置业务线应用说明。
    - 如果你已选择 **Windows Win32** (应用) ，请参阅 [Win32](/intune/apps-win32-app-management)应用管理，了解添加和配置Windows说明。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>适用于企业的 Microsoft Store 应用
如果你尚未注册应用适用于企业的 Microsoft Store，可以在购买应用时注册。 拥有应用后，你可以将其与Microsoft 托管桌面。 

**从应用商店购买适用于企业的 Microsoft Store**

1. Sign in to[适用于企业的 Microsoft Store](https://businessstore.microsoft.com) with your 适用于企业的 Microsoft Store Admin account.
2. 选择 **"购买我的组"。**
3. 使用"搜索"查找你需要的应用，然后选择该应用。
4. 在产品详细信息上，选择 **"获取应用"。** Microsoft Store将应用添加到 **你的组织** 的产品。
    
**验证 Intune 和 适用于企业的 Microsoft Store之间的同步是否处于活动状态**
1. Sign in to[适用于企业的 Microsoft Store](https://businessstore.microsoft.com) with your 适用于企业的 Microsoft Store Admin account.
2. 选择"**管理"。**
3. 选择 **设置"，** 然后选择"分发 **"。**
4. 在 **"管理工具"** 下，验证 Intune 是否列出且状态为 **"活动"。**  
    
**强制在 Intune 和 适用于企业的 Microsoft Store**
1. 登录到管理[Microsoft Endpoint Manager中心](https://go.microsoft.com/fwlink/?linkid=2109431)。
2. 选择 **"租户**  >  **管理连接器和令牌**  >  **适用于企业的 Microsoft Store"。**
3. 选择 **启用** 以 **启用适用于企业的 Microsoft Store同步允许你使用 Intune 访问批量购买的应用。** 
4. 选择首选语言，**然后选择"同步**"，获取从 Intune Microsoft Store购买的应用。

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>步骤 2：创建Azure AD组

为每个应用Azure AD三个组。 此表概述了你需要的组 (可用、必需和卸载) 。 

应用分配类型 |    组使用    | 示例Azure AD名称
--- | --- | ---
可用 |  该应用将在应用或公司门户提供。 | MMD – *应用名称* – 可用
必需 |  应用安装在选定组的设备上。 | MMD – *应用名称* – 必需
卸载 |  从所选组的设备卸载应用。 | MMD – *应用名称* – 卸载

将用户添加到这些组，以便提供应用、安装应用，或者将应用从他们的 Microsoft 托管桌面 设备。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>步骤 3：将应用分配给用户

**将应用分配给用户**

1. 登录到管理[Microsoft 托管桌面 。](https://aka.ms/mmdportal)
2. 在"托管桌面"窗格中，选择"**应用"。**
3. 在"应用工作负载"中，选择要为其分配用户的应用，然后选择"**分配用户组"。**
4. 对于特定应用，选择分配类型 (可用、必需、卸载) 分配相应的组。
5. 在"分配应用"窗格中，选择"确定 **"。**


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用Microsoft 托管桌面

1. 访问 [管理员门户](access-admin-portal.md)。
1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)。
1. [注册后调整设置](conditional-access.md)。
1. 部署并分配 [Intune 公司门户](company-portal.md)。
1. [分配许可证](assign-licenses.md)。
1. 本文 (部署) 。
1. [设置设备](set-up-devices.md)。
1. 设置 [使用 Autopilot 和注册状态页的首次运行体验](esp-first-run.md)。
1. [启用用户支持功能](enable-support.md)。
1. [让用户做好使用设备的准备](get-started-devices.md)。
1. [开始使用应用控制](get-started-app-control.md)。


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
