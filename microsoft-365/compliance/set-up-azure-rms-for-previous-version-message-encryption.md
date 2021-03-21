---
title: 为以前版本的邮件加密设置 Azure 权限管理
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: Office 365 邮件加密的早期版本依赖于 Microsoft Azure 权限管理 (以前称为 Windows Azure Active Directory 权限管理) 。
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919488"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="4d6af-103">为以前版本的邮件加密设置 Azure 权限管理</span><span class="sxs-lookup"><span data-stu-id="4d6af-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="4d6af-104">本主题介绍激活 Azure 权限管理 (RMS) （Azure 信息保护的一部分）以与以前版本的 Office 365 邮件加密 (OME) 一起使用时需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="4d6af-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="4d6af-105">本文仅适用于以前版本的 OME</span><span class="sxs-lookup"><span data-stu-id="4d6af-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="4d6af-106">如果尚未将组织移动到新的 OME 功能，但已部署 OME，则本文中的信息适用于您的组织。</span><span class="sxs-lookup"><span data-stu-id="4d6af-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="4d6af-107">Microsoft 建议你在组织合理时制定移动到新 OME 功能的计划。</span><span class="sxs-lookup"><span data-stu-id="4d6af-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="4d6af-108">有关说明，请参阅 [设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6af-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="4d6af-109">若要详细了解新功能如何首先工作，请参阅 [Office 365 邮件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6af-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="4d6af-110">本文的其余部分将介绍新的 OME 功能发布之前 OME 的行为。</span><span class="sxs-lookup"><span data-stu-id="4d6af-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="4d6af-111">使用以前版本的 Office 365 邮件加密的先决条件</span><span class="sxs-lookup"><span data-stu-id="4d6af-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="4d6af-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="4d6af-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="4d6af-113">Office 365 邮件加密 (OME) （包括 IRM）取决于 Azure RMS (Azure 权限) 。</span><span class="sxs-lookup"><span data-stu-id="4d6af-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="4d6af-114">Azure RMS 是 Azure 信息保护使用的保护技术。</span><span class="sxs-lookup"><span data-stu-id="4d6af-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="4d6af-115">若要使用 OME，组织必须包含 Exchange Online 或 Exchange Online Protection 订阅，而订阅又包括 Azure 权限管理订阅。</span><span class="sxs-lookup"><span data-stu-id="4d6af-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="4d6af-116">如果您不确定订阅包含哪些内容，请参阅邮件策略、恢复和合规性的 Exchange Online [服务说明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="4d6af-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

- <span data-ttu-id="4d6af-117">如果你拥有 Azure 权限管理，但没有为 Exchange Online 或 Exchange Online Protection 进行设置，本文将介绍如何激活 Azure 权限管理，然后介绍设置 OME 以使用 Azure 权限管理的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="4d6af-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="4d6af-118">如果你已设置 OME 以使用适用于 Exchange Online 或 Exchange Online Protection 的 Azure 权限管理，则根据设置方式，你可能已准备好立即开始使用 OME 及其新功能。</span><span class="sxs-lookup"><span data-stu-id="4d6af-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="4d6af-119">本文介绍如何确定是否正确设置了 OME、需要更改设置时应执行哪些操作，以及选择不更改设置时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="4d6af-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="4d6af-120">例如，若要使用新功能，必须将 Azure RMS 与 OME 一同使用。</span><span class="sxs-lookup"><span data-stu-id="4d6af-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="4d6af-121">不能将新功能与本地 Active Directory RMS 一同使用。</span><span class="sxs-lookup"><span data-stu-id="4d6af-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="4d6af-122">在 Office 365 中为以前版本的 OME 激活 Azure 权限管理</span><span class="sxs-lookup"><span data-stu-id="4d6af-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="4d6af-123">需要激活 Azure 权限管理，以便贵组织的用户能够将信息保护应用于他们发送的邮件，并打开受 Azure 权限管理服务保护的邮件和文件。</span><span class="sxs-lookup"><span data-stu-id="4d6af-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="4d6af-124">有关说明，请参阅 [激活 Azure 权限管理](/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="4d6af-124">For instructions, see [Activating Azure Rights Management](/azure/information-protection/activate-service).</span></span> <span data-ttu-id="4d6af-125">完成激活后，请返回此处并继续本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="4d6af-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="4d6af-126">将以前版本的 OME 设置为使用 Azure RMS，方法为将受信任的发布域 (TPDs) </span><span class="sxs-lookup"><span data-stu-id="4d6af-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="4d6af-127">TPD 是一个 XML 文件，其中包含有关您组织权限管理设置的信息。</span><span class="sxs-lookup"><span data-stu-id="4d6af-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="4d6af-128">例如，TPD 包含有关用于对证书和许可证进行签名和加密的服务器 (SLC) 、用于许可和发布等的 URL 的信息。</span><span class="sxs-lookup"><span data-stu-id="4d6af-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="4d6af-129">使用 TPD 将 TPD 导入Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4d6af-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4d6af-130">以前，您可以选择将 TPD 从 Active Directory 权限管理服务 (AD RMS) 组织。</span><span class="sxs-lookup"><span data-stu-id="4d6af-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="4d6af-131">但是，这样做将阻止你使用新的 OME 功能，不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="4d6af-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="4d6af-132">如果组织当前已按此方式配置，Microsoft 建议创建从本地 Active Directory RMS 迁移到基于云的 Azure 信息保护的计划。</span><span class="sxs-lookup"><span data-stu-id="4d6af-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="4d6af-133">有关详细信息，请参阅从 [AD RMS 迁移到 Azure 信息保护](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="4d6af-133">For more information, see [Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="4d6af-134">在迁移到 Azure 信息保护之前，你将不能使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="4d6af-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="4d6af-135">**从 Azure RMS 导入 TPD**</span><span class="sxs-lookup"><span data-stu-id="4d6af-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="4d6af-136">[使用远程 PowerShell 连接到 Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="4d6af-136">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="4d6af-137">选择与组织的地理位置对应的密钥共享 URL：</span><span class="sxs-lookup"><span data-stu-id="4d6af-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="4d6af-138">**位置**</span><span class="sxs-lookup"><span data-stu-id="4d6af-138">**Location**</span></span>|<span data-ttu-id="4d6af-139">**密钥共享位置 URL**</span><span class="sxs-lookup"><span data-stu-id="4d6af-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d6af-140">北美</span><span class="sxs-lookup"><span data-stu-id="4d6af-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4d6af-141">欧盟</span><span class="sxs-lookup"><span data-stu-id="4d6af-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4d6af-142">亚洲</span><span class="sxs-lookup"><span data-stu-id="4d6af-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4d6af-143">南美洲</span><span class="sxs-lookup"><span data-stu-id="4d6af-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4d6af-144">政府用 Office 365（政府社区云）</span><span class="sxs-lookup"><span data-stu-id="4d6af-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="4d6af-145">此 RMS 密钥共享位置为购买了 Office 365 政府版 SK 的客户保留。</span><span class="sxs-lookup"><span data-stu-id="4d6af-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="4d6af-146">通过运行 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet 配置密钥共享位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4d6af-146">Configure the key-sharing location by running the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="4d6af-147">例如，如果组织位于北美，则配置关键共享位置：</span><span class="sxs-lookup"><span data-stu-id="4d6af-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="4d6af-148">使用 [-RMSOnline 开关运行 Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet 以从 Azure 权限管理导入 TPD：</span><span class="sxs-lookup"><span data-stu-id="4d6af-148">Run the [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="4d6af-149">其中  *TPDName*  是你想要用于 TPD 的名称。</span><span class="sxs-lookup"><span data-stu-id="4d6af-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="4d6af-150">例如，"Contoso 北美 TPD"。</span><span class="sxs-lookup"><span data-stu-id="4d6af-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="4d6af-151">若要验证您是否已成功将组织配置为使用 Azure 权限管理服务，请运行带 -RMSOnline 开关的 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4d6af-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="4d6af-152">此外，此 cmdlet 还检查与 Azure 权限管理服务的连接、下载 TPD 并检查其有效性。</span><span class="sxs-lookup"><span data-stu-id="4d6af-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="4d6af-153">按如下所示 [运行 Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet，以禁止 Azure 权限管理模板在 Outlook 网页版和 Outlook 中可用：</span><span class="sxs-lookup"><span data-stu-id="4d6af-153">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="4d6af-154">按如下所示 [运行 Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet，为基于云的电子邮件组织启用 Azure 权限管理，并配置它以对 Office 365 邮件加密使用 Azure 权限管理：</span><span class="sxs-lookup"><span data-stu-id="4d6af-154">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="4d6af-155">若要验证您是否已成功导入 TPD 并启用 Azure 权限管理，请使用 Test-IRMConfiguration cmdlet 测试 Azure 权限管理功能。</span><span class="sxs-lookup"><span data-stu-id="4d6af-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="4d6af-156">有关详细信息，请参阅 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) 中的"示例 1"。</span><span class="sxs-lookup"><span data-stu-id="4d6af-156">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="4d6af-157">我使用 Active Directory 权限管理而非 Azure 信息保护设置了以前版本的 OME，我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="4d6af-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="4d6af-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="4d6af-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="4d6af-159">您可以继续使用现有的 Office 365 邮件加密邮件流规则与 Active Directory 权限管理，但不能配置或使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="4d6af-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="4d6af-160">相反，你需要迁移到 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="4d6af-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="4d6af-161">有关迁移以及这对组织的含义的信息，请参阅从 [AD RMS](/information-protection/deploy-use/prepare-environment-adrms)迁移到 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="4d6af-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="4d6af-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4d6af-162">Next steps</span></span>
<span data-ttu-id="4d6af-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="4d6af-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="4d6af-164">完成 Azure 权限管理设置后，如果要启用新的 OME 功能，请参阅设置基于 Azure 信息保护构建的新 [Office 365 邮件加密功能。](./set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="4d6af-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span></span>
  
<span data-ttu-id="4d6af-165">将组织设置为使用新的 OME 功能后，即可定义邮件流规则，以使用新的 [OME 功能保护电子邮件](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6af-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4d6af-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="4d6af-166">Related topics</span></span>
<span data-ttu-id="4d6af-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="4d6af-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="4d6af-168">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="4d6af-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="4d6af-169">有关 Office 365 加密的技术参考详情</span><span class="sxs-lookup"><span data-stu-id="4d6af-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="4d6af-170">什么是 Azure 权限管理？</span><span class="sxs-lookup"><span data-stu-id="4d6af-170">What is Azure Rights Management?</span></span>](/information-protection/understand-explore/what-is-azure-rms)