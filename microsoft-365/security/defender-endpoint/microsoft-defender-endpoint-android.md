---
title: Android 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Android 上安装和使用 Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， android， 安装， 部署， 卸载， intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 499ac9a6ee81bacb79cd83993d510f87e11c62c6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844714"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="911ef-104">Android 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="911ef-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="911ef-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="911ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="911ef-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="911ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="911ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="911ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="911ef-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="911ef-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="911ef-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="911ef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="911ef-110">本主题介绍如何在 Android 上安装、配置、更新和使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="911ef-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="911ef-111">在 Android 上运行其他第三方终结点保护产品以及 Defender for Endpoint 可能会导致性能问题和不可预知的系统错误。</span><span class="sxs-lookup"><span data-stu-id="911ef-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="911ef-112">如何在 Android 上安装 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="911ef-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="911ef-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="911ef-113">Prerequisites</span></span>

-   <span data-ttu-id="911ef-114">**对于最终用户**</span><span class="sxs-lookup"><span data-stu-id="911ef-114">**For end users**</span></span>

    -   <span data-ttu-id="911ef-115">分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。</span><span class="sxs-lookup"><span data-stu-id="911ef-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="911ef-116">请参阅 [适用于终结点的 Microsoft Defender 许可要求](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="911ef-116">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="911ef-117">Intune 公司门户应用可以从 Google Play 下载[，](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)并且可在 Android 设备上使用。</span><span class="sxs-lookup"><span data-stu-id="911ef-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="911ef-118">此外， (应用) 注册设备策略，Intune 公司门户强制执行 Intune 设备合规性策略。 [](/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="911ef-118">Additionally, device(s) can be [enrolled](/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="911ef-119">这要求为最终用户分配一个Microsoft Intune许可证。</span><span class="sxs-lookup"><span data-stu-id="911ef-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="911ef-120">若要详细了解如何分配许可证，请参阅 [向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="911ef-120">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="911ef-121">**对于管理员**</span><span class="sxs-lookup"><span data-stu-id="911ef-121">**For Administrators**</span></span>

    -   <span data-ttu-id="911ef-122">访问 Microsoft Defender 安全中心 门户。</span><span class="sxs-lookup"><span data-stu-id="911ef-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="911ef-123">Microsoft Intune在 Android 上部署 Microsoft Defender for Endpoint (MDM) 唯一受支持的移动设备管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="911ef-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="911ef-124">目前，仅支持在 Intune 中对 Android 相关设备合规性策略强制实施 Defender for Endpoint 的设备。</span><span class="sxs-lookup"><span data-stu-id="911ef-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="911ef-125">访问[Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心 ，将应用部署到组织中注册的用户组。</span><span class="sxs-lookup"><span data-stu-id="911ef-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="911ef-126">网络要求</span><span class="sxs-lookup"><span data-stu-id="911ef-126">Network Requirements</span></span>

- <span data-ttu-id="911ef-127">为了使 Android 上的 Microsoft Defender for Endpoint 在连接到网络时正常运行，需要将防火墙/代理配置为允许访问[Microsoft Defender for Endpoint 服务 URL。](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="911ef-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="911ef-128">系统要求</span><span class="sxs-lookup"><span data-stu-id="911ef-128">System Requirements</span></span>

-   <span data-ttu-id="911ef-129">运行 Android 6.0 及以上操作系统的 Android 设备。</span><span class="sxs-lookup"><span data-stu-id="911ef-129">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="911ef-130">Intune 公司门户 Google [Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)下载并安装应用。</span><span class="sxs-lookup"><span data-stu-id="911ef-130">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="911ef-131">必须注册设备才能强制执行 Intune 设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="911ef-131">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="911ef-132">安装说明</span><span class="sxs-lookup"><span data-stu-id="911ef-132">Installation instructions</span></span>

<span data-ttu-id="911ef-133">Android 上的 Microsoft Defender for Endpoint 支持在已注册的设备的两种模式（旧版设备管理员和 Android Enterprise安装。</span><span class="sxs-lookup"><span data-stu-id="911ef-133">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="911ef-134">**目前，具有工作配置文件的个人拥有设备和公司拥有的完全托管用户设备注册在 Android Enterprise。其他 Android Enterprise模式的支持将在准备就绪后公布。**</span><span class="sxs-lookup"><span data-stu-id="911ef-134">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="911ef-135">Android 上的 Microsoft Defender for Endpoint 部署通过 mdm Microsoft Intune (进行) 。</span><span class="sxs-lookup"><span data-stu-id="911ef-135">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="911ef-136">有关详细信息，请参阅使用 Microsoft Intune 在 Android 上[部署 Microsoft Defender for Endpoint。](android-intune.md)</span><span class="sxs-lookup"><span data-stu-id="911ef-136">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="911ef-137">**Android 上的 Microsoft Defender for Endpoint 现已在 [Google Play 上](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 可用。**</span><span class="sxs-lookup"><span data-stu-id="911ef-137">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="911ef-138">你可以从 Intune 连接到 Google Play，以跨设备管理员和 Android Enterprise应用部署 Microsoft Defender for Endpoint 应用。</span><span class="sxs-lookup"><span data-stu-id="911ef-138">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="911ef-139">如何在 Android 上配置适用于终结点的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="911ef-139">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="911ef-140">有关如何在 Android 上配置适用于终结点功能的 Microsoft Defender 的指南可在在 Android 功能上配置 [Microsoft Defender for Endpoint 中提供](android-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="911ef-140">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="911ef-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="911ef-141">Related topics</span></span>
- [<span data-ttu-id="911ef-142">使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="911ef-142">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="911ef-143">在 Android 功能上配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="911ef-143">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

