---
title: 应用程序准备 Microsoft 托管桌面
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: ebeb54bd5d1f50cbb6f78b1c8ad4a624c449b8c2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865602"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>应用程序准备 Microsoft 托管桌面

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Microsoft 和 Microsoft 托管桌面客户同样可以围绕用于 Microsoft 托管桌面应用程序的关键、 尚未不同责任。

## <a name="microsoft-responsibilites"></a>Microsoft 职责
**Office 365 应用程序**Microsoft 将提供完整的部署、 更新和支持的特定的 Office 365 应用程序服务。所有用户将都收到运行，以便用户可以迅速提高效率，包括在设备的图像的应用程序的 64 位版本的 Office 365 单击了基本集。项目和 Visio 中的应用程序的 Office 365 套件是单独授权。 Microsoft 托管桌面将提供部署组允许 IT 管理员管理许可证和部署这些适当地为其组织的应用程序。通过 Microsoft 托管桌面支持渠道这些应用程序的最终用户时，Microsoft 将提供支持。

**业务线应用程序**Microsoft 提供的面向 IT 管理员管理和作为 Intune 产品的一部分部署到最终用户其业务线应用程序的工具。Microsoft 将支持[业务线应用程序](#line-of-business-applications)中所述的应用程序部署问题 

**使用 Intune 部署**Intune 将链接到**Microsoft Store for Business**中，在 Microsoft 托管桌面入职培训允许已采购的应用程序通过 Intune 部署过程中。Microsoft 还会给最终用户部署的公司门户的基于 web 的版本，以便 IT 管理员可以为最终用户提供自助式体验。

**应用程序管理**Microsoft 可能确定受限制的应用程序，由于其系统影响不适合现代工作区。标识此类应用程序时 Microsoft 将通知客户，该应用程序将需要从租户中删除。 

## <a name="customer-responsibilities"></a>客户责任
Office 365 套件是 Microsoft 的工作效率产品的核心和包含的所有 Microsoft 托管桌面用户 Microsoft 365 许可证中。Microsoft 部署、 更新和支持 Microsoft 托管桌面设备的 Office 应用程序时仍有某些客户负责的区域。
- **分配许可证**的客户负责将相应的许可证分配给 Office 365 的最终用户。 
- **向安全组添加用户**-与用户客户需要项目或 Visio 的 IT 管理员必须这些将用户添加到适当的部署组。IT 管理员也是负责管理这些用户的生命周期结束。 
- **部署 Office 365 加载项**的客户负责部署到 Office 365 套件，这必要的任何插件。 

由于是唯一的每个客户的业务线 (LOB) 应用程序，客户负责管理未部署由 Microsoft 其组织内的所有应用程序。这包括：
- 确定所需的应用程序和用户需要它们
- 将应用程序分配给这些用户
- 创建和维护用于管理应用程序分配的 Azure Active Directory (AD) 组 

一旦被标识的 LOB 应用程序的核心集客户将采购、 许可、 打包、 和 Microsoft 托管桌面环境中测试这些应用程序。客户必须上载并部署到 Intune 以部署、 更新和停用其 LOB 应用程序的应用程序。客户负责管理 LOB 应用程序支持的用户。
 

## <a name="office-applications"></a>Office 应用程序
作为 Microsoft 365 E5 许可证的一部分，Microsoft 部署 Office 365 Standard Suite （64 位）。 

有关详细信息，请参阅[Microsoft 托管桌面技术](../intro/technologies.md)<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>业务线应用程序
此表总结了跨-的业务线 (LOB) 应用程序的不同阶段的责任。 

应用程序工作项 |    客户    | Microsoft
--- | --- | ---
**加入应用程序** |  |
确定应用程序所需的目标的用户组   | ![是](images/checkmark.png)  |
创建和管理应用程序部署 Azure AD 组 | ![是](images/checkmark.png) |   
**应用程序打包** |  |
包应用程序，以满足 Intune 部署标准 |  ![是](images/checkmark.png) |  
将应用程序上载到 Intune | ![是](images/checkmark.png)     |
在 Microsoft 托管桌面环境中测试应用程序 |    ![是](images/checkmark.png) |  
与最终用户的测试应用程序    | ![是](images/checkmark.png) |    
**Deployment** | |
管理，并将用户分配给应用程序  | ![是](images/checkmark.png)  |
Intune 部署工具提供向远程客户端应用程序| |   ![是](images/checkmark.png)
确定并部署应用程序通过 Intune 的更新 | ![是](images/checkmark.png)    |
卸载和删除应用程序，它们具有已停用时    | ![是](images/checkmark.png) |    
**管理** | |
采购和分配许可证 |   ![是](images/checkmark.png)     |
提供对业务线应用程序的最终用户支持  | ![是](images/checkmark.png) |
管理应用程序设置远程    | ![是](images/checkmark.png) |

LOB 应用程序要求的信息，请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)

## <a name="resources"></a>资源
超出范围 Microsoft 托管桌面操作的许多服务时有哪些 Microsoft 提供的可帮助客户管理自己的应用程序的服务。

### <a name="windows-upgrade-readiness"></a>Windows 升级准备
设置新的 Microsoft 托管的设备的关键部分了解设备用户所需的应用程序。Windows 升级准备是一个有助于企业理解其公司，内部应用程序环境并帮助他们如查看有关这些应用程序的关键数据的 Microsoft 工具：

- **应用程序使用率**的遥测数据用于监视应用程序使用率。
- **应用程序兼容性**的升级准备查看每个应用程序和看到如何广泛已部署在最新版本的 Windows 10 并评估如何确定它是否"准备 Windows"。此数据可帮助焦点测试不已广泛所采用的应用程序上的工作。

### <a name="intune-application-deployment"></a>Intune 应用程序部署
通过 Microsoft 托管桌面管理门户，或通过 Intune 门户，可以处理应用程序管理。Intune 的应用程序管理门户显示为 Windows、 Android 和 iOS 部署的应用程序。Microsoft 托管桌面管理门户限制到 Windows 10 应用程序的视图。二者都有通过 Azure 门户。 
- [Intune 应用程序管理基础知识](https://docs.microsoft.com/intune/app-management)
- [添加 Windows 32 应用程序](https://docs.microsoft.com/intune/lob-apps-windows)
- [添加 web 应用程序](https://docs.microsoft.com/intune/web-app)
- [分配并将应用程序部署到组](https://docs.microsoft.com/intune/apps-deploy)

### <a name="application-packaging-standards"></a>应用程序打包标准
部署 Windows 32 应用程序通过 Intune 它们必须打包为以下任意一个。MSI，.appx，或。MSIX。Intune 的最常见包类型是当前。MSI。
