---
title: 将Microsoft 365 Defender环境推广到生产环境、Microsoft 365 Defender评估、试用评估、保留评估、生产评估
description: 使用本文将 MDI、MDO、MDE 和 MCAS 的检测工具推广到 Microsoft 365 Defender 或 M365D 中的实时环境。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457690"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a><span data-ttu-id="2b1f9-103">将Microsoft 365 Defender环境推广到生产环境</span><span class="sxs-lookup"><span data-stu-id="2b1f9-103">Promote your Microsoft 365 Defender evaluation environment to production</span></span>

<span data-ttu-id="2b1f9-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2b1f9-104">**Applies to:**</span></span>
- <span data-ttu-id="2b1f9-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b1f9-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="2b1f9-106">若要将Microsoft 365 Defender环境推广到生产环境，请首先购买必要的许可证。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-106">To promote your Microsoft 365 Defender evaluation environment to production, first purchase the necessary license.</span></span> <span data-ttu-id="2b1f9-107">按照创建[eval](eval-create-eval-environment.md)环境并购买 Office 365 E5 许可证中的步骤 (而不是选择"开始免费试用") 。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-107">Follow the steps in [Create the eval environment](eval-create-eval-environment.md) and purchase the Office 365 E5 license (instead of selecting Start free trial).</span></span>

<span data-ttu-id="2b1f9-108">接下来，完成任何其他配置并展开试点组，直到这些试点组进入完全生产阶段。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-108">Next, complete any additional configuration and expand your pilot groups until these have reached full production.</span></span> 

## <a name="microsoft-defender-for-identity"></a><span data-ttu-id="2b1f9-109">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2b1f9-109">Microsoft Defender for Identity</span></span>
<span data-ttu-id="2b1f9-110">Defender for Identity 不需要任何其他配置。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-110">Defender for Identity doesn't require any additional configuration.</span></span> <span data-ttu-id="2b1f9-111">只需确保你已购买必要的许可证，并且在所有 Active Directory 域控制器和 Active Directory 联合身份验证服务 (AD FS 服务器上安装了) 。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-111">Just make sure you've purchased the necessary licenses and installed the sensor on all of your Active Directory domain controllers and Active Directory Federation Services (AD FS) servers.</span></span> 

## <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="2b1f9-112">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2b1f9-112">Microsoft Defender for Office 365</span></span>
<span data-ttu-id="2b1f9-113">成功评估或试用 MDO 后，可以提升至整个生产环境。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-113">After successfully evaluating or piloting MDO, it can be promoted to your entire production environment.</span></span>
1. <span data-ttu-id="2b1f9-114">购买和预配必要的许可证，并将其分配给生产用户。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-114">Purchase and provision the necessary licenses and assign them to your production users.</span></span>
2. <span data-ttu-id="2b1f9-115">针对生产电子邮件域或特定用户组 (标准或) 策略配置。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-115">Re-run recommended baseline policy configurations (either Standard or Strict) against your production email domain or specific groups of users.</span></span>
3. <span data-ttu-id="2b1f9-116">（可选）针对生产电子邮件域或用户组创建和配置任何自定义 MDO 策略。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-116">Optionally create and configure any custom MDO policies against your production email domain or groups of users.</span></span>  <span data-ttu-id="2b1f9-117">但是，请记住，任何分配的基线策略将始终优先于自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-117">However, remember that any assigned baseline policies will always take precedence over custom policies.</span></span>
4. <span data-ttu-id="2b1f9-118">将生产电子邮件域的公共 MX 记录更新为直接解析为 EOP。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-118">Update the public MX record for your production email domain to resolve directly to EOP.</span></span>
5. <span data-ttu-id="2b1f9-119">停用任何第三方 SMTP 网关，并禁用或删除与此中继关联的任何 EXO 连接器。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-119">Decommission any third-party SMTP gateways and disable or delete any EXO connectors associated with this relay.</span></span>

## <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="2b1f9-120">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2b1f9-120">Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="2b1f9-121">若要将 Microsoft Defender for Endpoint 评估环境从试点推广到生产环境，只需使用任何受支持的工具和方法将更多终结点 [载入服务](/defender-endpoint/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-121">To promote Microsoft Defender for Endpoint evaluation environment from a pilot to production, simply onboard more endpoints to the service using any of the [supported tools and methods](/defender-endpoint/onboard-configure).</span></span>

<span data-ttu-id="2b1f9-122">使用以下一般准则将更多设备载入到 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-122">Use the following general guidelines to onboard more devices to Microsoft Defender for Endpoint.</span></span> 

1. <span data-ttu-id="2b1f9-123">验证设备是否满足最低 [要求](/defender-endpoint/minimum-requirements)。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-123">Verify that the device fulfills the [minimum requirements](/defender-endpoint/minimum-requirements).</span></span>
2. <span data-ttu-id="2b1f9-124">根据设备，请按照 Defender for Endpoint 门户的载入部分中提供的配置步骤操作。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-124">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal.</span></span>
3. <span data-ttu-id="2b1f9-125">为设备使用适当的管理工具和部署方法。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-125">Use the appropriate management tool and deployment method for your devices.</span></span>
4.  <span data-ttu-id="2b1f9-126">运行检测测试，验证设备是否正确载入并报告给服务。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-126">Run a detection test to verify that the devices are properly onboarded and reporting to the service.</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="2b1f9-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2b1f9-127">Microsoft Cloud App Security</span></span>
<span data-ttu-id="2b1f9-128">Microsoft Cloud App Security不需要任何其他配置。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-128">Microsoft Cloud App Security doesn't require any additional configuration.</span></span> <span data-ttu-id="2b1f9-129">只需确保你已购买必要的许可证。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-129">Just make sure you've purchased the necessary licenses.</span></span> <span data-ttu-id="2b1f9-130">如果将部署范围缩小到某些用户组，请增加这些组的范围，直到达到生产规模。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-130">If you've scoped the deployment to certain user groups, increase the scope of these groups until you reach production scale.</span></span> 

