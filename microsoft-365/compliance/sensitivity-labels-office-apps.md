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
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417561"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="2db1f-104">敏感度标签在 Office 应用中的工作方式</span><span class="sxs-lookup"><span data-stu-id="2db1f-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="2db1f-105">在 Office 应用程序中使用敏感度标签有哪些先决条件？</span><span class="sxs-lookup"><span data-stu-id="2db1f-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="2db1f-106">常见要求</span><span class="sxs-lookup"><span data-stu-id="2db1f-106">Common requirements</span></span> 

- <span data-ttu-id="2db1f-107">[必须在安全与合规中心配置和发布](https://aka.ms/managemip)统一的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="2db1f-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="2db1f-108">用户必须使用其工作帐户登录到 Office。</span><span class="sxs-lookup"><span data-stu-id="2db1f-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="2db1f-109">用户必须分配有 Office 365 E3 或更高版本的许可证。</span><span class="sxs-lookup"><span data-stu-id="2db1f-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="2db1f-110">针对 Office for Windows 的其他要求</span><span class="sxs-lookup"><span data-stu-id="2db1f-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="2db1f-111">Azure 信息保护客户端必须未在 Office 中运行。</span><span class="sxs-lookup"><span data-stu-id="2db1f-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="2db1f-112">另请参阅：[敏感度标签能否与 Azure 信息保护客户端一起在 Office for Windows 中运行？](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)。</span><span class="sxs-lookup"><span data-stu-id="2db1f-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="2db1f-113">针对所有平台上的 Outlook 的其他要求</span><span class="sxs-lookup"><span data-stu-id="2db1f-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="2db1f-114">在标签配置中，如果已打开内容标记，则必须为要在传输中插入的内容标记使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="2db1f-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="2db1f-115">Office 目前支持哪些敏感度标签功能？</span><span class="sxs-lookup"><span data-stu-id="2db1f-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="2db1f-116"><font size="-1">功能</span><span class="sxs-lookup"><span data-stu-id="2db1f-116"><font size="-1">Capability</span></span><th><span data-ttu-id="2db1f-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="2db1f-117"><font size="-1">Windows</span></span><th><span data-ttu-id="2db1f-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="2db1f-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="2db1f-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2db1f-119"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2db1f-120">Excel</span><span class="sxs-lookup"><span data-stu-id="2db1f-120">Excel</span></span><br>
<span data-ttu-id="2db1f-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2db1f-121">PowerPoint</span></span><br>
<span data-ttu-id="2db1f-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="2db1f-122">Outlook</span></span>


<td><span data-ttu-id="2db1f-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2db1f-123"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2db1f-124">Excel</span><span class="sxs-lookup"><span data-stu-id="2db1f-124">Excel</span></span><br>
<span data-ttu-id="2db1f-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2db1f-125">PowerPoint</span></span><br>
<span data-ttu-id="2db1f-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="2db1f-126">Outlook</span></span>

<td><span data-ttu-id="2db1f-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2db1f-127"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2db1f-128">Excel</span><span class="sxs-lookup"><span data-stu-id="2db1f-128">Excel</span></span><br>
<span data-ttu-id="2db1f-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2db1f-129">PowerPoint</span></span>
<td><span data-ttu-id="2db1f-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="2db1f-130"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="2db1f-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2db1f-131"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2db1f-132">Excel</span><span class="sxs-lookup"><span data-stu-id="2db1f-132">Excel</span></span><br>
<span data-ttu-id="2db1f-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2db1f-133">PowerPoint</span></span>
<td><span data-ttu-id="2db1f-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="2db1f-134"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="2db1f-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2db1f-135"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2db1f-136">Excel</span><span class="sxs-lookup"><span data-stu-id="2db1f-136">Excel</span></span><br>
<span data-ttu-id="2db1f-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2db1f-137">PowerPoint</span></span>
<td><span data-ttu-id="2db1f-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-138"><font size="-1"> Outlook </b>
</span></span></tr>

<tr>
<td><span data-ttu-id="2db1f-139"><font size="-1">手动应用、更改或删除标签</span><span class="sxs-lookup"><span data-stu-id="2db1f-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="2db1f-140"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-140"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2db1f-142"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-142"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2db1f-144"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-144"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2db1f-146"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-147"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-147"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2db1f-149"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-150"><font size="-1">即将推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2db1f-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="2db1f-151"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="2db1f-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">应用默认标签</a>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="2db1f-153"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-153"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2db1f-155"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-155"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2db1f-157"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-157"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2db1f-159"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-160"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-160"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2db1f-162"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-163"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-164"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2db1f-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">要求提供更改标签的理由</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="2db1f-166"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-166"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2db1f-168"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-168"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2db1f-170"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-170"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2db1f-172"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-173"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-173"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2db1f-175"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-176"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-177"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2db1f-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">为自定义帮助页面提供帮助链接</a>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="2db1f-179"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-179"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2db1f-181"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-181"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2db1f-183"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-183"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2db1f-185"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-186"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-186"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2db1f-188"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-189"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-190"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2db1f-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">标记内容</a>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="2db1f-192"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-192"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2db1f-194"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-194"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2db1f-196"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-196"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2db1f-198"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-199"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-199"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="2db1f-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="2db1f-201"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-202"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-203"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-203"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2db1f-204"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">分配预定义的权限</a>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-204"><font size="-1">Assign pre-defined permissions</span></span><td><span data-ttu-id="2db1f-205"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-205"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2db1f-207"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-207"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2db1f-209"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-209"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2db1f-211"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-212"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="2db1f-212"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2db1f-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2db1f-214"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-215"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-216"><font size="-1">即将推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2db1f-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">允许用户分配权限</a>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Let users assign permissions</a>
</span></span><td><span data-ttu-id="2db1f-218"><font size="-1"><b>是</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2db1f-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="2db1f-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2db1f-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2db1f-220"><font size="-1"><b>是</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2db1f-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="2db1f-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="2db1f-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="2db1f-222"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-223"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-224"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="2db1f-225"><font size="-1">即将推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2db1f-226"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-227"><font size="-1">即将推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2db1f-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="2db1f-228"><font size="-1">向管理员发送<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">标签分析</a>数据</span><span class="sxs-lookup"><span data-stu-id="2db1f-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="2db1f-229"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2db1f-230"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2db1f-231"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-232"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-233"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-234"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-235"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-236"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="2db1f-237"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">要求用户为其电子邮件和文档应用标签</a>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-237"><font size="-1">Require users to apply a label to their email and documents</span></span><td><span data-ttu-id="2db1f-238"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2db1f-239"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2db1f-240"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-241"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-242"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-243"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-244"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-245"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="2db1f-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">将敏感度标签自动应用于内容</a>
</span><span class="sxs-lookup"><span data-stu-id="2db1f-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Apply a sensitivity label to content automatically</a>
</span></span><td><span data-ttu-id="2db1f-247"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2db1f-248"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2db1f-249"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-250"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-251"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-252"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-253"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2db1f-254"><font size="-1">待定</span><span class="sxs-lookup"><span data-stu-id="2db1f-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="2db1f-255"><sup>1</sup>如果已配置，将提示用户提供标签降级的理由。</span><span class="sxs-lookup"><span data-stu-id="2db1f-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="2db1f-256">但是，尚未向管理员提供理由数据。</span><span class="sxs-lookup"><span data-stu-id="2db1f-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="2db1f-257">当支持“向管理员发送标签分析数据”功能时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="2db1f-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="2db1f-258"><sup>2</sup>目前，仅在 Outlook for Windows 和 Outlook for Mac 中允许用户分配权限。</span><span class="sxs-lookup"><span data-stu-id="2db1f-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="2db1f-259">针对 Word、Excel 和 PowerPoint 的可用性待定。</span><span class="sxs-lookup"><span data-stu-id="2db1f-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="2db1f-260"><sup>3</sup>预计为 2019 日历年第 4 季度。</span><span class="sxs-lookup"><span data-stu-id="2db1f-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="2db1f-261">在为内容提供敏感度标签后，何时应用内容标记或加密？</span><span class="sxs-lookup"><span data-stu-id="2db1f-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="2db1f-262">应用程序</span><span class="sxs-lookup"><span data-stu-id="2db1f-262">Application</span></span> | <span data-ttu-id="2db1f-263">内容标记</span><span class="sxs-lookup"><span data-stu-id="2db1f-263">Content marking</span></span> | <span data-ttu-id="2db1f-264">加密</span><span class="sxs-lookup"><span data-stu-id="2db1f-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="2db1f-265">所有平台上的 Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2db1f-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="2db1f-266">立即</span><span class="sxs-lookup"><span data-stu-id="2db1f-266">Immediately</span></span> | <span data-ttu-id="2db1f-267">立即</span><span class="sxs-lookup"><span data-stu-id="2db1f-267">Immediately</span></span> |
| <span data-ttu-id="2db1f-268">Outlook for PC 和 Outlook for Mac</span><span class="sxs-lookup"><span data-stu-id="2db1f-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="2db1f-269">通过 Exchange Online 发送电子邮件之后</span><span class="sxs-lookup"><span data-stu-id="2db1f-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="2db1f-270">立即</span><span class="sxs-lookup"><span data-stu-id="2db1f-270">Immediately</span></span> |
| <span data-ttu-id="2db1f-271">网页版、iOS 版和 Android 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="2db1f-271">Outlook on the web, iOS, and Android</span></span> | <span data-ttu-id="2db1f-272">通过 Exchange Online 发送电子邮件之后</span><span class="sxs-lookup"><span data-stu-id="2db1f-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="2db1f-273">通过 Exchange Online 发送电子邮件之后</span><span class="sxs-lookup"><span data-stu-id="2db1f-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="2db1f-274">敏感度标签能否与 Azure 信息保护客户端一起在 Office for Windows 中运行？</span><span class="sxs-lookup"><span data-stu-id="2db1f-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="2db1f-275">否。</span><span class="sxs-lookup"><span data-stu-id="2db1f-275">No.</span></span> <span data-ttu-id="2db1f-276">如果在 Office for Windows 中加载 Azure 信息保护客户端，则会关闭敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="2db1f-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="2db1f-277">如果你已安装了 Azure 信息保护客户端，但你希望改为使用敏感度标签，则可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2db1f-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="2db1f-278">配置“ **使用 Office 中的“敏感度”功能应用并查看敏感度标签**”组策略设置，可在“**用户配置/管理模板/Microsoft Office 2016/安全设置**”下方找到该设置。</span><span class="sxs-lookup"><span data-stu-id="2db1f-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="2db1f-279">注意：可通过传统的组策略部署机制或 [Office 云策略服务](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)来部署此设置。</span><span class="sxs-lookup"><span data-stu-id="2db1f-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="2db1f-280">或者，你也可以卸载或 [禁用](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) Azure 信息保护客户端。</span><span class="sxs-lookup"><span data-stu-id="2db1f-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="2db1f-281">重新启动所有 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2db1f-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="2db1f-282">Office 的非订阅版本（例如 Office 2016 或 Office 2019）是否支持敏感度标签？</span><span class="sxs-lookup"><span data-stu-id="2db1f-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="2db1f-283">否。</span><span class="sxs-lookup"><span data-stu-id="2db1f-283">No.</span></span> <span data-ttu-id="2db1f-284">敏感度标签仅在 Office 365 订阅中受支持，在任何非订阅版本中均不受支持。</span><span class="sxs-lookup"><span data-stu-id="2db1f-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="2db1f-285">但是，可在非订阅版本的 Office 中使用 Azure 信息保护统一标记客户端。</span><span class="sxs-lookup"><span data-stu-id="2db1f-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="2db1f-286">在设置敏感度标签之前，我曾部署过保护模板。</span><span class="sxs-lookup"><span data-stu-id="2db1f-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="2db1f-287">它们去哪儿了？</span><span class="sxs-lookup"><span data-stu-id="2db1f-287">Where did they go?</span></span>

<span data-ttu-id="2db1f-288">启用敏感度标签后，管理员定义的[保护模板](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)将在 Office 用户体验中隐藏，因为对于已启用加密的敏感度标签而言，它们是多余的。</span><span class="sxs-lookup"><span data-stu-id="2db1f-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="2db1f-289">文件或电子邮件能否具有多个分类？</span><span class="sxs-lookup"><span data-stu-id="2db1f-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="2db1f-290">否。</span><span class="sxs-lookup"><span data-stu-id="2db1f-290">No.</span></span> <span data-ttu-id="2db1f-291">对于每个文档或电子邮件，用户每次可只选一个标签。</span><span class="sxs-lookup"><span data-stu-id="2db1f-291">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="2db1f-292">标记电子邮件后，任何附件会自动获得相同的标记吗？</span><span class="sxs-lookup"><span data-stu-id="2db1f-292">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="2db1f-293">否。</span><span class="sxs-lookup"><span data-stu-id="2db1f-293">No.</span></span> <span data-ttu-id="2db1f-294">标记带附件的电子邮件时，这些附件不会继承相同的标签。</span><span class="sxs-lookup"><span data-stu-id="2db1f-294">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="2db1f-295">附件要么没有标签，要么保留单独应用的标签。</span><span class="sxs-lookup"><span data-stu-id="2db1f-295">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="2db1f-296">但是，如果电子邮件标签应用了保护，则该保护将应用于 Office 附件。</span><span class="sxs-lookup"><span data-stu-id="2db1f-296">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2db1f-297">其他资源</span><span class="sxs-lookup"><span data-stu-id="2db1f-297">Additional resources</span></span>

[<span data-ttu-id="2db1f-298">有关 Azure 信息保护中分类和标记的常见问题</span><span class="sxs-lookup"><span data-stu-id="2db1f-298">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="2db1f-299">将敏感度标签应用于 Office 文档和电子邮件</span><span class="sxs-lookup"><span data-stu-id="2db1f-299">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
