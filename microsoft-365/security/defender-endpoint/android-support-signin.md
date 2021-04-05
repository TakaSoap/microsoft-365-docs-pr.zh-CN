---
title: Microsoft Defender for Endpoint for Android 疑难解答
description: 解决适用于 Android 的 Microsoft Defender for Endpoint 的问题
keywords: microsoft， defender， atp， mde， android， 云， 连接， 通信
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5fabcb3156a54d4aa8a4671d7561a8deca16fe1f
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587643"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="53a3c-104">Microsoft Defender for Endpoint for Android 疑难解答问题</span><span class="sxs-lookup"><span data-stu-id="53a3c-104">Troubleshooting issues on Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="53a3c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="53a3c-105">**Applies to:**</span></span>
- [<span data-ttu-id="53a3c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="53a3c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="53a3c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53a3c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="53a3c-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="53a3c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="53a3c-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="53a3c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="53a3c-110">在载入设备时，你可能会在安装应用后看到登录问题。</span><span class="sxs-lookup"><span data-stu-id="53a3c-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="53a3c-111">在载入期间，在设备上安装应用后，你可能会遇到登录问题。</span><span class="sxs-lookup"><span data-stu-id="53a3c-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="53a3c-112">本文提供的解决方案可帮助解决登录问题。</span><span class="sxs-lookup"><span data-stu-id="53a3c-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="53a3c-113">登录失败 - 意外错误</span><span class="sxs-lookup"><span data-stu-id="53a3c-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="53a3c-114">\**登录失败：意外\*\*\*错误，请稍后尝试*</span><span class="sxs-lookup"><span data-stu-id="53a3c-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![登录失败错误意外错误的图像](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="53a3c-116">**消息：**</span><span class="sxs-lookup"><span data-stu-id="53a3c-116">**Message:**</span></span>

<span data-ttu-id="53a3c-117">意外错误，请稍后尝试</span><span class="sxs-lookup"><span data-stu-id="53a3c-117">Unexpected error, try later</span></span>

<span data-ttu-id="53a3c-118">**原因：**</span><span class="sxs-lookup"><span data-stu-id="53a3c-118">**Cause:**</span></span>

<span data-ttu-id="53a3c-119">设备上安装了旧版本的"Microsoft Authenticator"应用。</span><span class="sxs-lookup"><span data-stu-id="53a3c-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="53a3c-120">**解决方案：**</span><span class="sxs-lookup"><span data-stu-id="53a3c-120">**Solution:**</span></span>

<span data-ttu-id="53a3c-121">从 Google Play 应用商店安装最新版本和 [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) 并重试</span><span class="sxs-lookup"><span data-stu-id="53a3c-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="53a3c-122">登录失败 - 许可证无效</span><span class="sxs-lookup"><span data-stu-id="53a3c-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="53a3c-123">\**登录失败：许可证\*\*\*无效，请联系管理员*</span><span class="sxs-lookup"><span data-stu-id="53a3c-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![登录失败的图像请联系管理员](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="53a3c-125">\**邮件：\*\*\*许可证无效，请联系管理员*</span><span class="sxs-lookup"><span data-stu-id="53a3c-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="53a3c-126">**原因：**</span><span class="sxs-lookup"><span data-stu-id="53a3c-126">**Cause:**</span></span>

<span data-ttu-id="53a3c-127">你未分配 Microsoft 365 许可证，或者你的组织没有 Microsoft 365 企业版订阅的许可证。</span><span class="sxs-lookup"><span data-stu-id="53a3c-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="53a3c-128">**解决方案：**</span><span class="sxs-lookup"><span data-stu-id="53a3c-128">**Solution:**</span></span>

<span data-ttu-id="53a3c-129">请与管理员联系以寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="53a3c-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="53a3c-130">某些 OEM 设备上不会阻止网络钓鱼页面</span><span class="sxs-lookup"><span data-stu-id="53a3c-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="53a3c-131">**适用于：** 仅特定 OEM</span><span class="sxs-lookup"><span data-stu-id="53a3c-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="53a3c-132">**小米**</span><span class="sxs-lookup"><span data-stu-id="53a3c-132">**Xiaomi**</span></span>

<span data-ttu-id="53a3c-133">某些用户不会阻止 Defender for Android 终结点检测到的网络钓鱼和有害的 Web 威胁。</span><span class="sxs-lookup"><span data-stu-id="53a3c-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="53a3c-134">以下功能在这些设备上不起作用。</span><span class="sxs-lookup"><span data-stu-id="53a3c-134">The following functionality doesn't work on these devices.</span></span>

![报告不安全网站的图像](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="53a3c-136">**原因：**</span><span class="sxs-lookup"><span data-stu-id="53a3c-136">**Cause:**</span></span>

<span data-ttu-id="53a3c-137">用户设备包括新的权限模型。</span><span class="sxs-lookup"><span data-stu-id="53a3c-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="53a3c-138">这将阻止 Defender for Endpoint for Android 在后台运行时显示弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="53a3c-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="53a3c-139">用户权限："在后台运行时显示弹出窗口"。</span><span class="sxs-lookup"><span data-stu-id="53a3c-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![弹出窗口设置的图像](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="53a3c-141">**解决方案：**</span><span class="sxs-lookup"><span data-stu-id="53a3c-141">**Solution:**</span></span>

<span data-ttu-id="53a3c-142">对一些设备启用所需的权限。</span><span class="sxs-lookup"><span data-stu-id="53a3c-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="53a3c-143">在后台运行时显示弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="53a3c-143">Display pop-up windows while running in the background.</span></span>
