---
title: 部署 Windows 10 企业安全功能
description: 在 Microsoft 365 Enterprise 的一部分部署 Pc 上的 Windows 10 Enterprise 所需的步骤提供高级指导。
keywords: Microsoft 365 Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业安全
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866039"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a><span data-ttu-id="2342b-104">步骤 5： 部署 Windows 10 企业安全功能</span><span class="sxs-lookup"><span data-stu-id="2342b-104">Step 5: Deploy Windows 10 Enterprise security features</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="2342b-105">Windows 10 提供了功能来帮助保护抵御威胁，帮助您保护您的设备，并帮助访问控制。</span><span class="sxs-lookup"><span data-stu-id="2342b-105">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> 

<span data-ttu-id="2342b-106">若要了解有关这些技术的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2342b-106">To learn more about these technologies, see:</span></span>
* <span data-ttu-id="2342b-107">[访问保护](https://docs.microsoft.com/windows/access-protection/)-了解访问控制，S/MIME 数字证书，凭据 Guard 用户帐户控制虚拟智能卡，Windows Hello 业务、 高级安全 Windows 防火墙和的详细信息</span><span class="sxs-lookup"><span data-stu-id="2342b-107">[Access protection](https://docs.microsoft.com/windows/access-protection/) - Learn about access control, S/MIME, digital certificates, Credential Guard, User Account Control, virtual smart cards, Windows Hello for Business, Windows Firewall with Advanced Security, and more</span></span>
* <span data-ttu-id="2342b-108">[设备安全](https://docs.microsoft.com/windows/device-security/)-包括 AppLocker、 BitLocker、 设备 Guard 和受信任的平台模块</span><span class="sxs-lookup"><span data-stu-id="2342b-108">[Device security](https://docs.microsoft.com/windows/device-security/) - Includes AppLocker, BitLocker, Device Guard, and Trusted Platform Module</span></span>
* <span data-ttu-id="2342b-109">[威胁保护](https://docs.microsoft.com/windows/threat-protection/)-包括 Windows Defender 安全中心、 Windows Defender 高级威胁保护、 Windows Defender 防病毒、 Windows Defender 应用程序 Guard、 Windows Defender 智能屏幕上，和 Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="2342b-109">[Threat protection](https://docs.microsoft.com/windows/threat-protection/) - Includes Windows Defender Security Center, Windows Defender Advanced Threat Protection, Windows Defender Antivirus, Windows Defender Application Guard, Windows Defender Smart Screen, and Windows Information Protection</span></span>

<span data-ttu-id="2342b-110">此步骤演示了如何部署、 管理、 配置和解决使用这些安全功能：</span><span class="sxs-lookup"><span data-stu-id="2342b-110">This step shows you how you can deploy, manage, configure, and troubleshoot using these security features:</span></span>

* [<span data-ttu-id="2342b-111">Windows Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="2342b-111">Windows Defender Antivirus</span></span>](#windows-defender-antivirus)
* [<span data-ttu-id="2342b-112">Windows Defender 攻击防护</span><span class="sxs-lookup"><span data-stu-id="2342b-112">Windows Defender Exploit Guard</span></span>](#windows-defender-exploit-guard)
* [<span data-ttu-id="2342b-113">Windows Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="2342b-113">Windows Defender Advanced Threat Protection</span></span>](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a><span data-ttu-id="2342b-114">Windows Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="2342b-114">Windows Defender Antivirus</span></span>
<span data-ttu-id="2342b-p101">Windows Defender 防病毒 (AV) 是内置 Windows 10 反恶意软件解决方案。它为台式机、 便携计算机和服务器提供了安全性和反恶意软件管理。有关 Windows Defender AV、 的最低硬件要求，以及如何管理此功能的详细信息，请参阅[Windows 10 和 Windows Server 2016 中的 Windows Defender 防病毒](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="2342b-p101">Windows Defender Antivirus (AV) is an antimalware solution that's built into Windows 10. It provides security and antimalware management for desktops, portable computers, and servers. For more info about Windows Defender AV, the minimum requirements, and how you can manage this feature, see [Windows Defender Antivirus in Windows 10 and Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).</span></span>

<span data-ttu-id="2342b-p102">如果您未使用 Windows Defender AV 为主要防病毒客户端，或者如果您还将使用 Windows Defender ATP，有一些注意事项您需要考虑在内。若要了解详细信息，请参阅[Windows Defender AV 兼容性](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="2342b-p102">If you are not using Windows Defender AV as your primary antivirus client, or if you are also using Windows Defender ATP, there are some considerations you need to take into account. To learn more, see [Windows Defender AV compatibility](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).</span></span>

### <a name="deployment-and-management"></a><span data-ttu-id="2342b-120">部署和管理</span><span class="sxs-lookup"><span data-stu-id="2342b-120">Deployment and management</span></span>
<span data-ttu-id="2342b-121">部署和管理 Windows Defender AV，请按照下面的指南操作：</span><span class="sxs-lookup"><span data-stu-id="2342b-121">To deploy and manage Windows Defender AV, follow the guidance here:</span></span>

* [<span data-ttu-id="2342b-122">部署、 管理和 Windows Defender AV 报告</span><span class="sxs-lookup"><span data-stu-id="2342b-122">Deploy, manage, and report on Windows Defender AV</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [<span data-ttu-id="2342b-123">管理和配置工具的参考主题</span><span class="sxs-lookup"><span data-stu-id="2342b-123">Reference topics for management and configuration tools</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a><span data-ttu-id="2342b-124">配置</span><span class="sxs-lookup"><span data-stu-id="2342b-124">Configuration</span></span>
<span data-ttu-id="2342b-p103">用户可以配置的功能的数量。人员的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="2342b-p103">Users can configure a number of features. For more info, see these resources:</span></span>

* [<span data-ttu-id="2342b-127">配置 Windows Defender AV 功能</span><span class="sxs-lookup"><span data-stu-id="2342b-127">Configure Windows Defender AV features</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [<span data-ttu-id="2342b-128">管理和配置工具的参考主题</span><span class="sxs-lookup"><span data-stu-id="2342b-128">Reference topics for management and configuration tools</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

<span data-ttu-id="2342b-129">以帮助了解配置选项，请参阅此列表的所有设置 （如定义其组策略配置）：[使用组策略设置来配置和管理 Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="2342b-129">To help understand configuration options, refer to this list of all settings (as defined by their Group Policy configuration): [Use Group Policy settings to configure and manage Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)</span></span>

<span data-ttu-id="2342b-p104">您可以使用[Windows Defender 防病毒保护评估指南](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus)有助于评估的保护级别和 Windows Defender AV 在您的网络影响。这也会很有用创建初始配置或作为快速入门指南，并定期更新用于配置和启用功能，以确保最大保护提供最有用的建议。</span><span class="sxs-lookup"><span data-stu-id="2342b-p104">You can use the [Windows Defender AV protection Evaluation Guide](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) to help evaluate the protection level and impact of Windows Defender AV on your network. This can also be useful in creating an initial configuration or as a ‘quick start guide’ and is regularly updated to provide the most useful recommendations for configuring and enabling features to ensure maximum protection.</span></span>

### <a name="reporting"></a><span data-ttu-id="2342b-132">报告</span><span class="sxs-lookup"><span data-stu-id="2342b-132">Reporting</span></span>
<span data-ttu-id="2342b-p105">您可以获取使用配置工具，如 System Center Configuration Manager 或 Microsoft Intune 报告。您还可以获取从更新合规性 (OMS) 或通过使用 Windows 事件日志中您 SIEM 报告。如果您具有 Windows Defender ATP 许可证，您可以获取 Windows Defender AV 检测到报告和执行基本的补救。人员的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="2342b-p105">You can obtain reporting by using a configuration tool, such as System Center Configuration Manager or Microsoft Intune. You can also obtain reporting from Update Compliance (OMS) or by consuming Windows event logs in your SIEM. If you have a license for Windows Defender ATP, you can also obtain reporting into Windows Defender AV detections and perform basic remediation. For more info, see these resources:</span></span>
* [<span data-ttu-id="2342b-137">部署、 管理和 Windows Defender AV 报告</span><span class="sxs-lookup"><span data-stu-id="2342b-137">Deploy, manage, and report on Windows Defender AV</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [<span data-ttu-id="2342b-138">报告 Windows Defender 防病毒保护</span><span class="sxs-lookup"><span data-stu-id="2342b-138">Report on Windows Defender AV protection</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [<span data-ttu-id="2342b-139">Windows Defender ATP 门户的概述 （英文)</span><span class="sxs-lookup"><span data-stu-id="2342b-139">Windows Defender ATP portal overview</span></span>](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a><span data-ttu-id="2342b-140">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2342b-140">Troubleshooting</span></span>
<span data-ttu-id="2342b-141">错误和事件代码的基本疑难解答的信息，请参阅[查看事件日志和错误代码，以解决 Windows Defender AV 的问题](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="2342b-141">For info on basic troubleshooting of error and event codes, see [Review event logs and error codes to troubleshoot issues with Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).</span></span>

<span data-ttu-id="2342b-p106">您还可以使用 Windows Defender 安全智能提交系统提交问题 （如误报）。若要了解如何，请参阅[向 Microsoft 提交问题](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="2342b-p106">You can also submit issues (such as false positives) by using the Windows Defender Security Intelligence submission system. To learn how, see [Submit issues to Microsoft](https://www.microsoft.com/wdsi/filesubmission).</span></span>

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a><span data-ttu-id="2342b-144">Windows Defender 攻击防护</span><span class="sxs-lookup"><span data-stu-id="2342b-144">Windows Defender Exploit Guard</span></span>
<span data-ttu-id="2342b-p107">Windows Defender 利用 Guard 是一组新的 Windows 10 主机入侵防护功能。有关 Windows Defender 利用 Guard、 的最低硬件要求，以及如何管理此功能的详细信息，请参阅[Windows Defender 利用 Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)。</span><span class="sxs-lookup"><span data-stu-id="2342b-p107">Windows Defender Exploit Guard is a new set of host intrusion prevention capabilities for Windows 10. For more info about Windows Defender Exploit Guard, the  minimum requirements, and how you can manage this feature, see [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).</span></span>

### <a name="deployment-management-and-configuration"></a><span data-ttu-id="2342b-147">部署、 管理和配置</span><span class="sxs-lookup"><span data-stu-id="2342b-147">Deployment, management, and configuration</span></span>
<span data-ttu-id="2342b-148">若要部署、 管理和配置 Windows Defender 利用 Guard，请按照下面的指南：</span><span class="sxs-lookup"><span data-stu-id="2342b-148">To deploy, manage, and configure Windows Defender Exploit Guard, follow the guidance here:</span></span>
* [<span data-ttu-id="2342b-149">利用保护</span><span class="sxs-lookup"><span data-stu-id="2342b-149">Exploit protection</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [<span data-ttu-id="2342b-150">攻击面保护</span><span class="sxs-lookup"><span data-stu-id="2342b-150">Attack surface protection</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [<span data-ttu-id="2342b-151">网络保护</span><span class="sxs-lookup"><span data-stu-id="2342b-151">Network protection</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [<span data-ttu-id="2342b-152">控制文件夹访问</span><span class="sxs-lookup"><span data-stu-id="2342b-152">Controlled folder access</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

<span data-ttu-id="2342b-p108">一系列评估主题可用来帮助评估的保护级别和 Windows Defender 利用保护的网络上的影响。也可以是在创建初始配置或作为快速入门指南有用和主题和指南定期将更新以用于配置和启用功能，以确保最大保护提供最有用的建议。有关详细信息，[利用 Guard 评估 Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)。</span><span class="sxs-lookup"><span data-stu-id="2342b-p108">You can use a series of evaluation topics to help evaluate the protection level and impact of Windows Defender Exploit Guard on your network. This can also be useful in creating an initial configuration or as a ‘quick start guide’ and the topics and guidance are regularly updated to provide the most useful recommendations for configuring and enabling features to ensure maximum protection. For more info,  [Evaluate Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).</span></span>

### <a name="reporting"></a><span data-ttu-id="2342b-156">报告</span><span class="sxs-lookup"><span data-stu-id="2342b-156">Reporting</span></span>
<span data-ttu-id="2342b-p109">您可以获取使用配置工具，如 System Center Configuration Manager 或 Intune 报告。您还可以获得通过使用 Windows 事件日志中您 SIEM 报告。如果您具有 Windows Defender ATP 许可证，您可以获取 Windows Defender AV 检测到报告和执行基本的补救。人员的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="2342b-p109">You can obtain reporting by using a configuration tool, such as System Center Configuration Manager or Intune. You can also obtain reporting by consuming Windows event logs in your SIEM. If you have a license for Windows Defender ATP, you can also obtain reporting into Windows Defender AV detections and perform basic remediation. For more info, see these resources:</span></span>
* [<span data-ttu-id="2342b-161">查看 Windows Defender 利用 Guard 事件</span><span class="sxs-lookup"><span data-stu-id="2342b-161">View Windows Defender Exploit Guard events</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [<span data-ttu-id="2342b-162">Windows Defender ATP 门户的概述 （英文)</span><span class="sxs-lookup"><span data-stu-id="2342b-162">Windows Defender ATP portal overview</span></span>](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a><span data-ttu-id="2342b-163">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2342b-163">Troubleshooting</span></span>
<span data-ttu-id="2342b-p110">可以执行基本故障排除或 （可选） 使用.cab 文件提供 Microsoft 并使用 Windows Defender 安全智能提交系统提交问题 （如误报）。若要了解如何，请参阅[向 Microsoft 提交问题](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="2342b-p110">You can perform basic troubleshooting or optionally provide Microsoft with .cab files and submit issues (such as false positives) by using the Windows Defender Security Intelligence submission system. To learn how, see [Submit issues to Microsoft](https://www.microsoft.com/wdsi/filesubmission).</span></span>


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a><span data-ttu-id="2342b-166">Windows Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="2342b-166">Windows Defender Advanced Threat Protection</span></span>
<span data-ttu-id="2342b-p111">Windows Defender ATP，仅适用于 Microsoft 企业 E5 365 计划，使企业客户，能够检测、 调查和响应他们的网络上的高级威胁的安全服务。有关 Windows Defender ATP、 的最低硬件要求，以及如何管理此功能的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2342b-p111">Windows Defender ATP, only available with the Microsoft 365 Enterprise E5 plan, is a security service that enables enterprise customers to detect, investigate, and respond to advanced threats on their networks. For more info about Windows Defender ATP, the minimum requirements, and how you can manage this feature, see:</span></span>

* [<span data-ttu-id="2342b-169">Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2342b-169">Windows Defender ATP</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [<span data-ttu-id="2342b-170">最低要求</span><span class="sxs-lookup"><span data-stu-id="2342b-170">Minimum requirements</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a><span data-ttu-id="2342b-171">部署、 管理和配置</span><span class="sxs-lookup"><span data-stu-id="2342b-171">Deployment, management, and configuration</span></span>
<span data-ttu-id="2342b-p112">若要部署 Windows Defender ATP，您需要确保您具有 Windows 许可证的权限。在验证已正确许可证后，您需要决定将存储数据的地理位置。之后，您可以开始加入到服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="2342b-p112">To deploy Windows Defender ATP, you’ll need to ensure you have the right Windows license. After verifying that you have the right license, you’ll need to decide the geolocation for where your data will be stored. After that, you can start onboarding endpoints to the service.</span></span>

<span data-ttu-id="2342b-175">这些步骤的详细信息，请参阅以下主要的主题：</span><span class="sxs-lookup"><span data-stu-id="2342b-175">For more details on these steps, see these main topics:</span></span> 

* [<span data-ttu-id="2342b-176">验证授权设置并完成设置</span><span class="sxs-lookup"><span data-stu-id="2342b-176">Validate licensing provisioning and complete set up</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="2342b-177">数据存储和隐私</span><span class="sxs-lookup"><span data-stu-id="2342b-177">Data storage and privacy</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="2342b-178">板载终结点和安装程序访问</span><span class="sxs-lookup"><span data-stu-id="2342b-178">Onboard endpoints and setup access</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a><span data-ttu-id="2342b-179">检测、 调查、 响应</span><span class="sxs-lookup"><span data-stu-id="2342b-179">Detect, investigate, respond</span></span>
<span data-ttu-id="2342b-p113">后成功入职培训终结点到服务，您可以启动调查从各种仪表板的警报。一旦已调查通知，您可以采取响应操作通知。</span><span class="sxs-lookup"><span data-stu-id="2342b-p113">After successfully onboarding endpoints to the service, you  can start investigating alerts from the various dashboards. Once you've investigated alerts, you can take response actions on alerts.</span></span> 

<span data-ttu-id="2342b-182">有关如何执行这些操作的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2342b-182">For more info on how to do these, see:</span></span>
* [<span data-ttu-id="2342b-183">Windows Defender ATP 门户的概述 （英文)</span><span class="sxs-lookup"><span data-stu-id="2342b-183">Windows Defender ATP portal overview</span></span>](https://go.microsoft.com/fwlink/?linkid=861596)
* [<span data-ttu-id="2342b-184">使用 Windows Defender ATP 门户</span><span class="sxs-lookup"><span data-stu-id="2342b-184">Use the Windows Defender ATP portal</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="2342b-185">采取响应措施</span><span class="sxs-lookup"><span data-stu-id="2342b-185">Take response actions</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a><span data-ttu-id="2342b-186">与其他产品和工具的集成</span><span class="sxs-lookup"><span data-stu-id="2342b-186">Integrate with other products and tools</span></span>
<span data-ttu-id="2342b-187">Windows Defender ATP 集成，并支持各种其他产品和工具以扩展其安全功能。</span><span class="sxs-lookup"><span data-stu-id="2342b-187">Windows Defender ATP integrates and supports various other products and tools to expand its security capabilities.</span></span> 

<span data-ttu-id="2342b-188">工具和其他产品的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2342b-188">For more info on the tools and other products, see:</span></span>
* [<span data-ttu-id="2342b-189">SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="2342b-189">SIEM tools</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="2342b-190">创建自定义通知</span><span class="sxs-lookup"><span data-stu-id="2342b-190">Create custom alerts</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="2342b-191">使用 Api</span><span class="sxs-lookup"><span data-stu-id="2342b-191">Use APIs</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="2342b-192">生成 Power BI 报表</span><span class="sxs-lookup"><span data-stu-id="2342b-192">Build Power BI reports</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a><span data-ttu-id="2342b-193">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2342b-193">Troubleshooting</span></span>
<span data-ttu-id="2342b-p114">您可能会遇到问题时入职培训或同时使用该产品。有关如何解决问题的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2342b-p114">You might encounter issues while onboarding or while using the product. For more info on how to address issues, see:</span></span>
* [<span data-ttu-id="2342b-196">解决入职培训问题</span><span class="sxs-lookup"><span data-stu-id="2342b-196">Troubleshooting onboarding issues</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="2342b-197">疑难解答 Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2342b-197">Troubleshooting Windows Defender ATP</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a><span data-ttu-id="2342b-198">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2342b-198">Next step</span></span>

[<span data-ttu-id="2342b-199">Windows 10 企业基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="2342b-199">Windows 10 Enterprise infrastructure exit criteria</span></span>](windows10-exit-criteria.md)
