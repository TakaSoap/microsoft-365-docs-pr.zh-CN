---
title: 将数据从 CellTrust SL2 平台存档到Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 了解如何设置和使用 CellTrust SL2 数据连接器来导入和存档移动应用数据。
ms.openlocfilehash: 0929a92978f9b48d40153b3cc7328e5e05b54fd0
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096946"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365-preview"></a><span data-ttu-id="92ce9-103">将数据从 CellTrust SL2 存档到Microsoft 365 (预览) </span><span class="sxs-lookup"><span data-stu-id="92ce9-103">Archive data from CellTrust SL2 to Microsoft 365 (preview)</span></span>

<span data-ttu-id="92ce9-104">CellTrust SL2 捕获移动通信数据，并集成了领先的存档技术，以满足 FINRA、HIPAA、FOIA 和 TCPA 等法规的电子发现要求。</span><span class="sxs-lookup"><span data-stu-id="92ce9-104">CellTrust SL2 captures mobile communications data and integrates with the leading archiving technologies to meet the electronic discovery requirements for regulations such as FINRA, HIPAA, FOIA, and TCPA.</span></span> <span data-ttu-id="92ce9-105">SL2 数据连接器将移动通信项目导入Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="92ce9-105">The SL2 Data Connector imports mobile communication items to Microsoft 365.</span></span> <span data-ttu-id="92ce9-106">本文介绍使用 CellTrust SL2 数据连接器进行存档Microsoft 365 SL2 与数据库集成的过程。</span><span class="sxs-lookup"><span data-stu-id="92ce9-106">This article describes the process for integrating SL2 with Microsoft 365 by using the CellTrust SL2 Data Connector for archiving.</span></span> <span data-ttu-id="92ce9-107">完成此过程假定你已订阅 CellTrust SL2 服务，并且熟悉 SL2 体系结构。</span><span class="sxs-lookup"><span data-stu-id="92ce9-107">Completing this process assumes that you have subscribed to CellTrust SL2 service and are familiar with the SL2 architecture.</span></span> <span data-ttu-id="92ce9-108">有关 SL2 的信息，请参阅<www.celltrust.com>。</span><span class="sxs-lookup"><span data-stu-id="92ce9-108">For information about SL2, see <www.celltrust.com>.</span></span>

<span data-ttu-id="92ce9-109">将数据导入 Microsoft 365 中的用户邮箱后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、Microsoft 365保留策略和通信合规性。</span><span class="sxs-lookup"><span data-stu-id="92ce9-109">After data is imported to user mailboxes in Microsoft 365, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, Microsoft 365 retention policies, and communication compliance.</span></span> <span data-ttu-id="92ce9-110">使用 CellTrust SL2 数据连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="92ce9-110">Using the CellTrust SL2 Data Connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a><span data-ttu-id="92ce9-111">使用 CellTrust SL2 数据连接器进行存档的概述</span><span class="sxs-lookup"><span data-stu-id="92ce9-111">Overview of archiving with the CellTrust SL2 Data Connector</span></span>

<span data-ttu-id="92ce9-112">CellTrust 的 SL2 平台捕获来自多个源的通信数据。</span><span class="sxs-lookup"><span data-stu-id="92ce9-112">CellTrust's SL2 platform captures communication data from multiple sources.</span></span> <span data-ttu-id="92ce9-113">SL2 数据源可以是个人到个人 (P2P) 或应用程序到 (A2P) 。</span><span class="sxs-lookup"><span data-stu-id="92ce9-113">SL2 data sources are either Person-to-Person (P2P) or Application-to-Person (A2P).</span></span> <span data-ttu-id="92ce9-114">本文中介绍的过程仅适用于 P2P 数据源。</span><span class="sxs-lookup"><span data-stu-id="92ce9-114">The process described in this article pertains only to P2P data sources.</span></span> <span data-ttu-id="92ce9-115">对于所有 P2P 数据源，协作中至少有一方是订阅 SL2 服务的 SL2 用户。</span><span class="sxs-lookup"><span data-stu-id="92ce9-115">For all P2P data sources, at least one party in the collaboration is an SL2 user who is subscribed to the SL2 service.</span></span> <span data-ttu-id="92ce9-116">以下概述介绍了在 Microsoft 365 中使用 CellTrust SL2 数据连接器Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="92ce9-116">The following overview explains the process of using the CellTrust SL2 Data Connector in Microsoft 365.</span></span>

