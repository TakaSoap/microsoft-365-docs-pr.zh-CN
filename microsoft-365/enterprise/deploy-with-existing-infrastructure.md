---
title: 使用现有基础结构部署 Microsoft 365 企业版
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 如果你具有现有基础结构，请逐步完成 Microsoft 365 企业版部署的退出条件。
ms.openlocfilehash: ace84e53da9b62b39a557b670c54c1be31d0b61a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638176"
---
# <a name="deployment-of-microsoft-365-for-enterprise-with-existing-infrastructure"></a><span data-ttu-id="f1709-103">使用现有基础结构部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="f1709-103">Deployment of Microsoft 365 for enterprise with existing infrastructure</span></span>

<span data-ttu-id="f1709-p101">许多组织都有现有网络、标识和其他组件，或者具有 Microsoft 本地产品和基于云的服务。本文将逐步介绍部署 Microsoft 365 企业版的各个阶段，可让你快速确定如何调整或更改现有基础结构。</span><span class="sxs-lookup"><span data-stu-id="f1709-p101">Many organizations have existing networking, identity, and other components or Microsoft on-premises products and cloud-based services. This article steps through each phase of the deployment of Microsoft 365 for enterprise so you can quickly determine how to adapt or change your existing infrastructure.</span></span>

<span data-ttu-id="f1709-p102">在退出每个阶段之前，必须检查其退出条件，这是一组必须满足的必需条件和要考虑的可选条件。每个阶段的退出条件可确保本地和云基础结构以及生成的端到端配置满足对 Microsoft 365 企业版部署的要求。</span><span class="sxs-lookup"><span data-stu-id="f1709-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meets the requirements for a Microsoft 365 for enterprise deployment.</span></span>

> [!Note] 
> <span data-ttu-id="f1709-p103">FastTrack 的优势在于持续且可重复（可用作订阅的一部分免费提供），由 Microsoft 工程师提供以帮助你按自己的节奏移动到云。此外，FastTrack 还可使你根据需要访问合格的合作伙伴以获取其他服务。目前为止，40,000 多个客户已启用此功能，FastTrack 可帮助最大化 ROI、加快部署，提高整个组织的采用率。请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)。</span><span class="sxs-lookup"><span data-stu-id="f1709-p103">FastTrack is an ongoing and repeatable benefit—available for free as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

## <a name="exit-criteria-for-networking-phase-1"></a><span data-ttu-id="f1709-112">网络退出条件（阶段 1）</span><span class="sxs-lookup"><span data-stu-id="f1709-112">Exit criteria for networking (phase 1)</span></span>

<span data-ttu-id="f1709-113">逐个符合网络基础结构的以下必需条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="f1709-113">Step through the following required and optional conditions for your networking infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for networking](./includes/deployment-exit-criteria-networking.md)]

## <a name="exit-criteria-for-identity-phase-2"></a><span data-ttu-id="f1709-114">身份退出条件（阶段 2）</span><span class="sxs-lookup"><span data-stu-id="f1709-114">Exit criteria for identity (phase 2)</span></span>

<span data-ttu-id="f1709-115">逐个符合标识基础结构的以下必需条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="f1709-115">Step through the following required and optional conditions for your identity infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-identity.md)]

## <a name="exit-criteria-for-windows-10-enterprise-phase-3"></a><span data-ttu-id="f1709-116">Windows 10 企业版退出条件（阶段 3）</span><span class="sxs-lookup"><span data-stu-id="f1709-116">Exit criteria for Windows 10 Enterprise (phase 3)</span></span>

<span data-ttu-id="f1709-117">逐个符合 Windows 10 企业版基础结构的以下必需条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="f1709-117">Step through the following required and optional conditions for your Windows 10 Enterprise infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-windows10.md)]

## <a name="exit-criteria-for-microsoft-365-apps-for-enterprise-phase-4"></a><span data-ttu-id="f1709-118">Microsoft 365 企业应用版（第 4 阶段）退出条件</span><span class="sxs-lookup"><span data-stu-id="f1709-118">Exit criteria for Microsoft 365 Apps for enterprise (phase 4)</span></span>

<span data-ttu-id="f1709-119">满足评估、计划部署和部署 Microsoft 365 企业应用版基础结构的要求。</span><span class="sxs-lookup"><span data-stu-id="f1709-119">Meet the requirements for assessment, deployment planning, and deployment of your Microsoft 365 Apps for enterprise infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for Microsoft 365 Apps for enterprise](./includes/deployment-exit-criteria-office365proplus.md)]

## <a name="exit-criteria-for-mobile-device-management-phase-5"></a><span data-ttu-id="f1709-120">移动设备管理的退出条件（阶段 5）</span><span class="sxs-lookup"><span data-stu-id="f1709-120">Exit criteria for mobile device management (phase 5)</span></span>

<span data-ttu-id="f1709-121">符合以下对移动设备管理基础结构的要求。</span><span class="sxs-lookup"><span data-stu-id="f1709-121">Meet the following requirements for your mobile device management infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for mobile device management](./includes/deployment-exit-criteria-mobility.md)]

## <a name="exit-criteria-for-information-protection-phase-6"></a><span data-ttu-id="f1709-122">信息保护的退出条件（阶段 6）</span><span class="sxs-lookup"><span data-stu-id="f1709-122">Exit criteria for information protection (phase 6)</span></span>

<span data-ttu-id="f1709-123">逐个符合信息保护基础结构的以下必需条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="f1709-123">Step through the following required and optional conditions for your information protection infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for information protection](./includes/deployment-exit-criteria-infoprotect.md)]

