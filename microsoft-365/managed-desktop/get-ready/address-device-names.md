---
title: 地址设备名称依赖关系
description: 删除对设备名称的依赖或请求异常
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 8642fd7c7c154359a31386fa5491932e19de7a43
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173135"
---
# <a name="address-device-name-dependency"></a>地址设备名称依赖关系

Microsoft 托管桌面注册设备时应用标准化名称格式，如果以后更改名称，将自动重命名设备。 有关详细信息，请参阅设备 [名称](../service-description/device-names.md)。

> [!IMPORTANT]
> 如果你的环境依赖于特定设备名称 (例如，为了支持特定的网络配置) ，你应该调查在注册到 Microsoft 托管桌面 之前删除该依赖关系的选项。 如果必须保留名称依赖项，可以通过管理门户提交请求以禁用重命名功能并使用[](../working-with-managed-desktop/admin-support.md)所需的名称格式。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
2. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看 [来宾帐户的先决条件](guest-accounts.md)。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. [准备用户对数据的访问权限](authentication.md)。
1. [准备应用](apps.md)。
1. [准备映射的驱动器](mapped-drives.md)。
1. [准备打印资源](printing.md)。
1. Address [device names (this article) .