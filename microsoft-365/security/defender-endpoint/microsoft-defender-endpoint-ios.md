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
ms.openlocfilehash: b4c2d586cd23a346db1bcebf891689ff648b639b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844702"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="c67a1-104">iOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c67a1-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c67a1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c67a1-105">**Applies to:**</span></span>
- [<span data-ttu-id="c67a1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c67a1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c67a1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c67a1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c67a1-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c67a1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c67a1-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c67a1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c67a1-110">**iOS 上的 Microsoft Defender for Endpoint** 将提供针对网站、电子邮件和应用中的网络钓鱼和不安全网络连接的防护。</span><span class="sxs-lookup"><span data-stu-id="c67a1-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="c67a1-111">所有警报都将通过警报窗格中的单个Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="c67a1-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="c67a1-112">该门户为安全团队提供了 iOS 设备上威胁的集中视图以及其他平台。</span><span class="sxs-lookup"><span data-stu-id="c67a1-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="c67a1-113">在 iOS 上运行其他第三方终结点保护产品以及 Defender for Endpoint 可能会导致性能问题和不可预知的系统错误。</span><span class="sxs-lookup"><span data-stu-id="c67a1-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="c67a1-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="c67a1-114">Pre-requisites</span></span>

<span data-ttu-id="c67a1-115">**对于最终用户**</span><span class="sxs-lookup"><span data-stu-id="c67a1-115">**For End Users**</span></span>

- <span data-ttu-id="c67a1-116">分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。</span><span class="sxs-lookup"><span data-stu-id="c67a1-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="c67a1-117">请参阅 [Microsoft Defender for Endpoint 许可要求](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="c67a1-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="c67a1-118">设备 (应用) 注册，[以Intune 公司门户](/mem/intune/user-help/enroll-your-device-in-intune-ios)Intune 设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="c67a1-118">Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="c67a1-119">这要求为最终用户分配一个Microsoft Intune许可证。</span><span class="sxs-lookup"><span data-stu-id="c67a1-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="c67a1-120">Intune 公司门户应用可以从[Apple App Store 下载](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="c67a1-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="c67a1-121">请注意，Apple 不允许重定向用户从应用商店下载其他应用，因此在载入 Microsoft Defender for Endpoint 应用之前，需要由用户完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="c67a1-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="c67a1-122">若要详细了解如何分配许可证，请参阅 [向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="c67a1-122">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="c67a1-123">**对于管理员**</span><span class="sxs-lookup"><span data-stu-id="c67a1-123">**For Administrators**</span></span>

- <span data-ttu-id="c67a1-124">访问 Microsoft Defender 安全中心 门户。</span><span class="sxs-lookup"><span data-stu-id="c67a1-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c67a1-125">Microsoft Intune唯一受支持的统一终结点管理 (UEM) 解决方案，用于部署 Microsoft Defender for Endpoint，以及强制执行 Intune 中与 Endpoint 相关的设备合规性策略的 Defender。</span><span class="sxs-lookup"><span data-stu-id="c67a1-125">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

- <span data-ttu-id="c67a1-126">访问[Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心 ，以将应用部署到组织中注册的用户组。</span><span class="sxs-lookup"><span data-stu-id="c67a1-126">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="c67a1-127">**系统要求**</span><span class="sxs-lookup"><span data-stu-id="c67a1-127">**System Requirements**</span></span>

- <span data-ttu-id="c67a1-128">运行 iOS 11.0 及以上设备的 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="c67a1-128">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="c67a1-129">iPad版本 1.1.15010101 之后正式支持的设备。</span><span class="sxs-lookup"><span data-stu-id="c67a1-129">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="c67a1-130">设备已注册Intune 公司门户[应用](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="c67a1-130">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="c67a1-131">安装说明</span><span class="sxs-lookup"><span data-stu-id="c67a1-131">Installation instructions</span></span>

<span data-ttu-id="c67a1-132">在 iOS 上部署 Microsoft Defender for Endpoint Microsoft Intune (MDM) 且受监督的设备和不受监督的设备都受支持。</span><span class="sxs-lookup"><span data-stu-id="c67a1-132">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="c67a1-133">最终用户还可以直接从 Apple 应用商店 [安装应用](https://aka.ms/mdatpiosappstore)。</span><span class="sxs-lookup"><span data-stu-id="c67a1-133">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="c67a1-134">有关详细信息，请参阅在[iOS 上部署 Microsoft Defender for Endpoint。](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="c67a1-134">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="c67a1-135">资源</span><span class="sxs-lookup"><span data-stu-id="c67a1-135">Resources</span></span>

- <span data-ttu-id="c67a1-136">通过访问 [iOS](ios-whatsnew.md) 版 Microsoft Defender for Endpoint 中的新增功能或博客，随时了解即将发布的 [版本](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。</span><span class="sxs-lookup"><span data-stu-id="c67a1-136">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="c67a1-137">通过应用内反馈系统或 [SecOps 门户提供反馈](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c67a1-137">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="c67a1-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c67a1-138">Next steps</span></span>

- [<span data-ttu-id="c67a1-139">在 iOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c67a1-139">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="c67a1-140">在 iOS 功能上配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c67a1-140">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
