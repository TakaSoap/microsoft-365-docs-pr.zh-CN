---
title: 了解 Microsoft 365 本地扫描仪数据丢失防护（预览）
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 本地扫描仪的数据丢失防护扩展了对文件活动的监视以及针对这些文件的安全操作，可扩展到本地文件共享和 SharePoint 文件夹和文档库。通过 Azure 信息保护 （AIP） 扫描仪扫描和保护文件
ms.openlocfilehash: f0a34a13630e42c5dd29734ad708b3c11bb1d587
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114160"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="b12ab-104">了解 Microsoft 365 本地扫描仪数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="b12ab-104">Learn about the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="b12ab-105">Microsoft 本地扫描仪的 Microsoft 数据丢失防护是 Microsoft 365 数据丢失防护 （DLP） 套件的一部分，可用于在 Microsoft 365 服务中发现和保护敏感项目。</span><span class="sxs-lookup"><span data-stu-id="b12ab-105">Microsoft data loss prevention on-premises scanner is part of the Microsoft 365 data loss prevention (DLP) suite of features that you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="b12ab-106">有关 Microsoft 所有 DLP 产品/服务的更多信息，请参阅[数据丢失防护概述](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="b12ab-106">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="b12ab-107">**DLP 本地扫描仪** 会对文件共享和 SharePoint 文档库以及文件夹中的本地数据（如果泄露）进行爬网，这些敏感项目可能给组织带来风险或带来合规性策略冲突的风险。</span><span class="sxs-lookup"><span data-stu-id="b12ab-107">The **DLP on-premises scanner** crawls on-premises data-at-rest in file shares and SharePoint document libraries and folders for sensitive items that, if leaked, would pose a risk to your organization or pose a risk of compliance policy violation.</span></span> <span data-ttu-id="b12ab-108">通过此操作，可了解确保正确使用和保护敏感项目所需的可见性和控制，还有助于防止可能泄露到其的风险行为。</span><span class="sxs-lookup"><span data-stu-id="b12ab-108">This gives you the visibility and control you need to ensure that sensitive items are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span> <span data-ttu-id="b12ab-109">DLP 本地扫描仪通过使用 [内置](sensitive-information-type-entity-definitions.md) 或 [自定义敏感信息类型](create-a-custom-sensitive-information-type.md) 检测敏感信息， [标签](sensitivity-labels.md) 或文件属性。</span><span class="sxs-lookup"><span data-stu-id="b12ab-109">The DLP on-premises scanner detects sensitive information by using [built-in](sensitive-information-type-entity-definitions.md) or [custom sensitive information](create-a-custom-sensitive-information-type.md) types, [sensitivity labels](sensitivity-labels.md) or file properties.</span></span> <span data-ttu-id="b12ab-110">[活动资源管理器](data-classification-activity-explorer.md) 中显示有关用户使用敏感项目的信息，并且通过 [DLP 策略对](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="b12ab-110">The information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a><span data-ttu-id="b12ab-111">DLP 本地扫描仪依赖于 Azure 信息保护扫描仪</span><span class="sxs-lookup"><span data-stu-id="b12ab-111">The DLP on-premises scanner relies on Azure Information Protection scanner</span></span>

<span data-ttu-id="b12ab-112">DLP 本地扫描仪依靠完整实施 Azure 信息保护 （AIP） 扫描仪来监视、标记和保护敏感项目。</span><span class="sxs-lookup"><span data-stu-id="b12ab-112">The DLP on-premises scanner relies on a full implementation of the Azure Information Protection (AIP) scanner to monitor, label and protect sensitive items.</span></span> <span data-ttu-id="b12ab-113">如果不熟悉 AIP 扫描仪，强烈建议自己熟悉它。</span><span class="sxs-lookup"><span data-stu-id="b12ab-113">If you aren't familiar with the AIP scanner, we strongly recommend familiarizing yourself with it.</span></span> <span data-ttu-id="b12ab-114">请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="b12ab-114">See these articles:</span></span>

