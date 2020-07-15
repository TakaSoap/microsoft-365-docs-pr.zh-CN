---
title: 在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio
description: Microsoft 托管桌面设备上有关安装 Microsoft Project 或 Microsoft Visio 的信息
keywords: Microsoft 托管桌面，Microsoft 365，microsoft Project，Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126823"
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
Microsoft 托管桌面将 Microsoft Project 和 Microsoft Visio 作为两个 Win32 应用程序添加到 Microsoft Intune 中。 我们还将在 Azure Active Directory 中创建两个组，这些组将被分配给具有 "可用" 的相应应用程序。 

**部署 Project 和 Visio**将该用户添加到相应的组中，并且该应用程序将在公司门户中变为可用。 同步可能需要几分钟时间，但随后你的用户可以从公司门户安装应用程序。 

Azure AD 组名称 | 要分配哪些用户？   
 --- | ---
新式工作区-办公室-Project_Install | 需要项目的用户
新式工作区-办公室-Visio_Install | 需要 Visio 的用户

## <a name="communicate-changes"></a>传达更改
IT 管理员必须让用户知道如何安装 Project 和 Visio，这一点非常重要。 这包括： 
- 当用户可使用这些应用程序时通知用户。 
- 有关如何从公司门户安装这些应用程序的说明。
