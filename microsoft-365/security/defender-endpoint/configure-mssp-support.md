---
title: 配置托管安全服务提供商支持
description: 执行必要步骤以配置 MSSP 与 Microsoft Defender for Endpoint 的集成
keywords: 托管安全服务提供程序， mssp， 配置， 集成
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165245"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="9067f-104">配置托管安全服务提供程序集成</span><span class="sxs-lookup"><span data-stu-id="9067f-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9067f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9067f-105">**Applies to:**</span></span>
- [<span data-ttu-id="9067f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9067f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9067f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9067f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9067f-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9067f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9067f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9067f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="9067f-110">您需要执行以下配置步骤以启用 MSSP 托管服务提供程序 (MSSP) 集成。</span><span class="sxs-lookup"><span data-stu-id="9067f-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="9067f-111">本文中的以下术语用于区分服务提供商和服务使用者：</span><span class="sxs-lookup"><span data-stu-id="9067f-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="9067f-112">MSSP：提供监视和管理组织的安全设备的安全组织。</span><span class="sxs-lookup"><span data-stu-id="9067f-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="9067f-113">MSSP 客户：使用 MSSP 服务的组织。</span><span class="sxs-lookup"><span data-stu-id="9067f-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="9067f-114">该集成将允许 MSSP 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9067f-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="9067f-115">获取对 MSSP 客户的 Microsoft Defender 安全中心门户的访问权限</span><span class="sxs-lookup"><span data-stu-id="9067f-115">Get access to MSSP customer's Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="9067f-116">获取电子邮件通知和</span><span class="sxs-lookup"><span data-stu-id="9067f-116">Get email notifications, and</span></span> 
- <span data-ttu-id="9067f-117">使用 SIEM 工具通过安全信息和事件管理 (警报) 警报</span><span class="sxs-lookup"><span data-stu-id="9067f-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="9067f-118">MSSP 客户需要授予对 Defender for Endpoint 租户的访问权限，以便 MSSP 可以访问门户，MSSP 客户才能执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="9067f-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="9067f-119">通常，MSSP 客户执行初始配置步骤以授予 MSSP 访问其 Windows Defender 安全中心租户的权限。</span><span class="sxs-lookup"><span data-stu-id="9067f-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="9067f-120">授予访问权限后，MSSP 客户或 MSSP 可以执行其他配置步骤。</span><span class="sxs-lookup"><span data-stu-id="9067f-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="9067f-121">通常，需要执行以下配置步骤：</span><span class="sxs-lookup"><span data-stu-id="9067f-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="9067f-122">**向 MICROSOFT Defender 安全中心授予 MSSP 访问权限**</span><span class="sxs-lookup"><span data-stu-id="9067f-122">**Grant the MSSP access to Microsoft Defender Security Center**</span></span> <br>
<span data-ttu-id="9067f-123">此操作需要由 MSSP 客户执行。</span><span class="sxs-lookup"><span data-stu-id="9067f-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="9067f-124">它向 MSSP 客户授予对 MSSP 客户的 Defender for Endpoint 租户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9067f-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="9067f-125">**配置发送到 MSSP 的警报通知**</span><span class="sxs-lookup"><span data-stu-id="9067f-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="9067f-126">MSSP 客户或 MSSP 可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9067f-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="9067f-127">这使 MSSP 知道需要为 MSSP 客户解决哪些警报。</span><span class="sxs-lookup"><span data-stu-id="9067f-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="9067f-128">**将警报从 MSSP 客户的租户提取到 SIEM 系统**</span><span class="sxs-lookup"><span data-stu-id="9067f-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="9067f-129">此操作由 MSSP 执行。</span><span class="sxs-lookup"><span data-stu-id="9067f-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="9067f-130">它允许 MSSP 在 SIEM 工具中获取警报。</span><span class="sxs-lookup"><span data-stu-id="9067f-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="9067f-131">**使用 API 从 MSSP 客户的租户提取警报**</span><span class="sxs-lookup"><span data-stu-id="9067f-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="9067f-132">此操作由 MSSP 执行。</span><span class="sxs-lookup"><span data-stu-id="9067f-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="9067f-133">它允许 MSSP 使用 API 获取警报。</span><span class="sxs-lookup"><span data-stu-id="9067f-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="9067f-134">MSSP 的多租户访问</span><span class="sxs-lookup"><span data-stu-id="9067f-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="9067f-135">若要了解如何实现多租户委派访问，请参阅S [multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)。</span><span class="sxs-lookup"><span data-stu-id="9067f-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="9067f-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="9067f-136">Related topics</span></span>
- [<span data-ttu-id="9067f-137">授予对门户的 MSSP 访问权限</span><span class="sxs-lookup"><span data-stu-id="9067f-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="9067f-138">访问 MSSP 客户门户</span><span class="sxs-lookup"><span data-stu-id="9067f-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="9067f-139">配置警报通知</span><span class="sxs-lookup"><span data-stu-id="9067f-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="9067f-140">从客户租户提取警报</span><span class="sxs-lookup"><span data-stu-id="9067f-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

