---
title: 安装 Intune 公司门户 Microsoft 托管桌面设备
description: 有关在 Microsoft 托管桌面设备上安装公司门户应用程序的信息
keywords: Microsoft 托管桌面, Microsoft 365, 公司门户
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: a9ce2b2455b6036170636ac564c450676473ac48
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390699"
---
# <a name="install-intune-company-portal-on-microsoft-managed-desktop-devices"></a>在 Microsoft 托管桌面设备上安装 Intune 公司门户

Microsoft 托管桌面要求 IT 管理员使用 Microsoft 托管桌面设备为其用户安装 Intune 公司门户。 以下是贵组织的一些好处:
- 用户有一个位置来浏览和安装可用的应用程序。 
- IT 管理员可以按类别组织其用户的应用程序。  
- 有些应用程序 (如 Microsoft Project 和 Microsoft Visio) 要求公司门户部署 Microsoft 托管桌面。
- IT 管理员可以为其组织自定义公司门户。 这包括品牌图像、在本地支持联系人中添加等。 有关详细信息, 请参阅 how [To Configure The Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app)。   

本主题介绍了将 Intune 公司门户部署到 Microsoft 托管桌面用户的过程。 整个过程如下所示:
1. 从 Microsoft Store for Business 购买公司门户并与 Intune 同步
2. 为您的用户分配公司门户
3. 向用户传达更改

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>第1步-从 Microsoft Store for Business 购买公司门户并与 Intune 同步
有关如何购买应用并与 Intune 同步的信息, 请参阅将*应用程序部署到 Microsoft 托管桌面设备*中的[Microsoft Store for Business 应用](deploy-apps.md#msfb-apps)。

本主题提供了有关如何执行以下操作的信息: 
- 购买 Microsoft Store for Business 中的公司门户 
- 在 Intune 与 Microsoft Store for Business 之间强制同步
- 验证 Intune 与 Microsoft Store for Business 之间的主动同步 

## <a name="step-2---assign-company-portal-to-your-users"></a>步骤 2-将公司门户分配给用户
通过 Microsoft 托管桌面管理门户将支持请求提交到 Microsoft 托管桌面操作。 在支持请求中, 请求将公司门户分配给您的用户。 Microsoft 托管桌面会将公司门户部署到你的租户, 并将应用安装在组织中的 Microsoft 托管桌面设备上。

有关使用 Microsoft 托管桌面提交支持请求的详细信息, 请参阅[Microsoft 托管桌面的管理员支持](../working-with-managed-desktop/admin-support.md)。

## <a name="step-3---communicate-change-to-your-users"></a>第3步-将更改传达给用户
作为组织的 IT 管理员, 让你的用户知道如何在你的组织中使用公司门户, 这一点非常重要。 Microsoft 托管桌面建议:
- 从公司门户安装应用程序的步骤。 有关详细信息, 请参阅在[设备上安装和共享应用](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)。
- 如何向 IT 管理员发送对当前不可用的应用程序的请求。
