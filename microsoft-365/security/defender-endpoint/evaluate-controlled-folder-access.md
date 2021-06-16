---
title: 受控文件夹访问评估
description: 了解受控文件夹访问权限如何有助于防止文件被恶意应用更改。
keywords: Exploit Protection， windows 10， windows defender， 勒索软件， 保护， 评估， 测试， 演示， 尝试
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 4254c5ea24d8c901ac5f6337b0c626afe02747e2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926639"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="54190-104">受控文件夹访问评估</span><span class="sxs-lookup"><span data-stu-id="54190-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54190-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="54190-105">**Applies to:**</span></span>
- [<span data-ttu-id="54190-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54190-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="54190-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54190-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="54190-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="54190-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="54190-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="54190-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="54190-110">[受控文件夹](controlled-folders.md) 访问权限是一项有助于保护文档和文件免受可疑或恶意应用修改的功能。</span><span class="sxs-lookup"><span data-stu-id="54190-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="54190-111">受控文件夹访问权限在 Windows Server 2019 和 Windows 10 客户端上受支持。</span><span class="sxs-lookup"><span data-stu-id="54190-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="54190-112">它尤其有助于防范尝试加密文件并[](https://www.microsoft.com/wdsi/threats/ransomware)阻止其成为勒索软件。</span><span class="sxs-lookup"><span data-stu-id="54190-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="54190-113">本文帮助你评估受控文件夹访问权限。</span><span class="sxs-lookup"><span data-stu-id="54190-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="54190-114">它介绍了如何启用审核模式，以便可以直接在组织中测试该功能。</span><span class="sxs-lookup"><span data-stu-id="54190-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="54190-115">还可以访问 Microsoft Defender for Endpoint 演示方案[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 确认功能是否正常工作并查看其工作方式。</span><span class="sxs-lookup"><span data-stu-id="54190-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="54190-116">使用审核模式衡量影响</span><span class="sxs-lookup"><span data-stu-id="54190-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="54190-117">在审核模式下启用受控文件夹访问权限，查看完全启用后将发生的情况记录。</span><span class="sxs-lookup"><span data-stu-id="54190-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="54190-118">测试此功能在组织中如何工作，以确保它不会影响你的业务线应用。</span><span class="sxs-lookup"><span data-stu-id="54190-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="54190-119">您还可以了解在特定时段内通常发生多少可疑文件修改尝试。</span><span class="sxs-lookup"><span data-stu-id="54190-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="54190-120">若要启用审核模式，请使用以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="54190-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="54190-121">如果你想要完全审核受控文件夹访问权限在组织中如何工作，你将需要使用管理工具将此设置部署到网络 (设备) 。</span><span class="sxs-lookup"><span data-stu-id="54190-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="54190-122">您还可以使用组策略、Intune、移动设备管理 (MDM) 或 Microsoft Endpoint Manager 配置和部署设置，如主要的受控文件夹[访问权限主题中所述](controlled-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="54190-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="54190-123">在事件查看器中查看受控Windows访问事件</span><span class="sxs-lookup"><span data-stu-id="54190-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="54190-124">以下受控文件夹访问权限事件显示在 microsoft/Windows/Windows Windows Defender/Operational 文件夹下的 Windows 事件查看器中。</span><span class="sxs-lookup"><span data-stu-id="54190-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="54190-125">事件 ID</span><span class="sxs-lookup"><span data-stu-id="54190-125">Event ID</span></span> | <span data-ttu-id="54190-126">说明</span><span class="sxs-lookup"><span data-stu-id="54190-126">Description</span></span>
-|-
 <span data-ttu-id="54190-127">5007</span><span class="sxs-lookup"><span data-stu-id="54190-127">5007</span></span> | <span data-ttu-id="54190-128">更改设置时的事件</span><span class="sxs-lookup"><span data-stu-id="54190-128">Event when settings are changed</span></span>
 <span data-ttu-id="54190-129">1124</span><span class="sxs-lookup"><span data-stu-id="54190-129">1124</span></span> | <span data-ttu-id="54190-130">已审核的受控文件夹访问事件</span><span class="sxs-lookup"><span data-stu-id="54190-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="54190-131">1123</span><span class="sxs-lookup"><span data-stu-id="54190-131">1123</span></span> | <span data-ttu-id="54190-132">阻止的受控文件夹访问事件</span><span class="sxs-lookup"><span data-stu-id="54190-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="54190-133">你可以配置Windows[转发订阅](/windows/win32/wec/setting-up-a-source-initiated-subscription)以集中收集日志。</span><span class="sxs-lookup"><span data-stu-id="54190-133">You can configure a [Windows Event Forwarding subscription](/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="54190-134">自定义受保护的文件夹和应用</span><span class="sxs-lookup"><span data-stu-id="54190-134">Customize protected folders and apps</span></span>

<span data-ttu-id="54190-135">在评估过程中，你可能希望添加到受保护的文件夹列表，或允许某些应用修改文件。</span><span class="sxs-lookup"><span data-stu-id="54190-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="54190-136">请参阅 [使用](controlled-folders.md) 受控文件夹访问权限保护重要文件夹，以使用管理工具配置功能，包括组策略、PowerShell 和 MDM 配置服务提供程序 (CSP) 。</span><span class="sxs-lookup"><span data-stu-id="54190-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="54190-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54190-137">See also</span></span>

* [<span data-ttu-id="54190-138">使用受控文件夹访问权限保护重要文件夹</span><span class="sxs-lookup"><span data-stu-id="54190-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="54190-139">评估 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54190-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="54190-140">使用审核模式</span><span class="sxs-lookup"><span data-stu-id="54190-140">Use audit mode</span></span>](audit-windows-defender.md)
