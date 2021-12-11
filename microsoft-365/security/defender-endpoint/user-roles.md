---
title: 为基于角色的访问控制创建和管理角色
description: 创建角色，并将分配给角色的权限定义为角色中基于角色的访问控制实现Microsoft 365 Defender
keywords: 用户角色， 角色， 访问 rbac
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a959edf1eaefcb25fd3fb8279e7e03d317c4f12e
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168350"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>为基于角色的访问控制创建和管理角色

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-roles-abovefoldlink)。

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>创建角色并将角色分配给Azure Active Directory组

以下步骤将指导您如何在角色Microsoft 365 Defender。 它假定你已创建Azure Active Directory用户组。

1. 使用分配<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>全局管理员角色的帐户登录登录。

2. 在导航窗格中，在"权限设置" ("下选择 \>  \> **") "。**

3. 选择 **"添加项目"。**

4. 输入要分配给角色的角色名称、说明和权限。

5. 选择 **"** 下一步"将角色分配给Azure AD安全组。

6. 使用筛选器选择Azure AD要添加到此角色的组。

7. **保存并关闭**。

8. 应用配置设置。

> [!IMPORTANT]
> 创建角色后，你需要创建设备组，并将设备组分配给刚创建的角色，从而提供对设备组的访问权限。

### <a name="permission-options"></a>权限选项

- **查看数据**
  - **安全操作** - 在门户中查看所有安全操作数据
  - **威胁漏洞管理**- 危险和漏洞管理门户中查看数据

- **可用修正操作**
  - **安全操作** - 执行响应操作、批准或消除挂起的修正操作、管理自动化和指示器的允许/阻止列表
  - **威胁和漏洞管理 - 异常处理**- 创建新的异常和管理活动异常
  - **威胁和漏洞管理 - 修正处理**- 提交新的修正请求、创建票证和管理现有修正活动

- **警报调查** - 管理警报、启动自动调查、运行扫描、收集调查包、管理设备标记以及仅下载可移植的可执行 (PE) 文件

- **管理门户系统设置** - 配置存储设置、SIEM 和威胁情报 API 设置 (应用全局) 、高级设置、自动文件上传、角色和设备组

    > [!NOTE]
    > 此设置仅适用于 Microsoft Defender 终结点管理员 (默认) 角色。

- **在 Defender for Cloud** 中管理安全设置 - 配置警报抑制设置、管理自动化的文件夹排除项、载入和载出设备、管理电子邮件通知、管理评估实验室

- **实时响应功能**
  - **基本** 命令：
    - 启动实时响应会话
    - 在远程设备上执行只读实时响应命令 (文件复制和执行) 
    - 通过实时响应从远程设备下载文件
  - **高级** 命令：
    - 从文件页面下载 PE 和非 PE 文件
    - Upload文件到远程设备
    - 从文件库查看脚本
    - 从文件库在远程设备上执行脚本

有关可用命令详细信息，请参阅 [使用实时响应调查设备](live-response.md)。

## <a name="edit-roles"></a>编辑角色

1. 使用分配<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>全局管理员角色的帐户登录登录。

2. 在导航窗格中，在"权限设置" ("下选择 \>  \> **") "。**

3. 选择要编辑的角色。

4. 单击 **“编辑”**。

5. 修改分配给角色的详细信息或组。

6. 单击 **保存并关闭**。

## <a name="delete-roles"></a>删除角色

1. 使用分配<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>全局管理员角色的帐户登录登录。

2. 在导航窗格中，在"权限设置" ("下选择 \>  \> **") "。**

3. 选择要删除的角色。

4. 单击下拉按钮，然后选择删除 **角色**。

## <a name="related-topic"></a>相关主题

- [访问门户的用户基本权限](basic-permissions.md)
- [创建和管理设备组](machine-groups.md)
