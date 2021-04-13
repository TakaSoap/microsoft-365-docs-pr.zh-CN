---
title: 解决 Microsoft Defender for Endpoint 中的 SIEM 工具集成问题
description: 解决将 SIEM 工具与 Microsoft Defender for Endpoint 一同使用时可能出现的问题。
keywords: 疑难解答， siem， 客户端密码， 密码
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 60220d00ca1b612564b72103b9206e3d6d89dc60
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689445"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="35c53-104">SIEM 工具集成问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="35c53-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="35c53-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="35c53-105">**Applies to:**</span></span>
- [<span data-ttu-id="35c53-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35c53-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="35c53-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35c53-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="35c53-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="35c53-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="35c53-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="35c53-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="35c53-110">在 SIEM 工具中拉取检测时，你可能需要解决问题。</span><span class="sxs-lookup"><span data-stu-id="35c53-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="35c53-111">此页面提供了解决可能遇到的问题的详细步骤。</span><span class="sxs-lookup"><span data-stu-id="35c53-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="35c53-112">了解如何获取新的客户端密码</span><span class="sxs-lookup"><span data-stu-id="35c53-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="35c53-113">如果你的客户端密码过期，或者如果你错位了启用 SIEM 工具应用程序时提供的副本，你将需要获取一个新密码。</span><span class="sxs-lookup"><span data-stu-id="35c53-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="35c53-114">登录到 [Azure 管理门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="35c53-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="35c53-115">选择 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="35c53-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="35c53-116">选择租户。</span><span class="sxs-lookup"><span data-stu-id="35c53-116">Select your tenant.</span></span>

4. <span data-ttu-id="35c53-117">单击 **"应用注册"。**</span><span class="sxs-lookup"><span data-stu-id="35c53-117">Click **App registrations**.</span></span> <span data-ttu-id="35c53-118">然后在"应用程序"列表中，选择应用程序。</span><span class="sxs-lookup"><span data-stu-id="35c53-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="35c53-119">选择 **"密钥** "部分，然后提供密钥说明并指定密钥有效期。</span><span class="sxs-lookup"><span data-stu-id="35c53-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="35c53-120">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="35c53-120">Click **Save**.</span></span> <span data-ttu-id="35c53-121">将显示键值。</span><span class="sxs-lookup"><span data-stu-id="35c53-121">The key value is displayed.</span></span>

7. <span data-ttu-id="35c53-122">复制值并将其保存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="35c53-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="35c53-123">获取刷新访问令牌时出错</span><span class="sxs-lookup"><span data-stu-id="35c53-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="35c53-124">如果在使用威胁情报 API 或 SIEM 工具时尝试获取刷新令牌时遇到错误，则需要在 Azure Active Directory 中添加相关应用程序的回复 URL。</span><span class="sxs-lookup"><span data-stu-id="35c53-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="35c53-125">登录到 [Azure 管理门户](https://ms.portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="35c53-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="35c53-126">选择 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="35c53-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="35c53-127">选择租户。</span><span class="sxs-lookup"><span data-stu-id="35c53-127">Select your tenant.</span></span>

4. <span data-ttu-id="35c53-128">单击 **"应用注册"。**</span><span class="sxs-lookup"><span data-stu-id="35c53-128">Click **App Registrations**.</span></span> <span data-ttu-id="35c53-129">然后在"应用程序"列表中，选择应用程序。</span><span class="sxs-lookup"><span data-stu-id="35c53-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="35c53-130">添加以下 URL：</span><span class="sxs-lookup"><span data-stu-id="35c53-130">Add the following URL:</span></span>
   - <span data-ttu-id="35c53-131">对于欧盟： `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="35c53-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="35c53-132">对于英国： `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="35c53-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="35c53-133">对于美国  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` ：。</span><span class="sxs-lookup"><span data-stu-id="35c53-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="35c53-134">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="35c53-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="35c53-135">启用 SIEM 连接器应用程序时出错</span><span class="sxs-lookup"><span data-stu-id="35c53-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="35c53-136">如果在尝试启用 SIEM 连接器应用程序时遇到错误，请检查浏览器的弹出窗口阻止程序设置。</span><span class="sxs-lookup"><span data-stu-id="35c53-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="35c53-137">启用该功能时，它可能会阻止打开的新窗口。</span><span class="sxs-lookup"><span data-stu-id="35c53-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="35c53-138">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="35c53-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="35c53-139">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="35c53-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="35c53-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="35c53-140">Related topics</span></span>
- [<span data-ttu-id="35c53-141">在 Microsoft Defender for Endpoint 中启用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="35c53-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="35c53-142">配置 ArcSight 以拉取适用于终结点检测的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="35c53-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="35c53-143">将检测拉取到 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="35c53-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="35c53-144">适用于终结点检测字段的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="35c53-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="35c53-145">使用 REST API 拉取 Microsoft Defender 的终结点检测</span><span class="sxs-lookup"><span data-stu-id="35c53-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
