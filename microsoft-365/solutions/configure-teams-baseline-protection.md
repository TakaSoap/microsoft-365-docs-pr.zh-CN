---
title: 配置具有基线保护的团队
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: 了解如何部署具有基线保护级别的团队。
ms.openlocfilehash: 16f37175c3aa7b420745e6126de1aa96368d618a
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613438"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="92c70-103">配置具有基线保护的团队</span><span class="sxs-lookup"><span data-stu-id="92c70-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="92c70-104">本文将介绍如何部署具有基线保护级别的团队。</span><span class="sxs-lookup"><span data-stu-id="92c70-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="92c70-105">通过此级别，用户可通过多种方式进行协作，同时提升权限管理，并针对过度共享提供基本保护。</span><span class="sxs-lookup"><span data-stu-id="92c70-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="92c70-106">此级别的建议保护包括标识和设备访问策略和恶意软件保护。</span><span class="sxs-lookup"><span data-stu-id="92c70-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="92c70-107">此外，可以根据需要应用条件访问策略和数据丢失保护。</span><span class="sxs-lookup"><span data-stu-id="92c70-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="92c70-108">初始保护</span><span class="sxs-lookup"><span data-stu-id="92c70-108">Initial protections</span></span>

<span data-ttu-id="92c70-109">第一步，我们建议配置基本身份和设备访问策略。</span><span class="sxs-lookup"><span data-stu-id="92c70-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="92c70-110">有关详细信息，请参阅[保护 Teams 聊天、组和文件的策略建议](../security/office-365-security/teams-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="92c70-110">See [Policy recommendations for securing Teams chats, groups, and files](../security/office-365-security/teams-access-policies.md) for details.</span></span>

