---
title: 管理接收更新Microsoft Defender 防病毒和位置
description: 管理如何接收保护更新Microsoft Defender 防病毒回退顺序。
keywords: 更新， 安全基线， 保护， 回退顺序， ADL， MMPC， UNC， 文件路径， 共享， wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 35873b371e773e793ae966a338150e2e5e256a42
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926027"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a><span data-ttu-id="ab9d6-104">管理 Microsoft Defender 防病毒软件保护更新源</span><span class="sxs-lookup"><span data-stu-id="ab9d6-104">Manage the sources for Microsoft Defender Antivirus protection updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab9d6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ab9d6-105">**Applies to:**</span></span>

- [<span data-ttu-id="ab9d6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ab9d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

<span data-ttu-id="ab9d6-107">使防病毒保护保持最新至关重要。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-107">Keeping your antivirus protection up to date is critical.</span></span> <span data-ttu-id="ab9d6-108">有两个组件可以管理适用于Microsoft Defender 防病毒：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-108">There are two components to managing protection updates for Microsoft Defender Antivirus:</span></span> 
- <span data-ttu-id="ab9d6-109">*从* 何处下载更新;和</span><span class="sxs-lookup"><span data-stu-id="ab9d6-109">*Where* the updates are downloaded from; and</span></span> 
- <span data-ttu-id="ab9d6-110">*下载* 和应用更新时。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-110">*When* updates are downloaded and applied.</span></span> 

<span data-ttu-id="ab9d6-111">本文介绍如何指定从何处下载更新 (这也称为回退) 。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-111">This article describes how to specify from where updates should be downloaded (this is also known as the fallback order).</span></span> <span data-ttu-id="ab9d6-112">请参阅[管理Microsoft Defender 防病毒](manage-updates-baselines-microsoft-defender-antivirus.md)更新和应用基线主题，大致了解更新如何工作以及如何配置更新的其他方面 (如计划更新) 。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-112">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md) topic for an overview on how updates work, and how to configure other aspects of updates (such as scheduling updates).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab9d6-113">Microsoft Defender 防病毒安全智能更新通过 Windows Update 提供，从 2019 年 10 月 21 日星期一开始，所有安全智能更新都将以 SHA-2 为独占签名。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-113">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update and starting Monday, October 21, 2019, all security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="ab9d6-114">必须更新设备以支持 SHA-2，才能更新安全智能。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-114">Your devices must be updated to support SHA-2 in order to update your security intelligence.</span></span> <span data-ttu-id="ab9d6-115">若要了解更多信息，请参阅适用于 Windows[和 WSUS 的 2019 SHA-2 代码签名支持要求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-115">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>  


<a id="fallback-order"></a>

## <a name="fallback-order"></a><span data-ttu-id="ab9d6-116">回退顺序</span><span class="sxs-lookup"><span data-stu-id="ab9d6-116">Fallback order</span></span>

<span data-ttu-id="ab9d6-117">通常，根据网络配置，将终结点配置为从主源单独下载更新，然后按优先级顺序下载其他源。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-117">Typically, you configure endpoints to individually download updates from a primary source followed by other sources in order of priority, based on your network configuration.</span></span> <span data-ttu-id="ab9d6-118">更新按指定的顺序从源获取。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-118">Updates are obtained from sources in the order you specify.</span></span> <span data-ttu-id="ab9d6-119">如果源不可用，将立即使用列表中的下一个源。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-119">If a source is not available, the next source in the list is used immediately.</span></span>

<span data-ttu-id="ab9d6-120">发布更新时，会应用一些逻辑以最大程度地减小更新的大小。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-120">When updates are published, some logic is applied to minimize the size of the update.</span></span> <span data-ttu-id="ab9d6-121">在大多数情况下，仅下载并应用最新更新与当前安装 (这称为设备上 delta) 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-121">In most cases, only the differences between the latest update and the update that is currently installed (this is referred to as the delta) on the device is downloaded and applied.</span></span> <span data-ttu-id="ab9d6-122">但是，增量的大小取决于两个主要因素：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-122">However, the size of the delta depends on two main factors:</span></span>
- <span data-ttu-id="ab9d6-123">设备上上次更新的年数;和</span><span class="sxs-lookup"><span data-stu-id="ab9d6-123">The age of the last update on the device; and</span></span> 
- <span data-ttu-id="ab9d6-124">用于下载和应用更新的源。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-124">The source used to download and apply updates.</span></span> 

