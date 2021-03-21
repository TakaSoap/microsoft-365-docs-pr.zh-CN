---
title: 如何确定数据治理建议的内容
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 安全中心与 Microsoft 365 合规中心根据你组织的当前设置提供数据管理建议，并让你可以通过几次单击进行设置。其中一些建议会检测组织中的特定内容，然后提供管理该内容的建议步骤。例如，建议可能会检测包含业务关键内容的项目（如律师-客户特权或 NDA 信息），然后让你自动为这些项目应用保留标签，以确保根据需要对它们进行分类和保留。本主题列出了你可能会看到的数据管理建议，并介绍了为触发每条建议而检测的内容。
ms.openlocfilehash: 9a022369fb783a498971c91664fa6532472d8589
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922606"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="0a9c2-106">如何确定数据治理建议的内容</span><span class="sxs-lookup"><span data-stu-id="0a9c2-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="0a9c2-p102">Microsoft 365 安全中心与 Microsoft 365 合规中心根据你组织的当前设置提供数据管理建议，并让你可以通过几次单击进行设置。其中一些建议会检测组织中的特定内容，然后提供管理该内容的建议步骤。例如，建议可能会检测包含业务关键内容的项目（如律师-客户特权或 NDA 信息），然后让你自动为这些项目应用保留标签，以确保根据需要对它们进行分类和保留。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-p102">The Microsoft 365 security center and Microsoft 365 compliance center provide recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they're classified and retained as needed.</span></span>

<span data-ttu-id="0a9c2-110">本主题列出了你可能会看到的数据治理建议，并介绍了为触发每条建议而检测的内容。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="0a9c2-111">清理语音邮件</span><span class="sxs-lookup"><span data-stu-id="0a9c2-111">Clean up voicemail</span></span>

