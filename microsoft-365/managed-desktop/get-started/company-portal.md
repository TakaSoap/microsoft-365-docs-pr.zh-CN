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
ms.openlocfilehash: 2686ec818fd2c4c912e12df76bf35f2435e2625cf95b53f1bd5a24be4f93c1e8
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53898679"
---
# <a name="install-intune-company-portal-on-devices"></a>在Intune 公司门户安装设备

Microsoft 托管桌面要求 IT 管理员使用 Intune 公司门户 为用户安装Microsoft 托管桌面服务器。 以下是组织的一些好处：
- 用户有一个浏览和安装可用应用程序的位置。 
- IT 管理员可以按用户类别组织应用程序。  
- 某些应用程序 (如 Microsoft Project 和 Microsoft Visio) 公司门户部署需要Microsoft 托管桌面。
- IT 管理员可以为公司门户自定义自定义策略。 这包括品牌映像、添加本地支持联系人等。 有关详细信息，请参阅[如何配置Microsoft Intune 公司门户应用](/intune/company-portal-app)。   

本主题记录向用户Intune 公司门户部署Microsoft 托管桌面过程。 整个过程如下所示：
1. 从 公司门户 购买适用于企业的 Microsoft Store并同步到 Intune
2. 将公司门户分配给用户
3. 向用户传达更改

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>步骤 1 - 从 公司门户购买适用于企业的 Microsoft Store并同步到 Intune
若要了解如何购买应用和与 Intune 同步，请参阅将应用部署到适用于企业的 Microsoft Store设备 [中的](deploy-apps.md#msfb-apps)Microsoft 托管桌面 *应用*。

本主题提供如何： 
- 从公司门户购买适用于企业的 Microsoft Store 
- 强制在 Intune 和 适用于企业的 Microsoft Store
- 验证 Intune 和 Intune 之间的活动适用于企业的 Microsoft Store 

## <a name="step-2---assign-company-portal-to-your-users"></a>步骤 2 - 公司门户分配给用户
注册 Microsoft 托管桌面 后，公司门户自动将应用部署到租户，Microsoft 托管桌面设备上安装应用。

## <a name="step-3---communicate-change-to-your-users"></a>步骤 3 - 将更改传达给用户
作为组织的 IT 管理员，让用户了解如何在组织中使用 公司门户很重要。 Microsoft 托管桌面建议：
- 从应用程序安装应用程序公司门户。 有关详细信息，请参阅在设备上 [安装和共享应用](/intune-user-help/install-apps-cpapp-windows)。
- 如何向 IT 管理员发送当前不可用的应用程序的请求。 有关详细信息，请参阅请求 [工作或学校应用](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用 Microsoft 托管桌面

1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)
2. [调整条件访问](conditional-access.md)
3. [分配许可证](assign-licenses.md)
4. 部署Intune 公司门户 (本主题) 
5. [启用企业状态漫游](enterprise-state-roaming.md)
6. [设置设备](set-up-devices.md)
7. [让用户做好使用设备的准备](get-started-devices.md)
8. [部署应用](deploy-apps.md)
