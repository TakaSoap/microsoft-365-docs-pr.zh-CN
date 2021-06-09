---
title: 使用组策略对象管理 Microsoft Defender for Endpoint
description: 了解如何使用组策略对象管理 Microsoft Defender for Endpoint
keywords: 迁移后， 管理， 操作， 维护， 利用率， PowerShell， Microsoft Defender for Endpoint， edr
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
ms.openlocfilehash: 15902e02156c59ec4edaed94f4ba321094bd42ac
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843018"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="f50e6-104">使用组策略对象管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f50e6-104">Manage Microsoft Defender for Endpoint with Group Policy Objects</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f50e6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f50e6-105">**Applies to:**</span></span>
- [<span data-ttu-id="f50e6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f50e6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f50e6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f50e6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f50e6-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f50e6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f50e6-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f50e6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="f50e6-110">我们建议使用[Microsoft Endpoint Manager](/mem)管理组织对也称为终结点 (的设备的威胁防护) 。</span><span class="sxs-lookup"><span data-stu-id="f50e6-110">We recommend using [Microsoft Endpoint Manager](/mem) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> <span data-ttu-id="f50e6-111">Endpoint Manager包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="f50e6-111">Endpoint Manager includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction).</span></span> <span data-ttu-id="f50e6-112">**[详细了解Endpoint Manager。](/mem/endpoint-manager-overview)**</span><span class="sxs-lookup"><span data-stu-id="f50e6-112">**[Learn more about Endpoint Manager](/mem/endpoint-manager-overview)**.</span></span> 

<span data-ttu-id="f50e6-113">可以使用域服务中的组策略Azure Active Directory管理 Microsoft Defender for Endpoint 中的某些设置。</span><span class="sxs-lookup"><span data-stu-id="f50e6-113">You can use Group Policy Objects in Azure Active Directory Domain Services to manage some settings in Microsoft Defender for Endpoint.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="f50e6-114">使用组策略对象配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f50e6-114">Configure Microsoft Defender for Endpoint with Group Policy Objects</span></span>

<span data-ttu-id="f50e6-115">下表列出了可以使用组策略对象配置 Microsoft Defender for Endpoint 时可执行的各种任务。</span><span class="sxs-lookup"><span data-stu-id="f50e6-115">The following table lists various tasks you can perform to configure Microsoft Defender for Endpoint with Group Policy Objects.</span></span>

|<span data-ttu-id="f50e6-116">任务</span><span class="sxs-lookup"><span data-stu-id="f50e6-116">Task</span></span>  |<span data-ttu-id="f50e6-117">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="f50e6-117">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="f50e6-118">**管理用户和计算机对象的设置**</span><span class="sxs-lookup"><span data-stu-id="f50e6-118">**Manage settings for user and computer objects**</span></span> <br/><br/><span data-ttu-id="f50e6-119">*自定义内置组策略对象，或创建自定义组策略对象和组织单位以满足组织需求。*</span><span class="sxs-lookup"><span data-stu-id="f50e6-119">*Customize built-in Group Policy Objects, or create custom Group Policy Objects and organizational units to suit your organizational needs.*</span></span>     |[<span data-ttu-id="f50e6-120">管理域服务托管Azure Active Directory中的组策略</span><span class="sxs-lookup"><span data-stu-id="f50e6-120">Administer Group Policy in an Azure Active Directory Domain Services managed domain</span></span>](/azure/active-directory-domain-services/manage-group-policy)   |
|<span data-ttu-id="f50e6-121">**配置Microsoft Defender 防病毒**</span><span class="sxs-lookup"><span data-stu-id="f50e6-121">**Configure Microsoft Defender Antivirus**</span></span> <br/><br/><span data-ttu-id="f50e6-122">*在组织设备上配置&功能，包括策略设置、排除、修正和计划扫描 (也称为终结点) 。*</span><span class="sxs-lookup"><span data-stu-id="f50e6-122">*Configure antivirus features & capabilities, including policy settings, exclusions, remediation, and scheduled scans on your organization's devices (also referred to as endpoints).*</span></span>   |[<span data-ttu-id="f50e6-123">使用组策略设置配置和管理Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="f50e6-123">Use Group Policy settings to configure and manage Microsoft Defender Antivirus</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[<span data-ttu-id="f50e6-124">使用组策略启用云保护</span><span class="sxs-lookup"><span data-stu-id="f50e6-124">Use Group Policy to enable cloud-delivered protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|<span data-ttu-id="f50e6-125">**管理组织的攻击面减少规则**</span><span class="sxs-lookup"><span data-stu-id="f50e6-125">**Manage your organization's attack surface reduction rules**</span></span> <br/><br/><span data-ttu-id="f50e6-126">*自定义攻击面减少规则，&文件夹中的文件，或者向显示在用户设备上的通知警报添加自定义文本。*</span><span class="sxs-lookup"><span data-stu-id="f50e6-126">*Customize your attack surface reduction rules by excluding files & folders, or by adding custom text to notification alerts that appear on users' devices.*</span></span> |[<span data-ttu-id="f50e6-127">使用组策略对象自定义攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="f50e6-127">Customize attack surface reduction rules with Group Policy Objects</span></span>](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|<span data-ttu-id="f50e6-128">**管理 Exploit Protection 设置**</span><span class="sxs-lookup"><span data-stu-id="f50e6-128">**Manage exploit protection settings**</span></span><br/><br/><span data-ttu-id="f50e6-129">*你可以自定义 Exploit Protection 设置、导入配置文件，然后使用组策略部署该配置文件。*</span><span class="sxs-lookup"><span data-stu-id="f50e6-129">*You can customize your exploit protection settings, import a configuration file, and then use Group Policy to deploy that configuration file.*</span></span>  |[<span data-ttu-id="f50e6-130">自定义 Exploit Protection 设置</span><span class="sxs-lookup"><span data-stu-id="f50e6-130">Customize exploit protection settings</span></span>](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[<span data-ttu-id="f50e6-131">导入、导出和部署 Exploit Protection 配置</span><span class="sxs-lookup"><span data-stu-id="f50e6-131">Import, export, and deploy exploit protection configurations</span></span>](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[<span data-ttu-id="f50e6-132">使用组策略分发配置</span><span class="sxs-lookup"><span data-stu-id="f50e6-132">Use Group Policy to distribute the configuration</span></span>](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|<span data-ttu-id="f50e6-133">**启用网络** 保护以帮助防止员工使用 Internet 上恶意内容的应用</span><span class="sxs-lookup"><span data-stu-id="f50e6-133">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="f50e6-134">*我们建议在 [测试环境中首先](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 使用审核模式进行网络保护，以查看在推出之前哪些应用将被阻止。*</span><span class="sxs-lookup"><span data-stu-id="f50e6-134">*We recommend using [audit mode](/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="f50e6-135">使用组策略打开网络保护</span><span class="sxs-lookup"><span data-stu-id="f50e6-135">Turn on network protection using Group Policy</span></span>](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|<span data-ttu-id="f50e6-136">**配置受控文件夹访问权限** 以防范勒索软件</span><span class="sxs-lookup"><span data-stu-id="f50e6-136">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="f50e6-137">*[受控文件夹访问权限](/microsoft-365/security/defender-endpoint/controlled-folders) 也称为反反somware保护。*</span><span class="sxs-lookup"><span data-stu-id="f50e6-137">*[Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders) is also referred to as antiransomware protection.*</span></span>  |[<span data-ttu-id="f50e6-138">使用组策略启用受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="f50e6-138">Enable controlled folder access using Group Policy</span></span>](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|<span data-ttu-id="f50e6-139">**配置Microsoft Defender SmartScreen** 以抵御 Internet 上的恶意站点和文件。</span><span class="sxs-lookup"><span data-stu-id="f50e6-139">**Configure Microsoft Defender SmartScreen** to protect against malicious sites and files on the internet.</span></span>  |[<span data-ttu-id="f50e6-140">使用Microsoft Defender SmartScreen策略配置 MDM (移动设备) 组策略和移动设备管理</span><span class="sxs-lookup"><span data-stu-id="f50e6-140">Configure Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings using Group Policy</span></span>](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|<span data-ttu-id="f50e6-141">**配置加密BitLocker，** 以保护组织中运行加密Windows</span><span class="sxs-lookup"><span data-stu-id="f50e6-141">**Configure encryption and BitLocker** to protect information on your organization's devices running Windows</span></span> |[<span data-ttu-id="f50e6-142">BitLocker组策略设置</span><span class="sxs-lookup"><span data-stu-id="f50e6-142">BitLocker Group Policy settings</span></span>](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|<span data-ttu-id="f50e6-143">**配置 Microsoft Defender Credential Guard** 以防止凭据盗窃攻击</span><span class="sxs-lookup"><span data-stu-id="f50e6-143">**Configure Microsoft Defender Credential Guard** to protect against credential theft attacks</span></span> |[<span data-ttu-id="f50e6-144">使用Windows Defender Credential Guard启用组策略</span><span class="sxs-lookup"><span data-stu-id="f50e6-144">Enable Windows Defender Credential Guard by using Group Policy</span></span>](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="f50e6-145">配置Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="f50e6-145">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="f50e6-146">如果尚未配置，请配置 Microsoft Defender 安全中心 **(**) 以查看警报、配置威胁防护功能以及查看有关组织整体安全状况 [https://securitycenter.windows.com](https://securitycenter.windows.com) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f50e6-146">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="f50e6-147">还可以配置最终用户是否可以在网站中查看这些功能Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="f50e6-147">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="f50e6-148">概述Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="f50e6-148">Overview of the Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="f50e6-149">终结点保护：Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="f50e6-149">Endpoint protection: Microsoft Defender Security Center</span></span>](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="f50e6-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f50e6-150">Next steps</span></span>

- [<span data-ttu-id="f50e6-151">大致了解危险和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="f50e6-151">Get an overview of threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="f50e6-152">访问 Microsoft Defender 安全中心安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="f50e6-152">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="f50e6-153">使用 Intune 管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f50e6-153">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