- [<span data-ttu-id="b12ab-115">什么是 Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="b12ab-115">What is Azure Information Protection</span></span>](/azure/information-protection/what-is-information-protection)
- [<span data-ttu-id="b12ab-116">什么是 Azure 信息保护统一标签扫描仪</span><span class="sxs-lookup"><span data-stu-id="b12ab-116">What is the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="b12ab-117">安装和部署 Azure 信息保护统一标签扫描仪的要求</span><span class="sxs-lookup"><span data-stu-id="b12ab-117">Requirements for installing and deploying the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-prereqs)
- [<span data-ttu-id="b12ab-118">教程：安装 Azure 信息保护 （AIP） 统一标签扫描仪</span><span class="sxs-lookup"><span data-stu-id="b12ab-118">Tutorial: Installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/tutorial-install-scanner)
- [<span data-ttu-id="b12ab-119">配置和安装 Azure 信息保护统一标记扫描器</span><span class="sxs-lookup"><span data-stu-id="b12ab-119">Configuring and installing the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install)
- [<span data-ttu-id="b12ab-120">Azure 信息保护统一标签客户端 - 版本发布历史记录和支持策略</span><span class="sxs-lookup"><span data-stu-id="b12ab-120">Azure Information Protection unified labeling client - Version release history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a><span data-ttu-id="b12ab-121">DLP 本地扫描仪操作</span><span class="sxs-lookup"><span data-stu-id="b12ab-121">DLP on-premises scanner actions</span></span>

<span data-ttu-id="b12ab-122">DLP 本地扫描仪通过以下四种方法之一来检测文件：</span><span class="sxs-lookup"><span data-stu-id="b12ab-122">DLP on-premises scanner detects files by one of these four methods:</span></span>

- <span data-ttu-id="b12ab-123">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="b12ab-123">sensitive information types</span></span>
- <span data-ttu-id="b12ab-124">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="b12ab-124">sensitivity labels</span></span>
- <span data-ttu-id="b12ab-125">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="b12ab-125">file extension</span></span>
- <span data-ttu-id="b12ab-126">仅 Office 文件的自定义文档属性</span><span class="sxs-lookup"><span data-stu-id="b12ab-126">custom document properties on Office files only</span></span> 

<span data-ttu-id="b12ab-127">如果检测到的文件存在泄露或合规性策略冲突的风险，DLP 本地扫描仪可能会执行以下四项操作之一。</span><span class="sxs-lookup"><span data-stu-id="b12ab-127">When a detected file poses a potential risk if leaked or a compliance policy violation, the DLP on-premises scanner can take one of these four actions.</span></span>

|<span data-ttu-id="b12ab-128">操作</span><span class="sxs-lookup"><span data-stu-id="b12ab-128">Action</span></span> |<span data-ttu-id="b12ab-129">说明</span><span class="sxs-lookup"><span data-stu-id="b12ab-129">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b12ab-130">**阻止这些用户访问存储在本地扫描仪中的文件 - 每个人**</span><span class="sxs-lookup"><span data-stu-id="b12ab-130">**Block these people from accessing file stored in  on-premises scanner - Everyone**</span></span> | <span data-ttu-id="b12ab-131">如果强制执行，此操作将阻止访问除内容所有者、最后一个修改该项目的帐户和管理员之外的所有帐户。</span><span class="sxs-lookup"><span data-stu-id="b12ab-131">When enforced, this action blocks access to all accounts except the content owner, the last account that modified the item and the administrator.</span></span> <span data-ttu-id="b12ab-132">为此，可在文件级别删除 NTFS/SharePoint 权限的所有帐户，文件所有者、存储库所有者（在 [设置存储库所有者](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) 设置的内容扫描作业中）、最后一次修改（只能在 SharePoint 中标识）和管理员。也会向扫描仪帐户授予该文件的 <2> <2> <3>操作权限。</span><span class="sxs-lookup"><span data-stu-id="b12ab-132">It does this by removing all accounts from NTFS/SharePoint permissions at the file level except the file owner, repository owner (set in the [Set repository owner](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) setting in content scan job), last modifier (can be identified in SharePoint only) and admin. The scanner account is also granted FC rights on the file.</span></span>|
|<span data-ttu-id="b12ab-133">**阻止这些用户访问存储在本地扫描仪中的文件 - 阻止组织范围的（公共）访问**</span><span class="sxs-lookup"><span data-stu-id="b12ab-133">**Block these people from accessing file stored in  on-premises scanner - block org-wide (public) access**</span></span>    |<span data-ttu-id="b12ab-134">强制使用时，此操作从文件访问控制列表 （ACL） 中删除 **_Everyone_*_、_*_NT AUTHORITY\经过身份验证的用户_*_和 _*_Domain Users_** SIDs。</span><span class="sxs-lookup"><span data-stu-id="b12ab-134">When enforced, this action removes the **_Everyone_*_, _*_NT AUTHORITY\authenticated users_*_, and _*_Domain Users_** SIDs from the file access control list (ACL).</span></span> <span data-ttu-id="b12ab-135">只有已明确授予文件或父文件夹权限的用户和组才能访问该文件。</span><span class="sxs-lookup"><span data-stu-id="b12ab-135">Only users and groups that have been explicitly granted rights to the file or parent folder will be able to access the file.</span></span>|
|<span data-ttu-id="b12ab-136">**设置对文件的权限**</span><span class="sxs-lookup"><span data-stu-id="b12ab-136">**Set permissions on the file**</span></span>|<span data-ttu-id="b12ab-137">强制使用时，此操作会强制文件继承其父文件夹的权限。</span><span class="sxs-lookup"><span data-stu-id="b12ab-137">When enforced, this action forces the file to inherit the permissions of its parent folder.</span></span> <span data-ttu-id="b12ab-138">默认情况下，只有在父文件夹的权限比文件上已有的权限更加严格时，才强制实施此操作。</span><span class="sxs-lookup"><span data-stu-id="b12ab-138">Be default, this action will only be enforced if the permissions on the parent folder are more restrictive than the permissions that are already on the file.</span></span> <span data-ttu-id="b12ab-139">例如，如果文件的 ACL 设置为仅允许 **_特定用户_*_，并且父文件夹配置为允许 _*_域用户_*_ 组，则该文件不会继承父文件夹权限。可通过选择 _*"继承"来覆盖此行为，即使父权限在管理** 限制。</span><span class="sxs-lookup"><span data-stu-id="b12ab-139">For example, if the ACL on the file is set to only allow **_specific users_*_ and the parent folder is configured to allow _*_Domain Users_*_ group, the parent folder permissions would not be inherited by the file. You can override this behavior by selecting the _\* Inherit even if parent permissions are less restrictive*\* option.</span></span>|
|<span data-ttu-id="b12ab-140">**从不正确的位置删除文件**</span><span class="sxs-lookup"><span data-stu-id="b12ab-140">**Remove the file from improper location**</span></span>|<span data-ttu-id="b12ab-141">强制安装后，此操作用 .txt 扩展名替换原始文件，将原始文件的副本隔离文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b12ab-141">When enforced, this action replaces the original file with a stub file with .txt extension and places a copy of the original file in a quarantine folder.</span></span> 

## <a name="whats-different-in-the-on-premises-scanner"></a><span data-ttu-id="b12ab-142">本地扫描仪中的不同功能</span><span class="sxs-lookup"><span data-stu-id="b12ab-142">What's different in the on-premises scanner</span></span>

<span data-ttu-id="b12ab-143">在深入研究本地扫描仪之前，有必要了解一些额外的概念。</span><span class="sxs-lookup"><span data-stu-id="b12ab-143">There are a few extra concepts that you need to be aware of before you dig into the on-premises scanner.</span></span>

### <a name="aip-repositories-and-content-scan-jobs"></a><span data-ttu-id="b12ab-144">AIP 存储库和内容扫描作业</span><span class="sxs-lookup"><span data-stu-id="b12ab-144">AIP repositories and content scan jobs</span></span>

<span data-ttu-id="b12ab-145">必须创建 AIP 内容扫描作业，并确定托管要由 DLP 引擎评估的文件的存储库。</span><span class="sxs-lookup"><span data-stu-id="b12ab-145">You must create an AIP content scan jobs and identify the repositories that host the files that you want to be evaluated by DLP engine.</span></span> <span data-ttu-id="b12ab-146">请确保在已创建的 AIP 内容扫描作业中启用 DLP 规则。</span><span class="sxs-lookup"><span data-stu-id="b12ab-146">Make sure you enable DLP rules in the created AIP content scan job.</span></span>

### <a name="policy-tips"></a><span data-ttu-id="b12ab-147">策略提示</span><span class="sxs-lookup"><span data-stu-id="b12ab-147">Policy tips</span></span>

<span data-ttu-id="b12ab-148">[策略](use-notifications-and-policy-tips.md) 在本地扫描仪中不可用。</span><span class="sxs-lookup"><span data-stu-id="b12ab-148">[Policy tips](use-notifications-and-policy-tips.md) are not available in on-premises scanner.</span></span>


### <a name="viewing-dlp-on-premises-scanner-events"></a><span data-ttu-id="b12ab-149">查看 DLP 本地扫描仪事件</span><span class="sxs-lookup"><span data-stu-id="b12ab-149">Viewing DLP on-premises scanner events</span></span>

<span data-ttu-id="b12ab-150">在 M365 合规中心、活动资源管理器或 [DLP 本地扫描仪](data-classification-activity-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="b12ab-150">You view DLP on-premises scanner data in the M365 Compliance Center [activity explorer](data-classification-activity-explorer.md).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="b12ab-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b12ab-151">Next steps</span></span>

<span data-ttu-id="b12ab-152">现在已了解 DLP 本地扫描仪，接着将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b12ab-152">Now that you've learned about DLP on-premises scanner, your next steps are:</span></span>

1. [<span data-ttu-id="b12ab-153">开始使用 DLP 本地扫描仪</span><span class="sxs-lookup"><span data-stu-id="b12ab-153">Get started with the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
2. [<span data-ttu-id="b12ab-154">使用 DLP 本地扫描仪</span><span class="sxs-lookup"><span data-stu-id="b12ab-154">Use the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="b12ab-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b12ab-155">See also</span></span>

- [<span data-ttu-id="b12ab-156">Microsoft 本地扫描仪数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="b12ab-156">Getting started with the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="b12ab-157">使用 Microsoft 本地扫描仪的数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="b12ab-157">Use the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="b12ab-158">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="b12ab-158">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="b12ab-159">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="b12ab-159">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="b12ab-160">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="b12ab-160">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)