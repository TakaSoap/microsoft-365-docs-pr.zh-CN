---
title: 权限&的先决条件 - 威胁和漏洞管理
description: 在开始使用威胁和漏洞管理之前，请确保你拥有相关的配置和权限。
keywords: 威胁&漏洞管理权限先决条件、威胁和漏洞管理权限先决条件、MDATP TVM 权限先决条件、漏洞管理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca095a7a65a114182d736176840fdd4e651a8646
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056094"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="bbf53-104">权限&的先决条件 - 威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="bbf53-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bbf53-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bbf53-105">**Applies to:**</span></span>

- [<span data-ttu-id="bbf53-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbf53-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bbf53-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="bbf53-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="bbf53-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbf53-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bbf53-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="bbf53-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bbf53-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="bbf53-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="bbf53-111">确保你的设备：</span><span class="sxs-lookup"><span data-stu-id="bbf53-111">Ensure that your devices:</span></span>

- <span data-ttu-id="bbf53-112">已载入到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbf53-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="bbf53-113">运行 [支持的操作系统和平台](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="bbf53-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="bbf53-114">在网络中安装并部署以下强制更新，以提高漏洞评估检测速率：</span><span class="sxs-lookup"><span data-stu-id="bbf53-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="bbf53-115">发布</span><span class="sxs-lookup"><span data-stu-id="bbf53-115">Release</span></span> | <span data-ttu-id="bbf53-116">安全更新 KB 编号和链接</span><span class="sxs-lookup"><span data-stu-id="bbf53-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="bbf53-117">Windows 10 版本 1709</span><span class="sxs-lookup"><span data-stu-id="bbf53-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="bbf53-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) [和 KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="bbf53-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="bbf53-119">Windows 10 版本 1803</span><span class="sxs-lookup"><span data-stu-id="bbf53-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="bbf53-120">[KB4493464](https://support.microsoft.com/help/4493464) 和 [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="bbf53-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="bbf53-121">Windows 10 版本 1809</span><span class="sxs-lookup"><span data-stu-id="bbf53-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="bbf53-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="bbf53-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="bbf53-123">Windows 10 版本 1903</span><span class="sxs-lookup"><span data-stu-id="bbf53-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="bbf53-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="bbf53-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="bbf53-125">已载入到 [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 和  [Microsoft Endpoint Configuration Manager，](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) 以帮助修正威胁和漏洞管理发现的威胁。</span><span class="sxs-lookup"><span data-stu-id="bbf53-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="bbf53-126">如果你使用的是 Configuration Manager，请更新控制台到最新版本。</span><span class="sxs-lookup"><span data-stu-id="bbf53-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="bbf53-127">**注意**：如果启用了 Intune 连接，则创建修正请求时可以选择创建 Intune 安全任务。</span><span class="sxs-lookup"><span data-stu-id="bbf53-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="bbf53-128">如果未设置连接，则不显示此选项。</span><span class="sxs-lookup"><span data-stu-id="bbf53-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="bbf53-129">具有至少一个可在设备页面中查看的安全建议</span><span class="sxs-lookup"><span data-stu-id="bbf53-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="bbf53-130">已标记或标记为共同管理</span><span class="sxs-lookup"><span data-stu-id="bbf53-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="bbf53-131">相关权限选项</span><span class="sxs-lookup"><span data-stu-id="bbf53-131">Relevant permission options</span></span>

1. <span data-ttu-id="bbf53-132">使用分配有安全管理员或全局管理员角色的帐户登录到 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="bbf53-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="bbf53-133">在导航窗格中，选择"设置 **>角色"。**</span><span class="sxs-lookup"><span data-stu-id="bbf53-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="bbf53-134">有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="bbf53-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="bbf53-135">查看数据</span><span class="sxs-lookup"><span data-stu-id="bbf53-135">View data</span></span>

- <span data-ttu-id="bbf53-136">**安全操作** - 在门户中查看所有安全操作数据</span><span class="sxs-lookup"><span data-stu-id="bbf53-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="bbf53-137">**威胁和漏洞管理** - 在门户中查看威胁和漏洞管理数据</span><span class="sxs-lookup"><span data-stu-id="bbf53-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="bbf53-138">活动修正操作</span><span class="sxs-lookup"><span data-stu-id="bbf53-138">Active remediation actions</span></span>

- <span data-ttu-id="bbf53-139">**安全操作** - 执行响应操作、批准或消除挂起的修正操作、管理自动化和指示器的允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="bbf53-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="bbf53-140">**威胁和漏洞管理 - 异常处理** - 创建新的异常并管理活动异常</span><span class="sxs-lookup"><span data-stu-id="bbf53-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="bbf53-141">**威胁和漏洞管理 - 修正处理** - 提交新的修正请求、创建票证和管理现有修正活动</span><span class="sxs-lookup"><span data-stu-id="bbf53-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="bbf53-142">有关详细信息，请参阅 [RBAC 权限选项](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="bbf53-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="bbf53-143">相关文章</span><span class="sxs-lookup"><span data-stu-id="bbf53-143">Related articles</span></span>

- [<span data-ttu-id="bbf53-144">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="bbf53-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="bbf53-145">支持的操作系统和平台</span><span class="sxs-lookup"><span data-stu-id="bbf53-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="bbf53-146">分配设备值</span><span class="sxs-lookup"><span data-stu-id="bbf53-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="bbf53-147">威胁和漏洞管理仪表板</span><span class="sxs-lookup"><span data-stu-id="bbf53-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

