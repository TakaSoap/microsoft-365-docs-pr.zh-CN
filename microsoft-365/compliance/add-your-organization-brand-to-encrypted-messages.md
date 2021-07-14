---
title: 将组织品牌添加到加密邮件中
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 了解Office 365管理员如何将组织的品牌应用于加密电子邮件&加密门户的内容。
ms.openlocfilehash: 95320e9f268f19cedd993efe4fa0e68fd75af125
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430728"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="7bf6a-103">向企业邮件加密加密邮件Microsoft 365组织品牌</span><span class="sxs-lookup"><span data-stu-id="7bf6a-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="7bf6a-104">你可以应用公司品牌来自定义组织的电子邮件和加密门户的外观。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="7bf6a-105">你需要将全局管理员权限应用于工作或学校帐户，然后才能开始操作。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="7bf6a-106">拥有这些权限后，使用 Get-OMEConfiguration 和 Set-OMEConfiguration Windows PowerShell cmdlet 自定义加密电子邮件的以下部分：</span><span class="sxs-lookup"><span data-stu-id="7bf6a-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="7bf6a-107">介绍性文本</span><span class="sxs-lookup"><span data-stu-id="7bf6a-107">Introductory text</span></span>

- <span data-ttu-id="7bf6a-108">免责声明文本</span><span class="sxs-lookup"><span data-stu-id="7bf6a-108">Disclaimer text</span></span>

- <span data-ttu-id="7bf6a-109">组织隐私声明的 URL</span><span class="sxs-lookup"><span data-stu-id="7bf6a-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="7bf6a-110">OME 门户中的文本</span><span class="sxs-lookup"><span data-stu-id="7bf6a-110">Text in the OME portal</span></span>

- <span data-ttu-id="7bf6a-111">显示在电子邮件和 OME 门户中的徽标，或者是否使用徽标</span><span class="sxs-lookup"><span data-stu-id="7bf6a-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="7bf6a-112">电子邮件和 OME 门户中的背景颜色</span><span class="sxs-lookup"><span data-stu-id="7bf6a-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="7bf6a-113">您也可以随时还原到默认的外观。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="7bf6a-114">如果您希望获得更多控制权，Office 365 高级邮件加密为来自组织的加密电子邮件创建多个模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="7bf6a-115">使用这些模板来控制最终用户体验的某些部分。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="7bf6a-116">例如，指定收件人是否可以使用 Google、Yahoo 和 Microsoft 帐户登录加密门户。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="7bf6a-117">使用模板实现多个用例，例如：</span><span class="sxs-lookup"><span data-stu-id="7bf6a-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="7bf6a-118">各个部门，如财务、销售等。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="7bf6a-119">不同产品</span><span class="sxs-lookup"><span data-stu-id="7bf6a-119">Different products</span></span>

- <span data-ttu-id="7bf6a-120">不同的地理区域或国家</span><span class="sxs-lookup"><span data-stu-id="7bf6a-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="7bf6a-121">是否允许吊销电子邮件</span><span class="sxs-lookup"><span data-stu-id="7bf6a-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="7bf6a-122">是否希望发送给外部收件人的电子邮件在指定的天数后过期。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="7bf6a-123">创建模板后，可以使用自定义邮件流规则将它们应用于加密Exchange电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="7bf6a-124">如果已Office 365 高级邮件加密，可以撤消使用这些模板打造品牌的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="7bf6a-125">使用 OME 品牌模板</span><span class="sxs-lookup"><span data-stu-id="7bf6a-125">Work with OME branding templates</span></span>

<span data-ttu-id="7bf6a-126">可以在品牌模板中修改多个功能。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="7bf6a-127">可以修改但不能删除默认模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="7bf6a-128">如果您具有高级邮件加密，则还可以创建、修改和删除自定义模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="7bf6a-129">使用Windows PowerShell一次使用一个品牌模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="7bf6a-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - 修改默认品牌模板或您创建的自定义品牌模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="7bf6a-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - 创建新的品牌模板，仅高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="7bf6a-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - 删除自定义品牌模板，仅高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="7bf6a-133">不能删除默认品牌模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="7bf6a-134">修改 OME 品牌模板</span><span class="sxs-lookup"><span data-stu-id="7bf6a-134">Modify an OME branding template</span></span>