![CellTrust SL2 服务的存档工作流](../media/CellTrustSL2ConnectorWorkflow.png)

1. <span data-ttu-id="92ce9-118">SL2 用户向云中的 SL2 服务发送和接收Microsoft Azure数据。</span><span class="sxs-lookup"><span data-stu-id="92ce9-118">SL2 users send and receive data to and from SL2 services in the Microsoft Azure cloud.</span></span>

2. <span data-ttu-id="92ce9-119">你的组织在 CellTrust 的 SL2 云服务环境中具有 SL2 域。</span><span class="sxs-lookup"><span data-stu-id="92ce9-119">Your organization has an SL2 domain in CellTrust's SL2 Cloud Service environment.</span></span> <span data-ttu-id="92ce9-120">你的域可能有一个或多个组织单位 (组织) 。</span><span class="sxs-lookup"><span data-stu-id="92ce9-120">Your domain may have one or more organizational units (OUs).</span></span> <span data-ttu-id="92ce9-121">SL2 云服务将你的数据传输到 Microsoft Azure 平台中的高度安全区域，以便你的数据永远不会离开Microsoft Azure环境。</span><span class="sxs-lookup"><span data-stu-id="92ce9-121">The SL2 Cloud Service transfers your data to a highly secure area in the Microsoft Azure platform, so that your data never leaves the Microsoft Azure environment.</span></span> <span data-ttu-id="92ce9-122">根据 SL2 计划 (Enterprise、SMB 或政府) ，你的域托管在 Microsoft Azure 政府或政府Microsoft Azure上。</span><span class="sxs-lookup"><span data-stu-id="92ce9-122">Depending on your SL2 plan (Enterprise, SMB, or Government), your domain is either hosted on Microsoft Azure Global or Microsoft Azure Government.</span></span>

3. <span data-ttu-id="92ce9-123">创建 CellTrust SL2 数据连接器后，你的域和 US (无论 SL2 计划是什么) ，都开始将数据发送到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="92ce9-123">After you create the CellTrust SL2 Data Connector, your domain and OUs (regardless of your SL2 plan), begin sending data to Microsoft 365.</span></span> <span data-ttu-id="92ce9-124">数据源的结构支持基于数据源、OUS 或域本身的报告。</span><span class="sxs-lookup"><span data-stu-id="92ce9-124">The data feed is structured to support reporting based on data sources, OUs, or the domain by itself.</span></span> <span data-ttu-id="92ce9-125">因此，贵组织只需要一个连接器来馈送所有数据源Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="92ce9-125">As a result, your organization needs only one connector to feed all your data sources to Microsoft 365.</span></span>

4. <span data-ttu-id="92ce9-126">连接器在每个映射用户下创建一个文件夹，该文件夹具有Office 365 **CellTrust SL2** 许可证。</span><span class="sxs-lookup"><span data-stu-id="92ce9-126">The connector creates a folder under each mapped user with an appropriate Office 365 license titled **CellTrust SL2**.</span></span> <span data-ttu-id="92ce9-127">此映射使用电子邮件地址将 CellTrust SL2 Office 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="92ce9-127">This mapping connects a CellTrust SL2 user to an Office 365 mailbox by using an email address.</span></span> <span data-ttu-id="92ce9-128">如果 CellTrust SL2 中的用户 ID 与 Office 365不匹配，将不会存档用户数据。</span><span class="sxs-lookup"><span data-stu-id="92ce9-128">If a user ID in CellTrust SL2 has no match in Office 365, the user's data will not be archived.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="92ce9-129">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="92ce9-129">Before you set up a connector</span></span>

