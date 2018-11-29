---
title: 阶段 3：Windows 10 企业版基础结构退出条件
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 06/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 确保你的配置符合 Microsoft 365 企业版针对 Windows 10 企业版的条件。
ms.openlocfilehash: 7ac79fec93e4b4aae0b075891917e2f88432b80f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865788"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="c9558-103">阶段 3：Windows 10 企业版基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="c9558-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="c9558-104">如果 Windows 10 企业版基础结构符合以下条件，则可继续第 4 阶段。</span><span class="sxs-lookup"><span data-stu-id="c9558-104">If your Windows 10 Enterprise infrastructure meets the following conditions, you’re ready to move to Phase 4.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="c9558-105">必需：已添加 Microsoft 365 域并已对其验证</span><span class="sxs-lookup"><span data-stu-id="c9558-105">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="c9558-106">Office 365 和 Intune 订阅的 Azure AD 租户是使用 Internet 域名（例如，contoso.com）配置的，而不是仅使用包含“onmicrosoft.com”的域名配置的。</span><span class="sxs-lookup"><span data-stu-id="c9558-106">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="c9558-p101">如果不这样做，则会在身份验证方法中限制你可以进行的配置。例如，传递和联合身份验证无法使用“onmicrosoft.com”域名。</span><span class="sxs-lookup"><span data-stu-id="c9558-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="c9558-109">如果需要，可在[步骤 1](windows10-prepare-your-org.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="c9558-109">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="c9558-110">可选：已添加用户并已对其许可</span><span class="sxs-lookup"><span data-stu-id="c9558-110">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="c9558-111">已添加对应于用户的帐户（直接添加到 Office 365 和 Intune 订阅的 Azure AD 租户，或从本地 Windows Server AD 中的目录同步）。</span><span class="sxs-lookup"><span data-stu-id="c9558-111">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Windows Server AD.</span></span>

