---
title: 在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio
description: Microsoft 托管桌面设备上有关安装 Microsoft Project 或 Microsoft Visio 的信息
keywords: Microsoft 托管桌面，Microsoft 365，microsoft Project，Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 30374e603350ecf9d5e5542263f004a22ccb0a67
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981703"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio

Microsoft Project 和 Microsoft Visio 要求在 Microsoft 托管桌面设备上安装特定步骤。 本主题介绍了这些应用程序的先决条件和安装过程。

## <a name="prerequisites"></a>先决条件

管理员应验证它们是否符合以下先决条件：
- **许可证数量**-您的用户必须能够使用的 microsoft Project 和 microsoft Visio 许可证的正确数量。 Microsoft 托管桌面目前仅支持这些应用程序的64位版本。 
- **许可证名称**-这些应用程序的相应许可证名称为：
    - **Microsoft project** -Project online Professional 或 Project Online 高级版
    - **Microsoft visio** -Visio Online 计划2
- **公司门户**-公司门户必须在你的租户中可用，你的用户才能安装这些应用程序。 如果公司门户未部署在你的租户中，请参阅[公司门户](company-portal.md)。

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>部署 Microsoft 托管桌面设备的 Project 和 Visio
提交你的支持请求后，Microsoft 托管桌面将通过 Microsoft Intune 创建三个 Azure AD 组和三个应用程序部署，以将应用程序部署到你的租户。  

**部署 Project 和 Visio**
1. **File a 支持请求**IT 管理员需要将支持请求文件，以使这些应用程序可供其用户使用。 有关联系 Microsoft 托管桌面的信息，请参阅[Microsoft 托管桌面的管理员支持](../working-with-managed-desktop/admin-support.md)。
2. **将用户分配给新的 AZURE AD 组**Microsoft 托管桌面将在你的租户和3个对应的应用程序部署中创建3个 Azure AD 组。 IT 管理员需要将用户分配给适当的组。

>[!NOTE]
>仅将用户分配给这些 Azure AD 组中的一个。 

Azure AD 组名称 | 要分配哪些用户？   
 --- | ---
新式办公-Project_Install | 仅需要项目的用户
新式办公-Visio_Install | 仅需要 Visio 的用户
新式办公-Visio_Project_Install | 需要 Project 和 Visio 的用户

一旦分配给这些组，应用程序将在公司门户中可用。 同步可能需要几分钟时间，但随后你的用户可以从公司门户安装应用程序。 

## <a name="communicate-changes"></a>传达更改
IT 管理员必须让用户知道如何安装 Project 和 Visio，这一点非常重要。 具体包括： 
- 当用户可使用这些应用程序时通知用户。 
- 有关如何从公司门户安装这些应用程序的说明。

>[!NOTE]
>用户必须先关闭所有 Office 应用程序，然后才能从公司门户安装 Microsoft Project 或 Microsoft Visio。 
