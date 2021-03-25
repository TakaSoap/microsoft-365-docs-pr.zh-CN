---
title: 适用于 iOS 的 Microsoft Defender ATP 概述
ms.reviewer: ''
description: 介绍如何安装和使用适用于 iOS 的 Microsoft Defender ATP
keywords: microsoft， defender， atp， ios， 概述， 安装， 部署， 卸载， intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 72c3cfd51e472bbbda61f0084e131c4298633193
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186985"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="41f57-104">适用于 iOS 的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="41f57-104">Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41f57-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="41f57-105">**Applies to:**</span></span>
- [<span data-ttu-id="41f57-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="41f57-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41f57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41f57-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="41f57-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="41f57-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="41f57-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="41f57-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="41f57-110">**Microsoft Defender for Endpoint for iOS** 将提供针对网站、电子邮件和应用中的网络钓鱼和不安全网络连接的防护。</span><span class="sxs-lookup"><span data-stu-id="41f57-110">**Microsoft Defender for Endpoint for iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="41f57-111">所有警报都将通过 Microsoft Defender 安全中心中的单个窗口窗格提供。</span><span class="sxs-lookup"><span data-stu-id="41f57-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="41f57-112">该门户为安全团队提供了 iOS 设备上威胁的集中视图以及其他平台。</span><span class="sxs-lookup"><span data-stu-id="41f57-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="41f57-113">将其他第三方终结点保护产品与 Defender for Endpoint for iOS 一起运行可能会导致性能问题和不可预知的系统错误。</span><span class="sxs-lookup"><span data-stu-id="41f57-113">Running other third-party endpoint protection products alongside Defender for Endpoint for iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="41f57-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="41f57-114">Pre-requisites</span></span>

<span data-ttu-id="41f57-115">**对于最终用户**</span><span class="sxs-lookup"><span data-stu-id="41f57-115">**For End Users**</span></span>

- <span data-ttu-id="41f57-116">分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。</span><span class="sxs-lookup"><span data-stu-id="41f57-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="41f57-117">请参阅 [Microsoft Defender for Endpoint 许可要求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="41f57-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="41f57-118">设备 (设备) Intune 公司门户[](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios)应用注册，以强制执行 Intune 设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="41f57-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="41f57-119">这需要为最终用户分配 Microsoft Intune 许可证。</span><span class="sxs-lookup"><span data-stu-id="41f57-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="41f57-120">可以从 Apple App Store 下载 Intune 公司 [门户应用](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="41f57-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="41f57-121">请注意，Apple 不允许重定向用户从应用商店下载其他应用，因此在载入 Microsoft Defender for Endpoint 应用之前，需要由用户完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="41f57-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="41f57-122">若要详细了解如何分配许可证，请参阅 [向用户分配许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="41f57-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="41f57-123">**对于管理员**</span><span class="sxs-lookup"><span data-stu-id="41f57-123">**For Administrators**</span></span>

- <span data-ttu-id="41f57-124">访问 Microsoft Defender 安全中心门户。</span><span class="sxs-lookup"><span data-stu-id="41f57-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="41f57-125">Microsoft Intune 是部署适用于 iOS 的 Microsoft Defender (MDM) 唯一受支持的移动设备管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="41f57-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for iOS.</span></span> <span data-ttu-id="41f57-126">目前，仅支持在 Intune 中强制执行适用于 iOS 相关设备合规性策略的 Defender for Endpoint 的设备。</span><span class="sxs-lookup"><span data-stu-id="41f57-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint for iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="41f57-127">访问 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，以将应用部署到组织中注册的用户组。</span><span class="sxs-lookup"><span data-stu-id="41f57-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="41f57-128">**系统要求**</span><span class="sxs-lookup"><span data-stu-id="41f57-128">**System Requirements**</span></span>

- <span data-ttu-id="41f57-129">运行 iOS 11.0 及以上设备的 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="41f57-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="41f57-130">从版本 1.1.15010101 开始，正式支持 iPad 设备。</span><span class="sxs-lookup"><span data-stu-id="41f57-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="41f57-131">设备已注册 [Intune 公司门户应用](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="41f57-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="41f57-132">**Microsoft Defender ATP (适用于适用于 iOS) 的 Microsoft Defender ATP 现已在 [Apple App Store 上提供](https://aka.ms/mdatpiosappstore)。**</span><span class="sxs-lookup"><span data-stu-id="41f57-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="41f57-133">安装说明</span><span class="sxs-lookup"><span data-stu-id="41f57-133">Installation instructions</span></span>

<span data-ttu-id="41f57-134">适用于 iOS 的 Microsoft Defender for Endpoint 部署通过 Microsoft Intune (MDM) 且受监督的设备和不受监督的设备均受支持。</span><span class="sxs-lookup"><span data-stu-id="41f57-134">Deployment of Microsoft Defender for Endpoint for iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="41f57-135">有关详细信息，请参阅 [部署适用于 iOS](ios-install.md)的 Microsoft Defender 终结点。</span><span class="sxs-lookup"><span data-stu-id="41f57-135">For more information, see [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="41f57-136">资源</span><span class="sxs-lookup"><span data-stu-id="41f57-136">Resources</span></span>

- <span data-ttu-id="41f57-137">访问我们的博客 ，随时了解即将发布的 [版本](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。</span><span class="sxs-lookup"><span data-stu-id="41f57-137">Stay informed about upcoming releases by visiting our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="41f57-138">通过应用内反馈系统或 [SecOps 门户提供反馈](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="41f57-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="41f57-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="41f57-139">Next steps</span></span>

- [<span data-ttu-id="41f57-140">部署适用于 iOS 的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="41f57-140">Deploy Microsoft Defender for Endpoint for iOS</span></span>](ios-install.md)
- [<span data-ttu-id="41f57-141">配置适用于 iOS 功能的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="41f57-141">Configure Microsoft Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