<span data-ttu-id="92c70-111">建议启用基本的 Defender for Office 365 功能，防范文档、附件和链接中的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="92c70-111">We also recommend turning on basic Defender for Office 365 features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="92c70-112">我们建议启用下表中的每个选项。</span><span class="sxs-lookup"><span data-stu-id="92c70-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="92c70-113">选项</span><span class="sxs-lookup"><span data-stu-id="92c70-113">Option</span></span>|<span data-ttu-id="92c70-114">信息</span><span class="sxs-lookup"><span data-stu-id="92c70-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="92c70-115">适用于 SPO、OneDrive 和 Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="92c70-115">Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="92c70-116">安全附件</span><span class="sxs-lookup"><span data-stu-id="92c70-116">Safe Attachments</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br>[<span data-ttu-id="92c70-117">Defender for Office 365 - SharePoint、OneDrive 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92c70-117">Defender for Office 365 - SharePoint, OneDrive, and Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)|
|<span data-ttu-id="92c70-118">安全文档</span><span class="sxs-lookup"><span data-stu-id="92c70-118">Safe Documents</span></span>|[<span data-ttu-id="92c70-119">Microsoft Defender for Office 365 中的安全文档</span><span class="sxs-lookup"><span data-stu-id="92c70-119">Safe Documents in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)|
|<span data-ttu-id="92c70-120">适用于 Teams 的安全链接</span><span class="sxs-lookup"><span data-stu-id="92c70-120">Safe Links for Teams</span></span>|[<span data-ttu-id="92c70-121">Teams 中 Office 365 安全链接</span><span class="sxs-lookup"><span data-stu-id="92c70-121">Office 365 Safe Links in Teams</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams)<br>[<span data-ttu-id="92c70-122">安全链接</span><span class="sxs-lookup"><span data-stu-id="92c70-122">Safe Links</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="92c70-123">团队来宾共享</span><span class="sxs-lookup"><span data-stu-id="92c70-123">Teams guest sharing</span></span>

<span data-ttu-id="92c70-124">在每层中，我们都可以选择与组织外部人员共享。</span><span class="sxs-lookup"><span data-stu-id="92c70-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="92c70-125">对于敏感和高度敏感层，我们可以选择使用敏感度标签在团队级别关闭来宾共享。</span><span class="sxs-lookup"><span data-stu-id="92c70-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="92c70-126">但必须启用“组织级别的来宾共享设置”，以使来宾共享在 Teams 中均可正常工作。</span><span class="sxs-lookup"><span data-stu-id="92c70-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Teams 来宾访问切换的屏幕截图](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="92c70-128">设定 Teams 来宾访问设置</span><span class="sxs-lookup"><span data-stu-id="92c70-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="92c70-129">访问 [https://admin.microsoft.com](https://admin.microsoft.com) 登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="92c70-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="92c70-130">在左侧导航中，单击“**显示全部**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="92c70-131">在“**管理中心**”下，单击“**团队**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-131">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="92c70-132">在 Teams 管理中心左侧导航中，展开“**组织范围的设置**”，然后单击“**来宾访问**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="92c70-133">确保 **在 Teams 中允许来宾访问** 设置为“**开**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="92c70-134">对其他来宾设置进行任何所需的更改，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="92c70-135">启用后，Teams 来宾设置最多可能需要二十四个小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="92c70-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="92c70-136">默认情况下，Office 365 组和 SharePoint 启用了来宾共享，但如果以前已更改了组织的任何来宾共享设置，建议参阅[在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)，以确保来宾共享在 Teams 中可用。</span><span class="sxs-lookup"><span data-stu-id="92c70-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="92c70-137">网站和文件共享</span><span class="sxs-lookup"><span data-stu-id="92c70-137">Site and file sharing</span></span>

<span data-ttu-id="92c70-138">为了降低意外与组织外部人员共享文件或文件夹的风险，建议将 SharePoint 的默认共享链接更改为“*仅限组织中的人员*”。</span><span class="sxs-lookup"><span data-stu-id="92c70-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="92c70-139">（如果用户需要在外部共享，并且启用了来宾共享，他们在共享时仍可以更改链接类型。）</span><span class="sxs-lookup"><span data-stu-id="92c70-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="92c70-140">更改默认共享链接</span><span class="sxs-lookup"><span data-stu-id="92c70-140">To change the default sharing link</span></span>
1. <span data-ttu-id="92c70-141">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="92c70-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="92c70-142">在“**策略**”下，单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-142">Under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="92c70-143">在“**文件和文件夹链接**”下，选中“**仅限组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-143">Under **File and folder links**, select **Only people in your organization**.</span></span>
4. <span data-ttu-id="92c70-144">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-144">Click **Save**.</span></span>

<span data-ttu-id="92c70-145">为了获得最佳的来宾共享体验，我们还建议你启用 [SharePoint 和 OneDrive与 Azure AD B2B 集成](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)。</span><span class="sxs-lookup"><span data-stu-id="92c70-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="92c70-146">创建团队</span><span class="sxs-lookup"><span data-stu-id="92c70-146">Create a team</span></span>

<span data-ttu-id="92c70-147">基线保护级别的其他配置在与团队相关联的 SharePoint 网站中完成。</span><span class="sxs-lookup"><span data-stu-id="92c70-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="92c70-148">[创建公共或私人团队](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)，然后再继续进行下一部分。</span><span class="sxs-lookup"><span data-stu-id="92c70-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="92c70-149">网站共享设置</span><span class="sxs-lookup"><span data-stu-id="92c70-149">Site sharing settings</span></span>

<span data-ttu-id="92c70-150">默认情况下，SharePoint 网站的成员可以邀请其他人加入该网站。</span><span class="sxs-lookup"><span data-stu-id="92c70-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="92c70-151">网站是团队的一部分时，团队成员将作为网站成员包括在内。</span><span class="sxs-lookup"><span data-stu-id="92c70-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="92c70-152">但是，直接添加到网站的人员不能访问团队的其他成员。</span><span class="sxs-lookup"><span data-stu-id="92c70-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="92c70-153">因此，我们建议仅通过团队来管理权限。</span><span class="sxs-lookup"><span data-stu-id="92c70-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="92c70-154">为了帮助进行权限管理，我们建议将关联的站点配置为仅允许所有者自己共享该站点。</span><span class="sxs-lookup"><span data-stu-id="92c70-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="92c70-155">这简化了权限管理，有助于阻止团队所有者不知道的人员访问。</span><span class="sxs-lookup"><span data-stu-id="92c70-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="92c70-156">对需要基线保护的每个团队执行此操作。</span><span class="sxs-lookup"><span data-stu-id="92c70-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="92c70-157">更新网站共享设置</span><span class="sxs-lookup"><span data-stu-id="92c70-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="92c70-158">在团队的工具栏中，单击“**文件**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="92c70-159">单击“**在 SharePoint 中打开**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="92c70-160">在 SharePoint 网站的工具栏中，依次单击设置图标和“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="92c70-161">在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-161">In the **Site permissions** pane, under **Sharing settings**, click **Change sharing settings**.</span></span>
5. <span data-ttu-id="92c70-162">在“**共享权限**”下，选择选择“**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="92c70-162">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="92c70-163">附加保护</span><span class="sxs-lookup"><span data-stu-id="92c70-163">Additional protections</span></span>

<span data-ttu-id="92c70-164">Microsoft 365 提供了其他用于保护内容的方法。</span><span class="sxs-lookup"><span data-stu-id="92c70-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="92c70-165">考虑以下选项是否有助于提高组织的安全性。</span><span class="sxs-lookup"><span data-stu-id="92c70-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="92c70-166">让来宾同意[使用条款](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)。</span><span class="sxs-lookup"><span data-stu-id="92c70-166">Have guests agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="92c70-167">为来宾用户配置“[会话超时策略](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)”。</span><span class="sxs-lookup"><span data-stu-id="92c70-167">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="92c70-168">创建“[敏感信息类型](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)”，并使用“[数据丢失保护](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)”来设置有关访问敏感信息的策略。</span><span class="sxs-lookup"><span data-stu-id="92c70-168">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="92c70-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92c70-169">See Also</span></span>

[<span data-ttu-id="92c70-170">管理 Teams 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="92c70-170">Manage meeting policies in Teams</span></span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)

[<span data-ttu-id="92c70-171">内部风险管理入门</span><span class="sxs-lookup"><span data-stu-id="92c70-171">Get started with insider risk management</span></span>](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure)