<span data-ttu-id="ab9d6-125">终结点上的更新越旧，下载越大。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-125">The older the updates on an endpoint, the larger the download will be.</span></span> <span data-ttu-id="ab9d6-126">但是，您还必须考虑下载频率。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-126">However, you must also consider download frequency as well.</span></span> <span data-ttu-id="ab9d6-127">更频繁的更新计划可能会导致更多的网络使用率，而不频繁的计划可能会导致每个下载的文件大小更大。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-127">A more frequent update schedule can result in more network usage, whereas a less-frequent schedule can result in larger file sizes per download.</span></span> 

<span data-ttu-id="ab9d6-128">可以在五个位置指定终结点应获取更新的位置：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-128">There are five locations where you can specify where an endpoint should obtain updates:</span></span> 

- [<span data-ttu-id="ab9d6-129">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="ab9d6-129">Microsoft Update</span></span>](https://support.microsoft.com/help/12373/windows-update-faq)
- [<span data-ttu-id="ab9d6-130">Windows服务器更新服务</span><span class="sxs-lookup"><span data-stu-id="ab9d6-130">Windows Server Update Service</span></span>](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [<span data-ttu-id="ab9d6-131">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ab9d6-131">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/core/servers/manage/updates)
- [<span data-ttu-id="ab9d6-132">网络文件共享</span><span class="sxs-lookup"><span data-stu-id="ab9d6-132">Network file share</span></span>](#unc-share)
- <span data-ttu-id="ab9d6-133">[Microsoft Defender 防病毒](https://www.microsoft.com/en-us/wdsi/defenderupdates)和其他 Microsoft 反恶意软件的安全 (策略和注册表中可能Microsoft 恶意软件防护中心 (MMPC) 安全智能，其以前名称.) </span><span class="sxs-lookup"><span data-stu-id="ab9d6-133">[Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) (Your policy and registry might have this listed as Microsoft Malware Protection Center (MMPC) security intelligence, its former name.)</span></span>

<span data-ttu-id="ab9d6-134">为了确保最佳保护级别，Microsoft 更新允许快速发布，这意味着频繁进行较小的下载。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-134">To ensure the best level of protection, Microsoft Update allows for rapid releases, which means smaller downloads on a frequent basis.</span></span> <span data-ttu-id="ab9d6-135">Windows服务器更新服务、Microsoft Endpoint Configuration Manager 和 Microsoft 安全智能更新源提供频率较少的更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-135">The Windows Server Update Service, Microsoft Endpoint Configuration Manager, and Microsoft security intelligence updates sources deliver less frequent updates.</span></span> <span data-ttu-id="ab9d6-136">因此，增量可能会更大，从而导致下载量更大。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-136">Thus, the delta can be larger, resulting in larger downloads.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ab9d6-137">如果在 Windows Server Update Service 或 Microsoft Update 之后将[Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx)安全智能页面更新设置为回退源，则仅在认为当前更新过期时从安全智能更新下载更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-137">If you have set [Microsoft Security intelligence page](https://www.microsoft.com/security/portal/definitions/adl.aspx) updates as a fallback source after Windows Server Update Service or Microsoft Update, updates are only downloaded from security intelligence updates when the current update is considered out-of-date.</span></span> <span data-ttu-id="ab9d6-138"> (默认情况下，这是连续七天无法从 Windows Server Update Service 或 Microsoft Update Services 应用更新) 。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-138">(By default, this is seven consecutive days of not being able to apply updates from the Windows Server Update Service or Microsoft Update services).</span></span>
> <span data-ttu-id="ab9d6-139">但是，你可以设置保护报告为过期 [前的天数](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-139">You can, however, [set the number of days before protection is reported as out-of-date](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span><p>
> <span data-ttu-id="ab9d6-140">从 2019 年 10 月 21 日星期一开始，安全智能更新将专门签署 SHA-2。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-140">Starting Monday, October 21, 2019, security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="ab9d6-141">必须更新设备以支持 SHA-2，才能获取最新的安全智能更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-141">Devices must be updated to support SHA-2 in order to get the latest security intelligence updates.</span></span> <span data-ttu-id="ab9d6-142">若要了解更多信息，请参阅适用于 Windows[和 WSUS 的 2019 SHA-2 代码签名支持要求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-142">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>

<span data-ttu-id="ab9d6-143">每个源都有一些典型方案，这些方案取决于网络的配置方式，以及发布更新的频繁情况，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-143">Each source has typical scenarios that depend on how your network is configured, in addition to how often they publish updates, as described in the following table:</span></span>

|<span data-ttu-id="ab9d6-144">位置</span><span class="sxs-lookup"><span data-stu-id="ab9d6-144">Location</span></span> | <span data-ttu-id="ab9d6-145">示例应用场景</span><span class="sxs-lookup"><span data-stu-id="ab9d6-145">Sample scenario</span></span> |
|---|---|
|<span data-ttu-id="ab9d6-146">Windows服务器更新服务</span><span class="sxs-lookup"><span data-stu-id="ab9d6-146">Windows Server Update Service</span></span> | <span data-ttu-id="ab9d6-147">使用 Windows 服务器更新服务管理网络更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-147">You are using Windows Server Update Service to manage updates for your network.</span></span>|
|<span data-ttu-id="ab9d6-148">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="ab9d6-148">Microsoft Update</span></span> | <span data-ttu-id="ab9d6-149">希望终结点直接连接到 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-149">You want your endpoints to connect directly to Microsoft Update.</span></span> <span data-ttu-id="ab9d6-150">这可用于不定期连接到企业网络的终结点，或者如果您没有使用 Windows 服务器更新服务来管理更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-150">This can be useful for endpoints that irregularly connect to your enterprise network, or if you do not use Windows Server Update Service to manage your updates.</span></span>|
|<span data-ttu-id="ab9d6-151">文件共享</span><span class="sxs-lookup"><span data-stu-id="ab9d6-151">File share</span></span> | <span data-ttu-id="ab9d6-152">你拥有未连接 Internet 的设备 (VM) 。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-152">You have non-Internet-connected devices (such as VMs).</span></span> <span data-ttu-id="ab9d6-153">可以使用连接到 Internet 的 VM 主机将更新下载到网络共享，VM 可从该共享获取更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-153">You can use your Internet-connected VM host to download the updates to a network share, from which the VMs can obtain the updates.</span></span> <span data-ttu-id="ab9d6-154">请参阅 [VDI 部署指南](deployment-vdi-microsoft-defender-antivirus.md) ，了解如何在虚拟桌面基础结构和 VDI (中使用) 文件共享。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-154">See the [VDI deployment guide](deployment-vdi-microsoft-defender-antivirus.md) for how file shares can be used in virtual desktop infrastructure (VDI) environments.</span></span>|
|<span data-ttu-id="ab9d6-155">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ab9d6-155">Microsoft Endpoint Manager</span></span> | <span data-ttu-id="ab9d6-156">你正在使用Microsoft Endpoint Manager更新终结点。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-156">You are using Microsoft Endpoint Manager to update your endpoints.</span></span>|
|<span data-ttu-id="ab9d6-157">安全智能更新Microsoft Defender 防病毒 Microsoft 反恶意软件 (以前称为 MMPC) </span><span class="sxs-lookup"><span data-stu-id="ab9d6-157">Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware (formerly referred to as MMPC)</span></span> |<span data-ttu-id="ab9d6-158">[确保你的设备已更新以支持 SHA-2。](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)</span><span class="sxs-lookup"><span data-stu-id="ab9d6-158">[Make sure your devices are updated to support SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span> <span data-ttu-id="ab9d6-159">Microsoft Defender 防病毒安全智能更新通过 Windows 更新提供，从 2019 年 10 月 21 日（星期一）开始，安全智能更新将专门签署 SHA-2。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-159">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update, and starting Monday October 21, 2019 security intelligence updates will be SHA-2 signed exclusively.</span></span> <br/><span data-ttu-id="ab9d6-160">下载最新的保护更新，因为最近感染或有助于为 VDI 部署预配强大的 [基本映像](deployment-vdi-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-160">Download the latest protection updates because of a recent infection or to help provision a strong, base image for [VDI deployment](deployment-vdi-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="ab9d6-161">此选项通常只用作最终回退源，而不是主源。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-161">This option should generally be used only as a final fallback source, and not the primary source.</span></span> <span data-ttu-id="ab9d6-162">只有在指定的天数内无法从 Windows 服务器更新服务或 Microsoft Update 下载更新时，才能[使用。](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)</span><span class="sxs-lookup"><span data-stu-id="ab9d6-162">It will only be used if updates cannot be downloaded from Windows Server Update Service or Microsoft Update for [a specified number of days](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span>|

<span data-ttu-id="ab9d6-163">可以管理更新源与组策略、Microsoft Endpoint Configuration Manager、PowerShell cmdlet 和 WMI 一同使用的顺序。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-163">You can manage the order in which update sources are used with Group Policy, Microsoft Endpoint Configuration Manager, PowerShell cmdlets, and WMI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab9d6-164">如果将 Windows 服务器更新服务设置为下载位置，则必须批准更新，而不考虑用于指定位置的管理工具。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-164">If you set Windows Server Update Service as a download location, you must approve the updates, regardless of the management tool you use to specify the location.</span></span> <span data-ttu-id="ab9d6-165">您可以使用 Windows Update Service 设置自动审批规则，当更新每天至少到达一次时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-165">You can set up an automatic approval rule with Windows Server Update Service, which might be useful as updates arrive at least once a day.</span></span> <span data-ttu-id="ab9d6-166">若要了解更多信息，请参阅[在独立 Windows Server Update Service 中同步终结点保护更新](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-166">To learn more, see [synchronize endpoint protection updates in standalone Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

<span data-ttu-id="ab9d6-167">本文中的过程首先介绍如何设置顺序，然后介绍如何设置文件共享选项（如果已启用此选项）。 </span><span class="sxs-lookup"><span data-stu-id="ab9d6-167">The procedures in this article first describe how to set the order, and then how to set up the **File share** option if you have enabled it.</span></span>

## <a name="use-group-policy-to-manage-the-update-location"></a><span data-ttu-id="ab9d6-168">使用组策略管理更新位置</span><span class="sxs-lookup"><span data-stu-id="ab9d6-168">Use Group Policy to manage the update location</span></span>

1. <span data-ttu-id="ab9d6-169">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="ab9d6-169">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="ab9d6-170">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-170">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="ab9d6-171">单击 **"策略\*\*\*\*"，然后单击"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="ab9d6-171">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="ab9d6-172">展开树以Windows **签名> Windows Defender >的组件并** 配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-172">Expand the tree to **Windows components > Windows Defender > Signature updates** and configure the following settings:</span></span>

   1.  <span data-ttu-id="ab9d6-173">双击定义 **下载安全智能更新** 的源的顺序设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-173">Double-click the **Define the order of sources for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   2.  <span data-ttu-id="ab9d6-174">输入源的顺序，用单个管道分隔，例如： `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` ，如以下屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-174">Enter the order of sources, separated by a single pipe, for example: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`, as shown in the following screenshot.</span></span>

   ![列出源顺序的组策略设置的屏幕截图](images/defender/wdav-order-update-sources.png)

   3. <span data-ttu-id="ab9d6-176">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-176">Click **OK**.</span></span> <span data-ttu-id="ab9d6-177">这将设置保护更新源的顺序。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-177">This will set the order of protection update sources.</span></span>

   4. <span data-ttu-id="ab9d6-178">双击"定义 **文件共享以下载安全智能** 更新"设置，并设置该选项为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="ab9d6-178">Double-click the **Define file shares for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   5. <span data-ttu-id="ab9d6-179">输入文件共享源。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-179">Enter the file share source.</span></span> <span data-ttu-id="ab9d6-180">如果有多个源，则按使用顺序输入每个源，用单个管道分隔。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-180">If you have multiple sources, enter each source in the order they should be used, separated by a single pipe.</span></span> <span data-ttu-id="ab9d6-181">使用 [标准 UNC](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) 表示法表示路径，例如 `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` ：。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-181">Use [standard UNC notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) for denoting the path, for example: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`.</span></span>  <span data-ttu-id="ab9d6-182">如果未输入任何路径，则 VM 下载更新时将跳过此源。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-182">If you do not enter any paths, then this source will be skipped when the VM downloads updates.</span></span>

   6. <span data-ttu-id="ab9d6-183">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-183">Click **OK**.</span></span> <span data-ttu-id="ab9d6-184">这将在定义源的顺序...组策略设置中引用该源时设置文件共享的顺序。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-184">This will set the order of file shares when that source is referenced in the **Define the order of sources...** group policy setting.</span></span>

> [!NOTE]
> <span data-ttu-id="ab9d6-185">对于 Windows 10 版本 1703（包括 1809）来说，策略路径是 **Windows Components > Microsoft Defender 防病毒 > Signature Updates** For Windows 10， version 1903， the policy path is Windows Components > Microsoft Defender 防病毒 > Security Intelligence **Updates**</span><span class="sxs-lookup"><span data-stu-id="ab9d6-185">For Windows 10, versions 1703 up to and including 1809, the policy path is **Windows Components > Microsoft Defender Antivirus > Signature Updates** For Windows 10, version 1903, the policy path is **Windows Components > Microsoft Defender Antivirus > Security Intelligence Updates**</span></span>

## <a name="use-configuration-manager-to-manage-the-update-location"></a><span data-ttu-id="ab9d6-186">使用 Configuration Manager 管理更新位置</span><span class="sxs-lookup"><span data-stu-id="ab9d6-186">Use Configuration Manager to manage the update location</span></span>

<span data-ttu-id="ab9d6-187">有关[配置当前分支Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates)的详细信息，请参阅 Configure Security intelligence Updates for Microsoft Endpoint Manager (for) 。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-187">See [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a><span data-ttu-id="ab9d6-188">使用 PowerShell cmdlet 管理更新位置</span><span class="sxs-lookup"><span data-stu-id="ab9d6-188">Use PowerShell cmdlets to manage the update location</span></span>

<span data-ttu-id="ab9d6-189">使用以下 PowerShell cmdlet 设置更新顺序。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-189">Use the following PowerShell cmdlets to set the update order.</span></span>

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
<span data-ttu-id="ab9d6-190">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-190">See the following articles for more information:</span></span>
- [<span data-ttu-id="ab9d6-191">Set-MpPreference -SignatureFallbackOrder</span><span class="sxs-lookup"><span data-stu-id="ab9d6-191">Set-MpPreference -SignatureFallbackOrder</span></span>](/powershell/module/defender/set-mppreference)
- [<span data-ttu-id="ab9d6-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span><span class="sxs-lookup"><span data-stu-id="ab9d6-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span></span>](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [<span data-ttu-id="ab9d6-193">使用 PowerShell cmdlet 配置并运行Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="ab9d6-193">Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab9d6-194">Defender cmdlet</span><span class="sxs-lookup"><span data-stu-id="ab9d6-194">Defender cmdlets</span></span>](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a><span data-ttu-id="ab9d6-195">使用 Windows Management Instruction (WMI) 管理更新位置</span><span class="sxs-lookup"><span data-stu-id="ab9d6-195">Use Windows Management Instruction (WMI) to manage the update location</span></span>

<span data-ttu-id="ab9d6-196">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-196">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

<span data-ttu-id="ab9d6-197">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-197">See the following articles for more information:</span></span>
- [<span data-ttu-id="ab9d6-198">Windows DefenderWMIv2 API</span><span class="sxs-lookup"><span data-stu-id="ab9d6-198">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a><span data-ttu-id="ab9d6-199">使用移动设备管理 (MDM) 管理更新位置</span><span class="sxs-lookup"><span data-stu-id="ab9d6-199">Use Mobile Device Management (MDM) to manage the update location</span></span>

<span data-ttu-id="ab9d6-200">有关[配置 MDM 的详细信息，请参阅策略 CSP - Defender/SignatureUpdateFallbackOrder。](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder)</span><span class="sxs-lookup"><span data-stu-id="ab9d6-200">See [Policy CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) for details on configuring MDM.</span></span>

## <a name="what-if-were-using-a-third-party-vendor"></a><span data-ttu-id="ab9d6-201">如果我们使用的是第三方供应商，该做什么？</span><span class="sxs-lookup"><span data-stu-id="ab9d6-201">What if we're using a third-party vendor?</span></span>

<span data-ttu-id="ab9d6-202">本文介绍如何配置和管理 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-202">This article describes how to configure and manage updates for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="ab9d6-203">但是，第三方供应商可用于执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-203">However, third-party vendors can be used to perform these tasks.</span></span> 

<span data-ttu-id="ab9d6-204">例如，假定 Contoso 已雇用 Fabrikam 来管理其安全解决方案，其中包括Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-204">For example, suppose that Contoso has hired Fabrikam to manage their security solution, which includes Microsoft Defender Antivirus.</span></span> <span data-ttu-id="ab9d6-205">Fabrikam 通常Windows [Management Instrumentation、PowerShell](./use-wmi-microsoft-defender-antivirus.md) [cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md)或 Windows[命令行](./command-line-arguments-microsoft-defender-antivirus.md)来部署修补程序和更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-205">Fabrikam typically uses [Windows Management Instrumentation](./use-wmi-microsoft-defender-antivirus.md), [PowerShell cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md), or [Windows command-line](./command-line-arguments-microsoft-defender-antivirus.md) to deploy patches and updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="ab9d6-206">Microsoft 不会测试第三方解决方案来管理Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-206">Microsoft does not test third-party solutions for managing Microsoft Defender Antivirus.</span></span>

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a><span data-ttu-id="ab9d6-207">为安全智能更新创建 UNC 共享</span><span class="sxs-lookup"><span data-stu-id="ab9d6-207">Create a UNC share for security intelligence updates</span></span>

<span data-ttu-id="ab9d6-208">使用 UNC/映射 (设置网络文件共享) 计划任务从 MMPC 站点下载安全智能更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-208">Set up a network file share (UNC/mapped drive) to download security intelligence updates from the MMPC site by using a scheduled task.</span></span>

1. <span data-ttu-id="ab9d6-209">在要预配共享和下载更新的系统上，创建一个要保存脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-209">On the system on which you want to provision the share and download the updates, create a folder to which you will save the script.</span></span>
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. <span data-ttu-id="ab9d6-210">创建将保存签名更新的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-210">Create the folder to which you will save the signature updates.</span></span>
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. <span data-ttu-id="ab9d6-211">从 下载 PowerShell [脚本](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-211">Download the PowerShell script from [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).</span></span>

4. <span data-ttu-id="ab9d6-212">单击 **"手动下载"。**</span><span class="sxs-lookup"><span data-stu-id="ab9d6-212">Click **Manual Download**.</span></span>

5. <span data-ttu-id="ab9d6-213">单击 **下载原始 nupkg 文件**。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-213">Click **Download the raw nupkg file**.</span></span>

6. <span data-ttu-id="ab9d6-214">提取文件。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-214">Extract the file.</span></span>

7. <span data-ttu-id="ab9d6-215">将文件SignatureDownloadCustomTask.ps1之前创建的文件夹 C：\Tool\PS-Scripts\ 。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-215">Copy the file SignatureDownloadCustomTask.ps1 to the folder you previously created, C:\Tool\PS-Scripts\ .</span></span>

8. <span data-ttu-id="ab9d6-216">使用命令行设置计划任务。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-216">Use the command line to set up the scheduled task.</span></span>
    > [!NOTE]
    > <span data-ttu-id="ab9d6-217">有两种类型的更新：完全更新和增量更新。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-217">There are two types of updates: full and delta.</span></span>
   - <span data-ttu-id="ab9d6-218">对于 x64 delta：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-218">For x64 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="ab9d6-219">对于 x64 完整版：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-219">For x64 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="ab9d6-220">对于 x86 增量：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-220">For x86 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="ab9d6-221">对于 x86 完整版：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-221">For x86 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

    > [!NOTE]
    > <span data-ttu-id="ab9d6-222">创建计划任务后，可以在 Microsoft\Windows\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="ab9d6-222">When the scheduled tasks are created, you can find these in the Task Scheduler under Microsoft\Windows\Windows Defender</span></span>
9. <span data-ttu-id="ab9d6-223">手动运行每个任务，并验证以下文件夹中 (mpam-d.exe、mpam-fe.exe 和 nis_full.exe) ， (您可能选择了不同的) ：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-223">Run each task manually and verify that you have data (mpam-d.exe, mpam-fe.exe, and nis_full.exe) in the following folders (you might have chosen different locations):</span></span>

   - <span data-ttu-id="ab9d6-224">C：\Temp\TempSigs\x86</span><span class="sxs-lookup"><span data-stu-id="ab9d6-224">C:\Temp\TempSigs\x86</span></span>
   - <span data-ttu-id="ab9d6-225">C：\Temp\TempSigs\x64</span><span class="sxs-lookup"><span data-stu-id="ab9d6-225">C:\Temp\TempSigs\x64</span></span>

   <span data-ttu-id="ab9d6-226">如果计划任务失败，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ab9d6-226">If the scheduled task fails, run the following commands:</span></span>

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```
    > [!NOTE]
    > <span data-ttu-id="ab9d6-227">问题还可能是由于执行策略。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-227">Issues could also be due to execution policy.</span></span>
    
10. <span data-ttu-id="ab9d6-228">创建一个指向 C：\Temp\TempSigs (例如 \\ server\updates) 。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-228">Create a share pointing to C:\Temp\TempSigs (e.g. \\server\updates).</span></span>
    > [!NOTE]
    > <span data-ttu-id="ab9d6-229">经过身份验证的用户至少必须具有"读取"访问权限。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-229">At a minimum, authenticated users must have "Read" access.</span></span>
11. <span data-ttu-id="ab9d6-230">将策略中的共享位置设置为共享。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-230">Set the share location in the policy to the share.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab9d6-231">请勿在路径中添加 x64 (或 x86) 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-231">Do not add the x64 (or x86) folder in the path.</span></span> <span data-ttu-id="ab9d6-232">进程mpcmdrun.exe自动添加它。</span><span class="sxs-lookup"><span data-stu-id="ab9d6-232">The mpcmdrun.exe process adds it automatically.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ab9d6-233">相关文章</span><span class="sxs-lookup"><span data-stu-id="ab9d6-233">Related articles</span></span>

- [<span data-ttu-id="ab9d6-234">部署Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="ab9d6-234">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab9d6-235">管理Microsoft Defender 防病毒更新并应用基线</span><span class="sxs-lookup"><span data-stu-id="ab9d6-235">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab9d6-236">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="ab9d6-236">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab9d6-237">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="ab9d6-237">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab9d6-238">管理移动设备和 VM 的更新</span><span class="sxs-lookup"><span data-stu-id="ab9d6-238">Manage updates for mobile devices and VMs</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab9d6-239">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="ab9d6-239">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
