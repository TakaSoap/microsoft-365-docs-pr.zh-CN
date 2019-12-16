---
title: Microsoft 威胁防护中的自动调查和响应
description: 简要了解 Microsoft 威胁防护中的自动调查和响应功能
keywords: 自动化, 调查, 警报, 触发器, 操作, 修正
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 8c82c00bb785086da424072581252e6085937921
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967905"
---
# <a name="automated-investigation-and-response-air-in-microsoft-threat-protection"></a><span data-ttu-id="a62bd-104">Microsoft 威胁防护中的自动调查和响应 (AIR)</span><span class="sxs-lookup"><span data-stu-id="a62bd-104">Automated investigation and response (AIR) in Microsoft Threat Protection</span></span>

<span data-ttu-id="a62bd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a62bd-105">**Applies to:**</span></span>
- <span data-ttu-id="a62bd-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="a62bd-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

## <a name="your-virtual-analyst"></a><span data-ttu-id="a62bd-107">你的虚拟分析师</span><span class="sxs-lookup"><span data-stu-id="a62bd-107">Your virtual analyst</span></span>

<span data-ttu-id="a62bd-108">触发安全警报后，安全运营团队将负责调查这些警报并采取措施以保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="a62bd-108">As security alerts are triggered, it’s up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="a62bd-109">对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。</span><span class="sxs-lookup"><span data-stu-id="a62bd-109">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="a62bd-110">安全运营团队可能对必须监视和防范的大量威胁感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="a62bd-110">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> 

<span data-ttu-id="a62bd-111">想象一下，你的第 1 层/第 2 层安全运营团队中有一名虚拟分析师。</span><span class="sxs-lookup"><span data-stu-id="a62bd-111">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="a62bd-112">虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。</span><span class="sxs-lookup"><span data-stu-id="a62bd-112">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="a62bd-113">虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。</span><span class="sxs-lookup"><span data-stu-id="a62bd-113">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="a62bd-114">这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。</span><span class="sxs-lookup"><span data-stu-id="a62bd-114">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="a62bd-115">这种情况听起来像科幻小说？绝不是！</span><span class="sxs-lookup"><span data-stu-id="a62bd-115">If this scenario sounds like science fiction, it’s not!</span></span> <span data-ttu-id="a62bd-116">这种虚拟分析师是 Microsoft 威胁防护套件的一部分，它的名称是“自动调查和响应”\*\* (AIR)。</span><span class="sxs-lookup"><span data-stu-id="a62bd-116">Such a virtual analyst is part of your Microsoft Threat Protection suite, and its name is *automated investigation and response* (AIR).</span></span>

<span data-ttu-id="a62bd-117">AIR 使你的安全运营团队能够极大地提高组织处理安全警报和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="a62bd-117">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="a62bd-118">借助 AIR，可以减少处理调查和修正活动的成本，并充分利用威胁防护套件。</span><span class="sxs-lookup"><span data-stu-id="a62bd-118">With AIR, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="a62bd-119">AIR 通过以下方式为安全运营团队提供帮助：</span><span class="sxs-lookup"><span data-stu-id="a62bd-119">AIR helps your security operations team by:</span></span>

1.  <span data-ttu-id="a62bd-120">确定是否需要针对威胁执行操作；</span><span class="sxs-lookup"><span data-stu-id="a62bd-120">Determining whether a threat requires action;</span></span>
2.  <span data-ttu-id="a62bd-121">执行（或建议执行）任何必要的修正操作；</span><span class="sxs-lookup"><span data-stu-id="a62bd-121">Performing (or recommending) any necessary remediation actions;</span></span>
3.  <span data-ttu-id="a62bd-122">确定应进行哪些其他调查；以及</span><span class="sxs-lookup"><span data-stu-id="a62bd-122">Determining what additional investigations should occur; and</span></span>
4.  <span data-ttu-id="a62bd-123">根据需要对其他警报重复此过程。</span><span class="sxs-lookup"><span data-stu-id="a62bd-123">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="a62bd-124">自动调查流程</span><span class="sxs-lookup"><span data-stu-id="a62bd-124">The automated investigation process</span></span>

<span data-ttu-id="a62bd-125">**警报** > **事件** > **自动调查** > **裁定** > **修正操作**</span><span class="sxs-lookup"><span data-stu-id="a62bd-125">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="a62bd-126">在较高级别，触发的警报会创建事件，这可以启动自动调查。</span><span class="sxs-lookup"><span data-stu-id="a62bd-126">At a high level, a triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="a62bd-127">该调查可能会导致执行一项或多项修正操作。</span><span class="sxs-lookup"><span data-stu-id="a62bd-127">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="a62bd-128">在 Microsoft 威胁防护中，每次自动调查都会将 Azure 高级威胁防护 (Azure ATP)、Microsoft Defender 高级威胁防护 (Microsoft Defender ATP) 和 Office 365 高级威胁防护 (Office 365 ATP) 之间的信号相关联，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="a62bd-128">In Microsoft Threat Protection, each automated investigation correlates signals across Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP), and Office 365 Advanced Threat Protection (Office 365 ATP), as summarized in the following table:</span></span> 