<span data-ttu-id="0a9c2-p103">在用户邮箱中检测到标识为“语音邮件”邮件类型的电子邮件时，将显示此建议。详细了解 [Exchange 中的邮件属性](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-p103">This recommendation appears when email messages identified as the message type 'voicemail' are detected in users' mailboxes. Learn more about [message properties in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="0a9c2-114">标记律师-客户特权内容</span><span class="sxs-lookup"><span data-stu-id="0a9c2-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="0a9c2-115">当满足以下任一条件时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="0a9c2-116">在电子邮件正文中检测到以下关键字的任何组合：</span><span class="sxs-lookup"><span data-stu-id="0a9c2-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="0a9c2-117">ACP</span><span class="sxs-lookup"><span data-stu-id="0a9c2-117">ACP</span></span>
    - <span data-ttu-id="0a9c2-118">律师客户特权</span><span class="sxs-lookup"><span data-stu-id="0a9c2-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="0a9c2-119">律师-客户特权</span><span class="sxs-lookup"><span data-stu-id="0a9c2-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="0a9c2-120">律师-客户特权的</span><span class="sxs-lookup"><span data-stu-id="0a9c2-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="0a9c2-121">在 SharePoint 或 OneDrive 文件中检测到以下关键字的任意组合：</span><span class="sxs-lookup"><span data-stu-id="0a9c2-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="0a9c2-122">ACP</span><span class="sxs-lookup"><span data-stu-id="0a9c2-122">ACP</span></span>
    - <span data-ttu-id="0a9c2-123">律师客户特权\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="0a9c2-124">AC 特权</span><span class="sxs-lookup"><span data-stu-id="0a9c2-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="0a9c2-125">保留音频文件</span><span class="sxs-lookup"><span data-stu-id="0a9c2-125">Retain audio files</span></span>

<span data-ttu-id="0a9c2-126">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="0a9c2-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="0a9c2-127">.MP3</span></span>
- <span data-ttu-id="0a9c2-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="0a9c2-128">.WMA</span></span>
- <span data-ttu-id="0a9c2-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="0a9c2-129">.WAV</span></span>
- <span data-ttu-id="0a9c2-130">.RA</span><span class="sxs-lookup"><span data-stu-id="0a9c2-130">.RA</span></span>
- <span data-ttu-id="0a9c2-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-131">.RAM</span></span>
- <span data-ttu-id="0a9c2-132">.RM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-132">.RM</span></span>
- <span data-ttu-id="0a9c2-133">.MID</span><span class="sxs-lookup"><span data-stu-id="0a9c2-133">.MID</span></span>
- <span data-ttu-id="0a9c2-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="0a9c2-134">.OGG</span></span>
- <span data-ttu-id="0a9c2-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="0a9c2-135">.AIFF</span></span>
- <span data-ttu-id="0a9c2-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-136">.PCM</span></span>
- <span data-ttu-id="0a9c2-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="0a9c2-137">.AAC</span></span>
- <span data-ttu-id="0a9c2-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="0a9c2-138">.FLAC</span></span>
- <span data-ttu-id="0a9c2-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="0a9c2-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="0a9c2-140">保留 CAD 文件</span><span class="sxs-lookup"><span data-stu-id="0a9c2-140">Retain CAD files</span></span>

<span data-ttu-id="0a9c2-141">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="0a9c2-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="0a9c2-142">.3DXML</span></span>
- <span data-ttu-id="0a9c2-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="0a9c2-143">.ACIS</span></span>
- <span data-ttu-id="0a9c2-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="0a9c2-144">.ARC</span></span>
- <span data-ttu-id="0a9c2-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-145">.ASM</span></span>
- <span data-ttu-id="0a9c2-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-146">.CAT\*</span></span>
- <span data-ttu-id="0a9c2-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="0a9c2-147">.CGR</span></span>
- <span data-ttu-id="0a9c2-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-148">.DW\*</span></span>
- <span data-ttu-id="0a9c2-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-149">.DX\*</span></span>
- <span data-ttu-id="0a9c2-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="0a9c2-150">.EDRW</span></span>
- <span data-ttu-id="0a9c2-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-151">.IAM</span></span>
- <span data-ttu-id="0a9c2-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="0a9c2-152">.IGES</span></span>
- <span data-ttu-id="0a9c2-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="0a9c2-153">.IGS</span></span>
- <span data-ttu-id="0a9c2-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="0a9c2-154">.IPT</span></span>
- <span data-ttu-id="0a9c2-155">.JT</span><span class="sxs-lookup"><span data-stu-id="0a9c2-155">.JT</span></span>
- <span data-ttu-id="0a9c2-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="0a9c2-156">.MF1</span></span>
- <span data-ttu-id="0a9c2-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="0a9c2-157">.NEU</span></span>
- <span data-ttu-id="0a9c2-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="0a9c2-158">.PAR</span></span>
- <span data-ttu-id="0a9c2-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="0a9c2-159">.PKG</span></span>
- <span data-ttu-id="0a9c2-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="0a9c2-160">.PRC</span></span>
- <span data-ttu-id="0a9c2-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="0a9c2-161">.PRT</span></span>
- <span data-ttu-id="0a9c2-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-162">.PSM</span></span>
- <span data-ttu-id="0a9c2-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="0a9c2-163">.PWD</span></span>
- <span data-ttu-id="0a9c2-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-164">.SLD\*</span></span>
- <span data-ttu-id="0a9c2-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="0a9c2-165">.STEP</span></span>
- <span data-ttu-id="0a9c2-166">.STL</span><span class="sxs-lookup"><span data-stu-id="0a9c2-166">.STL</span></span>
- <span data-ttu-id="0a9c2-167">.STP</span><span class="sxs-lookup"><span data-stu-id="0a9c2-167">.STP</span></span>
- <span data-ttu-id="0a9c2-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="0a9c2-168">.U3D</span></span>
- <span data-ttu-id="0a9c2-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="0a9c2-169">.UNV</span></span>
- <span data-ttu-id="0a9c2-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="0a9c2-170">.VRML</span></span>
- <span data-ttu-id="0a9c2-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="0a9c2-171">.WRL</span></span>
- <span data-ttu-id="0a9c2-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-172">.X_\*</span></span>
- <span data-ttu-id="0a9c2-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="0a9c2-173">.XAS</span></span>
- <span data-ttu-id="0a9c2-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-174">.XMT\*</span></span>
- <span data-ttu-id="0a9c2-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="0a9c2-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="0a9c2-176">保留图像文件</span><span class="sxs-lookup"><span data-stu-id="0a9c2-176">Retain image files</span></span>

<span data-ttu-id="0a9c2-177">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="0a9c2-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="0a9c2-178">.JPEG</span></span>
- <span data-ttu-id="0a9c2-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="0a9c2-179">.GIF</span></span>
- <span data-ttu-id="0a9c2-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-180">.TIF\*</span></span>
- <span data-ttu-id="0a9c2-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="0a9c2-181">.BMP</span></span>
- <span data-ttu-id="0a9c2-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="0a9c2-182">.PNG</span></span>
- <span data-ttu-id="0a9c2-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="0a9c2-183">.RAW</span></span>
- <span data-ttu-id="0a9c2-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="0a9c2-184">.PSD</span></span>
- <span data-ttu-id="0a9c2-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="0a9c2-185">.PSP</span></span>
- <span data-ttu-id="0a9c2-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="0a9c2-186">.JPG</span></span>
- <span data-ttu-id="0a9c2-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="0a9c2-187">.EXIF</span></span>
- <span data-ttu-id="0a9c2-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-188">.PPM</span></span>
- <span data-ttu-id="0a9c2-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-189">.PGM</span></span>
- <span data-ttu-id="0a9c2-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-190">.PBM</span></span>
- <span data-ttu-id="0a9c2-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-191">.PNM</span></span>
- <span data-ttu-id="0a9c2-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="0a9c2-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="0a9c2-193">保留 NDA 内容</span><span class="sxs-lookup"><span data-stu-id="0a9c2-193">Retain NDA content</span></span> 

<span data-ttu-id="0a9c2-194">当满足以下任一条件时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="0a9c2-195">在电子邮件正文中检测到以下关键字的任何组合：</span><span class="sxs-lookup"><span data-stu-id="0a9c2-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="0a9c2-196">NDA</span><span class="sxs-lookup"><span data-stu-id="0a9c2-196">NDA</span></span>
    - <span data-ttu-id="0a9c2-197">“保密协议”</span><span class="sxs-lookup"><span data-stu-id="0a9c2-197">"Non-Disclosure Agreement"</span></span>
    - <span data-ttu-id="0a9c2-198">“保密协议”</span><span class="sxs-lookup"><span data-stu-id="0a9c2-198">"Non Disclosure Agreement"</span></span>

- <span data-ttu-id="0a9c2-199">在 SharePoint 或 OneDrive 中的 .PDF 或 .DOC 文件中检测到以下关键字的任意组合：</span><span class="sxs-lookup"><span data-stu-id="0a9c2-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="0a9c2-200">NDA</span><span class="sxs-lookup"><span data-stu-id="0a9c2-200">NDA</span></span>
    - <span data-ttu-id="0a9c2-201">保密协议</span><span class="sxs-lookup"><span data-stu-id="0a9c2-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="0a9c2-202">保留软件开发文件</span><span class="sxs-lookup"><span data-stu-id="0a9c2-202">Retain software development files</span></span>

<span data-ttu-id="0a9c2-203">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="0a9c2-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="0a9c2-204">.ASAX</span></span>
- <span data-ttu-id="0a9c2-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="0a9c2-205">.ASM</span></span>
- <span data-ttu-id="0a9c2-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-206">.ASP\*</span></span>
- <span data-ttu-id="0a9c2-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="0a9c2-207">.BAT</span></span>
- <span data-ttu-id="0a9c2-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="0a9c2-208">.CONFIG</span></span>
- <span data-ttu-id="0a9c2-209">.CS</span><span class="sxs-lookup"><span data-stu-id="0a9c2-209">.CS</span></span>
- <span data-ttu-id="0a9c2-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="0a9c2-210">.CSS</span></span>
- <span data-ttu-id="0a9c2-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="0a9c2-211">.DISCO</span></span>
- <span data-ttu-id="0a9c2-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-212">.HTM\*</span></span>
- <span data-ttu-id="0a9c2-213">.INC</span><span class="sxs-lookup"><span data-stu-id="0a9c2-213">.INC</span></span>
- <span data-ttu-id="0a9c2-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="0a9c2-214">.JAD</span></span>
- <span data-ttu-id="0a9c2-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="0a9c2-215">.JAVA</span></span>
- <span data-ttu-id="0a9c2-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-216">.JS\*</span></span>
- <span data-ttu-id="0a9c2-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="0a9c2-217">.LIB</span></span>
- <span data-ttu-id="0a9c2-218">.O</span><span class="sxs-lookup"><span data-stu-id="0a9c2-218">.O</span></span>
- <span data-ttu-id="0a9c2-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="0a9c2-219">.PHP</span></span>
- <span data-ttu-id="0a9c2-220">.RC</span><span class="sxs-lookup"><span data-stu-id="0a9c2-220">.RC</span></span>
- <span data-ttu-id="0a9c2-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="0a9c2-221">.RESX</span></span>
- <span data-ttu-id="0a9c2-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="0a9c2-222">.RPT</span></span>
- <span data-ttu-id="0a9c2-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="0a9c2-223">.RSS</span></span>
- <span data-ttu-id="0a9c2-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="0a9c2-224">.SCPT</span></span>
- <span data-ttu-id="0a9c2-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="0a9c2-225">.SRC</span></span>
- <span data-ttu-id="0a9c2-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-226">.VB\*</span></span>
- <span data-ttu-id="0a9c2-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="0a9c2-227">.WSF</span></span>
- <span data-ttu-id="0a9c2-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="0a9c2-228">.XCODEPROJ</span></span>
- <span data-ttu-id="0a9c2-229">.XML</span><span class="sxs-lookup"><span data-stu-id="0a9c2-229">.XML</span></span>
- <span data-ttu-id="0a9c2-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="0a9c2-230">.XSD</span></span>
- <span data-ttu-id="0a9c2-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="0a9c2-232">保留视频文件</span><span class="sxs-lookup"><span data-stu-id="0a9c2-232">Retain video files</span></span>

<span data-ttu-id="0a9c2-233">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="0a9c2-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="0a9c2-234">.AVCHD</span></span>
- <span data-ttu-id="0a9c2-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="0a9c2-235">.AVI</span></span>
- <span data-ttu-id="0a9c2-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="0a9c2-236">.FLV</span></span>
- <span data-ttu-id="0a9c2-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="0a9c2-237">.MOV</span></span>
- <span data-ttu-id="0a9c2-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="0a9c2-238">.MP2V</span></span>
- <span data-ttu-id="0a9c2-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="0a9c2-239">.MP4</span></span>
- <span data-ttu-id="0a9c2-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="0a9c2-240">.MP4V</span></span>
- <span data-ttu-id="0a9c2-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="0a9c2-241">.MPE</span></span>
- <span data-ttu-id="0a9c2-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="0a9c2-242">.MPEG</span></span>
- <span data-ttu-id="0a9c2-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="0a9c2-243">.MPEG1</span></span>
- <span data-ttu-id="0a9c2-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="0a9c2-244">.MPEG2</span></span>
- <span data-ttu-id="0a9c2-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="0a9c2-245">.MPEG4</span></span>
- <span data-ttu-id="0a9c2-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="0a9c2-246">.MPG</span></span>
- <span data-ttu-id="0a9c2-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="0a9c2-247">.MPG2</span></span>
- <span data-ttu-id="0a9c2-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="0a9c2-248">.MPG4</span></span>
- <span data-ttu-id="0a9c2-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="0a9c2-249">.WMV</span></span>
- <span data-ttu-id="0a9c2-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="0a9c2-250">.XMV</span></span>