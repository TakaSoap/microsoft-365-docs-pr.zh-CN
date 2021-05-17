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
# <a name="localize-the-user-experience"></a><span data-ttu-id="0b459-104">本地化用户体验</span><span class="sxs-lookup"><span data-stu-id="0b459-104">Localize the user experience</span></span>

<span data-ttu-id="0b459-105">Microsoft 托管桌面设备的用户可以在设置过程中选择他们选择的语言， ("开箱即用体验"，) 之后。</span><span class="sxs-lookup"><span data-stu-id="0b459-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="0b459-106">在设置 ("开箱使用体验") </span><span class="sxs-lookup"><span data-stu-id="0b459-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="0b459-107">在完成设置的过程中，用户可以选择他们选择的语言。</span><span class="sxs-lookup"><span data-stu-id="0b459-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="0b459-108">此选择会影响以下属性：</span><span class="sxs-lookup"><span data-stu-id="0b459-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="0b459-109">Windows 10语言功能：</span><span class="sxs-lookup"><span data-stu-id="0b459-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="0b459-110">显示语言</span><span class="sxs-lookup"><span data-stu-id="0b459-110">Display language</span></span>
    - <span data-ttu-id="0b459-111">键盘语言</span><span class="sxs-lookup"><span data-stu-id="0b459-111">Keyboard language</span></span>
    - <span data-ttu-id="0b459-112">按需与语言相关的功能</span><span class="sxs-lookup"><span data-stu-id="0b459-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="0b459-113">Microsoft 365 应用版语言Enterprise：</span><span class="sxs-lookup"><span data-stu-id="0b459-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="0b459-114">显示语言</span><span class="sxs-lookup"><span data-stu-id="0b459-114">Display language</span></span>
    - <span data-ttu-id="0b459-115">校对和创作工具</span><span class="sxs-lookup"><span data-stu-id="0b459-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="0b459-116">用户只有在设置过程中选择语言，才能按需获取与语言相关的功能。</span><span class="sxs-lookup"><span data-stu-id="0b459-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="0b459-117">完成设置后</span><span class="sxs-lookup"><span data-stu-id="0b459-117">After completing setup</span></span>

<span data-ttu-id="0b459-118">用户可以选择自己选择的语言，以便Windows 10 Microsoft 365 应用版设置Enterprise完成之后随时进行配置。</span><span class="sxs-lookup"><span data-stu-id="0b459-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="0b459-119">具体来说：</span><span class="sxs-lookup"><span data-stu-id="0b459-119">Specifically:</span></span>

- <span data-ttu-id="0b459-120">Windows 10语言功能：</span><span class="sxs-lookup"><span data-stu-id="0b459-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="0b459-121">显示语言</span><span class="sxs-lookup"><span data-stu-id="0b459-121">Display language</span></span>
    - <span data-ttu-id="0b459-122">键盘语言</span><span class="sxs-lookup"><span data-stu-id="0b459-122">Keyboard language</span></span>

- <span data-ttu-id="0b459-123">Microsoft 365 应用版语言Enterprise：</span><span class="sxs-lookup"><span data-stu-id="0b459-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="0b459-124">显示语言</span><span class="sxs-lookup"><span data-stu-id="0b459-124">Display language</span></span>
    - <span data-ttu-id="0b459-125">校对和创作工具</span><span class="sxs-lookup"><span data-stu-id="0b459-125">Proofing and authoring tools</span></span>

