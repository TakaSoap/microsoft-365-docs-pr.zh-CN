---
title: 本地化用户体验
description: 如何为用户本地化设备
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023257"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="c662b-104">本地化用户体验</span><span class="sxs-lookup"><span data-stu-id="c662b-104">Localize the user experience</span></span>

<span data-ttu-id="c662b-105">Microsoft 托管桌面设备的用户可以在设置过程中选择他们选择的语言， ("开箱即用体验"，) 之后。</span><span class="sxs-lookup"><span data-stu-id="c662b-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="c662b-106">在设置 ("开箱使用体验") </span><span class="sxs-lookup"><span data-stu-id="c662b-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="c662b-107">在完成设置的过程中，用户可以选择他们选择的语言。</span><span class="sxs-lookup"><span data-stu-id="c662b-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="c662b-108">此选择会影响以下属性：</span><span class="sxs-lookup"><span data-stu-id="c662b-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="c662b-109">Windows 10 语言功能：</span><span class="sxs-lookup"><span data-stu-id="c662b-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="c662b-110">显示语言</span><span class="sxs-lookup"><span data-stu-id="c662b-110">Display language</span></span>
    - <span data-ttu-id="c662b-111">键盘语言</span><span class="sxs-lookup"><span data-stu-id="c662b-111">Keyboard language</span></span>
    - <span data-ttu-id="c662b-112">按需与语言相关的功能</span><span class="sxs-lookup"><span data-stu-id="c662b-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="c662b-113">Microsoft 365 企业应用版语言功能：</span><span class="sxs-lookup"><span data-stu-id="c662b-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="c662b-114">显示语言</span><span class="sxs-lookup"><span data-stu-id="c662b-114">Display language</span></span>
    - <span data-ttu-id="c662b-115">校对和创作工具</span><span class="sxs-lookup"><span data-stu-id="c662b-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="c662b-116">用户只有在设置过程中选择语言，才能按需获取与语言相关的功能。</span><span class="sxs-lookup"><span data-stu-id="c662b-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="c662b-117">完成设置后</span><span class="sxs-lookup"><span data-stu-id="c662b-117">After completing setup</span></span>

<span data-ttu-id="c662b-118">设置过程完成后，用户可以随时为 Windows 10 和 Microsoft 365 企业应用版选择其选择的语言。</span><span class="sxs-lookup"><span data-stu-id="c662b-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="c662b-119">具体来说：</span><span class="sxs-lookup"><span data-stu-id="c662b-119">Specifically:</span></span>

- <span data-ttu-id="c662b-120">Windows 10 语言功能：</span><span class="sxs-lookup"><span data-stu-id="c662b-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="c662b-121">显示语言</span><span class="sxs-lookup"><span data-stu-id="c662b-121">Display language</span></span>
    - <span data-ttu-id="c662b-122">键盘语言</span><span class="sxs-lookup"><span data-stu-id="c662b-122">Keyboard language</span></span>

- <span data-ttu-id="c662b-123">Microsoft 365 企业应用版语言功能：</span><span class="sxs-lookup"><span data-stu-id="c662b-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="c662b-124">显示语言</span><span class="sxs-lookup"><span data-stu-id="c662b-124">Display language</span></span>
    - <span data-ttu-id="c662b-125">校对和创作工具</span><span class="sxs-lookup"><span data-stu-id="c662b-125">Proofing and authoring tools</span></span>

