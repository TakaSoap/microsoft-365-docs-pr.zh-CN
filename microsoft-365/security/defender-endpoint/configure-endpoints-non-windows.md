---
title: 将非Windows设备载入 Microsoft Defender for Endpoint 服务
description: 配置非Windows设备，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 服务。
keywords: 载入非Windows设备， macos， linux， 设备管理， 为终结点设备配置 Microsoft Defender
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
ms.openlocfilehash: 1c10576b72793ab3833f2e9027e3814a449334ee
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933921"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="ffb56-104">载入非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="ffb56-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ffb56-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ffb56-105">**Applies to:**</span></span>
- [<span data-ttu-id="ffb56-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ffb56-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ffb56-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffb56-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ffb56-108">**平台**</span><span class="sxs-lookup"><span data-stu-id="ffb56-108">**Platforms**</span></span>
- <span data-ttu-id="ffb56-109">macOS</span><span class="sxs-lookup"><span data-stu-id="ffb56-109">macOS</span></span>
- <span data-ttu-id="ffb56-110">Linux</span><span class="sxs-lookup"><span data-stu-id="ffb56-110">Linux</span></span>

><span data-ttu-id="ffb56-111">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ffb56-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ffb56-112">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ffb56-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="ffb56-113">Defender for Endpoint 为用户和非 Windows平台提供了集中式安全Windows体验。</span><span class="sxs-lookup"><span data-stu-id="ffb56-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="ffb56-114">你将能够查看来自各种支持的操作系统和操作系统警报 (操作系统) Microsoft Defender 安全中心更好地保护组织的网络。</span><span class="sxs-lookup"><span data-stu-id="ffb56-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="ffb56-115">你需要了解与 Defender for Endpoint 兼容的确切的 Linux 发行版和 macOS 版本，集成工作。</span><span class="sxs-lookup"><span data-stu-id="ffb56-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="ffb56-116">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="ffb56-116">For more information, see:</span></span>
- [<span data-ttu-id="ffb56-117">Linux 上的 Microsoft Defender for Endpoint 系统要求</span><span class="sxs-lookup"><span data-stu-id="ffb56-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="ffb56-118">[macOS 上的 Microsoft Defender for Endpoint 系统要求](microsoft-defender-endpoint-mac.md#system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="ffb56-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="ffb56-119">载入非Windows设备</span><span class="sxs-lookup"><span data-stu-id="ffb56-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="ffb56-120">你需要执行以下步骤来载入非Windows设备：</span><span class="sxs-lookup"><span data-stu-id="ffb56-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="ffb56-121">选择你的首选载入方法：</span><span class="sxs-lookup"><span data-stu-id="ffb56-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="ffb56-122">对于 macOS 设备，你可以选择通过 Microsoft Defender for Endpoint 或第三方解决方案载入。</span><span class="sxs-lookup"><span data-stu-id="ffb56-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="ffb56-123">有关详细信息，请参阅 Mac 上的[Microsoft Defender for Endpoint。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)</span><span class="sxs-lookup"><span data-stu-id="ffb56-123">For more information, see [Microsoft Defender for Endpoint on Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="ffb56-124">对于其他非Windows设备选择"通过第三Windows **集成载入非非集成设备"。**</span><span class="sxs-lookup"><span data-stu-id="ffb56-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="ffb56-125">在导航窗格中，选择 **互操作性**  >  **合作伙伴**。</span><span class="sxs-lookup"><span data-stu-id="ffb56-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="ffb56-126">确保列出了第三方解决方案。</span><span class="sxs-lookup"><span data-stu-id="ffb56-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="ffb56-127">在 **"合作伙伴应用程序**"选项卡中，选择支持非Windows合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="ffb56-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="ffb56-128">选择 **"打开合作伙伴** 页面"以打开合作伙伴的页面。</span><span class="sxs-lookup"><span data-stu-id="ffb56-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="ffb56-129">按照页面上提供的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="ffb56-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="ffb56-130">创建帐户或订阅合作伙伴解决方案后，应进入一个阶段，要求贵组织的租户全局管理员接受来自合作伙伴应用程序的权限请求。</span><span class="sxs-lookup"><span data-stu-id="ffb56-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="ffb56-131">仔细阅读权限请求，确保它与所需的服务保持一致。</span><span class="sxs-lookup"><span data-stu-id="ffb56-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="ffb56-132">按照第三方解决方案的说明运行检测测试。</span><span class="sxs-lookup"><span data-stu-id="ffb56-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="ffb56-133">载出非Windows设备</span><span class="sxs-lookup"><span data-stu-id="ffb56-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="ffb56-134">按照第三方文档将第三方解决方案与 Microsoft Defender for Endpoint 断开连接。</span><span class="sxs-lookup"><span data-stu-id="ffb56-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="ffb56-135">删除 Azure AD 租户中第三方解决方案的权限。</span><span class="sxs-lookup"><span data-stu-id="ffb56-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="ffb56-136">登录到 [Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="ffb56-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="ffb56-137">选择 **Azure Active Directory > Enterprise应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="ffb56-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="ffb56-138">选择要离开的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ffb56-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="ffb56-139">选择" **删除"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ffb56-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ffb56-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="ffb56-140">Related topics</span></span>
- [<span data-ttu-id="ffb56-141">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="ffb56-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="ffb56-142">载入服务器</span><span class="sxs-lookup"><span data-stu-id="ffb56-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="ffb56-143">配置代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="ffb56-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="ffb56-144">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="ffb56-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
