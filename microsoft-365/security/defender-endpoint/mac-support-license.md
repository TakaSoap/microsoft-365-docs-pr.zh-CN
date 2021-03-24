---
title: 解决 Microsoft Defender ATP for Mac 的许可证问题
description: 解决 Microsoft Defender ATP for Mac 中的许可证问题。
keywords: microsoft， defender， atp， mac， 性能
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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056000"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="ce44c-104">解决 Microsoft Defender for Endpoint for Mac 的许可证问题</span><span class="sxs-lookup"><span data-stu-id="ce44c-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ce44c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ce44c-105">**Applies to:**</span></span>

- [<span data-ttu-id="ce44c-106">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="ce44c-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="ce44c-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ce44c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="ce44c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce44c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ce44c-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ce44c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ce44c-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ce44c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ce44c-111">当你要完成适用于 [Mac](microsoft-defender-endpoint-mac.md) 的 Microsoft Defender for Endpoint 和 [手动](mac-install-manually.md) 部署测试或 PoC (概念证明) ，你可能会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="ce44c-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![许可证错误的图像](images/no-license-found.png)

<span data-ttu-id="ce44c-113">**消息：**</span><span class="sxs-lookup"><span data-stu-id="ce44c-113">**Message:**</span></span> 

<span data-ttu-id="ce44c-114">未找到许可证</span><span class="sxs-lookup"><span data-stu-id="ce44c-114">No license found</span></span>

<span data-ttu-id="ce44c-115">看起来你的组织没有 Microsoft 365 企业版订阅的许可证。</span><span class="sxs-lookup"><span data-stu-id="ce44c-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="ce44c-116">请与管理员联系以寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="ce44c-116">Contact your administrator for help.</span></span>

<span data-ttu-id="ce44c-117">**原因：**</span><span class="sxs-lookup"><span data-stu-id="ce44c-117">**Cause:**</span></span> 

<span data-ttu-id="ce44c-118">你已部署和/或安装了适用于 macOS 的 Microsoft Defender for Endpoint 程序包 ("下载安装程序包") 但你可能已运行配置脚本 ("下载载入程序包") 。</span><span class="sxs-lookup"><span data-stu-id="ce44c-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="ce44c-119">**解决方案：**</span><span class="sxs-lookup"><span data-stu-id="ce44c-119">**Solution:**</span></span>

<span data-ttu-id="ce44c-120">按照以下 MicrosoftDefenderATPOnboardingMacOs.py 说明操作： [客户端配置](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="ce44c-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

