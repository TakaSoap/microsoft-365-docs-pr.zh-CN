---
title: Microsoft 365 企业版底层基础结构
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解组织中部署 Microsoft 365 企业版底层基础结构的主要阶段。
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865398"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="de9d4-103">Microsoft 365 企业版底层基础结构</span><span class="sxs-lookup"><span data-stu-id="de9d4-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="de9d4-104">若要充分实现 Microsoft 365 企业版的好处，请从其底层基础结构开始部署。</span><span class="sxs-lookup"><span data-stu-id="de9d4-104">To fully realize the benefits of Microsoft 365 Enterprise, you’ll begin your deployment with its foundation infrastructure.</span></span> 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a><span data-ttu-id="de9d4-105">部署 Microsoft 365 企业版的底层基础结构</span><span class="sxs-lookup"><span data-stu-id="de9d4-105">Foundation infrastructure for deploying Microsoft 365 Enterprise</span></span>

<span data-ttu-id="de9d4-p101">底层基础结构是部署生产力工作负载（如 Office 365 中的 Microsoft Teams 和 Exchange Online）和方案（如迁移到 Microsoft 365 和自动执行客户端更新）的基础。它提供了智能安全性和集成功能，不仅简化了持续管理，还确保客户端软件更新有最新生产力和安全增强。</span><span class="sxs-lookup"><span data-stu-id="de9d4-p101">The foundation infrastructure is the groundwork upon which you can deploy productivity workloads (such as Microsoft Teams and Exchange Online in Office 365) and scenarios (such as migrating to Microsoft 365 and automating client updates). It provides intelligent security and integration that simplifies ongoing management, which ensures that your client software is updated with the latest productivity and security enhancements.</span></span>

<span data-ttu-id="de9d4-108">将通过以下阶段在组织中计划和部署 Microsoft 365 企业版的底层基础结构：</span><span class="sxs-lookup"><span data-stu-id="de9d4-108">You'll use the following phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise in your organization:</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="de9d4-109">阶段 1：网络</span><span class="sxs-lookup"><span data-stu-id="de9d4-109">Phase 1: Networking</span></span>](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="de9d4-110">阶段 2：身份</span><span class="sxs-lookup"><span data-stu-id="de9d4-110">Phase 2: Identity</span></span>](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="de9d4-111">阶段 3：Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="de9d4-111">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="de9d4-112">阶段 4：Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="de9d4-112">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="de9d4-113">阶段 5：移动设备管理</span><span class="sxs-lookup"><span data-stu-id="de9d4-113">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="de9d4-114">阶段 6：信息保护</span><span class="sxs-lookup"><span data-stu-id="de9d4-114">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)|


<span data-ttu-id="de9d4-p102">在退出每个阶段之前，必须检查其退出条件，这是一组必须满足的必需条件和要考虑的可选条件。每个阶段的退出条件可确保本地和云基础结构以及生成的端到端配置满足对 Microsoft 365 企业版部署的要求。</span><span class="sxs-lookup"><span data-stu-id="de9d4-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="de9d4-117">观看此短视频，了解基础结构内容的原理。</span><span class="sxs-lookup"><span data-stu-id="de9d4-117">Watch this short video on how the foundation infrastructure content works.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="de9d4-118">下图显示了整体 Microsoft 365 企业版部署内容的基础结构及熟悉方法。</span><span class="sxs-lookup"><span data-stu-id="de9d4-118">The following figure shows the foundation infrastructure in the overall Microsoft 365 Enterprise deployment content and your path through it.</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a><span data-ttu-id="de9d4-119">FastTrack</span><span class="sxs-lookup"><span data-stu-id="de9d4-119">FastTrack</span></span>

<span data-ttu-id="de9d4-p103">FastTrack 的优势在于持续且可重复（可用作订阅的一部分），由 Microsoft 工程师提供以帮助你按自己的节奏移动到云。此外，FastTrack 还可使你根据需要访问合格的合作伙伴以获取其他服务。目前为止，40,000 多个客户已启用此功能，FastTrack 可帮助最大化 ROI、加快部署，提高整个组织的采用率。请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)。</span><span class="sxs-lookup"><span data-stu-id="de9d4-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span> 

<span data-ttu-id="de9d4-p104">若要充分利用 FastTrack 来部署 Microsoft 365 企业版，可以使用 FastTrack [Microsoft 365 部署顾问](https://aka.ms/microsoft365setupguide)，了解如何部署和设置底层基础结构。必须以全局管理员的身份在 Office 365 或 Microsoft 365 租户中登录，才能访问此页面。</span><span class="sxs-lookup"><span data-stu-id="de9d4-p104">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="next-step"></a><span data-ttu-id="de9d4-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="de9d4-126">Next step</span></span>

<span data-ttu-id="de9d4-p105">如果你有 Office 365、企业移动性 + 安全性或 Windows 10 企业版的现有基础结构，请参阅[使用现有基础结构部署 Microsoft 365 企业版](deploy-with-existing-infrastructure.md)。本文将系统介绍每个阶段的退出条件。使用此信息，可使你更快速地确定为使 IT 基础结构符合 Microsoft 365 企业版要求而需要更改的内容。</span><span class="sxs-lookup"><span data-stu-id="de9d4-p105">If you have existing infrastructure for Office 365, Enterprise Mobility + Security, or Windows 10 Enterprise, see [Deployment of Microsoft 365 Enterprise with existing infrastructure](deploy-with-existing-infrastructure.md). This article steps you through the exit criteria for each phase. With this information, you can more quickly determine what you need to change to make your IT infrastructure Microsoft 365 Enterprise-compliant.</span></span>

<span data-ttu-id="de9d4-130">否则，可通过[阶段 1：网络](networking-infrastructure.md)开始你的 Microsoft 365 企业版端到端部署历程。</span><span class="sxs-lookup"><span data-stu-id="de9d4-130">Otherwise, you can begin your Microsoft 365 Enterprise end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>