---
title: 阶段 3：Windows 10 企业版基础结构退出条件
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 确保你的配置符合 Microsoft 365 企业版针对 Windows 10 企业版的条件。
ms.openlocfilehash: 42d8ec912a70aecef49672682c25f5e42c4bbe21
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085551"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="1f0fb-103">阶段 3：Windows 10 企业版基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="1f0fb-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![阶段 3：Windows 10 企业版](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="1f0fb-105">确保你的 Windows 10 企业版基础结构符合以下必需条件，以及你认为可选的那些条件。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-105">Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="1f0fb-106">必需：已添加 Microsoft 365 域并已对其验证</span><span class="sxs-lookup"><span data-stu-id="1f0fb-106">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="1f0fb-107">Office 365 和 Intune 订阅的 Azure AD 租户是使用 Internet 域名（例如，contoso.com）配置的，而不是仅使用包含“onmicrosoft.com”的域名配置的。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-107">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="1f0fb-p101">如果不这样做，则会在身份验证方法中限制你可以进行的配置。例如，传递和联合身份验证无法使用“onmicrosoft.com”域名。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="1f0fb-110">如果需要，可在[步骤 1](windows10-prepare-your-org.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-110">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="1f0fb-111">可选：已添加用户并已对其许可</span><span class="sxs-lookup"><span data-stu-id="1f0fb-111">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="1f0fb-112">已添加对应于用户的帐户（直接添加到 Office 365 和 Intune 订阅的 Azure AD 租户，或从本地 Active Directory 域服务 (AD DS) 中的目录同步）。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-112">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="1f0fb-113">添加用户后，即可向其分配 Microsoft 365 企业版许可证（可直接分配为全局或用户管理员，或通过组成员身份自动分配）。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-113">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="1f0fb-114">如果需要，可在[步骤 1](windows10-prepare-your-org.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-114">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="1f0fb-115">可选：已启用诊断</span><span class="sxs-lookup"><span data-stu-id="1f0fb-115">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="1f0fb-116">已使用组策略、Microsoft Intune、注册表编辑器或命令提示符启用了诊断数据设置。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-116">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="1f0fb-117">如果需要，可在[步骤 1](windows10-prepare-your-org.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-117">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="1f0fb-118">需要就地升级：为操作系统部署创建 Configuration Manager 任务序列</span><span class="sxs-lookup"><span data-stu-id="1f0fb-118">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="1f0fb-119">若要对运行 Windows 7 或 Windows 8.1 的设备启动 Configuration Manager 任务序列以执行就地升级，必须完成以下设置：</span><span class="sxs-lookup"><span data-stu-id="1f0fb-119">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="1f0fb-120">设置合适的 Windows 诊断数据级别</span><span class="sxs-lookup"><span data-stu-id="1f0fb-120">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="1f0fb-121">已验证 Windows 升级准备就绪情况</span><span class="sxs-lookup"><span data-stu-id="1f0fb-121">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="1f0fb-122">已创建一个 Configuration Manager 任务序列，其中包括使用 Windows 10 OS 映像的设备集合和操作系统部署</span><span class="sxs-lookup"><span data-stu-id="1f0fb-122">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="1f0fb-p102">完成以上设置后，即可对已准备好升级 Windows 的设备执行就地升级。为了发挥 Microsoft 365 企业版的最佳功能，请尽量将运行 Windows 7 和 Windows 8.1 的设备进行升级。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="1f0fb-p103">每个运行 Windows 10 企业版的设备都可以体验 Microsoft 365 企业版集成解决方案带来的优势。其他运行 Windows 7 或 Windows 8.1 的设备将无法使用 Windows 10 企业版的云连接技术和高级功能。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="1f0fb-127">如果需要，可在[步骤 2](windows10-deploy-inplaceupgrade.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-127">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="1f0fb-128">需要新设备：配置的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="1f0fb-128">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="1f0fb-129">若要使用 Windows Autopilot 对新设备部署和自定义 Windows 10 企业版，必须完成以下设置：</span><span class="sxs-lookup"><span data-stu-id="1f0fb-129">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="1f0fb-130">已配置合适的 Windows 诊断数据级别</span><span class="sxs-lookup"><span data-stu-id="1f0fb-130">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="1f0fb-131">已配置 Windows Autopilot 的先决条件，其中包括：</span><span class="sxs-lookup"><span data-stu-id="1f0fb-131">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="1f0fb-132">设备注册和 OOBE 自定义</span><span class="sxs-lookup"><span data-stu-id="1f0fb-132">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="1f0fb-133">针对 OOBE 的公司品牌塑造</span><span class="sxs-lookup"><span data-stu-id="1f0fb-133">Company branding for OOBE</span></span>
   - <span data-ttu-id="1f0fb-134">Microsoft Intune 中的 MDM 自动注册</span><span class="sxs-lookup"><span data-stu-id="1f0fb-134">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="1f0fb-135">Windows Autopilot 所使用的云服务的网络连接</span><span class="sxs-lookup"><span data-stu-id="1f0fb-135">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="1f0fb-136">已预安装 Windows 10 版本 1703 或更高版本的设备</span><span class="sxs-lookup"><span data-stu-id="1f0fb-136">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="1f0fb-137">已为组织选择了 Windows Autopilot 部署计划</span><span class="sxs-lookup"><span data-stu-id="1f0fb-137">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="1f0fb-138">一旦 Windows Autopilot 配置准备就绪，即可使用它来为以下设备配置和自定义开箱即用 (OOBE) 的 Windows 10 企业版体验：</span><span class="sxs-lookup"><span data-stu-id="1f0fb-138">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="1f0fb-139">新设备</span><span class="sxs-lookup"><span data-stu-id="1f0fb-139">New devices</span></span>
- <span data-ttu-id="1f0fb-140">组织中已完成自带设置的设备。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-140">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="1f0fb-141">Windows Autopilot 配置设备并将其连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-141">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="1f0fb-142">如未安装 Windows Autopilot，则必须手动配置新设备，包括与 Azure AD 的连接。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-142">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="1f0fb-143">如果需要，可在[步骤 3](windows10-deploy-autopilot.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-143">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="1f0fb-144">可选：你正在使用 Windows Analytics 设备运行状况来监控基于 Windows 10 企业版的设备。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-144">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="1f0fb-p104">你将监视器中有关设备运行状况的信息与设备运行状况结合使用，以检测和修正影响最终用户的问题。快速解决最终用户的问题可减少你的支持成本，并可向用户展示 IT 部门对 Windows 10 企业版的承诺，以帮助推动整个组织使用 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="1f0fb-147">如果需要，可在[步骤 4](windows10-enable-windows-analytics.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-147">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="1f0fb-148">必需：你正在使用 Windows Defender 防病毒或正在使用你自己的反恶意软件解决方案</span><span class="sxs-lookup"><span data-stu-id="1f0fb-148">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="1f0fb-p105">已部署 Windows Defender 防病毒软件或已部署你自己的防病毒解决方案来保护运行 Windows 10 企业版的设备免受恶意软件的侵害。如果已部署 Windows Defender 防病毒软件，则已实施报告方法（例如，Microsoft Endpoint Configuration Manager 或 Microsoft Intune）来监控防病毒事件和活动。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as Microsoft Endpoint Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="1f0fb-151">如果需要，可在[步骤 5](windows10-enable-security-features.md#windows10-sec-av) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-151">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="1f0fb-152">必需：你正在使用 Windows Defender 攻击防护</span><span class="sxs-lookup"><span data-stu-id="1f0fb-152">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="1f0fb-153">已部署 Windows Defender 攻击防护来保护运行 Windows 10 企业版的设备免受入侵，并已实施报告方法（例如，Configuration Manager 或 Microsoft Intune）来监控入侵事件和活动。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-153">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="1f0fb-154">如果需要，可在[步骤 5](windows10-enable-security-features.md#windows10-sec-eg) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-154">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a><span data-ttu-id="1f0fb-155">必需：你正在使用 Microsoft Defender 高级威胁防护（仅限 Microsoft 365 E5）</span><span class="sxs-lookup"><span data-stu-id="1f0fb-155">Required: You are using Microsoft Defender Advanced Threat Protection (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="1f0fb-156">已部署 Microsoft Defender 高级威胁防护 (ATP)，以针对运行 Windows 10 企业版的网络和设备检测、调查和响应高级威胁。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-156">You deployed Microsoft Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="1f0fb-157">（可选）已将 Microsoft Defender ATP 与其他工具集成，以扩展其功能。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-157">Optionally, you have integrated Microsoft Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="1f0fb-158">如果需要，可在[步骤 5](windows10-enable-security-features.md#windows10-sec-atp) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-158">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="1f0fb-159">结果和后续步骤</span><span class="sxs-lookup"><span data-stu-id="1f0fb-159">Results and next steps</span></span>

<span data-ttu-id="1f0fb-160">你的 Windows 10 企业版基础架构已准备好开始在新设备上安装并在运行以前版本的 Windows 的设备上就地升级，并且你正在使用 Windows 10 企业版的主要安全功能。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-160">Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.</span></span>

|||
|:-------|:-----|
|![阶段 4：Office 365 专业增强版](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="1f0fb-162">如果你正在执行 Microsoft 365 企业版端到端部署的各个阶段，下一个阶段是 [Office 365 专业增强版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="1f0fb-162">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
