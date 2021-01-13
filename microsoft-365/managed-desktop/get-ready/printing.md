---
title: 为 Microsoft 托管桌面准备打印资源
description: 确保打印工作顺畅的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: b6e809505fed8b1f84eb502dc08751ad1f0b587c
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841395"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备打印资源

当你准备好注册 Microsoft 托管桌面时，你应该评估打印要求并确定适合你的环境的方法。 有三个选项：
 
- 部署 Microsoft 通用打印解决方案，使 Microsoft 托管桌面设备可以轻松发现打印机。 有关详细信息，请参阅 [什么是通用打印](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)。
- 使用自定义 PowerShell 脚本直接部署打印机。 按照"设置本地打印机 ["部分中的步骤](#set-up-local-printers) 操作。
- 使用与加入 Azure Active Directory 域的 Windows 10 设备兼容的非 Microsoft 云打印解决方案。 解决方案必须满足 Microsoft 托管桌面的软件要求。 有关详细信息，请参阅 [Microsoft 托管桌面应用要求](../service-description/mmd-app-requirements.md)。
 
在所有情况下，如果打印机驱动程序在 Microsoft 更新或 Microsoft Store 中不可用，你必须自己获取它们，然后将它们打包，以使用 Microsoft Intune 部署到 Microsoft 托管桌面设备。 有关详细信息，请参阅 [Intune 独立版 - Win32 应用管理](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>设置本地打印机

如果决定使用自定义 PowerShell 脚本部署打印机，并且已准备打印资源，请按照以下步骤部署共享打印机：

1.  导航到 Microsoft 托管桌面门户。
2.  在管理 *门户的"* 支持和支持>部分提交标记为"打印机部署"的请求，并提供以下详细信息：
    - 需要为 Microsoft 托管桌面设备部署的所有 UNC 路径到共享打印机位置
    - 需要访问这些共享打印机的用户组
3.  使用管理门户，我们将告知你请求完成时间。 最初，我们将仅将配置部署到"测试"部署组的设备。
4.  必须测试并确认配置是否如预期工作。 使用支持请求 **中的** "讨论"选项卡进行回复，以告知我们完成测试时间。
5.  然后，我们将配置部署到其他部署组。
