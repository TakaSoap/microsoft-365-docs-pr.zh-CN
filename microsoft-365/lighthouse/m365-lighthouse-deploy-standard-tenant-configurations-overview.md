---
title: 使用基线部署标准租户配置的概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用) ，Microsoft 365 Lighthouse使用基线部署标准租户配置。
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409173"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a><span data-ttu-id="a2058-103">使用基线部署标准租户配置的概述</span><span class="sxs-lookup"><span data-stu-id="a2058-103">Overview of using baselines to deploy standard tenant configurations</span></span> 

> [!NOTE]
> <span data-ttu-id="a2058-104">本文中所述的功能在预览版中，可能会更改，并且仅对满足要求 [的合作伙伴可用](m365-lighthouse-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2058-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="a2058-105">如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="a2058-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="a2058-106">Microsoft 365 Lighthouse基线提供了一种可重复且可扩展的方法，可让你跨多个租户评估和管理Microsoft 365安全设置。</span><span class="sxs-lookup"><span data-stu-id="a2058-106">Microsoft 365 Lighthouse baselines provide a repeatable and scalable way for you to assess and manage Microsoft 365 security settings across multiple tenants.</span></span> <span data-ttu-id="a2058-107">基线还通过保护用户、设备和数据的配置帮助监视核心安全策略和租户合规性标准。</span><span class="sxs-lookup"><span data-stu-id="a2058-107">Baselines also help monitor core security policies and tenant compliance standards with configurations that secure users, devices, and data.</span></span>

<span data-ttu-id="a2058-108">旨在帮助合作伙伴按自己的节奏实现客户采用安全性，Microsoft 365 Lighthouse为 Microsoft 365 服务提供一组标准基线参数和预定义配置。</span><span class="sxs-lookup"><span data-stu-id="a2058-108">Designed to help partners enable customer adoption of security at their own pace, Microsoft 365 Lighthouse provides a standard set of baseline parameters and pre-defined configurations for Microsoft 365 services.</span></span> <span data-ttu-id="a2058-109">这些安全配置可帮助衡量租户Microsoft 365合规性进度。</span><span class="sxs-lookup"><span data-stu-id="a2058-109">These security configurations help measure your tenants' Microsoft 365 security and compliance progress.</span></span>

<span data-ttu-id="a2058-110">可以从内部查看默认基线及其部署Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="a2058-110">You can view the default baseline and its deployment steps from within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="a2058-111">若要将基线应用于租户，请选择左侧导航 **窗格中的** "租户"，然后选择租户。</span><span class="sxs-lookup"><span data-stu-id="a2058-111">To apply baselines to a tenant, select **Tenants** in the left navigation pane, and then select a tenant.</span></span> <span data-ttu-id="a2058-112">接下来，转到"部署 **计划"** 选项卡，实现所需的基线。</span><span class="sxs-lookup"><span data-stu-id="a2058-112">Next, go to the **Deployment plans** tab and implement the desired baseline.</span></span>

## <a name="standard-baseline-security-templates"></a><span data-ttu-id="a2058-113">标准基线安全模板</span><span class="sxs-lookup"><span data-stu-id="a2058-113">Standard baseline security templates</span></span>

<span data-ttu-id="a2058-114">Microsoft 365 Lighthouse工作负载的标准基线配置旨在帮助所有托管租户达到可接受的安全范围和合规性状态。</span><span class="sxs-lookup"><span data-stu-id="a2058-114">Microsoft 365 Lighthouse standard baseline configurations for security workloads are designed to help all managed tenants reach an acceptable state of security coverage and compliance.</span></span>

<span data-ttu-id="a2058-115">下表中的基线配置是标准配置，Microsoft 365 Lighthouse默认比较基准。</span><span class="sxs-lookup"><span data-stu-id="a2058-115">The baseline configurations in the following table come standard with the Microsoft 365 Lighthouse default baseline.</span></span><br><br>

| <span data-ttu-id="a2058-116">基线配置</span><span class="sxs-lookup"><span data-stu-id="a2058-116">Baseline configuration</span></span> | <span data-ttu-id="a2058-117">说明</span><span class="sxs-lookup"><span data-stu-id="a2058-117">Description</span></span> |
|--|--|
| <span data-ttu-id="a2058-118">要求管理员使用 MFA</span><span class="sxs-lookup"><span data-stu-id="a2058-118">Require MFA for admins</span></span> | <span data-ttu-id="a2058-119">仅报告条件访问策略，要求对管理员进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="a2058-119">A report-only Conditional Access policy requiring multifactor authentication for admins.</span></span> <span data-ttu-id="a2058-120">所有云应用程序都需要它。</span><span class="sxs-lookup"><span data-stu-id="a2058-120">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="a2058-121">要求最终用户使用 MFA</span><span class="sxs-lookup"><span data-stu-id="a2058-121">Require MFA for end users</span></span> | <span data-ttu-id="a2058-122">仅报告条件访问策略，要求用户进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="a2058-122">A report-only Conditional Access policy that requires multifactor authentication for users.</span></span> <span data-ttu-id="a2058-123">所有云应用程序都需要它。</span><span class="sxs-lookup"><span data-stu-id="a2058-123">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="a2058-124">阻止传统身份验证</span><span class="sxs-lookup"><span data-stu-id="a2058-124">Block legacy authentication</span></span> | <span data-ttu-id="a2058-125">用于阻止旧客户端身份验证的仅报告条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="a2058-125">A report-only Conditional Access policy to block legacy client authentication.</span></span> |
| <span data-ttu-id="a2058-126">在 Azure AD Microsoft Endpoint Manager注册设备</span><span class="sxs-lookup"><span data-stu-id="a2058-126">Enroll devices in Microsoft Endpoint Manager – Azure AD Join</span></span> | <span data-ttu-id="a2058-127">设备注册，允许租户设备注册Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="a2058-127">Device enrollment to allow your tenant devices to enroll in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="a2058-128">这是通过设置自动注册在 Azure Active Directory 和 Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="a2058-128">This is done by setting up Auto Enrollment between Azure Active Directory and Microsoft Endpoint Manager.</span></span> |
| <span data-ttu-id="a2058-129">防病毒 (AV) 策略配置</span><span class="sxs-lookup"><span data-stu-id="a2058-129">Antivirus (AV) policy configuration</span></span> | <span data-ttu-id="a2058-130">具有预配置Windows配置的设备配置配置文件Microsoft Defender 防病毒配置文件。</span><span class="sxs-lookup"><span data-stu-id="a2058-130">A Device Configuration profile for Windows devices with pre-configured Microsoft Defender Antivirus settings.</span></span> |
| <span data-ttu-id="a2058-131">窗口 10 合规性策略设置</span><span class="sxs-lookup"><span data-stu-id="a2058-131">Window 10 Compliance policy set up</span></span> | <span data-ttu-id="a2058-132">一Windows预配置设置的设备策略，以满足基本合规性要求。</span><span class="sxs-lookup"><span data-stu-id="a2058-132">A Windows device policy with pre-configured settings to meet basic compliance requirements.</span></span> |

## <a name="related-content"></a><span data-ttu-id="a2058-133">相关内容</span><span class="sxs-lookup"><span data-stu-id="a2058-133">Related content</span></span>

<span data-ttu-id="a2058-134">[部署Microsoft 365 Lighthouse文章](m365-lighthouse-deploy-baselines.md) (部署) </span><span class="sxs-lookup"><span data-stu-id="a2058-134">[Deploy Microsoft 365 Lighthouse baselines](m365-lighthouse-deploy-baselines.md) (article)</span></span>\
<span data-ttu-id="a2058-135">[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="a2058-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