<span data-ttu-id="c662b-126">若要使 [](#supported-languages)Microsoft 365 企业应用版支持的语言可供用户安装，将用户添加到"新式 **Workplace-Office-Language_Packs** 组"。</span><span class="sxs-lookup"><span data-stu-id="c662b-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="c662b-127">这些语言将在 Intune 公司门户中提供。</span><span class="sxs-lookup"><span data-stu-id="c662b-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="c662b-128">支持的语言</span><span class="sxs-lookup"><span data-stu-id="c662b-128">Supported languages</span></span>

<span data-ttu-id="c662b-129">对于新设备，制造商必须提供包含你要求的语言的设备映像。</span><span class="sxs-lookup"><span data-stu-id="c662b-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="c662b-130">如果你的制造商映像包含支持的语言列表中提供的语言，服务仍支持该映像。</span><span class="sxs-lookup"><span data-stu-id="c662b-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="c662b-131">如果要重新使用现有设备，可能需要与 Microsoft 客户代表合作，以获取相应的映像。</span><span class="sxs-lookup"><span data-stu-id="c662b-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="c662b-132">有关详细信息，请参阅设备 [图像](../service-description/device-images.md)。</span><span class="sxs-lookup"><span data-stu-id="c662b-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="c662b-133">Microsoft [托管桌面](../service-description/device-images.md#universal-image) 提供的通用映像包括以下语言和适用于 Windows 10：</span><span class="sxs-lookup"><span data-stu-id="c662b-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="c662b-134">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="c662b-134">Arabic</span></span>
- <span data-ttu-id="c662b-135">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="c662b-135">Bulgarian</span></span>
- <span data-ttu-id="c662b-136">简体中文</span><span class="sxs-lookup"><span data-stu-id="c662b-136">Chinese Simplified</span></span>
- <span data-ttu-id="c662b-137">繁体中文</span><span class="sxs-lookup"><span data-stu-id="c662b-137">Chinese Traditional</span></span>
- <span data-ttu-id="c662b-138">克罗地亚语</span><span class="sxs-lookup"><span data-stu-id="c662b-138">Croatian</span></span>
- <span data-ttu-id="c662b-139">捷克语</span><span class="sxs-lookup"><span data-stu-id="c662b-139">Czech</span></span>
- <span data-ttu-id="c662b-140">丹麦语</span><span class="sxs-lookup"><span data-stu-id="c662b-140">Danish</span></span>  
- <span data-ttu-id="c662b-141">荷兰语</span><span class="sxs-lookup"><span data-stu-id="c662b-141">Dutch</span></span>  
- <span data-ttu-id="c662b-142">英语 (美国、英国、澳大利亚、CA、) </span><span class="sxs-lookup"><span data-stu-id="c662b-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="c662b-143">爱沙尼亚语</span><span class="sxs-lookup"><span data-stu-id="c662b-143">Estonian</span></span>
- <span data-ttu-id="c662b-144">芬兰语</span><span class="sxs-lookup"><span data-stu-id="c662b-144">Finnish</span></span> 
- <span data-ttu-id="c662b-145">法语 (法国、加拿大) </span><span class="sxs-lookup"><span data-stu-id="c662b-145">French (France, Canada)</span></span>
- <span data-ttu-id="c662b-146">德语</span><span class="sxs-lookup"><span data-stu-id="c662b-146">German</span></span>
- <span data-ttu-id="c662b-147">希腊语</span><span class="sxs-lookup"><span data-stu-id="c662b-147">Greek</span></span>
- <span data-ttu-id="c662b-148">希伯来语</span><span class="sxs-lookup"><span data-stu-id="c662b-148">Hebrew</span></span>
- <span data-ttu-id="c662b-149">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="c662b-149">Hungarian</span></span>
- <span data-ttu-id="c662b-150">印度尼西亚语</span><span class="sxs-lookup"><span data-stu-id="c662b-150">Indonesian</span></span>
- <span data-ttu-id="c662b-151">意大利语</span><span class="sxs-lookup"><span data-stu-id="c662b-151">Italian</span></span>
- <span data-ttu-id="c662b-152">日语</span><span class="sxs-lookup"><span data-stu-id="c662b-152">Japanese</span></span>
- <span data-ttu-id="c662b-153">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="c662b-153">Korean</span></span>
- <span data-ttu-id="c662b-154">拉脱维亚语</span><span class="sxs-lookup"><span data-stu-id="c662b-154">Latvian</span></span>
- <span data-ttu-id="c662b-155">立陶宛语</span><span class="sxs-lookup"><span data-stu-id="c662b-155">Lithuanian</span></span>
- <span data-ttu-id="c662b-156">挪威语（博克马尔）</span><span class="sxs-lookup"><span data-stu-id="c662b-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="c662b-157">波兰语</span><span class="sxs-lookup"><span data-stu-id="c662b-157">Polish</span></span>
- <span data-ttu-id="c662b-158">葡萄牙语（巴西）</span><span class="sxs-lookup"><span data-stu-id="c662b-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="c662b-159">葡萄牙语（葡萄牙）</span><span class="sxs-lookup"><span data-stu-id="c662b-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="c662b-160">罗马尼亚语</span><span class="sxs-lookup"><span data-stu-id="c662b-160">Romanian</span></span>
- <span data-ttu-id="c662b-161">俄语</span><span class="sxs-lookup"><span data-stu-id="c662b-161">Russian</span></span> 
- <span data-ttu-id="c662b-162">塞尔维亚 (拉丁语字母) </span><span class="sxs-lookup"><span data-stu-id="c662b-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="c662b-163">斯洛伐克语</span><span class="sxs-lookup"><span data-stu-id="c662b-163">Slovak</span></span>
- <span data-ttu-id="c662b-164">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="c662b-164">Slovenian</span></span>
- <span data-ttu-id="c662b-165">西班牙语 (西班牙、墨西哥) </span><span class="sxs-lookup"><span data-stu-id="c662b-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="c662b-166">瑞典语</span><span class="sxs-lookup"><span data-stu-id="c662b-166">Swedish</span></span>
- <span data-ttu-id="c662b-167">泰语</span><span class="sxs-lookup"><span data-stu-id="c662b-167">Thai</span></span>
- <span data-ttu-id="c662b-168">土耳其语</span><span class="sxs-lookup"><span data-stu-id="c662b-168">Turkish</span></span>
- <span data-ttu-id="c662b-169">乌克兰语</span><span class="sxs-lookup"><span data-stu-id="c662b-169">Ukrainian</span></span>
- <span data-ttu-id="c662b-170">越南语</span><span class="sxs-lookup"><span data-stu-id="c662b-170">Vietnamese</span></span>

<span data-ttu-id="c662b-171">Microsoft 365 企业应用版可能支持略有不同的列表。</span><span class="sxs-lookup"><span data-stu-id="c662b-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="c662b-172">如果用户需要此处列出的语言外的其他语言，请通过使用管理门户 提出[](../working-with-managed-desktop/admin-support.md)[支持请求](access-admin-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="c662b-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="c662b-173">支持和操作的语言</span><span class="sxs-lookup"><span data-stu-id="c662b-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="c662b-174">用户支持</span><span class="sxs-lookup"><span data-stu-id="c662b-174">User support</span></span>
<span data-ttu-id="c662b-175">Microsoft 托管桌面仅提供英文版支持。</span><span class="sxs-lookup"><span data-stu-id="c662b-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="c662b-176">如果用户在"获取帮助"应用中选择其他语言，他们将从常规 Microsoft 支持渠道获得支持，而不是直接从 Microsoft 托管桌面获得支持。</span><span class="sxs-lookup"><span data-stu-id="c662b-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="c662b-177">有关详细信息，请参阅 [获取用户帮助](../working-with-managed-desktop/end-user-support.md)。</span><span class="sxs-lookup"><span data-stu-id="c662b-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="c662b-178">如果你的用户需要其他语言的支持，你将需要通过非 Microsoft 支持源或你自己的组织提供。</span><span class="sxs-lookup"><span data-stu-id="c662b-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="c662b-179">管理员支持和操作</span><span class="sxs-lookup"><span data-stu-id="c662b-179">Admin support and operations</span></span>
<span data-ttu-id="c662b-180">Microsoft 托管桌面仅提供英语版管理员支持。</span><span class="sxs-lookup"><span data-stu-id="c662b-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="c662b-181">这包括管理门户和与 Microsoft 托管桌面操作的所有通信。</span><span class="sxs-lookup"><span data-stu-id="c662b-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="c662b-182">你应该假设所有与管理员相关的交互和界面都将采用英语，除非另行指定。</span><span class="sxs-lookup"><span data-stu-id="c662b-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


