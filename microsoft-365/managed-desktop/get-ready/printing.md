---
title: 为 Microsoft 托管桌面准备打印资源
description: 确保打印工作平稳的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 3f77074aa11e9dc82c8fac9763fdebfd2fc49d99
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287205"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备打印资源

当你准备好注册Microsoft 托管桌面，你应该评估打印要求并确定适合你的环境的方法。 有三个选项：

- 部署 Microsoft 通用打印解决方案，使设备Microsoft 托管桌面发现打印机。 有关详细信息，请参阅 [什么是通用打印](/universal-print/fundamentals/universal-print-whatis)。
- 使用自定义 PowerShell 脚本直接部署打印机。 按照设置本地打印机 [部分中的步骤](#set-up-local-printers) 操作。
- 使用与加入域的 Windows 10 兼容的非 Microsoft 云打印Azure Active Directory解决方案。 解决方案必须满足软件要求，Microsoft 托管桌面。 有关详细信息，请参阅应用[Microsoft 托管桌面要求](../service-description/mmd-app-requirements.md)。
 
在所有情况下，如果打印机驱动程序在 Microsoft 更新或 Microsoft Store 中不可用，你必须自己获取它们，然后将它们打包，以使用 Microsoft Intune 将其部署到 Microsoft 托管桌面 设备。 有关详细信息，请参阅 [Intune 独立 - Win32 应用管理](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>设置本地打印机

如果决定使用自定义 PowerShell 脚本部署打印机并准备打印资源，请按照以下步骤部署共享打印机：

1. 导航到Microsoft 托管桌面门户。
2. 在管理 *门户的"* 支持> **支持** 请求"部分提交标记为"打印机部署"的请求，并提供以下详细信息：
    - 需要为设备部署的所有共享打印机位置的 UNC Microsoft 托管桌面路径
    - 需要访问这些共享打印机的用户组
3. 使用管理门户，我们将告知你请求完成时间。 最初，我们将仅将配置部署到测试部署组的设备。
4. 必须测试并确认配置是否如预期工作。 使用支持 **请求中的** "讨论"选项卡进行回复，以在测试完成时告诉我们。
5. 然后，我们将配置部署到其他部署组。

## <a name="steps-to-get-ready"></a>准备步骤

1. Review [Prerequisites for Microsoft 托管桌面](prerequisites.md).
2. 使用 [准备情况评估工具](readiness-assessment-tool.md)。
3. [来宾帐户的先决条件](guest-accounts.md)
4. [Microsoft 托管桌面的网络配置](network.md)
5. [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)
6. [为 Microsoft 托管桌面准备本地资源访问权限](authentication.md)
7. [Microsoft 托管桌面中的应用](apps.md)
8. [为 Microsoft 托管桌面准备映射的驱动器](mapped-drives.md)
9. [准备打印资源Microsoft 托管桌面 (](printing.md)本文) 
