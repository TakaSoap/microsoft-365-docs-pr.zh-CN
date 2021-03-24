---
title: 使用 Configuration Manager 管理 Microsoft Defender for Endpoint
description: 了解如何使用 Configuration Manager 管理 Microsoft Defender for Endpoint
keywords: 迁移后， 管理， 操作， 维护， 利用率， Configuration Manager， windows defender 高级威胁防护， atp， edr
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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 36599d830ac737b112df9f7c948e65829d6a7ce6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056102"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="61226-104">使用 Configuration Manager 管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61226-104">Manage Microsoft Defender for Endpoint with Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61226-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="61226-105">**Applies to:**</span></span>
- [<span data-ttu-id="61226-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61226-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="61226-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61226-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="61226-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="61226-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="61226-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="61226-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="61226-110">我们建议使用 [Microsoft Endpoint Manager，](https://docs.microsoft.com/mem)其中包括 [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) (Intune) 和 [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) (Configuration Manager) 来管理组织针对设备的威胁防护功能 (也称为终结点) 。</span><span class="sxs-lookup"><span data-stu-id="61226-110">We recommend using We recommend using [Microsoft Endpoint Manager](https://docs.microsoft.com/mem), which includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) (Intune) and [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) (Configuration Manager) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> 
- [<span data-ttu-id="61226-111">详细了解终结点管理器</span><span class="sxs-lookup"><span data-stu-id="61226-111">Learn more about Endpoint Manager</span></span>](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [<span data-ttu-id="61226-112">使用 Configuration Manager 和 Intune 在 Windows 10 设备上共同管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61226-112">Co-manage Microsoft Defender for Endpoint on Windows 10 devices with Configuration Manager and Intune</span></span>](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="61226-113">使用 Configuration Manager 配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61226-113">Configure Microsoft Defender for Endpoint with Configuration Manager</span></span>

|<span data-ttu-id="61226-114">任务</span><span class="sxs-lookup"><span data-stu-id="61226-114">Task</span></span>  |<span data-ttu-id="61226-115">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="61226-115">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="61226-116">**安装 Configuration Manager** 控制台（如果尚未安装）</span><span class="sxs-lookup"><span data-stu-id="61226-116">**Install the Configuration Manager console** if you don't already have it</span></span><br/><br/><span data-ttu-id="61226-117">*如果你还没有配置管理器控制台，请使用这些资源获取位并安装它。*</span><span class="sxs-lookup"><span data-stu-id="61226-117">*If you don't already have the Configuration Manger console, use these resources to get the bits and install it.*</span></span> |[<span data-ttu-id="61226-118">获取安装媒体</span><span class="sxs-lookup"><span data-stu-id="61226-118">Get the installation media</span></span>](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[<span data-ttu-id="61226-119">安装 Configuration Manager 控制台</span><span class="sxs-lookup"><span data-stu-id="61226-119">Install the Configuration Manager console</span></span>](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|<span data-ttu-id="61226-120">**使用 Configuration Manager 将设备载入** 到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61226-120">**Use Configuration Manager to onboard devices** to Microsoft Defender for Endpoint</span></span> <br/><br/> <span data-ttu-id="61226-121">*如果你的设备已 (或) 尚未载入到 Microsoft Defender for Endpoint，可以使用 Configuration Manager 完成这一操作。*</span><span class="sxs-lookup"><span data-stu-id="61226-121">*If you have devices (or endpoints) not already onboarded to Microsoft Defender for Endpoint, you can do that with Configuration Manager.*</span></span>   |[<span data-ttu-id="61226-122">使用 Configuration Manager 载入到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61226-122">Onboard to Microsoft Defender for Endpoint with Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|<span data-ttu-id="61226-123">**管理客户端计算机和终结点** 的反恶意软件策略 (Windows 防火墙) </span><span class="sxs-lookup"><span data-stu-id="61226-123">**Manage antimalware policies and Windows Firewall security** for client computers (endpoints)</span></span><br/><br/><span data-ttu-id="61226-124">*配置终结点保护功能，包括适用于终结点的 Microsoft Defender、Exploit Protection、应用程序控制、反恶意软件、防火墙设置等。*</span><span class="sxs-lookup"><span data-stu-id="61226-124">*Configure endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*</span></span>  |[<span data-ttu-id="61226-125">Configuration Manager：Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="61226-125">Configuration Manager: Endpoint Protection</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|<span data-ttu-id="61226-126">**选择在组织设备上更新** 反恶意软件更新的方法</span><span class="sxs-lookup"><span data-stu-id="61226-126">**Choose methods for updating antimalware updates** on your organization's devices</span></span> <br/><br/><span data-ttu-id="61226-127">*借助 Configuration Manager 中的 Endpoint Protection，可以从多种方法中选择，使反恶意软件定义在组织设备上保持最新。*</span><span class="sxs-lookup"><span data-stu-id="61226-127">*With Endpoint Protection in Configuration Manager, you can choose from several methods to keep antimalware definitions up to date on your organization's devices.*</span></span> |[<span data-ttu-id="61226-128">配置 Endpoint Protection 的定义更新</span><span class="sxs-lookup"><span data-stu-id="61226-128">Configure definition updates for Endpoint Protection</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[<span data-ttu-id="61226-129">使用 Configuration Manager 提供定义更新</span><span class="sxs-lookup"><span data-stu-id="61226-129">Use Configuration Manager to deliver definition updates</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|<span data-ttu-id="61226-130">**启用网络** 保护以帮助防止员工使用 Internet 上恶意内容的应用</span><span class="sxs-lookup"><span data-stu-id="61226-130">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="61226-131">*我们建议在 [测试环境中首先](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) 使用审核模式进行网络保护，以查看在推出之前哪些应用将被阻止。*</span><span class="sxs-lookup"><span data-stu-id="61226-131">*We recommend using [audit mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="61226-132">使用 Configuration Manager 打开网络保护</span><span class="sxs-lookup"><span data-stu-id="61226-132">Turn on network protection with Configuration Manager</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|<span data-ttu-id="61226-133">**配置受控文件夹访问权限** 以防范勒索软件</span><span class="sxs-lookup"><span data-stu-id="61226-133">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="61226-134">*受控文件夹访问权限也称为反反somware保护。*</span><span class="sxs-lookup"><span data-stu-id="61226-134">*Controlled folder access is also referred to as antiransomware protection.*</span></span>   |[<span data-ttu-id="61226-135">终结点保护：受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="61226-135">Endpoint protection: Controlled folder access</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[<span data-ttu-id="61226-136">在 Microsoft Endpoint Configuration Manage 中启用受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="61226-136">Enable controlled folder access in Microsoft Endpoint Configuration Manage</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="61226-137">配置 Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="61226-137">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="61226-138">如果尚未配置，请配置 Microsoft **Defender** 安全中心 () 以查看警报、配置威胁防护功能以及查看有关组织整体安全状况 [https://securitycenter.windows.com](https://securitycenter.windows.com) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="61226-138">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="61226-139">还可以配置最终用户是否可以在 Microsoft Defender 安全中心看到的功能以及这些功能。</span><span class="sxs-lookup"><span data-stu-id="61226-139">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="61226-140">Microsoft Defender 安全中心概述</span><span class="sxs-lookup"><span data-stu-id="61226-140">Overview of the Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="61226-141">终结点保护：Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="61226-141">Endpoint protection: Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="61226-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="61226-142">Next steps</span></span>

- [<span data-ttu-id="61226-143">获取威胁和漏洞管理的概述</span><span class="sxs-lookup"><span data-stu-id="61226-143">Get an overview of threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="61226-144">访问 Microsoft Defender 安全中心安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="61226-144">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="61226-145">使用 Intune 管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61226-145">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
