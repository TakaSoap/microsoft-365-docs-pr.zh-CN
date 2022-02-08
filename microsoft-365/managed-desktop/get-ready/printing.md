---
title: 为 Microsoft 托管桌面准备打印资源
description: 确保打印工作平稳的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: a66075637a15eb39eda38e318070af2bcbdc8fe6
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444517"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备打印资源

当你准备好注册打印Microsoft 托管桌面，你应该评估打印要求并确定适合你的环境的方法。 有三个选项：

| 选项 | 说明 |
| ------ | ------ |
| 部署 Microsoft 通用打印解决方案 | Microsoft 通用打印解决方案使设备Microsoft 托管桌面发现打印机。 有关详细信息，请参阅什么是 [通用打印](/universal-print/fundamentals/universal-print-whatis)。 |
| 使用自定义 PowerShell 脚本直接部署打印机 | 按照设置本地打印机 [部分中的步骤](#set-up-local-printers) 操作。 |
| 使用非 Microsoft 云打印解决方案 | 使用非 Microsoft 云打印解决方案，该解决方案与 Windows 10 设备兼容并加入 Azure Active Directory 域。 解决方案必须满足软件要求，Microsoft 托管桌面。 有关详细信息，请参阅Microsoft 托管桌面[应用要求](../service-description/mmd-app-requirements.md)。 |

在以上所有选项中，如果打印机驱动程序在 Microsoft 更新或 Microsoft Store 中不可用，则必须自己获取它们，并打包它们以使用 Microsoft Intune 将其部署到 Microsoft 托管桌面 设备。 有关详细信息，请参阅 [Intune 独立 - Win32 应用管理](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>设置本地打印机

以下说明假定你已准备打印资源，并决定使用自定义 PowerShell 脚本部署打印机。

**若要使用自定义 PowerShell 脚本部署打印机：**

1. 导航到Microsoft 托管桌面门户。
1. 在管理 *门户的"* 支持> **支持请求"部分提交** 标记为"打印机部署"的请求。
1. 提供以下详细信息：
    - 需要为设备部署的所有共享打印机位置的 UNC Microsoft 托管桌面路径。
    - 需要访问这些共享打印机的用户组。
1. 使用管理门户，我们将告知你请求完成时间。 最初，我们将仅将配置部署到测试部署组的设备。
1. 测试并确认配置是否如预期工作。
1. 使用支持 **请求中的** "讨论"选项卡进行回复，以告知我们完成测试时间。
1. 然后，我们将配置部署到其他部署组。

## <a name="steps-to-get-ready"></a>准备步骤

1. 查看 [托管桌面应用](prerequisites.md)。
1. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看 [来宾帐户的先决条件](guest-accounts.md)。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. [准备用户对数据的访问权限](authentication.md)。
1. [准备应用](apps.md)。
1. [准备映射的驱动器](mapped-drives.md)。
1. 准备本文 (打印) 。
1. 地址 [设备名称](address-device-names.md)。
