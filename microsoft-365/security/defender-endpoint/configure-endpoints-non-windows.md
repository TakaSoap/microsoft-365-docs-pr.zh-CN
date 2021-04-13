---
title: 将非 Windows 设备载入 Microsoft Defender for Endpoint 服务
description: 配置非 Windows 设备，以便它们可以将传感器数据发送到 Microsoft Defender ATP 服务。
keywords: 载入非 Windows 设备， macos， linux， 设备管理， 配置 Windows ATP 设备， 为终结点设备配置 Microsoft Defender
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
ms.openlocfilehash: 71f230f557792d75659dc4dbfc5911811514d5ea
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687873"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="4a5df-104">载入非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="4a5df-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4a5df-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4a5df-105">**Applies to:**</span></span>
- [<span data-ttu-id="4a5df-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4a5df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4a5df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a5df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="4a5df-108">**平台**</span><span class="sxs-lookup"><span data-stu-id="4a5df-108">**Platforms**</span></span>
- <span data-ttu-id="4a5df-109">macOS</span><span class="sxs-lookup"><span data-stu-id="4a5df-109">macOS</span></span>
- <span data-ttu-id="4a5df-110">Linux</span><span class="sxs-lookup"><span data-stu-id="4a5df-110">Linux</span></span>

><span data-ttu-id="4a5df-111">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="4a5df-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4a5df-112">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4a5df-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="4a5df-113">Defender for Endpoint 为 Windows 和非 Windows 平台提供了集中式安全操作体验。</span><span class="sxs-lookup"><span data-stu-id="4a5df-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="4a5df-114">你将能够在 Microsoft Defender 安全中心内查看各种受支持操作系统 (操作系统) 警报，并更好地保护组织的网络。</span><span class="sxs-lookup"><span data-stu-id="4a5df-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="4a5df-115">你需要了解与 Defender for Endpoint 兼容的确切的 Linux 发行版和 macOS 版本，集成工作。</span><span class="sxs-lookup"><span data-stu-id="4a5df-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="4a5df-116">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="4a5df-116">For more information, see:</span></span>
- [<span data-ttu-id="4a5df-117">Linux 上的 Microsoft Defender for Endpoint 系统要求</span><span class="sxs-lookup"><span data-stu-id="4a5df-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="4a5df-118">[macOS 上的 Microsoft Defender for Endpoint 系统要求](microsoft-defender-endpoint-mac.md#system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="4a5df-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="4a5df-119">载入非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="4a5df-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="4a5df-120">你需要执行以下步骤来载入非 Windows 设备：</span><span class="sxs-lookup"><span data-stu-id="4a5df-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="4a5df-121">选择你的首选载入方法：</span><span class="sxs-lookup"><span data-stu-id="4a5df-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="4a5df-122">对于 macOS 设备，你可以选择通过 Microsoft Defender ATP 或第三方解决方案载入。</span><span class="sxs-lookup"><span data-stu-id="4a5df-122">For macOS devices, you can choose to onboard through Microsoft Defender ATP or through a third-party solution.</span></span> <span data-ttu-id="4a5df-123">有关详细信息，请参阅[Microsoft Defender for Endpoint for Mac。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)</span><span class="sxs-lookup"><span data-stu-id="4a5df-123">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="4a5df-124">对于其他非 Windows 设备，选择通过第三方集成载入 **非 Windows 设备**。</span><span class="sxs-lookup"><span data-stu-id="4a5df-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="4a5df-125">在导航窗格中，选择 **互操作性**  >  **合作伙伴**。</span><span class="sxs-lookup"><span data-stu-id="4a5df-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="4a5df-126">确保列出了第三方解决方案。</span><span class="sxs-lookup"><span data-stu-id="4a5df-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="4a5df-127">在 **"合作伙伴应用程序"** 选项卡中，选择支持非 Windows 设备的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="4a5df-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="4a5df-128">选择 **"打开合作伙伴** 页面"以打开合作伙伴的页面。</span><span class="sxs-lookup"><span data-stu-id="4a5df-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="4a5df-129">按照页面上提供的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4a5df-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="4a5df-130">创建帐户或订阅合作伙伴解决方案后，应进入一个阶段，要求贵组织的租户全局管理员接受来自合作伙伴应用程序的权限请求。</span><span class="sxs-lookup"><span data-stu-id="4a5df-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="4a5df-131">仔细阅读权限请求，确保它与所需的服务保持一致。</span><span class="sxs-lookup"><span data-stu-id="4a5df-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="4a5df-132">按照第三方解决方案的说明运行检测测试。</span><span class="sxs-lookup"><span data-stu-id="4a5df-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="4a5df-133">载出非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="4a5df-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="4a5df-134">按照第三方文档将第三方解决方案与 Microsoft Defender for Endpoint 断开连接。</span><span class="sxs-lookup"><span data-stu-id="4a5df-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="4a5df-135">删除 Azure AD 租户中第三方解决方案的权限。</span><span class="sxs-lookup"><span data-stu-id="4a5df-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="4a5df-136">登录到 [Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="4a5df-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="4a5df-137">选择 **"Azure Active Directory >企业应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="4a5df-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="4a5df-138">选择要离开的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a5df-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="4a5df-139">选择" **删除"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="4a5df-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4a5df-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="4a5df-140">Related topics</span></span>
- [<span data-ttu-id="4a5df-141">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="4a5df-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="4a5df-142">载入服务器</span><span class="sxs-lookup"><span data-stu-id="4a5df-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="4a5df-143">配置代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="4a5df-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="4a5df-144">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="4a5df-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