<span data-ttu-id="7bf6a-135">使用Windows PowerShell一次修改一个品牌模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="7bf6a-136">如果您具有高级邮件加密，则还可以创建、修改和删除自定义模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="7bf6a-137">使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="7bf6a-138">有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7bf6a-139">按照 [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) 中所述使用 Set-OMEConfiguration cmdlet，或使用以下图形和表作为指南。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![可自定义的电子邮件部件](../media/ome-template-breakout.png)

|<span data-ttu-id="7bf6a-141">**自定义加密体验的这一功能**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="7bf6a-142">**使用这些命令**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7bf6a-143">背景色</span><span class="sxs-lookup"><span data-stu-id="7bf6a-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="7bf6a-144">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="7bf6a-145">有关背景颜色详细信息， [请参阅本文稍后](#background-color-reference) 介绍的"背景颜色"部分。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="7bf6a-146">徽标</span><span class="sxs-lookup"><span data-stu-id="7bf6a-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="7bf6a-147">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="7bf6a-148">支持的文件格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="7bf6a-149">徽标文件的最佳大小：小于 40 KB</span><span class="sxs-lookup"><span data-stu-id="7bf6a-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="7bf6a-150">徽标图像的最佳大小：170x70 像素。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="7bf6a-151">如果图像超过这些尺寸，服务会调整徽标大小，以显示在门户中。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="7bf6a-152">该服务不会修改图形文件本身。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="7bf6a-153">为了获得最佳结果，请使用最佳大小。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="7bf6a-154">发件人姓名和电子邮件地址旁边的文本</span><span class="sxs-lookup"><span data-stu-id="7bf6a-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="7bf6a-155">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="7bf6a-156">"阅读邮件"按钮上显示的文本</span><span class="sxs-lookup"><span data-stu-id="7bf6a-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="7bf6a-157">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="7bf6a-158">显示在"阅读邮件"按钮下方的文本</span><span class="sxs-lookup"><span data-stu-id="7bf6a-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="7bf6a-159">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="7bf6a-160">隐私声明链接的 URL</span><span class="sxs-lookup"><span data-stu-id="7bf6a-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="7bf6a-161">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="7bf6a-162">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="7bf6a-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="7bf6a-163">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="7bf6a-164">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="7bf6a-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="7bf6a-165">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="7bf6a-166">为此自定义模板启用或禁用一次传递代码的身份验证</span><span class="sxs-lookup"><span data-stu-id="7bf6a-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="7bf6a-167">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-167">**Examples:**</span></span> <br/><span data-ttu-id="7bf6a-168">为此自定义模板启用一次密码</span><span class="sxs-lookup"><span data-stu-id="7bf6a-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="7bf6a-169">为此自定义模板禁用一次密码</span><span class="sxs-lookup"><span data-stu-id="7bf6a-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="7bf6a-170">为此自定义模板启用或禁用 Microsoft、Google 或 Yahoo 标识的身份验证</span><span class="sxs-lookup"><span data-stu-id="7bf6a-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="7bf6a-171">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-171">**Examples:**</span></span> <br/><span data-ttu-id="7bf6a-172">为此自定义模板启用社交 ID</span><span class="sxs-lookup"><span data-stu-id="7bf6a-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="7bf6a-173">为此自定义模板禁用社交 ID</span><span class="sxs-lookup"><span data-stu-id="7bf6a-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="7bf6a-174">使用高级邮件加密功能创建 OME (模板) </span><span class="sxs-lookup"><span data-stu-id="7bf6a-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="7bf6a-175">如果已Office 365 高级邮件加密，可以使用[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet 为组织创建自定义品牌模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="7bf6a-176">创建模板后，使用 Set-OMEConfiguration cmdlet 修改模板，如修改 [OME 品牌模板 中所述](#modify-an-ome-branding-template)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="7bf6a-177">可以创建多个模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-177">You can create multiple templates.</span></span>

<span data-ttu-id="7bf6a-178">创建新的自定义品牌模板：</span><span class="sxs-lookup"><span data-stu-id="7bf6a-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="7bf6a-179">使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="7bf6a-180">有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7bf6a-181">使用 [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet 创建新模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="7bf6a-182">例如，</span><span class="sxs-lookup"><span data-stu-id="7bf6a-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="7bf6a-183">将默认品牌模板返回到其原始值</span><span class="sxs-lookup"><span data-stu-id="7bf6a-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="7bf6a-184">若要从默认模板中删除所有修改，包括品牌自定义等，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7bf6a-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="7bf6a-185">使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="7bf6a-186">有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7bf6a-187">使用 **Set-OMEConfiguration** cmdlet，如 [Set-OMEConfiguration 中所述](/powershell/module/exchange/Set-OMEConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="7bf6a-188">若要从 DisclaimerText、EmailText 和 PortalText 值中删除组织的品牌自定义，请将其值设置为空字符串 `""` 。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="7bf6a-189">对于所有图像值（如徽标），将值设置为  `"$null"` 。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="7bf6a-190">下表介绍了加密自定义选项默认值。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="7bf6a-191">将加密体验的此功能还原到默认的文本和图片</span><span class="sxs-lookup"><span data-stu-id="7bf6a-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="7bf6a-192">使用这些命令</span><span class="sxs-lookup"><span data-stu-id="7bf6a-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="7bf6a-193">加密电子邮件随附的默认文本。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="7bf6a-194">默认文本显示在说明的上方，以查看加密邮件</span><span class="sxs-lookup"><span data-stu-id="7bf6a-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="7bf6a-195">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="7bf6a-196">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="7bf6a-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="7bf6a-197">**示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="7bf6a-198">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="7bf6a-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="7bf6a-199">**还原为默认值的示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="7bf6a-200">徽标</span><span class="sxs-lookup"><span data-stu-id="7bf6a-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="7bf6a-201">**还原为默认值的示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="7bf6a-202">背景色</span><span class="sxs-lookup"><span data-stu-id="7bf6a-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="7bf6a-203">**还原为默认值的示例：**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="7bf6a-204">使用高级邮件加密 (自定义品牌模板) </span><span class="sxs-lookup"><span data-stu-id="7bf6a-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="7bf6a-205">你只能删除你创建的品牌模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="7bf6a-206">不能删除默认品牌模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="7bf6a-207">若要删除自定义品牌模板：</span><span class="sxs-lookup"><span data-stu-id="7bf6a-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="7bf6a-208">使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="7bf6a-209">有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7bf6a-210">使用 **Remove-OMEConfiguration** cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7bf6a-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="7bf6a-211">例如，</span><span class="sxs-lookup"><span data-stu-id="7bf6a-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="7bf6a-212">有关详细信息，请参阅 [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="7bf6a-213">创建Exchange自定义品牌应用于加密电子邮件的自定义邮件流规则</span><span class="sxs-lookup"><span data-stu-id="7bf6a-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7bf6a-214">扫描和修改邮件的第三方应用程序可能会阻止正确应用 OME 品牌。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-214">Third-party applications that scan and modify mail can prevent OME branding from being applied correctly.</span></span>

<span data-ttu-id="7bf6a-215">修改默认模板或创建新的品牌模板后，可以创建 Exchange 邮件流规则，以根据特定条件应用自定义品牌。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-215">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="7bf6a-216">在下列情况下，此类规则将应用自定义品牌：</span><span class="sxs-lookup"><span data-stu-id="7bf6a-216">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="7bf6a-217">如果电子邮件是由最终用户使用 Outlook 或 Outlook 网页版 手动加密的，则Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="7bf6a-217">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="7bf6a-218">如果电子邮件由邮件流规则或数据丢失防护策略Exchange自动加密</span><span class="sxs-lookup"><span data-stu-id="7bf6a-218">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="7bf6a-219">若要了解如何创建应用加密Exchange邮件流规则，请参阅在邮件流规则中定义用于加密[Office 365。](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="7bf6a-219">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="7bf6a-220">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="7bf6a-220">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="7bf6a-221">选择" **管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-221">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="7bf6a-222">In the Microsoft 365 管理中心， choose **Admin centers** \> **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="7bf6a-222">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="7bf6a-223">在 EAC 中，**转到"邮件** 流 \> ""规则"，然后选择"**新建**" ![ 图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-223">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="7bf6a-224">有关使用 EAC 的信息，请参阅 Exchange[中的管理Exchange Online。](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="7bf6a-224">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="7bf6a-225">在 **"** 名称"中，键入规则的名称，例如销售部门的品牌。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-225">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="7bf6a-226">在 **"应用此规则的条件"** 中，从可用条件列表中选择条件"发件人位于组织内部"和您希望满足的其他条件。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-226">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="7bf6a-227">例如，您可能需要将特定品牌模板应用于：</span><span class="sxs-lookup"><span data-stu-id="7bf6a-227">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="7bf6a-228">从财务部门成员发送的所有加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="7bf6a-228">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="7bf6a-229">使用特定关键字（如"外部"或"合作伙伴"）发送的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="7bf6a-229">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="7bf6a-230">发送到特定域的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="7bf6a-230">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="7bf6a-231">From **Do the following，** select **Modify the message security** Apply \> **custom branding to OME messages**.</span><span class="sxs-lookup"><span data-stu-id="7bf6a-231">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="7bf6a-232">接下来，从下拉列表中选择品牌模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-232">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="7bf6a-233"> (可选) 您可以配置邮件流规则以应用加密和自定义品牌。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-233">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="7bf6a-234">From **Do the following**， select Modify the message **security**， and then choose Apply Office 365 邮件加密 and **rights protection**.</span><span class="sxs-lookup"><span data-stu-id="7bf6a-234">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="7bf6a-235">从列表中选择 RMS 模板，选择"保存 **"，** 然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-235">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="7bf6a-236">模板列表包括默认模板和选项以及您创建的任何自定义模板。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-236">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="7bf6a-237">如果列表为空，请确保你已Office 365 邮件加密新功能进行设置。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-237">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="7bf6a-238">有关说明，请参阅[设置新的Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-238">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="7bf6a-239">有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-239">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="7bf6a-240">有关"不要转发 **"选项的信息** ，请参阅电子邮件 [的"不要转发"选项](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-240">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="7bf6a-241">有关仅加密 **选项** 的信息，请参阅 [加密仅电子邮件选项](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-241">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="7bf6a-242">如果要 **指定其他** 操作，请选择"添加操作"。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-242">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="7bf6a-243">背景色参考</span><span class="sxs-lookup"><span data-stu-id="7bf6a-243">Background color reference</span></span>

<span data-ttu-id="7bf6a-244">可用于背景色的颜色名称有限。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-244">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="7bf6a-245">可以使用十六进制代码值代替颜色名称 (#RRGGBB) 。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-245">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="7bf6a-246">可以使用与颜色名称对应的十六进制代码值，或者可以使用自定义的十六进制代码值。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-246">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="7bf6a-247">请务必将十六进制代码值括在引号中 (例如 `"#f0f8ff"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-247">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="7bf6a-248">下表介绍了可用的背景色名称及其对应的十六进制代码值。</span><span class="sxs-lookup"><span data-stu-id="7bf6a-248">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="7bf6a-249">**颜色名称**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-249">**Color name**</span></span>|<span data-ttu-id="7bf6a-250">**颜色代码**</span><span class="sxs-lookup"><span data-stu-id="7bf6a-250">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="7bf6a-251">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-251">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="7bf6a-252">#faebd7</span><span class="sxs-lookup"><span data-stu-id="7bf6a-252">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="7bf6a-253">#00ffff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-253">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="7bf6a-254">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="7bf6a-254">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="7bf6a-255">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-255">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="7bf6a-256">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="7bf6a-256">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="7bf6a-257">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="7bf6a-257">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="7bf6a-258">#000000</span><span class="sxs-lookup"><span data-stu-id="7bf6a-258">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="7bf6a-259">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="7bf6a-259">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="7bf6a-260">#0000ff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-260">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="7bf6a-261">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="7bf6a-261">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="7bf6a-262">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="7bf6a-262">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="7bf6a-263">#deb887</span><span class="sxs-lookup"><span data-stu-id="7bf6a-263">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="7bf6a-264">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="7bf6a-264">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="7bf6a-265">#7fff00</span><span class="sxs-lookup"><span data-stu-id="7bf6a-265">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="7bf6a-266">#d2691e</span><span class="sxs-lookup"><span data-stu-id="7bf6a-266">#d2691e</span></span>|
|`coral`|<span data-ttu-id="7bf6a-267">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="7bf6a-267">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="7bf6a-268">#6495ed</span><span class="sxs-lookup"><span data-stu-id="7bf6a-268">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="7bf6a-269">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="7bf6a-269">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="7bf6a-270">#dc143c</span><span class="sxs-lookup"><span data-stu-id="7bf6a-270">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="7bf6a-271">#00ffff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-271">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="7bf6a-272">#00008b</span><span class="sxs-lookup"><span data-stu-id="7bf6a-272">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="7bf6a-273">#008b8b</span><span class="sxs-lookup"><span data-stu-id="7bf6a-273">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="7bf6a-274">#b8860b</span><span class="sxs-lookup"><span data-stu-id="7bf6a-274">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="7bf6a-275">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="7bf6a-275">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="7bf6a-276">#006400</span><span class="sxs-lookup"><span data-stu-id="7bf6a-276">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="7bf6a-277">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="7bf6a-277">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="7bf6a-278">#8b008b</span><span class="sxs-lookup"><span data-stu-id="7bf6a-278">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="7bf6a-279">#556b2f</span><span class="sxs-lookup"><span data-stu-id="7bf6a-279">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="7bf6a-280">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="7bf6a-280">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="7bf6a-281">#9932cc</span><span class="sxs-lookup"><span data-stu-id="7bf6a-281">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="7bf6a-282">#8b0000</span><span class="sxs-lookup"><span data-stu-id="7bf6a-282">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="7bf6a-283">#e9967a</span><span class="sxs-lookup"><span data-stu-id="7bf6a-283">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="7bf6a-284">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="7bf6a-284">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="7bf6a-285">#483d8b</span><span class="sxs-lookup"><span data-stu-id="7bf6a-285">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="7bf6a-286">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="7bf6a-286">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="7bf6a-287">#00ced1</span><span class="sxs-lookup"><span data-stu-id="7bf6a-287">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="7bf6a-288">#9400d3</span><span class="sxs-lookup"><span data-stu-id="7bf6a-288">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="7bf6a-289">#ff1493</span><span class="sxs-lookup"><span data-stu-id="7bf6a-289">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="7bf6a-290">#00bfff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-290">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="7bf6a-291">#696969</span><span class="sxs-lookup"><span data-stu-id="7bf6a-291">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="7bf6a-292">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-292">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="7bf6a-293">#b22222</span><span class="sxs-lookup"><span data-stu-id="7bf6a-293">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="7bf6a-294">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="7bf6a-294">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="7bf6a-295">#228b22</span><span class="sxs-lookup"><span data-stu-id="7bf6a-295">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="7bf6a-296">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-296">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="7bf6a-297">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="7bf6a-297">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="7bf6a-298">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-298">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="7bf6a-299">#ffd700</span><span class="sxs-lookup"><span data-stu-id="7bf6a-299">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="7bf6a-300">#daa520</span><span class="sxs-lookup"><span data-stu-id="7bf6a-300">#daa520</span></span>|
|`gray`|<span data-ttu-id="7bf6a-301">#808080</span><span class="sxs-lookup"><span data-stu-id="7bf6a-301">#808080</span></span>|
|`green`|<span data-ttu-id="7bf6a-302">#008000</span><span class="sxs-lookup"><span data-stu-id="7bf6a-302">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="7bf6a-303">#adff2f</span><span class="sxs-lookup"><span data-stu-id="7bf6a-303">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="7bf6a-304">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="7bf6a-304">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="7bf6a-305">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="7bf6a-305">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="7bf6a-306">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="7bf6a-306">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="7bf6a-307">#4b0082</span><span class="sxs-lookup"><span data-stu-id="7bf6a-307">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="7bf6a-308">#fffff0</span><span class="sxs-lookup"><span data-stu-id="7bf6a-308">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="7bf6a-309">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="7bf6a-309">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="7bf6a-310">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="7bf6a-310">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="7bf6a-311">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="7bf6a-311">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="7bf6a-312">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="7bf6a-312">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="7bf6a-313">#fffacd</span><span class="sxs-lookup"><span data-stu-id="7bf6a-313">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="7bf6a-314">#add8e6</span><span class="sxs-lookup"><span data-stu-id="7bf6a-314">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="7bf6a-315">#f08080</span><span class="sxs-lookup"><span data-stu-id="7bf6a-315">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="7bf6a-316">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-316">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="7bf6a-317">#fafad2</span><span class="sxs-lookup"><span data-stu-id="7bf6a-317">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="7bf6a-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="7bf6a-318">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="7bf6a-319">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="7bf6a-319">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="7bf6a-320">#90ee90</span><span class="sxs-lookup"><span data-stu-id="7bf6a-320">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="7bf6a-321">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="7bf6a-321">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="7bf6a-322">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="7bf6a-322">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="7bf6a-323">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="7bf6a-323">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="7bf6a-324">#87cefa</span><span class="sxs-lookup"><span data-stu-id="7bf6a-324">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="7bf6a-325">#778899</span><span class="sxs-lookup"><span data-stu-id="7bf6a-325">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="7bf6a-326">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="7bf6a-326">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="7bf6a-327">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="7bf6a-327">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="7bf6a-328">#00ff00</span><span class="sxs-lookup"><span data-stu-id="7bf6a-328">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="7bf6a-329">#32cd32</span><span class="sxs-lookup"><span data-stu-id="7bf6a-329">#32cd32</span></span>|
|`linen`|<span data-ttu-id="7bf6a-330">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="7bf6a-330">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="7bf6a-331">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-331">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="7bf6a-332">#800000</span><span class="sxs-lookup"><span data-stu-id="7bf6a-332">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="7bf6a-333">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="7bf6a-333">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="7bf6a-334">#0000cd</span><span class="sxs-lookup"><span data-stu-id="7bf6a-334">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="7bf6a-335">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="7bf6a-335">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="7bf6a-336">#9370db</span><span class="sxs-lookup"><span data-stu-id="7bf6a-336">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="7bf6a-337">#3cb371</span><span class="sxs-lookup"><span data-stu-id="7bf6a-337">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="7bf6a-338">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="7bf6a-338">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="7bf6a-339">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="7bf6a-339">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="7bf6a-340">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="7bf6a-340">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="7bf6a-341">#c71585</span><span class="sxs-lookup"><span data-stu-id="7bf6a-341">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="7bf6a-342">#191970</span><span class="sxs-lookup"><span data-stu-id="7bf6a-342">#191970</span></span>|
|`mintcream`|<span data-ttu-id="7bf6a-343">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="7bf6a-343">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="7bf6a-344">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="7bf6a-344">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="7bf6a-345">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="7bf6a-345">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="7bf6a-346">#ffdead</span><span class="sxs-lookup"><span data-stu-id="7bf6a-346">#ffdead</span></span>|
|`navy`|<span data-ttu-id="7bf6a-347">#000080</span><span class="sxs-lookup"><span data-stu-id="7bf6a-347">#000080</span></span>|
|`oldlace`|<span data-ttu-id="7bf6a-348">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="7bf6a-348">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="7bf6a-349">#808000</span><span class="sxs-lookup"><span data-stu-id="7bf6a-349">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="7bf6a-350">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="7bf6a-350">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="7bf6a-351">#ffa500</span><span class="sxs-lookup"><span data-stu-id="7bf6a-351">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="7bf6a-352">#ff4500</span><span class="sxs-lookup"><span data-stu-id="7bf6a-352">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="7bf6a-353">#da70d6</span><span class="sxs-lookup"><span data-stu-id="7bf6a-353">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="7bf6a-354">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="7bf6a-354">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="7bf6a-355">#98fb98</span><span class="sxs-lookup"><span data-stu-id="7bf6a-355">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="7bf6a-356">#afeeee</span><span class="sxs-lookup"><span data-stu-id="7bf6a-356">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="7bf6a-357">#db7093</span><span class="sxs-lookup"><span data-stu-id="7bf6a-357">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="7bf6a-358">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="7bf6a-358">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="7bf6a-359">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="7bf6a-359">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="7bf6a-360">#cd853f</span><span class="sxs-lookup"><span data-stu-id="7bf6a-360">#cd853f</span></span>|
|`pink`|<span data-ttu-id="7bf6a-361">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="7bf6a-361">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="7bf6a-362">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="7bf6a-362">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="7bf6a-363">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="7bf6a-363">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="7bf6a-364">#800080</span><span class="sxs-lookup"><span data-stu-id="7bf6a-364">#800080</span></span>|
|`red`|<span data-ttu-id="7bf6a-365">#ff0000</span><span class="sxs-lookup"><span data-stu-id="7bf6a-365">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="7bf6a-366">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="7bf6a-366">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="7bf6a-367">#4169e1</span><span class="sxs-lookup"><span data-stu-id="7bf6a-367">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="7bf6a-368">#8b4513</span><span class="sxs-lookup"><span data-stu-id="7bf6a-368">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="7bf6a-369">#fa8072</span><span class="sxs-lookup"><span data-stu-id="7bf6a-369">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="7bf6a-370">#f4a460</span><span class="sxs-lookup"><span data-stu-id="7bf6a-370">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="7bf6a-371">#00ff00</span><span class="sxs-lookup"><span data-stu-id="7bf6a-371">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="7bf6a-372">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="7bf6a-372">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="7bf6a-373">#a0522d</span><span class="sxs-lookup"><span data-stu-id="7bf6a-373">#a0522d</span></span>|
|`silver`|<span data-ttu-id="7bf6a-374">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="7bf6a-374">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="7bf6a-375">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="7bf6a-375">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="7bf6a-376">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="7bf6a-376">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="7bf6a-377">#708090</span><span class="sxs-lookup"><span data-stu-id="7bf6a-377">#708090</span></span>|
|`snow`|<span data-ttu-id="7bf6a-378">#fffafa</span><span class="sxs-lookup"><span data-stu-id="7bf6a-378">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="7bf6a-379">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="7bf6a-379">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="7bf6a-380">#4682b4</span><span class="sxs-lookup"><span data-stu-id="7bf6a-380">#4682b4</span></span>|
|`tan`|<span data-ttu-id="7bf6a-381">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="7bf6a-381">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="7bf6a-382">#008080</span><span class="sxs-lookup"><span data-stu-id="7bf6a-382">#008080</span></span>|
|`thistle`|<span data-ttu-id="7bf6a-383">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="7bf6a-383">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="7bf6a-384">#ff6347</span><span class="sxs-lookup"><span data-stu-id="7bf6a-384">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="7bf6a-385">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="7bf6a-385">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="7bf6a-386">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="7bf6a-386">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="7bf6a-387">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="7bf6a-387">#f5deb3</span></span>|
|`white`|<span data-ttu-id="7bf6a-388">#ffffff</span><span class="sxs-lookup"><span data-stu-id="7bf6a-388">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="7bf6a-389">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="7bf6a-389">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="7bf6a-390">#ffff00</span><span class="sxs-lookup"><span data-stu-id="7bf6a-390">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="7bf6a-391">#9acd32</span><span class="sxs-lookup"><span data-stu-id="7bf6a-391">#9acd32</span></span>|