<span data-ttu-id="c9558-112">添加用户后，即可向其分配 Microsoft 365 企业版许可证（可直接分配为全局或用户管理员，或通过组成员身份自动分配）。</span><span class="sxs-lookup"><span data-stu-id="c9558-112">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="c9558-113">如果需要，可在[步骤 1](windows10-prepare-your-org.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="c9558-113">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="c9558-114">可选：已启用诊断</span><span class="sxs-lookup"><span data-stu-id="c9558-114">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="c9558-115">已使用组策略、Microsoft Intune、注册表编辑器或命令提示符启用了诊断数据设置。</span><span class="sxs-lookup"><span data-stu-id="c9558-115">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="c9558-116">如果需要，可在[步骤 1](windows10-prepare-your-org.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="c9558-116">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="c9558-117">需要就地升级：为操作系统部署创建 Configuration Manager 任务序列</span><span class="sxs-lookup"><span data-stu-id="c9558-117">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="c9558-118">若要对运行 Windows 7 或 Windows 8.1 的设备启动 Configuration Manager 任务序列以执行就地升级，必须完成以下设置：</span><span class="sxs-lookup"><span data-stu-id="c9558-118">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="c9558-119">设置合适的 Windows 诊断数据级别</span><span class="sxs-lookup"><span data-stu-id="c9558-119">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="c9558-120">验证 Windows 升级准备就绪情况</span><span class="sxs-lookup"><span data-stu-id="c9558-120">Verify the readiness to upgrade Windows</span></span>
- <span data-ttu-id="c9558-121">创建一个 Configuration Manager 任务序列，其中包括使用 Windows 10 OS 映像的设备集合和操作系统部署</span><span class="sxs-lookup"><span data-stu-id="c9558-121">Create a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="c9558-p102">完成以上设置后，即可对已准备好升级 Windows 的设备执行就地升级。为了发挥 Microsoft 365 企业版的最佳功能，请尽量将运行 Windows 7 和 Windows 8.1 的设备进行升级。</span><span class="sxs-lookup"><span data-stu-id="c9558-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="c9558-p103">每个运行 Windows 10 企业版的设备都可以体验 Microsoft 365 企业版集成解决方案带来的优势。其他运行 Windows 7 或 Windows 8.1 的设备将无法使用 Windows 10 企业版的云连接技术和高级功能。</span><span class="sxs-lookup"><span data-stu-id="c9558-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="c9558-126">如果需要，可在[步骤 2](windows10-deploy-inplaceupgrade.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="c9558-126">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="c9558-127">需要新设备：配置的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="c9558-127">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="c9558-128">若要使用 Windows Autopilot 对新设备部署和自定义 Windows 10 企业版，必须完成以下设置：</span><span class="sxs-lookup"><span data-stu-id="c9558-128">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="c9558-129">设置合适的 Windows 诊断数据级别</span><span class="sxs-lookup"><span data-stu-id="c9558-129">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="c9558-130">已完成 Windows Autopilot 的先决条件，其中包括：</span><span class="sxs-lookup"><span data-stu-id="c9558-130">Completed the prerequisites for Windows Autopilot, which include:</span></span>
- <span data-ttu-id="c9558-131">设备注册和 OOBE 自定义</span><span class="sxs-lookup"><span data-stu-id="c9558-131">Device registration and OOBE customization</span></span>
- <span data-ttu-id="c9558-132">针对 OOBE 的公司品牌塑造</span><span class="sxs-lookup"><span data-stu-id="c9558-132">Company branding for OOBE</span></span>
- <span data-ttu-id="c9558-133">Microsoft Intune 中的 MDM 自动注册</span><span class="sxs-lookup"><span data-stu-id="c9558-133">MDM auto-enrollment in Microsoft Intune</span></span>
- <span data-ttu-id="c9558-134">Windows Autopilot 所使用的云服务的网络连接</span><span class="sxs-lookup"><span data-stu-id="c9558-134">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="c9558-135">设备必须已预安装 Windows 10 版本 1703 或更高版本</span><span class="sxs-lookup"><span data-stu-id="c9558-135">Devices must be pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="c9558-136">已为组织选择了 Windows Autopilot 部署计划</span><span class="sxs-lookup"><span data-stu-id="c9558-136">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="c9558-137">一旦 Windows Autopilot 配置准备就绪，即可使用它来为以下设备配置和自定义开箱即用 (OOBE) 的 Windows 10 企业版体验：</span><span class="sxs-lookup"><span data-stu-id="c9558-137">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="c9558-138">新设备</span><span class="sxs-lookup"><span data-stu-id="c9558-138">New devices</span></span>
- <span data-ttu-id="c9558-139">组织中已完成自带设置的设备。</span><span class="sxs-lookup"><span data-stu-id="c9558-139">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="c9558-140">Windows Autopilot 配置设备并将其连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="c9558-140">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="c9558-141">如未安装 Windows Autopilot，则必须手动配置新设备，包括与 Azure AD 的连接。</span><span class="sxs-lookup"><span data-stu-id="c9558-141">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="c9558-142">如果需要，可在[步骤 3](windows10-deploy-autopilot.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="c9558-142">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="c9558-143">可选：你正在使用 Windows Analytics 设备运行状况来监控基于 Windows 10 企业版的设备。</span><span class="sxs-lookup"><span data-stu-id="c9558-143">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="c9558-p104">你将监视器中有关设备运行状况的信息与设备运行状况结合使用，以检测和修正影响最终用户的问题。快速解决最终用户的问题可减少你的支持成本，并可向用户展示 IT 部门对 Windows 10 企业版的承诺，以帮助推动整个组织使用 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="c9558-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="c9558-146">如果需要，可在[步骤 4](windows10-enable-windows-analytics.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="c9558-146">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="c9558-147">必需：你正在使用 Windows Defender 防病毒或正在使用你自己的反恶意软件解决方案</span><span class="sxs-lookup"><span data-stu-id="c9558-147">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="c9558-p105">已部署 Windows Defender 防病毒或已部署你自己的防病毒解决方案，以保护运行 Windows 10 企业版的设备免受恶意软件的侵害。如果已部署 Windows Defender 防病毒，则已实施报告方法（例如，System Center Configuration Manager 或 Microsoft Intune），以监控防病毒事件和活动。</span><span class="sxs-lookup"><span data-stu-id="c9558-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="c9558-150">如果需要，可在[步骤 5](windows10-enable-security-features.md#windows10-sec-av) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="c9558-150">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="c9558-151">必需：你正在使用 Windows Defender 攻击防护</span><span class="sxs-lookup"><span data-stu-id="c9558-151">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="c9558-152">已部署 Windows Defender 攻击防护，以保护运行 Windows 10 企业版的设备免受入侵，并已实施报告方法（例如，System Center Configuration Manager 或 Microsoft Intune），以监控入侵事件和活动。</span><span class="sxs-lookup"><span data-stu-id="c9558-152">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="c9558-153">如果需要，可在[步骤 5](windows10-enable-security-features.md#windows10-sec-eg) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="c9558-153">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-windows-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="c9558-154">必需：你正在使用 Windows Defender 高级威胁防护（仅限 Microsoft 365 企业版 E5）</span><span class="sxs-lookup"><span data-stu-id="c9558-154">Required: You are using Windows Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="c9558-155">已部署 Windows Defender 高级威胁防护 (ATP)，以针对运行 Windows 10 企业版的网络和设备检测、调查和响应高级威胁。</span><span class="sxs-lookup"><span data-stu-id="c9558-155">You deployed Windows Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="c9558-156">（可选）已将 Windows Defender ATP 与其他工具集成，以扩展其功能。</span><span class="sxs-lookup"><span data-stu-id="c9558-156">Optionally, you have integrated Windows Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="c9558-157">如果需要，可在[步骤 5](windows10-enable-security-features.md#windows10-sec-atp) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="c9558-157">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>


## <a name="next-phase"></a><span data-ttu-id="c9558-158">下一阶段</span><span class="sxs-lookup"><span data-stu-id="c9558-158">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="c9558-159">Microsoft 365 企业版端到端部署过程中的下一个阶段是 [Office 365 专业增强版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="c9558-159">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
