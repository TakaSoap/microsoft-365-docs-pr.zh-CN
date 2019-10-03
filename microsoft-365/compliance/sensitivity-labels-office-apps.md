---
title: 敏感度标签在 Office 应用中的工作方式
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用敏感度标签，可以对敏感内容进行分类和保护，同时确保组织内人员的工作效率和协作能力不受阻碍。敏感度标签可用于强制执行保护设置，如对已标记内容设置加密或水印。
ms.openlocfilehash: 1de7eadfcf95a54917c1d5e2cc0d42cc1ad486a5
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378645"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="f0e74-104">敏感度标签在 Office 应用中的工作方式</span><span class="sxs-lookup"><span data-stu-id="f0e74-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="f0e74-105">在 Office 应用程序中使用敏感度标签有哪些先决条件？</span><span class="sxs-lookup"><span data-stu-id="f0e74-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="f0e74-106">常见要求</span><span class="sxs-lookup"><span data-stu-id="f0e74-106">Common requirements</span></span> 

- <span data-ttu-id="f0e74-107">[必须在安全与合规中心配置和发布](https://aka.ms/managemip)统一的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="f0e74-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="f0e74-108">用户必须使用其工作帐户登录到 Office。</span><span class="sxs-lookup"><span data-stu-id="f0e74-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="f0e74-109">用户必须分配有 Office 365 E3 或更高版本的许可证。</span><span class="sxs-lookup"><span data-stu-id="f0e74-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="f0e74-110">针对 Office for Windows 的其他要求</span><span class="sxs-lookup"><span data-stu-id="f0e74-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="f0e74-111">Azure 信息保护客户端必须未在 Office 中运行。</span><span class="sxs-lookup"><span data-stu-id="f0e74-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="f0e74-112">另请参阅：[敏感度标签能否与 Azure 信息保护客户端一起在 Office for Windows 中运行？](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)。</span><span class="sxs-lookup"><span data-stu-id="f0e74-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="f0e74-113">针对所有平台上的 Outlook 的其他要求</span><span class="sxs-lookup"><span data-stu-id="f0e74-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="f0e74-114">在标签配置中，如果已打开内容标记，则必须为要在传输中插入的内容标记使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f0e74-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="f0e74-115">Office 目前支持哪些敏感度标签功能？</span><span class="sxs-lookup"><span data-stu-id="f0e74-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="f0e74-116"><font size="-1">功能</span><span class="sxs-lookup"><span data-stu-id="f0e74-116"><font size="-1"></span></span><th><span data-ttu-id="f0e74-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="f0e74-117"><font size="-1"></span></span><th><span data-ttu-id="f0e74-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="f0e74-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="f0e74-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="f0e74-119"><font size="-1">Word</span></span><br>
<span data-ttu-id="f0e74-120">Excel</span><span class="sxs-lookup"><span data-stu-id="f0e74-120">Excel</span></span><br>
<span data-ttu-id="f0e74-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f0e74-121">PowerPoint</span></span><br>
<span data-ttu-id="f0e74-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="f0e74-122">Outlook</span></span>


<td><span data-ttu-id="f0e74-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="f0e74-123"><font size="-1">Word</span></span><br>
<span data-ttu-id="f0e74-124">Excel</span><span class="sxs-lookup"><span data-stu-id="f0e74-124">Excel</span></span><br>
<span data-ttu-id="f0e74-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f0e74-125">PowerPoint</span></span><br>
<span data-ttu-id="f0e74-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="f0e74-126">Outlook</span></span>

<td><span data-ttu-id="f0e74-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="f0e74-127"><font size="-1">Word</span></span><br>
<span data-ttu-id="f0e74-128">Excel</span><span class="sxs-lookup"><span data-stu-id="f0e74-128">Excel</span></span><br>
<span data-ttu-id="f0e74-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f0e74-129">PowerPoint</span></span>
<td><span data-ttu-id="f0e74-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="f0e74-130"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="f0e74-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="f0e74-131"><font size="-1">Word</span></span><br>
<span data-ttu-id="f0e74-132">Excel</span><span class="sxs-lookup"><span data-stu-id="f0e74-132">Excel</span></span><br>
<span data-ttu-id="f0e74-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f0e74-133">PowerPoint</span></span>
<td><span data-ttu-id="f0e74-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="f0e74-134"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="f0e74-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="f0e74-135"><font size="-1">Word</span></span><br>
<span data-ttu-id="f0e74-136">Excel</span><span class="sxs-lookup"><span data-stu-id="f0e74-136">Excel</span></span><br>
<span data-ttu-id="f0e74-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f0e74-137">PowerPoint</span></span>
<td><span data-ttu-id="f0e74-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-138">Outlook</span></span></tr>

<tr>
<td><span data-ttu-id="f0e74-139"><font size="-1">手动应用、更改或删除标签</span><span class="sxs-lookup"><span data-stu-id="f0e74-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="f0e74-140"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-140">Yes</span></span><br><span data-ttu-id="f0e74-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="f0e74-142"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-142">Yes</span></span><br><span data-ttu-id="f0e74-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="f0e74-144"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-144">Yes</span></span><br><span data-ttu-id="f0e74-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="f0e74-146"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-147"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-147">Yes</span></span><br><span data-ttu-id="f0e74-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="f0e74-149"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-150"><font size="-1">即将推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f0e74-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="f0e74-151"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="f0e74-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">应用默认标签</a>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="f0e74-153"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-153">Yes</span></span><br><span data-ttu-id="f0e74-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="f0e74-155"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-155">Yes</span></span><br><span data-ttu-id="f0e74-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="f0e74-157"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-157">Yes</span></span><br><span data-ttu-id="f0e74-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="f0e74-159"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-160"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-160">Yes</span></span><br><span data-ttu-id="f0e74-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="f0e74-162"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-163"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-164"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="f0e74-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">要求提供更改标签的理由</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="f0e74-166"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-166">Yes</span></span><br><span data-ttu-id="f0e74-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="f0e74-168"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-168">Yes</span></span><br><span data-ttu-id="f0e74-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="f0e74-170"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-170">Yes</span></span><br><span data-ttu-id="f0e74-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="f0e74-172"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-173"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-173">Yes</span></span><br><span data-ttu-id="f0e74-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="f0e74-175"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-176"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-177"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="f0e74-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">为自定义帮助页面提供帮助链接</a>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="f0e74-179"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-179">Yes</span></span><br><span data-ttu-id="f0e74-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="f0e74-181"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-181">Yes</span></span><br><span data-ttu-id="f0e74-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="f0e74-183"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-183">Yes</span></span><br><span data-ttu-id="f0e74-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="f0e74-185"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-186"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-186">Yes</span></span><br><span data-ttu-id="f0e74-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="f0e74-188"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-189"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-190"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="f0e74-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">标记内容</a>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="f0e74-192"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-192">Yes</span></span><br><span data-ttu-id="f0e74-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="f0e74-194"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-194">Yes</span></span><br><span data-ttu-id="f0e74-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="f0e74-196"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-196">Yes</span></span><br><span data-ttu-id="f0e74-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="f0e74-198"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-199"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-199">Yes</span></span><br><span data-ttu-id="f0e74-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="f0e74-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="f0e74-201"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-202"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-203"><font size="-1">即将推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f0e74-203"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="f0e74-204"><font size="-1">分配预定义的权限</span><span class="sxs-lookup"><span data-stu-id="f0e74-204"><font size="-1">Assign pre-defined permissions</span></span>
<td><span data-ttu-id="f0e74-205"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-205">Yes</span></span><br><span data-ttu-id="f0e74-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="f0e74-207"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-207">Yes</span></span><br><span data-ttu-id="f0e74-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="f0e74-209"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-209">Yes</span></span><br><span data-ttu-id="f0e74-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="f0e74-211"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-212"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="f0e74-212">Yes</span></span><br><span data-ttu-id="f0e74-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="f0e74-214"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-215"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-216"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="f0e74-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">允许用户分配权限</a>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-217">Let users assign permissions</span></span><td><span data-ttu-id="f0e74-218"><font size="-1"><b>是</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f0e74-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="f0e74-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="f0e74-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="f0e74-220"><font size="-1"><b>是</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f0e74-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="f0e74-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="f0e74-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="f0e74-222"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-223"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-224"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="f0e74-225"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="f0e74-226"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-227"><font size="-1">即将推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f0e74-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="f0e74-228"><font size="-1">向管理员发送<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">标签分析</a>数据</span><span class="sxs-lookup"><span data-stu-id="f0e74-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="f0e74-229"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="f0e74-230"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="f0e74-231"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-232"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-233"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-234"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-235"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-236"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="f0e74-237"><font size="-1">要求用户为其电子邮件和文档应用标签</span><span class="sxs-lookup"><span data-stu-id="f0e74-237"><font size="-1">Require users to apply a label to their email and documents</span></span>
<td><span data-ttu-id="f0e74-238"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="f0e74-239"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="f0e74-240"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-241"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-242"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-243"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-244"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-245"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="f0e74-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">将敏感度标签自动应用于内容</a>
</span><span class="sxs-lookup"><span data-stu-id="f0e74-246">Apply a sensitivity label to content automatically</span></span><td><span data-ttu-id="f0e74-247"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="f0e74-248"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="f0e74-249"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-250"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-251"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-252"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-253"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="f0e74-254"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="f0e74-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="f0e74-255"><sup>1</sup>如果已配置，将提示用户提供标签降级的理由。</span><span class="sxs-lookup"><span data-stu-id="f0e74-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="f0e74-256">但是，尚未向管理员提供理由数据。</span><span class="sxs-lookup"><span data-stu-id="f0e74-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="f0e74-257">当支持“向管理员发送标签分析数据”功能时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="f0e74-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="f0e74-258"><sup>2</sup>目前，仅在 Outlook for Windows 和 Outlook for Mac 中允许用户分配权限。</span><span class="sxs-lookup"><span data-stu-id="f0e74-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="f0e74-259">针对 Word、Excel 和 PowerPoint 的可用性待定。</span><span class="sxs-lookup"><span data-stu-id="f0e74-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="f0e74-260"><sup>3</sup>预计为 2019 日历年第 4 季度。</span><span class="sxs-lookup"><span data-stu-id="f0e74-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="f0e74-261">在为内容提供敏感度标签后，何时应用内容标记或加密？</span><span class="sxs-lookup"><span data-stu-id="f0e74-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="f0e74-262">应用程序</span><span class="sxs-lookup"><span data-stu-id="f0e74-262">Application</span></span> | <span data-ttu-id="f0e74-263">内容标记</span><span class="sxs-lookup"><span data-stu-id="f0e74-263">Content marking</span></span> | <span data-ttu-id="f0e74-264">加密</span><span class="sxs-lookup"><span data-stu-id="f0e74-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="f0e74-265">所有平台上的 Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f0e74-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="f0e74-266">立即</span><span class="sxs-lookup"><span data-stu-id="f0e74-266">Immediately</span></span> | <span data-ttu-id="f0e74-267">立即</span><span class="sxs-lookup"><span data-stu-id="f0e74-267">Immediately</span></span> |
| <span data-ttu-id="f0e74-268">Outlook for PC 和 Outlook for Mac</span><span class="sxs-lookup"><span data-stu-id="f0e74-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="f0e74-269">通过 Exchange Online 发送电子邮件之后</span><span class="sxs-lookup"><span data-stu-id="f0e74-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="f0e74-270">立即</span><span class="sxs-lookup"><span data-stu-id="f0e74-270">Immediately</span></span> |
| <span data-ttu-id="f0e74-271">所有平台上的 Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f0e74-271">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="f0e74-272">通过 Exchange Online 发送电子邮件之后</span><span class="sxs-lookup"><span data-stu-id="f0e74-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="f0e74-273">通过 Exchange Online 发送电子邮件之后</span><span class="sxs-lookup"><span data-stu-id="f0e74-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="f0e74-274">敏感度标签能否与 Azure 信息保护客户端一起在 Office for Windows 中运行？</span><span class="sxs-lookup"><span data-stu-id="f0e74-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="f0e74-275">否。</span><span class="sxs-lookup"><span data-stu-id="f0e74-275">No.</span></span> <span data-ttu-id="f0e74-276">如果在 Office for Windows 中加载 Azure 信息保护客户端，则会关闭敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="f0e74-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="f0e74-277">如果你已安装了 Azure 信息保护客户端，但你希望改为使用敏感度标签，则可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f0e74-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="f0e74-278">配置“ **使用 Office 中的“敏感度”功能应用并查看敏感度标签**”组策略设置，可在“**用户配置/管理模板/Microsoft Office 2016/安全设置**”下方找到该设置。</span><span class="sxs-lookup"><span data-stu-id="f0e74-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="f0e74-279">注意：可通过传统的组策略部署机制或 [Office 云策略服务](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)来部署此设置。</span><span class="sxs-lookup"><span data-stu-id="f0e74-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="f0e74-280">或者，你也可以卸载或 [禁用](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) Azure 信息保护客户端。</span><span class="sxs-lookup"><span data-stu-id="f0e74-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="f0e74-281">重新启动所有 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0e74-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="f0e74-282">Office 的非订阅版本（例如 Office 2016 或 Office 2019）是否支持敏感度标签？</span><span class="sxs-lookup"><span data-stu-id="f0e74-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="f0e74-283">否。</span><span class="sxs-lookup"><span data-stu-id="f0e74-283">No.</span></span> <span data-ttu-id="f0e74-284">敏感度标签仅在 Office 365 订阅中受支持，在任何非订阅版本中均不受支持。</span><span class="sxs-lookup"><span data-stu-id="f0e74-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="f0e74-285">但是，可在非订阅版本的 Office 中使用 Azure 信息保护统一标记客户端。</span><span class="sxs-lookup"><span data-stu-id="f0e74-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="f0e74-286">在设置敏感度标签之前，我曾部署过保护模板。</span><span class="sxs-lookup"><span data-stu-id="f0e74-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="f0e74-287">它们去哪儿了？</span><span class="sxs-lookup"><span data-stu-id="f0e74-287">Where did they go?</span></span>

<span data-ttu-id="f0e74-288">启用敏感度标签后，管理员定义的[保护模板](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)将在 Office 用户体验中隐藏，因为对于已启用加密的敏感度标签而言，它们是多余的。</span><span class="sxs-lookup"><span data-stu-id="f0e74-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="f0e74-289">文件或电子邮件能否具有多个分类？</span><span class="sxs-lookup"><span data-stu-id="f0e74-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="f0e74-290">用户一次只能为每个文档或电子邮件选择一个标签，这通常只会导致一个分类。</span><span class="sxs-lookup"><span data-stu-id="f0e74-290">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span> <span data-ttu-id="f0e74-291">但是，如果用户选择一个子标签，则实际上同时应用了两个标签，即主要标签和次要标签。</span><span class="sxs-lookup"><span data-stu-id="f0e74-291">However, if users select a sublabel, this actually applies two labels at the same time; a primary label and a secondary label.</span></span> <span data-ttu-id="f0e74-292">通过使用子标签，文件可以具有两个分类，分别表示父级/子级关系，以实现更高级别的控制。</span><span class="sxs-lookup"><span data-stu-id="f0e74-292">By using sublabels, a file can have two classifications that denote a parent/child relationship for an additional level of control.</span></span> 

<span data-ttu-id="f0e74-293">例如，标签 **机密** 可能包含 **法律** 和 **财务**等子标签。</span><span class="sxs-lookup"><span data-stu-id="f0e74-293">For example, the label **Confidential** might contain sublabels such as **Legal** and **Finance**.</span></span> <span data-ttu-id="f0e74-294">可将不同的分类视觉标记和不同的权限管理模板应用于这些子标签。</span><span class="sxs-lookup"><span data-stu-id="f0e74-294">You can apply different classification visual markings and different Rights Management templates to these sublabels.</span></span> <span data-ttu-id="f0e74-295">用户不能自行选择 **机密** 标签，只能选择其子标签之一，例如 **法律**。</span><span class="sxs-lookup"><span data-stu-id="f0e74-295">A user cannot select the **Confidential** label by itself; only one of its sublabels, such as **Legal**.</span></span> <span data-ttu-id="f0e74-296">因此，他们看到的标签是 **机密** / **法律**。</span><span class="sxs-lookup"><span data-stu-id="f0e74-296">As a result, the label that they see set is **Confidential** / **Legal**.</span></span> <span data-ttu-id="f0e74-297">该文件的元数据包括 **机密**的一个自定义文本属性、 **法律**的一个自定义文本属性以及另一个包含两个值（**机密和法律**）的属性。</span><span class="sxs-lookup"><span data-stu-id="f0e74-297">The metadata for that file includes one custom text property for **Confidential**, one custom text property for **Legal**, and another that contains both values (**Confidential Legal**).</span></span> 

<span data-ttu-id="f0e74-298">使用子标签时，请不要在主要标签上配置视觉标记、保护和条件。</span><span class="sxs-lookup"><span data-stu-id="f0e74-298">When you use sublabels, don't configure visual markings, protection, and conditions at the primary label.</span></span> <span data-ttu-id="f0e74-299">使用子级别时，仅在子标签上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="f0e74-299">When you use sublevels, configure these setting on the sublabel only.</span></span> <span data-ttu-id="f0e74-300">如果在主要标签及其子标签上配置这些设置，则子标签上的设置优先。</span><span class="sxs-lookup"><span data-stu-id="f0e74-300">If you configure these settings on the primary label and its sublabel, the settings at the sublabel take precedence.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="f0e74-301">标记电子邮件后，任何附件会自动获得相同的标记吗？</span><span class="sxs-lookup"><span data-stu-id="f0e74-301">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="f0e74-302">否。</span><span class="sxs-lookup"><span data-stu-id="f0e74-302">No.</span></span> <span data-ttu-id="f0e74-303">标记带附件的电子邮件时，这些附件不会继承相同的标签。</span><span class="sxs-lookup"><span data-stu-id="f0e74-303">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="f0e74-304">附件要么没有标签，要么保留单独应用的标签。</span><span class="sxs-lookup"><span data-stu-id="f0e74-304">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="f0e74-305">但是，如果电子邮件标签应用了保护，则该保护将应用于 Office 附件。</span><span class="sxs-lookup"><span data-stu-id="f0e74-305">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0e74-306">其他资源</span><span class="sxs-lookup"><span data-stu-id="f0e74-306">Additional resources</span></span>

[<span data-ttu-id="f0e74-307">有关 Azure 信息保护中分类和标记的常见问题</span><span class="sxs-lookup"><span data-stu-id="f0e74-307">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="f0e74-308">将敏感度标签应用于 Office 文档和电子邮件</span><span class="sxs-lookup"><span data-stu-id="f0e74-308">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)