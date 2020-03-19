---
title: 准备打印 Microsoft 托管桌面的资源
description: 确保打印顺利进行的重要步骤
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a90d104915ecdd31d9ac35a6393fba74a3816ea8
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826424"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>准备打印 Microsoft 托管桌面的资源

在准备好在 Microsoft 托管桌面中注册时，应评估打印要求并为您的环境确定正确的方法。 有三个选项：
 
- 部署 Microsoft 混合云打印解决方案，使 Microsoft 托管桌面设备能够更轻松地发现打印机。 有关详细信息，请参阅[Deploy Windows Server 混合云打印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。
- 使用自定义 PowerShell 脚本直接部署打印机。 按照 "[设置本地打印机](#set-up-local-printers)" 部分中的步骤执行此操作。
- 使用与加入 Azure Active Directory 域的 Windows 10 设备兼容的非 Microsoft 云打印解决方案。 解决方案必须满足 Microsoft 托管桌面的软件要求。 有关详细信息，请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)。
 
在所有情况下，如果无法从 Microsoft Update 或 Microsoft Store 中获取打印机驱动程序，则必须自己获取这些驱动程序，并使用 Microsoft Intune 将其打包以部署到 Microsoft 托管桌面设备。 有关详细信息，请参阅[Intune 独立-Win32 应用管理](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>设置本地打印机

如果您已决定使用自定义 PowerShell 脚本部署打印机并准备好打印资源，请按照以下步骤部署共享打印机：

1.  导航到 Microsoft 托管桌面门户。
2.  在管理门户的 "**支持 > 支持请求**" 部分中的 "提交标记为*打印机部署*的请求" 中，提供以下详细信息：
    - 将需要为 Microsoft 托管桌面设备部署的共享打印机位置的所有 UNC 路径
    - 需要访问这些共享打印机的用户组
3.  使用管理门户，我们会在请求完成时通知你。 最初，我们仅将配置部署到测试部署组中的设备。
4.  您必须测试和确认配置是否按预期运行。 使用支持请求中的 "**讨论**" 选项卡进行答复，让我们知道您何时完成测试。
5.  然后，我们将配置部署到其他部署组。
