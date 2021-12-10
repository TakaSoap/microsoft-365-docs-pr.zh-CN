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
ms.openlocfilehash: d10f2e938e201fa25505abc820d05b03af04e543
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374408"
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
    - 使用解决方法更正应按设计正常运行 (如 BitLocker 激活或系统时间不更新) 
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

1. 登录到 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单。
2. 查找 **"Microsoft 托管桌面"** 部分，然后选择"**设备**"边栏选项卡，其中包含两个选项卡："设备"选项卡和"提升 **请求"** 选项卡。 
3. 若要在"设备"选项卡上创建新的提升请求，请选择要提升的单个设备，然后从"设备操作"下拉菜单中选择"请求提升"。 将显示新的提升请求飞入窗格，并预先填充该字段中的设备名称。
4. 或者，若要在"提升请求"选项卡上创建新的提升请求，请选择 **"+新建提升请求"。**
5. 提供以下详细信息：
    - **从你自己的** 支持票证系统支持票证 ID。
    - **设备名称** ("提升请求"选项卡创建请求时) ：输入设备序列号，然后从菜单中选择设备。 
    - **类别**：选择最适合你的问题的类别。 如果没有选项看起来接近，请选择"其他 **"。** 最好尽可能选择类别。
    - **标题**：提供设备上问题的简短说明。
    - **计划行动**：提供授予提升权限后计划要采取疑难解答步骤。 
6. 选择“**提交**”。
7. 可在提升请求选项卡上看到所有活动请求和已关闭 **请求的列表和** 详细信息。



## <a name="escalation-requests"></a>升级请求


如果需要将 [问题上报](../service-description/user-support.md#escalation-portal) 给 Microsoft，请按照以下步骤操作：

1. 登录到 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到"**租户管理"** 菜单。
2. 查找"Microsoft 托管桌面"部分，然后选择"**服务请求"。**
3. 在"**服务请求"** 边栏选项卡上，选择 **"+ 新建支持请求"。**
4. 在"标题"框中提供 **一个非常简短的** 说明。 然后将"请求 **类型"设置为****"事件"。** 
5. 选择 **最适合** 你的问题的 **类别** 和子类别，然后选择下一 **步**。
6. 在 **"详细信息** "部分，提供以下信息：
    - **说明**：添加可帮助团队了解此问题的其他任何详细信息。 如果需要附加文件，可以在提交后返回请求以完成这一操作。
    - **主要联系人信息**：提供有关如何联系负责与团队合作的主要人员的信息。
7. 选择 **"严重性"** 级别。 有关详细信息，请参阅支持请求严重性定义。
8. 尽可能提供有关请求的信息，以帮助团队快速响应。 根据请求的类型，您可能需要提供不同的详细信息。
9. 查看您提供的所有信息，以确保准确性。
10. 准备就绪后，选择 **“创建”**。
