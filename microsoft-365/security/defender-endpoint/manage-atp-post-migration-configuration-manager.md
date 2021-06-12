---
title: 使用 Configuration Manager 管理 Microsoft Defender for Endpoint
description: 了解如何使用 Configuration Manager 管理 Microsoft Defender for Endpoint
keywords: 迁移后， 管理， 操作， 维护， 利用率， Configuration Manager， Microsoft Defender for Endpoint， edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: 5fde3bfad69a5851dd94b76afb262f8be12d0360
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908253"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="af11e-104">使用 Configuration Manager 管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af11e-104">Manage Microsoft Defender for Endpoint with Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af11e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="af11e-105">**Applies to:**</span></span>
- [<span data-ttu-id="af11e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af11e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="af11e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af11e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="af11e-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="af11e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af11e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="af11e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="af11e-110">我们建议使用[Microsoft Endpoint Manager，](/mem)其中包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) 和[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) 来管理组织对设备的威胁防护功能 (也称为终结点) 。</span><span class="sxs-lookup"><span data-stu-id="af11e-110">We recommend using We recommend using [Microsoft Endpoint Manager](/mem), which includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) and [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> 
- [<span data-ttu-id="af11e-111">详细了解Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="af11e-111">Learn more about Endpoint Manager</span></span>](/mem/endpoint-manager-overview)
- [<span data-ttu-id="af11e-112">使用 Configuration Manager 和 Intune 在 Windows 10 设备上共同管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af11e-112">Co-manage Microsoft Defender for Endpoint on Windows 10 devices with Configuration Manager and Intune</span></span>](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="af11e-113">使用 Configuration Manager 配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af11e-113">Configure Microsoft Defender for Endpoint with Configuration Manager</span></span>

|<span data-ttu-id="af11e-114">任务</span><span class="sxs-lookup"><span data-stu-id="af11e-114">Task</span></span>  |<span data-ttu-id="af11e-115">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="af11e-115">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="af11e-116">**安装 Configuration Manager** 控制台（如果尚未安装）</span><span class="sxs-lookup"><span data-stu-id="af11e-116">**Install the Configuration Manager console** if you don't already have it</span></span><br/><br/><span data-ttu-id="af11e-117">*如果你还没有配置管理器控制台，请使用这些资源获取位并安装它。*</span><span class="sxs-lookup"><span data-stu-id="af11e-117">*If you don't already have the Configuration Manger console, use these resources to get the bits and install it.*</span></span> |[<span data-ttu-id="af11e-118">获取安装媒体</span><span class="sxs-lookup"><span data-stu-id="af11e-118">Get the installation media</span></span>](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[<span data-ttu-id="af11e-119">安装 Configuration Manager 控制台</span><span class="sxs-lookup"><span data-stu-id="af11e-119">Install the Configuration Manager console</span></span>](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|<span data-ttu-id="af11e-120">**使用 Configuration Manager 将设备载入** 到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af11e-120">**Use Configuration Manager to onboard devices** to Microsoft Defender for Endpoint</span></span> <br/><br/> <span data-ttu-id="af11e-121">*如果你的设备已 (或) 尚未载入到 Microsoft Defender for Endpoint，可以使用 Configuration Manager 完成这一操作。*</span><span class="sxs-lookup"><span data-stu-id="af11e-121">*If you have devices (or endpoints) not already onboarded to Microsoft Defender for Endpoint, you can do that with Configuration Manager.*</span></span>   |[<span data-ttu-id="af11e-122">使用 Configuration Manager 载入到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af11e-122">Onboard to Microsoft Defender for Endpoint with Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|<span data-ttu-id="af11e-123">**管理客户端计算机和 Windows** 终结点的反恶意软件策略 (防火墙) </span><span class="sxs-lookup"><span data-stu-id="af11e-123">**Manage antimalware policies and Windows Firewall security** for client computers (endpoints)</span></span><br/><br/><span data-ttu-id="af11e-124">*配置终结点保护功能，包括适用于终结点的 Microsoft Defender、Exploit Protection、应用程序控制、反恶意软件、防火墙设置等。*</span><span class="sxs-lookup"><span data-stu-id="af11e-124">*Configure endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*</span></span>  |[<span data-ttu-id="af11e-125">Configuration Manager：Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="af11e-125">Configuration Manager: Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|<span data-ttu-id="af11e-126">**选择在组织设备上更新** 反恶意软件更新的方法</span><span class="sxs-lookup"><span data-stu-id="af11e-126">**Choose methods for updating antimalware updates** on your organization's devices</span></span> <br/><br/><span data-ttu-id="af11e-127">*使用Endpoint Protection管理器中，你可以选择多种方法使反恶意软件定义在组织设备上保持最新。*</span><span class="sxs-lookup"><span data-stu-id="af11e-127">*With Endpoint Protection in Configuration Manager, you can choose from several methods to keep antimalware definitions up to date on your organization's devices.*</span></span> |[<span data-ttu-id="af11e-128">配置应用程序的定义Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="af11e-128">Configure definition updates for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[<span data-ttu-id="af11e-129">使用 Configuration Manager 提供定义更新</span><span class="sxs-lookup"><span data-stu-id="af11e-129">Use Configuration Manager to deliver definition updates</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|<span data-ttu-id="af11e-130">**启用网络** 保护以帮助防止员工使用 Internet 上恶意内容的应用</span><span class="sxs-lookup"><span data-stu-id="af11e-130">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="af11e-131">*我们建议在 [测试环境中首先](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 使用审核模式进行网络保护，以查看在推出之前哪些应用将被阻止。*</span><span class="sxs-lookup"><span data-stu-id="af11e-131">*We recommend using [audit mode](/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="af11e-132">使用 Configuration Manager 打开网络保护</span><span class="sxs-lookup"><span data-stu-id="af11e-132">Turn on network protection with Configuration Manager</span></span>](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|<span data-ttu-id="af11e-133">**配置受控文件夹访问权限** 以防范勒索软件</span><span class="sxs-lookup"><span data-stu-id="af11e-133">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="af11e-134">*受控文件夹访问权限也称为反反somware保护。*</span><span class="sxs-lookup"><span data-stu-id="af11e-134">*Controlled folder access is also referred to as antiransomware protection.*</span></span>   |[<span data-ttu-id="af11e-135">终结点保护：受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="af11e-135">Endpoint protection: Controlled folder access</span></span>](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[<span data-ttu-id="af11e-136">在 Microsoft Endpoint Configuration Manage 中启用受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="af11e-136">Enable controlled folder access in Microsoft Endpoint Configuration Manage</span></span>](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="af11e-137">配置Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="af11e-137">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="af11e-138">如果尚未配置，请配置 Microsoft 365 Defender 门户以查看警报、配置威胁防护功能，并查看有关组织整体安全状况的详细信息。</span><span class="sxs-lookup"><span data-stu-id="af11e-138">If you haven't already done so, configure your Microsoft 365 Defender portal to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> <span data-ttu-id="af11e-139">请参阅[Microsoft Defender 安全中心](microsoft-defender-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="af11e-139">See [Microsoft Defender Security Center](microsoft-defender-security-center.md).</span></span> <span data-ttu-id="af11e-140">还可以配置最终用户是否可以在 defender 门户中查看Microsoft 365功能。</span><span class="sxs-lookup"><span data-stu-id="af11e-140">You can also configure whether and what features end users can see in the Microsoft 365 Defender portal.</span></span>

- [<span data-ttu-id="af11e-141">概述Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="af11e-141">Overview of the Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="af11e-142">终结点保护：Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="af11e-142">Endpoint protection: Microsoft Defender Security Center</span></span>](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="af11e-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="af11e-143">Next steps</span></span>

- [<span data-ttu-id="af11e-144">大致了解危险和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="af11e-144">Get an overview of threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="af11e-145">访问 Microsoft Defender 安全中心安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="af11e-145">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="af11e-146">使用 Intune 管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af11e-146">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
