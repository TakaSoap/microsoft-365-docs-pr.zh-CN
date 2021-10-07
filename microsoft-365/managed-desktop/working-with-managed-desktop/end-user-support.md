---
title: 获取用户对 Microsoft 托管桌面
description: 用户如何获取有关服务和设备的帮助
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1e7d616f9644c7f81e4a0abf55e2d33d54016c55
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150302"
---
# <a name="getting-help-for-users"></a>获取针对用户的帮助

如果已达到工作流中需要请求提升的设备访问权限或[](../service-description/user-support.md)向 Microsoft 升级的点，请按照以下步骤操作：
 
>[!NOTE]
>这些支持选项不适用于"测试"组中设备。

## <a name="elevation-requests"></a>提升请求

在请求提升对设备的访问权限之前，最好查看最适合的操作。

- **典型** 操作是此过程的目的，在解决设备问题时，将定期Microsoft 托管桌面操作。 示例包括：
    - 提升内置系统疑难解答程序、命令提示符或Windows PowerShell
    - 业务线应用程序疑难解答
    - 使用解决方法更正应按设计 (某些内容，例如 BitLocker 激活或系统时间不更新) 
    - 提升设备管理器以执行更新驱动程序、卸载设备或扫描新更改等操作

- **不建议的操作** 包括：
    - 安装软件或浏览器
    - 在外部安装驱动程序Windows设置，包括用于外围设备的驱动程序
    - 安装.msi或.exe文件
    - 安装Windows功能

- **不支持的操作** 包括：
    - 安装与安全或管理功能Microsoft 托管桌面或操作相冲突的软件或功能
    - 禁用Windows所需的功能，Microsoft 托管桌面 BitLocker
    - 修改组织管理的设置

### <a name="to-request-elevation"></a>请求提升

1. 转到 的门户 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) ，然后使用你的 Azure Active Directory 凭据登录。
2. 选择 **"新建提升请求"。**
3. 提供以下详细信息：
    - **从你自己的** 支持票证系统支持票证 ID。
    - **设备名称**：输入设备序列号，然后从菜单中选择设备。
    - **类别**：选择最适合你的问题的类别。 如果没有选项看起来接近，请选择"其他 **"。** 最好尽可能选择类别。
    - **子类别**：选择最适合该问题的类别。 如果没有选项看起来接近，请选择"其他 **"。**
    - **标题**：提供设备上问题的简短说明。
    - **计划行动**：提供授予提升权限后计划要采取疑难解答步骤。 
4. 选择“**提交**”。


## <a name="escalation-requests"></a>升级请求


如果需要将 [问题上报](../service-description/user-support.md#escalation-portal) 给 Microsoft，请按照以下步骤操作：

1. 转到 的门户 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) ，然后使用你的 Azure Active Directory 凭据登录。
2. 选择 **"升级请求"，** 然后选择"**新建升级请求"。**
3. 提供以下详细信息：
    - **类别**：选择最适合你的问题的类别。
    - **标题**：提供一个非常简短的说明。
    - **说明**：添加可帮助团队了解此问题的其他任何详细信息。 如果需要附加文件，可以在提交后返回请求以完成这一操作。
    - **主要联系人信息**：提供有关如何联系负责与团队合作的主要人员的信息。
4. 选择“**提交**”。
5. 重新访问同一门户中的票证，以与团队进行交互。

> [!NOTE]
> 只有严重性 C 问题可以通过此路径进行升级。 对于其他问题，请与 IT 管理员联系，以通过管理门户提出请求。