<span data-ttu-id="0b459-126">若要使 [Microsoft 365 应用版](#supported-languages)for Enterprise 支持的语言可供用户安装，可以将用户添加到新式 **Workplace-Office-Language_Packs** 组。</span><span class="sxs-lookup"><span data-stu-id="0b459-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="0b459-127">这些语言将在 Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="0b459-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="0b459-128">支持的语言</span><span class="sxs-lookup"><span data-stu-id="0b459-128">Supported languages</span></span>

<span data-ttu-id="0b459-129">对于新设备，制造商必须提供包含你要求的语言的设备映像。</span><span class="sxs-lookup"><span data-stu-id="0b459-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="0b459-130">如果你的制造商映像包含支持的语言列表中提供的语言，服务仍支持该映像。</span><span class="sxs-lookup"><span data-stu-id="0b459-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="0b459-131">如果要重新使用现有设备，可能需要与 Microsoft 客户代表合作，以获取相应的映像。</span><span class="sxs-lookup"><span data-stu-id="0b459-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="0b459-132">有关详细信息，请参阅设备 [图像](../service-description/device-images.md)。</span><span class="sxs-lookup"><span data-stu-id="0b459-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="0b459-133">该[映像提供](../service-description/device-images.md#universal-image)的通用Microsoft 托管桌面包括以下语言和Windows 10：</span><span class="sxs-lookup"><span data-stu-id="0b459-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="0b459-134">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="0b459-134">Arabic</span></span>
- <span data-ttu-id="0b459-135">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="0b459-135">Bulgarian</span></span>
- <span data-ttu-id="0b459-136">简体中文</span><span class="sxs-lookup"><span data-stu-id="0b459-136">Chinese Simplified</span></span>
- <span data-ttu-id="0b459-137">繁体中文</span><span class="sxs-lookup"><span data-stu-id="0b459-137">Chinese Traditional</span></span>
- <span data-ttu-id="0b459-138">克罗地亚语</span><span class="sxs-lookup"><span data-stu-id="0b459-138">Croatian</span></span>
- <span data-ttu-id="0b459-139">捷克语</span><span class="sxs-lookup"><span data-stu-id="0b459-139">Czech</span></span>
- <span data-ttu-id="0b459-140">丹麦语</span><span class="sxs-lookup"><span data-stu-id="0b459-140">Danish</span></span>  
- <span data-ttu-id="0b459-141">荷兰语</span><span class="sxs-lookup"><span data-stu-id="0b459-141">Dutch</span></span>  
- <span data-ttu-id="0b459-142">英语 (美国、英国、澳大利亚、CA、) </span><span class="sxs-lookup"><span data-stu-id="0b459-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="0b459-143">爱沙尼亚语</span><span class="sxs-lookup"><span data-stu-id="0b459-143">Estonian</span></span>
- <span data-ttu-id="0b459-144">芬兰语</span><span class="sxs-lookup"><span data-stu-id="0b459-144">Finnish</span></span> 
- <span data-ttu-id="0b459-145">法语 (法国、加拿大) </span><span class="sxs-lookup"><span data-stu-id="0b459-145">French (France, Canada)</span></span>
- <span data-ttu-id="0b459-146">德语</span><span class="sxs-lookup"><span data-stu-id="0b459-146">German</span></span>
- <span data-ttu-id="0b459-147">希腊语</span><span class="sxs-lookup"><span data-stu-id="0b459-147">Greek</span></span>
- <span data-ttu-id="0b459-148">希伯来语</span><span class="sxs-lookup"><span data-stu-id="0b459-148">Hebrew</span></span>
- <span data-ttu-id="0b459-149">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="0b459-149">Hungarian</span></span>
- <span data-ttu-id="0b459-150">印度尼西亚语</span><span class="sxs-lookup"><span data-stu-id="0b459-150">Indonesian</span></span>
- <span data-ttu-id="0b459-151">意大利语</span><span class="sxs-lookup"><span data-stu-id="0b459-151">Italian</span></span>
- <span data-ttu-id="0b459-152">日语</span><span class="sxs-lookup"><span data-stu-id="0b459-152">Japanese</span></span>
- <span data-ttu-id="0b459-153">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="0b459-153">Korean</span></span>
- <span data-ttu-id="0b459-154">拉脱维亚语</span><span class="sxs-lookup"><span data-stu-id="0b459-154">Latvian</span></span>
- <span data-ttu-id="0b459-155">立陶宛语</span><span class="sxs-lookup"><span data-stu-id="0b459-155">Lithuanian</span></span>
- <span data-ttu-id="0b459-156">挪威语（博克马尔）</span><span class="sxs-lookup"><span data-stu-id="0b459-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="0b459-157">波兰语</span><span class="sxs-lookup"><span data-stu-id="0b459-157">Polish</span></span>
- <span data-ttu-id="0b459-158">葡萄牙语（巴西）</span><span class="sxs-lookup"><span data-stu-id="0b459-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="0b459-159">葡萄牙语（葡萄牙）</span><span class="sxs-lookup"><span data-stu-id="0b459-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="0b459-160">罗马尼亚语</span><span class="sxs-lookup"><span data-stu-id="0b459-160">Romanian</span></span>
- <span data-ttu-id="0b459-161">俄语</span><span class="sxs-lookup"><span data-stu-id="0b459-161">Russian</span></span> 
- <span data-ttu-id="0b459-162">塞尔维亚 (拉丁语字母) </span><span class="sxs-lookup"><span data-stu-id="0b459-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="0b459-163">斯洛伐克语</span><span class="sxs-lookup"><span data-stu-id="0b459-163">Slovak</span></span>
- <span data-ttu-id="0b459-164">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="0b459-164">Slovenian</span></span>
- <span data-ttu-id="0b459-165">西班牙语 (西班牙、墨西哥) </span><span class="sxs-lookup"><span data-stu-id="0b459-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="0b459-166">瑞典语</span><span class="sxs-lookup"><span data-stu-id="0b459-166">Swedish</span></span>
- <span data-ttu-id="0b459-167">泰语</span><span class="sxs-lookup"><span data-stu-id="0b459-167">Thai</span></span>
- <span data-ttu-id="0b459-168">土耳其语</span><span class="sxs-lookup"><span data-stu-id="0b459-168">Turkish</span></span>
- <span data-ttu-id="0b459-169">乌克兰语</span><span class="sxs-lookup"><span data-stu-id="0b459-169">Ukrainian</span></span>
- <span data-ttu-id="0b459-170">越南语</span><span class="sxs-lookup"><span data-stu-id="0b459-170">Vietnamese</span></span>

<span data-ttu-id="0b459-171">Microsoft 365 应用版Enterprise列表可能略有不同。</span><span class="sxs-lookup"><span data-stu-id="0b459-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="0b459-172">如果用户需要此处列出的语言外的其他语言，请通过使用管理门户 提出[](../working-with-managed-desktop/admin-support.md)[支持请求](access-admin-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="0b459-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="0b459-173">支持和操作的语言</span><span class="sxs-lookup"><span data-stu-id="0b459-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="0b459-174">用户支持</span><span class="sxs-lookup"><span data-stu-id="0b459-174">User support</span></span>
<span data-ttu-id="0b459-175">Microsoft 托管桌面仅提供英文版支持。</span><span class="sxs-lookup"><span data-stu-id="0b459-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="0b459-176">如果用户在 microsoft 应用中选择获取帮助语言，他们将从一般 Microsoft 支持渠道获得支持，而不是直接从 microsoft Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="0b459-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="0b459-177">有关详细信息，请参阅 [获取用户帮助](../working-with-managed-desktop/end-user-support.md)。</span><span class="sxs-lookup"><span data-stu-id="0b459-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="0b459-178">如果你的用户需要其他语言的支持，你将需要通过非 Microsoft 支持源或你自己的组织提供。</span><span class="sxs-lookup"><span data-stu-id="0b459-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="0b459-179">管理员支持和操作</span><span class="sxs-lookup"><span data-stu-id="0b459-179">Admin support and operations</span></span>
<span data-ttu-id="0b459-180">Microsoft 托管桌面仅提供英语版管理员支持。</span><span class="sxs-lookup"><span data-stu-id="0b459-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="0b459-181">这包括管理门户和与管理员操作Microsoft 托管桌面通信。</span><span class="sxs-lookup"><span data-stu-id="0b459-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="0b459-182">你应该假设所有与管理员相关的交互和界面都将采用英语，除非另行指定。</span><span class="sxs-lookup"><span data-stu-id="0b459-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


