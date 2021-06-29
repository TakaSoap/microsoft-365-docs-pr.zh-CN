---
title: iOS 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 iOS 上安装和使用 Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 概述， 安装， 部署， 卸载， intune
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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194849"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="de73f-104">iOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="de73f-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="de73f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="de73f-105">**Applies to:**</span></span>
- [<span data-ttu-id="de73f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="de73f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="de73f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de73f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="de73f-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="de73f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="de73f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="de73f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="de73f-110">**iOS 上的 Microsoft Defender for Endpoint** 可抵御来自网站、电子邮件和应用的网络钓鱼和不安全的网络连接。</span><span class="sxs-lookup"><span data-stu-id="de73f-110">**Microsoft Defender for Endpoint on iOS** offers protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="de73f-111">所有警报都将通过警报窗格中的单个Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="de73f-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="de73f-112">该门户为安全团队提供了 iOS 设备上威胁的集中视图以及其他平台。</span><span class="sxs-lookup"><span data-stu-id="de73f-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="de73f-113">在 iOS 上运行其他第三方终结点保护产品以及 Defender for Endpoint 可能会导致性能问题和不可预知的系统错误。</span><span class="sxs-lookup"><span data-stu-id="de73f-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="de73f-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="de73f-114">Pre-requisites</span></span>

<span data-ttu-id="de73f-115">**对于最终用户**</span><span class="sxs-lookup"><span data-stu-id="de73f-115">**For End Users**</span></span>

- <span data-ttu-id="de73f-116">分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。</span><span class="sxs-lookup"><span data-stu-id="de73f-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="de73f-117">请参阅 [Microsoft Defender for Endpoint 许可要求](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="de73f-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="de73f-118">**对于已注册设备**： (设备) 通过应用注册Intune 公司门户强制执行 Intune [](/mem/intune/user-help/enroll-your-device-in-intune-ios)设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="de73f-118">**For enrolled devices**: Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="de73f-119">这要求为最终用户分配一个Microsoft Intune许可证。</span><span class="sxs-lookup"><span data-stu-id="de73f-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="de73f-120">Intune 公司门户应用可以从[Apple App Store 下载](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="de73f-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="de73f-121">请注意，Apple 不允许重定向用户从应用商店下载其他应用，因此在载入 Microsoft Defender for Endpoint 应用之前，需要由用户完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="de73f-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="de73f-122">**对于注销的设备：设备** (注册) 注册Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="de73f-122">**For unenrolled devices**: Device(s) are registered with Azure Active Directory.</span></span> <span data-ttu-id="de73f-123">这要求最终用户通过应用 Microsoft Authenticator[登录](https://apps.apple.com/app/microsoft-authenticator/id983156458)。</span><span class="sxs-lookup"><span data-stu-id="de73f-123">This requires end user to be signed in through [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

- <span data-ttu-id="de73f-124">若要详细了解如何分配许可证，请参阅 [向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="de73f-124">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="de73f-125">**对于管理员**</span><span class="sxs-lookup"><span data-stu-id="de73f-125">**For Administrators**</span></span>

- <span data-ttu-id="de73f-126">访问 Microsoft Defender 安全中心 门户。</span><span class="sxs-lookup"><span data-stu-id="de73f-126">Access to the Microsoft Defender Security Center portal.</span></span>

- <span data-ttu-id="de73f-127">访问[Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心 ，以将应用部署到组织中注册的用户组。</span><span class="sxs-lookup"><span data-stu-id="de73f-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="de73f-128">Microsoft Intune唯一受支持的统一终结点管理 (UEM) 解决方案，用于部署 Microsoft Defender for Endpoint，以及强制执行 Intune 中与 Endpoint 相关的设备合规性策略的 Defender。</span><span class="sxs-lookup"><span data-stu-id="de73f-128">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

<span data-ttu-id="de73f-129">**系统要求**</span><span class="sxs-lookup"><span data-stu-id="de73f-129">**System Requirements**</span></span>

- <span data-ttu-id="de73f-130">运行 iOS 11.0 及以上设备的 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="de73f-130">iOS device running iOS 11.0 and above.</span></span> <span data-ttu-id="de73f-131">iPad版本 1.1.15010101 之后正式支持的设备。</span><span class="sxs-lookup"><span data-stu-id="de73f-131">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="de73f-132">设备已注册到 Intune 公司门户[应用，或者](https://apps.apple.com/us/app/intune-company-portal/id719171358)通过 Azure Active Directory[注册](https://apps.apple.com/app/microsoft-authenticator/id983156458)Microsoft Authenticator。</span><span class="sxs-lookup"><span data-stu-id="de73f-132">Device is either enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358) or registered with Azure Active Directory through [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="de73f-133">安装说明</span><span class="sxs-lookup"><span data-stu-id="de73f-133">Installation instructions</span></span>

<span data-ttu-id="de73f-134">可通过使用 MEM Microsoft Endpoint Manager (在 iOS 上部署 Microsoft Defender for Endpoint) 并且支持受监督设备以及不受监督的设备。</span><span class="sxs-lookup"><span data-stu-id="de73f-134">Deployment of Microsoft Defender for Endpoint on iOS can be done via Microsoft Endpoint Manager (MEM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="de73f-135">最终用户还可以直接从 Apple 应用商店 [安装应用](https://aka.ms/mdatpiosappstore)。</span><span class="sxs-lookup"><span data-stu-id="de73f-135">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="de73f-136">有关详细信息，请参阅在[iOS 上部署 Microsoft Defender for Endpoint。](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="de73f-136">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="de73f-137">资源</span><span class="sxs-lookup"><span data-stu-id="de73f-137">Resources</span></span>

- <span data-ttu-id="de73f-138">通过访问 [iOS](ios-whatsnew.md) 版 Microsoft Defender for Endpoint 中的新增功能或博客，随时了解即将发布的 [版本](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。</span><span class="sxs-lookup"><span data-stu-id="de73f-138">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="de73f-139">通过应用内反馈系统或 [SecOps 门户提供反馈](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="de73f-139">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="de73f-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="de73f-140">Next steps</span></span>

- [<span data-ttu-id="de73f-141">在 iOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="de73f-141">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="de73f-142">在 iOS 功能上配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="de73f-142">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