- <span data-ttu-id="92ce9-130">验证 CellTrust SL2 云服务环境中是否具有域。</span><span class="sxs-lookup"><span data-stu-id="92ce9-130">Verify that you have a domain in the CellTrust SL2 cloud service environment.</span></span> <span data-ttu-id="92ce9-131">有关获取生产或试用 SL2 域的其他信息，请联系 [CellTrust](https://www.celltrust.com/contact-us/#form)。</span><span class="sxs-lookup"><span data-stu-id="92ce9-131">For additional information on obtaining a production or trial SL2 domain, [Contact CellTrust](https://www.celltrust.com/contact-us/#form).</span></span>

- <span data-ttu-id="92ce9-132">获取凭据以访问 SL2 域的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="92ce9-132">Obtain the credentials to access the administrator account for your SL2 domain.</span></span>

- <span data-ttu-id="92ce9-133">必须在步骤 1 中创建 CellTrust SL2 数据连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="92ce9-133">The user who creates the CellTrust SL2 data connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="92ce9-134">若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** 此Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="92ce9-134">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="92ce9-135">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="92ce9-135">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="92ce9-136">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="92ce9-136">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="92ce9-137">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="92ce9-137">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="92ce9-138">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="92ce9-138">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-a-celltrust-sl2-connector"></a><span data-ttu-id="92ce9-139">步骤 1：创建 CellTrust SL2 连接器</span><span class="sxs-lookup"><span data-stu-id="92ce9-139">Step 1: Create a CellTrust SL2 connector</span></span>

<span data-ttu-id="92ce9-140">第一步是在数据连接器Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="92ce9-140">The first step is to create a data connector in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="92ce9-141">转到左侧 <https://compliance.microsoft.com> 导航 **窗格，然后单击** "数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="92ce9-141">Go to <https://compliance.microsoft.com> and click **Data connectors** on the left navigation pane.</span></span>

2. <span data-ttu-id="92ce9-142">在" **概述"** 选项卡上，单击 **"筛选** "并选择 **"By CellTrust"，** 然后应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="92ce9-142">On the **Overview** tab, click **Filter** and select **By CellTrust**, and then apply the filter.</span></span>

   ![配置筛选器以显示 CellTrust 连接器](../media/DataConnectorsFilter.png)

3. <span data-ttu-id="92ce9-144">单击 **CellTrust SL2 (预览) 。**</span><span class="sxs-lookup"><span data-stu-id="92ce9-144">Click **CellTrust SL2 (preview**).</span></span>

4. <span data-ttu-id="92ce9-145">在 **CellTrust SL2 (预览**) "产品说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="92ce9-145">On the **CellTrust SL2 (preview**) product description page, click **Add connector**.</span></span>

5. <span data-ttu-id="92ce9-146">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="92ce9-146">On the **Terms of service** page, click **Accept**.</span></span>

6. <span data-ttu-id="92ce9-147">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="92ce9-147">Enter a unique name that identifies the connector and then click **Next**.</span></span> <span data-ttu-id="92ce9-148">创建连接器后，输入的名称将标识"数据连接器 **"页上的** 连接器。</span><span class="sxs-lookup"><span data-stu-id="92ce9-148">The name you enter will identify the connector on the **Data connectors** page after you create it.</span></span>

7. <span data-ttu-id="92ce9-149">在"**登录到您的 CellTrust 帐户"页上**，单击 **"登录到 CellTrust"。**</span><span class="sxs-lookup"><span data-stu-id="92ce9-149">On the **Sign in to your CellTrust account** page, click **Sign into CellTrust**.</span></span> <span data-ttu-id="92ce9-150">You'll be redirected to the **CellTrust Portal for Microsoft 365** in a new browser window.</span><span class="sxs-lookup"><span data-stu-id="92ce9-150">You'll be redirected to the **CellTrust Portal for Microsoft 365** in a new browser window.</span></span>

## <a name="step-2-select-the-domains-or-ous-to-archive"></a><span data-ttu-id="92ce9-151">步骤 2：选择要存档的域或 US</span><span class="sxs-lookup"><span data-stu-id="92ce9-151">Step 2: Select the domains or OUs to archive</span></span>

<span data-ttu-id="92ce9-152">下一步是登录到 CellTrust SL2 域的管理员帐户，然后选择要将其存档在 Microsoft 365 中的域和 MICROSOFT 365。</span><span class="sxs-lookup"><span data-stu-id="92ce9-152">The next step is to sign into an administrator account for your CellTrust SL2 domain and select the domains and OUs to archive in Microsoft 365.</span></span>

1. <span data-ttu-id="92ce9-153">在"CellTrust **Microsoft 365** 连接器"页上，选择 SL2 云服务中的环境以显示登录页。</span><span class="sxs-lookup"><span data-stu-id="92ce9-153">On the CellTrust **Microsoft 365 Connector** page, select your environment in the SL2 cloud service to display a sign-in page.</span></span>

   <span data-ttu-id="92ce9-154">通常，应该会看到一个表示环境的选项。</span><span class="sxs-lookup"><span data-stu-id="92ce9-154">Typically, you should see one option representing your environment.</span></span> <span data-ttu-id="92ce9-155">但是，如果您在多个环境中拥有域，则会看到每个环境的选项。</span><span class="sxs-lookup"><span data-stu-id="92ce9-155">However, if you have domains in more than one environment, you will see options for each environment.</span></span> <span data-ttu-id="92ce9-156">做出选择后，你将重定向到 SL2 登录页。</span><span class="sxs-lookup"><span data-stu-id="92ce9-156">After you make a selection, you'll be redirected to the SL2 login page.</span></span>

2. <span data-ttu-id="92ce9-157">使用域或 OU 管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="92ce9-157">Sign in with your Domain or OU Administrator account credentials.</span></span>

   <span data-ttu-id="92ce9-158">如果你以 SL2 域管理员登录，你将看到域的名称和该域中的 US。</span><span class="sxs-lookup"><span data-stu-id="92ce9-158">If you sign in as an SL2 domain administrator, you will see the name of your domain and the OUs in that domain.</span></span> <span data-ttu-id="92ce9-159">如果没有 US，则只能看到域的名称。</span><span class="sxs-lookup"><span data-stu-id="92ce9-159">If you do not have OUs, you only see the name of your domain.</span></span> <span data-ttu-id="92ce9-160">如果您以 OU 管理员角色登录，则只会看到 OU 的名称。</span><span class="sxs-lookup"><span data-stu-id="92ce9-160">If you log in as OU Administrator, you only see the name of your OU.</span></span>

3. <span data-ttu-id="92ce9-161">启用要存档的业务单位。</span><span class="sxs-lookup"><span data-stu-id="92ce9-161">Enable the business units you wish to archive.</span></span> <span data-ttu-id="92ce9-162">选择域不会自动选择 US。</span><span class="sxs-lookup"><span data-stu-id="92ce9-162">Selecting the domain will not automatically select the OUs.</span></span> <span data-ttu-id="92ce9-163">必须单独启用每个 OU 才能将其存档。</span><span class="sxs-lookup"><span data-stu-id="92ce9-163">You must enable each OU separately to archive it.</span></span>

   ![启用要存档的 US](../media/EnableCellTrustOUs.png)

4. <span data-ttu-id="92ce9-165">完成选择后，关闭浏览器窗口，然后返回到向导Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="92ce9-165">When you're finished with your selections, close the browser window and return to the wizard page in Microsoft 365 compliance center.</span></span> <span data-ttu-id="92ce9-166">几秒钟后，向导将自动前进到映射用户的下一步。</span><span class="sxs-lookup"><span data-stu-id="92ce9-166">After a few seconds, the wizard automatically advances to the next step of mapping users.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="92ce9-167">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="92ce9-167">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="92ce9-168">最后一步是映射用户并完成连接器设置Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="92ce9-168">The last step is to map users and complete the connector setup in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="92ce9-169">在"**用户映射"** 页上，如果用户的电子邮件地址在 SL2 和 Microsoft 365 中均相同，请选择"启用自动用户映射"。</span><span class="sxs-lookup"><span data-stu-id="92ce9-169">On the **User mapping** page, select **Enable automatic user mapping** if the email address for users is the same in both SL2 and  Microsoft 365.</span></span> <span data-ttu-id="92ce9-170">否则，您应通过上载 CSV 文件手动将用户的 SL2 地址映射到其Microsoft 365电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="92ce9-170">Otherwise, you should manually user email addresses by uploading a CSV file that maps users' SL2 address to their Microsoft 365 address.</span></span>

2. <span data-ttu-id="92ce9-171">单击 **"下** 一步"，查看设置，然后单击" **完成** "以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="92ce9-171">Click **Next**, review your settings, and then click **Finish** to create the connector.</span></span>

   <span data-ttu-id="92ce9-172">新连接器将添加到"数据连接器" **页上** 的列表中。</span><span class="sxs-lookup"><span data-stu-id="92ce9-172">The new connector is added to the list on the **Data connectors** page.</span></span>

## <a name="get-help-from-celltrust"></a><span data-ttu-id="92ce9-173">从 CellTrust 获取帮助</span><span class="sxs-lookup"><span data-stu-id="92ce9-173">Get help from CellTrust</span></span>

<span data-ttu-id="92ce9-174">有关与 CellTrust 联系的详细信息，请参阅 [CellTrust 客户支持](https://www.celltrust.com/contact-us/#support) 页，了解有关设置 CellTrust SL2 数据连接器的帮助。</span><span class="sxs-lookup"><span data-stu-id="92ce9-174">See the [CellTrust Customer Support page](https://www.celltrust.com/contact-us/#support) for details about contacting CellTrust for help with setting up a CellTrust SL2 data connector.</span></span>

## <a name="more-information"></a><span data-ttu-id="92ce9-175">更多信息</span><span class="sxs-lookup"><span data-stu-id="92ce9-175">More information</span></span>

- <span data-ttu-id="92ce9-176">域管理员可以为域或该域中的任何 US 设置连接器。</span><span class="sxs-lookup"><span data-stu-id="92ce9-176">A domain administrator can set up a connector for the domain or any OUs in that domain.</span></span> <span data-ttu-id="92ce9-177">如果使用 OU 管理员帐户，则只能为特定 OU 设置连接器。</span><span class="sxs-lookup"><span data-stu-id="92ce9-177">If you use the OU Administrator account, you can only set up a connector for that specific OU.</span></span>

- <span data-ttu-id="92ce9-178">若要成功完成上述步骤，您必须获得一个Microsoft 365 E5许可证，并拥有适当的Microsoft Office权限。</span><span class="sxs-lookup"><span data-stu-id="92ce9-178">To successfully complete the steps above, you must be assigned a Microsoft 365 E5 license and have the proper Microsoft Office admin rights.</span></span>

- <span data-ttu-id="92ce9-179">若要测试新连接器，使用 SL2 移动应用或 SL2 门户发送短信。</span><span class="sxs-lookup"><span data-stu-id="92ce9-179">To test the new connector, send a text message using your SL2 mobile app or from your SL2 portal.</span></span> <span data-ttu-id="92ce9-180">转到你的邮箱Microsoft 365打开收件箱中的 **CellTrust SL2** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="92ce9-180">Go to your Microsoft 365 mailbox and open the **CellTrust SL2** folder in your Inbox.</span></span> <span data-ttu-id="92ce9-181">可能需要几分钟时间，短信才能显示在邮箱中。</span><span class="sxs-lookup"><span data-stu-id="92ce9-181">It may take a few minutes for the text messages to show up in your mailbox.</span></span>

- <span data-ttu-id="92ce9-182">许多法律和法规都要求以如下方式保留电子通信：在请求时，可以将通信生成为证据。</span><span class="sxs-lookup"><span data-stu-id="92ce9-182">Many laws and regulations require electronic communication to be preserved in such a way that, when requested, it can be produced as evidence.</span></span> <span data-ttu-id="92ce9-183">电子 (电子数据) 用于遵守电子通信的生产要求。</span><span class="sxs-lookup"><span data-stu-id="92ce9-183">Electronic Discovery (eDiscovery) is used to comply with the production of electronic communication.</span></span> <span data-ttu-id="92ce9-184">企业资讯存档 (EIA) 解决方案旨在执行电子数据展示，并提供保留策略管理、数据分类和内容监督等功能。</span><span class="sxs-lookup"><span data-stu-id="92ce9-184">Enterprise Information Archiving (EIA) solutions are designed to perform eDiscovery, and provide features such as retention policy management, data classification, and content supervision.</span></span> <span data-ttu-id="92ce9-185">Microsoft 365提供长期保留解决方案，以遵守影响组织的法规和标准。</span><span class="sxs-lookup"><span data-stu-id="92ce9-185">Microsoft 365 offers a long-term retention solution for compliance with the regulations and standards that affect your organization.</span></span>

- <span data-ttu-id="92ce9-186">本文档 *中使用的* 术语"存档"是指在 EIA 存档解决方案中使用的企业资讯 (存档) 。</span><span class="sxs-lookup"><span data-stu-id="92ce9-186">The term *archiving* as used in this document refers to archiving in the context of use within an Enterprise Information Archiving (EIA) solution.</span></span> <span data-ttu-id="92ce9-187">EIA 解决方案具有电子数据展示功能，可生成用于法律诉讼、诉讼、审核和调查的文档。</span><span class="sxs-lookup"><span data-stu-id="92ce9-187">EIA solutions have eDiscovery features that produce documents for legal proceedings, litigation, audits, and investigations.</span></span> <span data-ttu-id="92ce9-188">在用于灾难恢复和业务连续性的备份和还原上下文中进行存档并非本文档中术语的预定用途。</span><span class="sxs-lookup"><span data-stu-id="92ce9-188">Archiving in the context of backup and restore used for disaster recovery and business continuity isn't the intended use of the term within this document.</span></span>