|<span data-ttu-id="a62bd-129">实体</span><span class="sxs-lookup"><span data-stu-id="a62bd-129">Entities</span></span> |<span data-ttu-id="a62bd-130">威胁防护服务</span><span class="sxs-lookup"><span data-stu-id="a62bd-130">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="a62bd-131">设备（也称为终结点）</span><span class="sxs-lookup"><span data-stu-id="a62bd-131">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="a62bd-132">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a62bd-132">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="a62bd-133">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="a62bd-133">Azure ATP role groups</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="a62bd-134">电子邮件内容（邮箱中的文件和邮件）</span><span class="sxs-lookup"><span data-stu-id="a62bd-134">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="a62bd-135">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="a62bd-135">Office 365 ATP Safe Links</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |


<span data-ttu-id="a62bd-136">每次调查都会针对调查的每条证据生成裁定（*恶意*、*可疑*或*干净*）。</span><span class="sxs-lookup"><span data-stu-id="a62bd-136">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *Clean*) for each piece of evidence investigated.</span></span> <span data-ttu-id="a62bd-137">根据威胁的类型和最终裁定结果，自动执行修正操作，或者在组织的安全运营团队批准后执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="a62bd-137">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization’s security operations team.</span></span> <span data-ttu-id="a62bd-138">"[操作中心](mtp-action-center.md)中列出了待处理和已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="a62bd-138">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="a62bd-139">运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。</span><span class="sxs-lookup"><span data-stu-id="a62bd-139">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="a62bd-140">如果在其他位置看到受影响的实体，自动调查将扩大其范围，以包括该实体，并且将运行常规安全性 Playbook。</span><span class="sxs-lookup"><span data-stu-id="a62bd-140">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="a62bd-141">并非每个警报都会触发自动调查，也不是每个调查都会导致自动修正操作；这一切都取决于你的组织配置 AIR 的方式。</span><span class="sxs-lookup"><span data-stu-id="a62bd-141">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how AIR is configured for your organization.</span></span> 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a><span data-ttu-id="a62bd-142">Microsoft 威胁防护中的 AIR 要求</span><span class="sxs-lookup"><span data-stu-id="a62bd-142">Requirements for AIR in Microsoft Threat Protection</span></span>

| | |
|--|--|
|<span data-ttu-id="a62bd-143">订阅要求</span><span class="sxs-lookup"><span data-stu-id="a62bd-143">Subscription requirements</span></span> |<span data-ttu-id="a62bd-144">- 已启用标识和威胁防护的 Microsoft 365 E5 或 Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="a62bd-144">- Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection</span></span><br/><span data-ttu-id="a62bd-145">- 请参阅 [Microsoft 365 计划](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview#plans)</span><span class="sxs-lookup"><span data-stu-id="a62bd-145">- See [Microsoft 365 plans](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview#plans)</span></span>|
|<span data-ttu-id="a62bd-146">网络要求</span><span class="sxs-lookup"><span data-stu-id="a62bd-146">Network requirements</span></span> |<span data-ttu-id="a62bd-147">- 已启用 [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)</span><span class="sxs-lookup"><span data-stu-id="a62bd-147">- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) enabled</span></span><br/><span data-ttu-id="a62bd-148">- 已配置 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS)</span><span class="sxs-lookup"><span data-stu-id="a62bd-148">- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) configured</span></span><br/><span data-ttu-id="a62bd-149">- [与 Azure ATP 集成的 MCAS](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span><span class="sxs-lookup"><span data-stu-id="a62bd-149">- [MCAS integrated with Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span> |
|<span data-ttu-id="a62bd-150">Windows 计算机要求</span><span class="sxs-lookup"><span data-stu-id="a62bd-150">Windows machine requirements</span></span> |<span data-ttu-id="a62bd-151">- 已安装 Windows 10 版本 1709 或更高版本（请参阅 [Windows 10 发行信息](https://docs.microsoft.com/windows/release-information/)）</span><span class="sxs-lookup"><span data-stu-id="a62bd-151">- Windows 10, version 1709 or later installed (See [Windows 10 release information](https://docs.microsoft.com/windows/release-information/))</span></span><br/><span data-ttu-id="a62bd-152">- 已配置 [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="a62bd-152">- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) configured</span></span> <br/><span data-ttu-id="a62bd-153">- 已配置 [Windows Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</span><span class="sxs-lookup"><span data-stu-id="a62bd-153">Windows Defender Antivirus</span></span> |
|<span data-ttu-id="a62bd-154">权限</span><span class="sxs-lookup"><span data-stu-id="a62bd-154">Permissions</span></span> |<span data-ttu-id="a62bd-155">- 若要*配置* AIR，必须在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配\*\*\*\*“全局管理员”或“安全管理员”\*\*\*\* 角色。</span><span class="sxs-lookup"><span data-stu-id="a62bd-155">- To *configure* AIR, you must have the **Global Administrator** or **Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or in the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span><br/><br/><span data-ttu-id="a62bd-156">- 若要*使用* AIR 功能，请参阅[操作中心任务所需的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="a62bd-156">- To *use* AIR capabilities, see [Required permissions for Action center tasks](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span> |

## <a name="next-steps"></a><span data-ttu-id="a62bd-157">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a62bd-157">Next steps</span></span>

- [<span data-ttu-id="a62bd-158">批准或拒绝与自动调查和响应相关的操作</span><span class="sxs-lookup"><span data-stu-id="a62bd-158">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="a62bd-159">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="a62bd-159">Learn more about the Action center</span></span>](mtp-action-center.md)
