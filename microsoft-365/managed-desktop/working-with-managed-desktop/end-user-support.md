---
title: 获取用户对 Microsoft 托管桌面
description: 用户如何获取有关服务和设备的帮助
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 48be29f8db689ddd0911d7512b267ba50c85a469
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322403"
---
# <a name="getting-help-for-users"></a>获取针对用户的帮助

如果已达到工作流中需要请求提升的设备访问权限或[](../service-description/user-support.md)向 Microsoft 升级的点，请按照以下步骤操作：

>[!NOTE]
>这些支持选项不适用于"测试"组中设备。

## <a name="elevation-requests"></a>提升请求

在请求提升对设备的访问权限之前，最好查看最适合的操作。

| 操作 | 示例 |
| ------ | ------ |
| **典型操作** 适用于提升请求过程。 在解决设备问题时，会Microsoft 托管桌面执行。 | <ul><li>提升内置系统疑难解答、命令提示符或Windows PowerShell业务线应用程序疑难解答。</li><li>使用解决方法更正应按设计正常运行 (如 BitLocker 激活或系统时间不更新) 。</li><li>提升设备管理器以执行更新驱动程序、卸载设备或扫描新更改等操作。</li></ul>
| **不推荐的操作** | <ul><li>安装软件或浏览器。</li><li>在设备设置Windows驱动程序，包括外设驱动程序。</li><li>安装.msi或.exe文件。</li><li>安装Windows功能。</li></ul>
| **不支持的操作** | <ul><li>安装与安全或管理功能Microsoft 托管桌面或操作相冲突的软件或功能。</li><li>禁用Windows所需的功能，Microsoft 托管桌面 BitLocker。</li><li>修改组织管理的设置。</li><ul>

**若要请求提升：**

1. 登录到"[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单。
1. 在"**Microsoft 托管桌面**"部分中，选择"**设备**"，其中包含两个选项卡："设备"选项卡和"**提升请求"** 选项卡。
1. 若要在"设备" **选项卡上创建新的** 提升请求，请选择要提升的单个设备。
1. 从设备操作下拉菜单中，选择请求 **提升**。 将显示新的提升请求飞入，并预先填充该字段中的设备名称。
1. 相反，若要在"提升请求"选项卡中创建新的提升请求，请选择 **"+新建提升请求"。**
1. 提供以下详细信息：
    - **支持票证 ID**：这是来自你自己的支持票证系统。
    - **设备名称**：这仅在从"提升请求" **选项卡创建请求时** 发生。输入设备序列号，然后从菜单中选择设备。
    - **类别**：选择最适合你的问题的类别。 如果没有选项看起来接近，请选择"其他 **"**。 最好尽可能选择类别。
    - **标题**：提供设备上问题的简短说明。
    - **操作计划**：提供授予提升权限后计划要采取疑难解答步骤。
1. 选择“**提交**”。
1. 可在"提升请求"选项卡上看到所有活动请求和已关闭 **请求的列表和** 详细信息。

## <a name="escalation-requests"></a>升级请求

**将 [问题](../service-description/user-support.md#escalation-portal) 上报给 Microsoft：**

1. 登录到"[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到"**租户管理"** 菜单。
2. 在"Microsoft 托管桌面"部分，选择 **"服务请求"**。
3. 在" **服务请求"** 部分，选择 **"+ 新建支持请求"**。
4. 在"标题"字段中 **提供简要** 说明。 然后，将"**请求类型"设置为****"事件"**。
5. 选择 **最适合** 您的问题的 **"** 类别"和"子类别"。 然后，选择“下一步”。
6. 在 **"详细信息** "部分，提供以下信息：
    - **说明**：添加任何有助于团队了解该问题的额外详细信息。 如果需要附加文件，可以在提交后返回请求以完成这一操作。
    - **主要联系人信息**：提供有关如何联系负责与团队合作的主要人员的信息。
7. 选择 **"严重性"** 级别。 有关详细信息，请参阅支持 [请求严重性定义](../working-with-managed-desktop/admin-support.md#support-request-severity-definitions)。
8. 尽可能提供有关请求的信息，以帮助团队快速响应。 根据请求的类型，您可能需要提供不同的详细信息。
9. 查看您提供的所有信息，以确保准确性。
10. 准备就绪后，选择 **“创建”**。
