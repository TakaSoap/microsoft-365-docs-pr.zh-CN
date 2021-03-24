---
title: 为基于角色的访问控制创建和管理角色
description: 创建角色，并定义作为 Microsoft Defender 安全中心中基于角色的访问控制实现一部分分配给角色的权限
keywords: 用户角色， 角色， 访问 rbac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055880"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="8ce6c-104">为基于角色的访问控制创建和管理角色</span><span class="sxs-lookup"><span data-stu-id="8ce6c-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ce6c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8ce6c-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ce6c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ce6c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8ce6c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ce6c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8ce6c-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8ce6c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8ce6c-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="8ce6c-110">创建角色并将角色分配给 Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="8ce6c-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="8ce6c-111">以下步骤将指导你如何在 Microsoft Defender 安全中心创建角色。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="8ce6c-112">它假定你已创建 Azure Active Directory 用户组。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="8ce6c-113">使用分配有 [安全管理员](https://securitycenter.windows.com/) 或全局管理员角色的帐户登录到 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="8ce6c-114">在导航窗格中，选择"设置 **>角色"。**</span><span class="sxs-lookup"><span data-stu-id="8ce6c-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="8ce6c-115">选择 **"添加项目"。**</span><span class="sxs-lookup"><span data-stu-id="8ce6c-115">Select **Add item**.</span></span>

4. <span data-ttu-id="8ce6c-116">输入要分配给角色的角色名称、说明和权限。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="8ce6c-117">选择 **"下** 一步"，将角色分配给 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="8ce6c-118">使用筛选器选择要添加到此角色的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="8ce6c-119">**保存并关闭**。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-119">**Save and close**.</span></span>

8. <span data-ttu-id="8ce6c-120">应用配置设置。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ce6c-121">创建角色后，你需要创建设备组，并将设备组分配给刚创建的角色，从而提供对设备组的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="8ce6c-122">权限选项</span><span class="sxs-lookup"><span data-stu-id="8ce6c-122">Permission options</span></span>

- <span data-ttu-id="8ce6c-123">**查看数据**</span><span class="sxs-lookup"><span data-stu-id="8ce6c-123">**View data**</span></span>
    - <span data-ttu-id="8ce6c-124">**安全操作** - 在门户中查看所有安全操作数据</span><span class="sxs-lookup"><span data-stu-id="8ce6c-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="8ce6c-125">**威胁和漏洞管理** - 在门户中查看威胁和漏洞管理数据</span><span class="sxs-lookup"><span data-stu-id="8ce6c-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="8ce6c-126">**活动修正操作**</span><span class="sxs-lookup"><span data-stu-id="8ce6c-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="8ce6c-127">**安全操作** - 执行响应操作、批准或消除挂起的修正操作、管理自动化和指示器的允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="8ce6c-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="8ce6c-128">**威胁和漏洞管理 - 异常处理** - 创建新的异常并管理活动异常</span><span class="sxs-lookup"><span data-stu-id="8ce6c-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="8ce6c-129">**威胁和漏洞管理 - 修正处理** - 提交新的修正请求、创建票证和管理现有修正活动</span><span class="sxs-lookup"><span data-stu-id="8ce6c-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="8ce6c-130">**警报调查** - 管理警报、启动自动调查、运行扫描、收集调查包、管理设备标记，以及仅下载可移植的可执行 (PE) 文件</span><span class="sxs-lookup"><span data-stu-id="8ce6c-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="8ce6c-131">**管理门户系统设置** - 配置存储设置、SIEM 和威胁情报 API (应用全局) 、高级设置、自动文件上传、角色和设备组</span><span class="sxs-lookup"><span data-stu-id="8ce6c-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="8ce6c-132">此设置仅适用于 Microsoft Defender 终结点管理员 (默认) 角色。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="8ce6c-133">**在安全中心管理安全设置** - 配置警报抑制设置、管理用于自动化的文件夹排除项、载入和载出设备、管理电子邮件通知、管理评估实验室</span><span class="sxs-lookup"><span data-stu-id="8ce6c-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="8ce6c-134">**实时响应功能**</span><span class="sxs-lookup"><span data-stu-id="8ce6c-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="8ce6c-135">**基本** 命令：</span><span class="sxs-lookup"><span data-stu-id="8ce6c-135">**Basic** commands:</span></span>
        - <span data-ttu-id="8ce6c-136">启动实时响应会话</span><span class="sxs-lookup"><span data-stu-id="8ce6c-136">Start a live response session</span></span>
        - <span data-ttu-id="8ce6c-137">在远程设备上执行只读实时响应命令 (文件复制和执行除外</span><span class="sxs-lookup"><span data-stu-id="8ce6c-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="8ce6c-138">**高级** 命令：</span><span class="sxs-lookup"><span data-stu-id="8ce6c-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="8ce6c-139">通过实时响应从远程设备下载文件</span><span class="sxs-lookup"><span data-stu-id="8ce6c-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="8ce6c-140">从文件页面下载 PE 和非 PE 文件</span><span class="sxs-lookup"><span data-stu-id="8ce6c-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="8ce6c-141">将文件上传到远程设备</span><span class="sxs-lookup"><span data-stu-id="8ce6c-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="8ce6c-142">从文件库查看脚本</span><span class="sxs-lookup"><span data-stu-id="8ce6c-142">View a script from the files library</span></span>
        - <span data-ttu-id="8ce6c-143">从文件库在远程设备上执行脚本</span><span class="sxs-lookup"><span data-stu-id="8ce6c-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="8ce6c-144">有关可用命令详细信息，请参阅 [使用实时响应调查设备](live-response.md)。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="8ce6c-145">编辑角色</span><span class="sxs-lookup"><span data-stu-id="8ce6c-145">Edit roles</span></span>

1. <span data-ttu-id="8ce6c-146">使用分配有 [安全管理员](https://securitycenter.windows.com/) 或全局管理员角色的帐户登录到 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="8ce6c-147">在导航窗格中，选择"设置 **>角色"。**</span><span class="sxs-lookup"><span data-stu-id="8ce6c-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="8ce6c-148">选择要编辑的角色。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="8ce6c-149">单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-149">Click **Edit**.</span></span>

5. <span data-ttu-id="8ce6c-150">修改分配给角色的详细信息或组。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="8ce6c-151">单击 **保存并关闭**。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="8ce6c-152">删除角色</span><span class="sxs-lookup"><span data-stu-id="8ce6c-152">Delete roles</span></span>

1. <span data-ttu-id="8ce6c-153">使用分配有 [安全管理员](https://securitycenter.windows.com/) 或全局管理员角色的帐户登录到 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="8ce6c-154">在导航窗格中，选择"设置 **>角色"。**</span><span class="sxs-lookup"><span data-stu-id="8ce6c-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="8ce6c-155">选择要删除的角色。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="8ce6c-156">单击下拉按钮，然后选择删除 **角色**。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="8ce6c-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="8ce6c-157">Related topic</span></span>

- [<span data-ttu-id="8ce6c-158">访问门户的用户基本权限</span><span class="sxs-lookup"><span data-stu-id="8ce6c-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="8ce6c-159">创建和管理设备组</span><span class="sxs-lookup"><span data-stu-id="8ce6c-159">Create and manage device groups</span></span>](machine-groups.md)
