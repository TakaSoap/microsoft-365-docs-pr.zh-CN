---
title: 为 Microsoft 托管桌面准备应用程序
description: ''
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289059"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备应用程序

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
microsoft 和 microsoft 托管桌面客户在 microsoft 托管桌面中使用的应用程序同等重要, 但也是不同的责任。

## <a name="microsoft-responsibilities"></a>Microsoft 职责
**Office 365 应用程序**Microsoft 将提供针对特定 Office 365 应用程序的部署、更新和支持的完整服务。 所有用户都将收到 Office 365 的基本集。单击以运行, 64 位版本的应用程序包含在设备的图像中, 以便用户可以快速提高工作效率。 Office 365 套件中的项目和 Visio 应用程序是单独许可的。  Microsoft 托管桌面将提供部署组, 让 IT 管理员能够管理许可证并为其组织适当地部署这些应用程序。 microsoft 将通过 microsoft 托管桌面支持频道支持这些应用程序的最终用户。

**业务线应用程序**Microsoft 为 IT 管理员提供了工具, 以便将业务线 (LOB) 应用程序作为 Intune 产品的一部分管理和部署到最终用户。 Microsoft 将支持应用程序部署问题, 如[业务线应用程序](#line-of-business-applications)中所述 

**使用 Intune 部署**在 microsoft 托管桌面载入期间, Intune 将链接到**microsoft Store for Business** , 从而允许通过 Intune 部署已应用的应用。 microsoft 还会将 microsoft Store 中的公司门户应用程序部署到最终用户, 以便 IT 管理员可以为他们的最终用户提供自助服务体验。

**应用程序管理**Microsoft 可能会发现由于其系统影响而不适合新式工作场所的受限制应用程序。 如果标识了这样的应用程序, Microsoft 将会通知客户, 并且需要从租户中删除该应用程序。 

有关受限制的应用程序行为和应用要求的详细信息, 请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>客户责任
Office 365 套件是 microsoft 生产率产品的核心, 并包含在适用于所有 microsoft 托管桌面用户的 microsoft 365 许可证中。 虽然 microsoft 将 Office 应用程序部署、更新并支持到 microsoft 托管桌面设备, 但仍有一些客户负责这些方面。
- **分配许可证**-客户负责向最终用户分配适用于 Office 365 的许可证。 
- **将用户添加到安全组**-对于具有需要 Project 或 Visio 的用户的客户, IT 管理员必须将这些用户添加到相应的部署组。 IT 管理员还负责管理这些用户的生命周期的结束。 
- **部署 office 365 外接**程序-客户负责将任何插件部署到 Office 365 套件 (认为有必要)。 

由于业务线 (LOB) 应用程序对于每个客户都是唯一的, 因此客户负责管理其组织中的所有应用程序, 而不是由 Microsoft 部署的。 具体包括：
- 确定所需的应用程序以及需要它们的用户
- 将应用程序分配给这些用户
- 创建和维护用于管理应用程序分配的 Azure Active Directory (AD) 组 

客户必须将 LOB 应用上传到 Intune。 然后, 他们负责在各自的生命周期中部署、更新和解除这些应用程序, 并为其用户管理这些应用程序的支持。

## <a name="office-applications"></a>Office 应用程序
作为 microsoft 365 E5 许可证的一部分, Office 365 标准套件 (64 位) 由 microsoft 部署。 

有关详细信息, 请参阅[Microsoft 托管桌面技术](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>业务线应用程序
此表汇总了业务线 (LOB) 应用程序的各个阶段的责任。 

应用程序工作项 |    客户    | Microsoft
--- | --- | ---
**载入应用** |  |
确定目标用户组所需的应用程序   | ![是](images/checkmark.png)  |
创建和管理应用程序部署的 Azure AD 组 | ![是](images/checkmark.png) |   
**应用程序打包** |  |
程序包应用程序以满足 Intune 部署标准 |  ![是](images/checkmark.png) |  
将应用程序上载到 Intune | ![是](images/checkmark.png)     |
在 Microsoft 托管桌面环境中测试应用程序 |    ![是](images/checkmark.png) |  
使用最终用户测试应用程序    | ![是](images/checkmark.png) |    
**部署** | |
管理用户并将其分配给应用程序  | ![是](images/checkmark.png)  |
Intune 部署工具将应用程序传递到远程客户端| |   ![是](images/checkmark.png)
通过 Intune 识别和部署应用程序更新 | ![是](images/checkmark.png)    |
Unistall 和删除已停用的应用程序    | ![是](images/checkmark.png) |    
**管理** | |
购买和分配许可证 |   ![是](images/checkmark.png)     |
为业务线应用程序提供最终用户支持  | ![是](images/checkmark.png) |
远程管理应用程序设置    | ![是](images/checkmark.png) |

有关 LOB 应用程序要求的信息, 请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>Intune 应用程序部署
可以通过 Microsoft 托管桌面管理门户或 Intune 门户来处理应用程序管理。 Intune 的应用程序管理门户显示为 Windows、Android 和 iOS 部署的应用程序。 Microsoft 托管桌面管理门户将视图限制为 Windows 10 应用程序。 两者均可通过 Azure 门户获得。 
* [Intune 应用管理基础](https://docs.microsoft.com/intune/app-management)
* [向 Intune 添加应用程序](https://docs.microsoft.com/intune/app-management)
   * [添加业务线应用程序](https://docs.microsoft.com/intune/lob-apps-windows)
   * [将 Win32 应用程序添加到 Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [添加 web 应用程序](https://docs.microsoft.com/intune/web-app)
* [部署应用程序](https://docs.microsoft.com/intune/apps-deploy)
   * [将应用程序部署到 Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* 公司门户
   * [部署公司门户](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [配置公司门户应用程序](https://docs.microsoft.com/intune/company-portal-app)
