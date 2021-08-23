---
title: 在Intune 公司门户安装设备
description: 有关在设备上安装公司门户Microsoft 托管桌面的信息
keywords: Microsoft 托管桌面、Microsoft 365、公司门户
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 04b65c6abbdaa2233bdfb25a7f7af8644d60d435
ms.sourcegitcommit: 00a8a3376ea02770143af9a80cbe17a2b62636e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2021
ms.locfileid: "58364981"
---
# <a name="install-intune-company-portal-on-devices"></a>在Intune 公司门户安装设备

Microsoft 托管桌面 IT 管理员需要使用 Intune 公司门户 为用户安装 Microsoft 托管桌面 服务。 以下是组织的一些好处：
- 用户有一个浏览和安装可用应用程序的位置。 
- IT 管理员可以按用户类别组织应用程序。  
- 某些应用程序 (如 Microsoft Project 和 Microsoft Visio) 公司门户部署需要Microsoft 托管桌面。
- IT 管理员可以为公司门户自定义自定义策略。 这包括品牌映像、添加本地支持联系人等。 有关详细信息，请参阅[如何配置Microsoft Intune 公司门户应用](/intune/company-portal-app)。   

本主题介绍向用户Intune 公司门户部署Microsoft 托管桌面过程。 整个过程如下所示：
1. 从 公司门户购买适用于企业的 Microsoft Store并同步到 Intune
2. 将公司门户分配给用户
3. 向用户传达更改

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>步骤 1 - 从 公司门户购买适用于企业的 Microsoft Store并同步到 Intune
若要了解如何购买应用和与 Intune 同步，[请参阅将适用于企业的 Microsoft Store](deploy-apps.md#msfb-apps)部署到设备中的Microsoft 托管桌面 *应用*。

本主题提供如何： 
- 从公司门户购买适用于企业的 Microsoft Store 
- 强制在 Intune 和 适用于企业的 Microsoft Store
- 验证 Intune 和 Intune 之间的活动适用于企业的 Microsoft Store 

## <a name="step-2---assign-company-portal-to-your-users"></a>步骤 2 - 公司门户分配给用户
注册 Microsoft 托管桌面 后，公司门户部署到租户，并在你的组织的 Microsoft 托管桌面 设备上安装应用。

## <a name="step-3---communicate-change-to-your-users"></a>步骤 3 - 将更改传达给用户
作为组织的 IT 管理员，让用户了解如何在组织中使用 公司门户很重要。 Microsoft 托管桌面建议：
- 从应用程序安装应用程序公司门户。 有关详细信息，请参阅在设备上 [安装和共享应用](/intune-user-help/install-apps-cpapp-windows)。
- 如何向 IT 管理员发送当前不可用的应用程序的请求。 有关详细信息，请参阅请求 [工作或学校应用](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用 Microsoft 托管桌面

1. 访问 [管理门户](access-admin-portal.md)。
1. [在管理门户中添加并验证管理员联系人](add-admin-contacts.md)。
1. [注册后调整设置](conditional-access.md)。
1. 部署和分配Intune 公司门户 (本文) 。
1. [分配许可证](assign-licenses.md)。
1. [部署应用](deploy-apps.md)。
1. [设置设备](set-up-devices.md)
1. 设置 [Autopilot 和注册状态页面的首次运行体验](esp-first-run.md)。
1. [启用用户支持功能](enable-support.md)。
1. [让用户准备好使用设备](get-started-devices.md)。
1. [应用控件入门](get-started-app-control.md)。
