---
title: 设置连接器以存档 Bloomberg 邮件数据
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
description: 管理员可以设置数据连接器，以将数据从 Bloomberg 邮件电子邮件工具导入和存档到 Microsoft 365。 这使你可以存档 Microsoft 365 中第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: c29f8d0c09ce5e84ecf18830df4585f51361995b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919950"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a><span data-ttu-id="a8cec-104">设置连接器以存档 Bloomberg 邮件数据</span><span class="sxs-lookup"><span data-stu-id="a8cec-104">Set up a connector to archive Bloomberg Message data</span></span>

<span data-ttu-id="a8cec-105">使用 Microsoft 365 合规中心内的数据连接器从 [Bloomberg Message](https://www.bloomberg.com/professional/product/collaboration/) 协作工具导入和存档金融服务电子邮件数据。</span><span class="sxs-lookup"><span data-stu-id="a8cec-105">Use a data connector in the Microsoft 365 compliance center to import and archive financial services email data from the [Bloomberg Message](https://www.bloomberg.com/professional/product/collaboration/) collaboration tool.</span></span> <span data-ttu-id="a8cec-106">设置和配置连接器后，它每天连接到组织的一次安全 FTP (SFTP) 网站，将电子邮件项目导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8cec-106">After you set up and configure a connector, it connects to your organization's Bloomberg secure FTP (SFTP) site once every day, and imports email items to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="a8cec-107">在将 Bloomberg 邮件数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 Bloomberg Message 数据。</span><span class="sxs-lookup"><span data-stu-id="a8cec-107">After Bloomberg Message data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation hold, content search, In-place archiving, auditing, Communication compliance, and Microsoft 365 retention policies to Bloomberg Message data.</span></span> <span data-ttu-id="a8cec-108">例如，您可以使用内容搜索工具搜索 Bloomberg Message 电子邮件，或将包含 Bloomberg Message 数据的邮箱与高级电子数据展示案例中的保管人关联。</span><span class="sxs-lookup"><span data-stu-id="a8cec-108">For example, you can search Bloomberg Message emails using the content search tool or associate the mailbox that contains the Bloomberg Message data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="a8cec-109">使用一个 Bloomberg 邮件连接器在 Microsoft 365 中导入和存档数据可帮助你的组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="a8cec-109">Using a Bloomberg Message connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-bloomberg-message-data"></a><span data-ttu-id="a8cec-110">存档 Bloomberg 邮件数据概述</span><span class="sxs-lookup"><span data-stu-id="a8cec-110">Overview of archiving Bloomberg Message data</span></span>

<span data-ttu-id="a8cec-111">以下概述介绍了使用连接器在 Microsoft 365 中存档 Bloomberg Message 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="a8cec-111">The following overview explains the process of using a connector to archive Bloomberg Message data in Microsoft 365.</span></span>

![Bloomberg 邮件导入和存档过程](../media/BloombergMessageArchiving.png)

1. <span data-ttu-id="a8cec-113">你的组织与 Bloomberg 合作，以设置一个 Bloomberg SFTP 网站。</span><span class="sxs-lookup"><span data-stu-id="a8cec-113">Your organization works with Bloomberg to set up a Bloomberg SFTP site.</span></span> <span data-ttu-id="a8cec-114">You'll also work with Bloomberg to configure Bloomberg Message to copy email messages to the Bloomberg SFTP site.</span><span class="sxs-lookup"><span data-stu-id="a8cec-114">You'll also work with Bloomberg to configure Bloomberg Message to copy email messages to the Bloomberg SFTP site.</span></span>

2. <span data-ttu-id="a8cec-115">每 24 小时发送一次，来自 Bloomberg Message 的电子邮件将复制到 Bloomberg SFTP 网站。</span><span class="sxs-lookup"><span data-stu-id="a8cec-115">Once every 24 hours, email messages from Bloomberg Message are copied to the Bloomberg SFTP site.</span></span>

3. <span data-ttu-id="a8cec-116">你在 Microsoft 365 合规中心创建的 Bloomberg 邮件连接器每天连接到一个 Bloomberg SFTP 网站，将过去 24 小时内的电子邮件转移到 Microsoft 云中安全的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="a8cec-116">The Bloomberg Message connector that you create in the Microsoft 365 compliance center connects to the Bloomberg SFTP site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

4. <span data-ttu-id="a8cec-117">连接器将电子邮件项目导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8cec-117">The connector imports the email message items to the mailbox of a specific user.</span></span> <span data-ttu-id="a8cec-118">将在特定用户的邮箱中创建一个名为 BloombergMessage 的新文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a8cec-118">A new folder named BloombergMessage is created in the specific user's mailbox and the items will be imported to it.</span></span> 

   <span data-ttu-id="a8cec-119">连接器使用 CorporateEmailAddress 属性的值实现此操作。</span><span class="sxs-lookup"><span data-stu-id="a8cec-119">The connector does this by using the value of the CorporateEmailAddress property.</span></span> <span data-ttu-id="a8cec-120">每个电子邮件都包含此属性，该属性填充了电子邮件每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a8cec-120">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="a8cec-121">除了使用 *CorporateEmailAddress* 属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。</span><span class="sxs-lookup"><span data-stu-id="a8cec-121">In addition to automatic user mapping using the value of the *CorporateEmailAddress* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="a8cec-122">此映射文件包含一个 Bloomberg UUID 和组织中每个用户的相应 Microsoft 365 邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="a8cec-122">This mapping file contains a Bloomberg UUID and the corresponding Microsoft 365 mailbox address for each user in your organization.</span></span> <span data-ttu-id="a8cec-123">如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。</span><span class="sxs-lookup"><span data-stu-id="a8cec-123">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at the custom-mapping file.</span></span> <span data-ttu-id="a8cec-124">如果找不到与用户的 Bloomberg UUID 对应的有效 Microsoft 365 用户，连接器将使用电子邮件项目的 *CorporateEmailAddress* 属性。</span><span class="sxs-lookup"><span data-stu-id="a8cec-124">If it doesn't find a valid Microsoft 365 user that corresponds to a user's Bloomberg UUID, the connector uses the *CorporateEmailAddress* property of the email item.</span></span> <span data-ttu-id="a8cec-125">如果连接器在电子邮件项目的自定义映射文件或 *CorporateEmailAddress* 属性中找不到有效的 Microsoft 365 用户，则不导入该项目。</span><span class="sxs-lookup"><span data-stu-id="a8cec-125">If the connector doesn't find a valid Microsoft 365 user in either the custom-mapping file or the *CorporateEmailAddress* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a8cec-126">开始之前</span><span class="sxs-lookup"><span data-stu-id="a8cec-126">Before you begin</span></span>

<span data-ttu-id="a8cec-127">存档 Bloomberg 邮件数据所需的一些实施步骤在 Microsoft 365 外部，必须先完成，然后才能在合规中心创建连接器。</span><span class="sxs-lookup"><span data-stu-id="a8cec-127">Some of the implementation steps required to archive Bloomberg Message data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="a8cec-128">订阅 [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)。</span><span class="sxs-lookup"><span data-stu-id="a8cec-128">Subscribe to [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA).</span></span> <span data-ttu-id="a8cec-129">这是必需的，以便你可以登录到 Bloomberg Anywhere 以访问必须设置和配置的 Bloomberg SFTP 网站。</span><span class="sxs-lookup"><span data-stu-id="a8cec-129">This is required so that you can log in to Bloomberg Anywhere to access the Bloomberg SFTP site that you have to set up and configure.</span></span>

- <span data-ttu-id="a8cec-130">设置一个 Bloomberg SFTP (安全文件传输协议) 网站。</span><span class="sxs-lookup"><span data-stu-id="a8cec-130">Set up a Bloomberg SFTP (Secure file transfer protocol) site.</span></span> <span data-ttu-id="a8cec-131">与 Bloomberg 合作设置 SFTP 网站后，一天中将一条来自 Bloomberg Message 的数据上载到 SFTP 网站。</span><span class="sxs-lookup"><span data-stu-id="a8cec-131">After working with Bloomberg to set up the SFTP site, data from Bloomberg Message is uploaded to the SFTP site every day.</span></span> <span data-ttu-id="a8cec-132">在步骤 2 创建的连接器连接到此 SFTP 网站，将电子邮件数据传输至 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8cec-132">The connector you create in Step 2 connects to this SFTP site and transfers the email data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="a8cec-133">SFTP 还加密在传输过程中发送到邮箱的 Bloomberg 邮件数据。</span><span class="sxs-lookup"><span data-stu-id="a8cec-133">SFTP also encrypts the Bloomberg Message data that is sent to mailboxes during the transfer process.</span></span>

  <span data-ttu-id="a8cec-134">有关 Bloomberg SFTP (*也称为 BB-SFTP*) ：</span><span class="sxs-lookup"><span data-stu-id="a8cec-134">For information about Bloomberg SFTP (also called *BB-SFTP*):</span></span>

  - <span data-ttu-id="a8cec-135">请参阅位于 Bloomberg Support 的"SFTP 连接标准 ["文档](https://www.bloomberg.com/professional/support/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="a8cec-135">See the "SFTP Connectivity Standards" document at [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/).</span></span>

  - <span data-ttu-id="a8cec-136">联系 [Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)。</span><span class="sxs-lookup"><span data-stu-id="a8cec-136">Contact [Bloomberg customer support](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).</span></span>

   > [!NOTE]
   > <span data-ttu-id="a8cec-137">如果组织已部署连接器以存档 Instant Bloomberg 数据，则无需设置其他 SFTP 网站。</span><span class="sxs-lookup"><span data-stu-id="a8cec-137">If your organization already deployed a connector to archive Instant Bloomberg data, you don't need to set up another SFTP site.</span></span> <span data-ttu-id="a8cec-138">你可以将同一 SFTP 网站用于 Bloomberg 邮件连接器。</span><span class="sxs-lookup"><span data-stu-id="a8cec-138">You can use the same SFTP site for the Bloomberg Message connector.</span></span>

- <span data-ttu-id="a8cec-139">与 Bloomberg 合作设置 SFTP 网站后，在回复了 Bloomberg 实施电子邮件后，Bloomberg 会向您提供一些信息。</span><span class="sxs-lookup"><span data-stu-id="a8cec-139">After you work with Bloomberg to set up an SFTP site, Bloomberg will provide some information to you after you respond to the Bloomberg implementation email message.</span></span> <span data-ttu-id="a8cec-140">保存以下信息的副本。</span><span class="sxs-lookup"><span data-stu-id="a8cec-140">Save a copy of the following information.</span></span> <span data-ttu-id="a8cec-141">您可以使用它在步骤 3 中设置连接器。</span><span class="sxs-lookup"><span data-stu-id="a8cec-141">You use it to set up a connector in Step 3.</span></span>

  - <span data-ttu-id="a8cec-142">公司代码，它是组织的 ID，用于登录到 Bloomberg SFTP 网站。</span><span class="sxs-lookup"><span data-stu-id="a8cec-142">Firm code, which is an ID for your organization and is used to log in to the Bloomberg SFTP site.</span></span>

  - <span data-ttu-id="a8cec-143">你的 Bloomberg SFTP 网站的密码</span><span class="sxs-lookup"><span data-stu-id="a8cec-143">Password for your Bloomberg SFTP site</span></span>

  - <span data-ttu-id="a8cec-144">一个用于 Bloomberg SFTP (URL，例如，sftp.bloomberg.com) 。</span><span class="sxs-lookup"><span data-stu-id="a8cec-144">URL for Bloomberg SFTP site (for example, sftp.bloomberg.com).</span></span> <span data-ttu-id="a8cec-145">此外，Bloomberg 还可以为 Bloomberg SFTP 网站提供相应的 IP 地址，该地址还可用于设置连接器。</span><span class="sxs-lookup"><span data-stu-id="a8cec-145">In addition, Bloomberg may also provide a corresponding IP address for the Bloomberg SFTP site, which also can be used to set up the connector.</span></span>

  - <span data-ttu-id="a8cec-146">Bloomberg SFTP 网站的端口号</span><span class="sxs-lookup"><span data-stu-id="a8cec-146">Port number for Bloomberg SFTP site</span></span>

- <span data-ttu-id="a8cec-147">Bloomberg 邮件连接器一天中总共可以导入 200，000 个项目。</span><span class="sxs-lookup"><span data-stu-id="a8cec-147">The Bloomberg Message connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="a8cec-148">如果 SFTP 网站上有 200，000 多个项目，则这些项均不会导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a8cec-148">If there are more than 200,000 items on the SFTP site, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="a8cec-149">必须在 Exchange Online 中分配在步骤 3 (中创建一个 Bloomberg 邮件连接器且在步骤 1) 中下载公钥和 IP 地址的用户。</span><span class="sxs-lookup"><span data-stu-id="a8cec-149">The user who creates a Bloomberg Message connector in Step 3 (and who downloads the public keys and IP address in Step 1) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a8cec-150">这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。</span><span class="sxs-lookup"><span data-stu-id="a8cec-150">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a8cec-151">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="a8cec-151">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="a8cec-152">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="a8cec-152">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a8cec-153">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="a8cec-153">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a8cec-154">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="a8cec-154">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a><span data-ttu-id="a8cec-155">步骤 1：获取 SSH 和 PGP 公钥</span><span class="sxs-lookup"><span data-stu-id="a8cec-155">Step 1: Obtain SSH and PGP public keys</span></span>

<span data-ttu-id="a8cec-156">第一步是获取安全命令行管理程序 (SSH) PGP (公钥) 。</span><span class="sxs-lookup"><span data-stu-id="a8cec-156">The first step is to obtain a copy of the public keys for Secure Shell (SSH) and Pretty Good Privacy (PGP).</span></span> <span data-ttu-id="a8cec-157">使用步骤 2 中的这些密钥配置 Bloomberg SFTP 网站，以允许在步骤 3) 创建的连接器 (连接到 SFTP 网站，将一封"一条"邮件电子邮件数据传输给 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8cec-157">You use these keys in Step 2 to configure the Bloomberg SFTP site to allow the connector (that you create in Step 3) to connect to the SFTP site and transfer the Bloomberg Message email data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="a8cec-158">您还可以在此步骤中获取 IP 地址，该地址在配置 Bloomberg SFTP 网站时使用。</span><span class="sxs-lookup"><span data-stu-id="a8cec-158">You also obtain an IP address in this step, which you use when configuring the Bloomberg SFTP site.</span></span>

1. <span data-ttu-id="a8cec-159">转到 [ https://compliance.microsoft.com\ https://compliance.microsoft.com) ] (，然后单击左侧导航 **中的** "数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="a8cec-159">Go to [https://compliance.microsoft.com\](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a8cec-160">在"**数据连接器"页面** 的 **"Bloomberg Message"** 下，单击"**查看"。**</span><span class="sxs-lookup"><span data-stu-id="a8cec-160">On the **Data connectors** page under **Bloomberg Message**, click **View**.</span></span>

3. <span data-ttu-id="a8cec-161">在 **"Bloomberg 邮件** "产品说明页面上，单击" **添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="a8cec-161">On the **Bloomberg Message** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="a8cec-162">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="a8cec-162">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="a8cec-163">在步骤 1 下的"为 **Bloomberg SFTP** 网站添加凭据"上，单击"下载 **SSH** 密钥"、"下载 **PGP** 密钥"和"下载 **IP** 地址"链接，将每个文件的副本保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="a8cec-163">On the **Add credentials for Bloomberg SFTP site** under step 1, click the **Download SSH key**, **Download PGP key**, and **Download IP address** links to save a copy of each file to your local computer.</span></span> <span data-ttu-id="a8cec-164">这些文件包含以下项，用于配置步骤 2 中的 Bloomberg SFTP 网站：</span><span class="sxs-lookup"><span data-stu-id="a8cec-164">These files contain the following items that are used to configure the Bloomberg SFTP site in Step 2:</span></span>

   - <span data-ttu-id="a8cec-165">SSH 公钥：此密钥用于配置安全命令行管理程序 (SSH) ，以在连接器连接到 Bloomberg SFTP 网站时启用安全远程登录。</span><span class="sxs-lookup"><span data-stu-id="a8cec-165">SSH public key: This key is used to configure Secure Shell (SSH) to enable a secure remote login when the connector connects to the Bloomberg SFTP site.</span></span>

   - <span data-ttu-id="a8cec-166">PGP 公钥：此密钥用于配置从 Bloomberg SFTP 网站传输到 Microsoft 365 的数据加密。</span><span class="sxs-lookup"><span data-stu-id="a8cec-166">PGP public key: This key is used to configure the encryption of data that's transferred from the Bloomberg SFTP site to Microsoft 365.</span></span>

   - <span data-ttu-id="a8cec-167">IP 地址：将 Bloomberg SFTP 网站配置为仅接受来自此 IP 地址的连接请求，由你在步骤 3 创建的 Bloomberg 邮件连接器使用。</span><span class="sxs-lookup"><span data-stu-id="a8cec-167">IP address: The Bloomberg SFTP site is configured to accept a connection request only from this IP address, which is used by the Bloomberg Message connector that you create in Step 3.</span></span>

6. <span data-ttu-id="a8cec-168">单击 **"** 取消"关闭向导。</span><span class="sxs-lookup"><span data-stu-id="a8cec-168">Click **Cancel** to close the wizard.</span></span> <span data-ttu-id="a8cec-169">在步骤 3 中返回到此向导以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="a8cec-169">You come back to this wizard in Step 3 to create the connector.</span></span>

## <a name="step-2-configure-the-bloomberg-sftp-site"></a><span data-ttu-id="a8cec-170">步骤 2：配置 Bloomberg SFTP 网站</span><span class="sxs-lookup"><span data-stu-id="a8cec-170">Step 2: Configure the Bloomberg SFTP site</span></span>

> [!NOTE]
> <span data-ttu-id="a8cec-171">如前所述，如果你的组织之前设置了一个 Bloomberg SFTP 网站来存档 Instant Bloomberg 数据，则不必设置另一个。</span><span class="sxs-lookup"><span data-stu-id="a8cec-171">As previously stated, if you're organization has previously set up a Bloomberg SFTP site to archive Instant Bloomberg data, you don't have to set up another one.</span></span> <span data-ttu-id="a8cec-172">可以在步骤 3 中创建连接器时指定相同的 SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="a8cec-172">You can specify the same SFTP site when you create the connector in Step 3.</span></span>

<span data-ttu-id="a8cec-173">下一步是使用 SSH 和 PGP 公钥以及你在步骤 1 中获得的 IP 地址为 Bloomberg SFTP 网站配置 SSH 身份验证和 PGP 加密。</span><span class="sxs-lookup"><span data-stu-id="a8cec-173">The next step is to use the SSH and PGP public keys and the IP address that you obtained in Step 1 to configure SSH authentication and PGP encryption for the Bloomberg SFTP site.</span></span> <span data-ttu-id="a8cec-174">这样，你在步骤 3 创建的 Bloomberg 邮件连接器可以连接到 Bloomberg SFTP 网站，将 Bloomberg Message 数据传输给 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a8cec-174">This lets the Bloomberg Message connector that you create in Step 3 connect to the Bloomberg SFTP site and transfer Bloomberg Message data to Microsoft 365.</span></span> <span data-ttu-id="a8cec-175">你需要与 Bloomberg 客户支持合作，以设置你的 Bloomberg SFTP 网站。</span><span class="sxs-lookup"><span data-stu-id="a8cec-175">You need to work with Bloomberg customer support to set up your Bloomberg SFTP site.</span></span> <span data-ttu-id="a8cec-176">请联系 [Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="a8cec-176">Contact [Bloomberg customer support](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) for assistance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8cec-177">Bloomberg 建议你在步骤 1 中下载的三个文件附加到电子邮件，并发送给客户支持团队，当与它们合作设置你的 Bloomberg SFTP 网站时。</span><span class="sxs-lookup"><span data-stu-id="a8cec-177">Bloomberg recommends that you attach the three files that you downloaded in Step 1 to an email message and send it to their customer support team when working with them to set up your Bloomberg SFTP site.</span></span>

## <a name="step-3-create-a-bloomberg-message-connector"></a><span data-ttu-id="a8cec-178">步骤 3：创建一个 Bloomberg 邮件连接器</span><span class="sxs-lookup"><span data-stu-id="a8cec-178">Step 3: Create a Bloomberg Message connector</span></span>

<span data-ttu-id="a8cec-179">最后一步是在 Microsoft 365 合规中心创建一个 Bloomberg 邮件连接器。</span><span class="sxs-lookup"><span data-stu-id="a8cec-179">The last step is to create a Bloomberg Message connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a8cec-180">连接器使用你提供的信息连接到 Bloomberg SFTP 网站，将电子邮件转移到 Microsoft 365 中的相应用户邮箱框。</span><span class="sxs-lookup"><span data-stu-id="a8cec-180">The connector uses the information you provide to connect to the Bloomberg SFTP site and transfer email messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="a8cec-181">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="a8cec-181">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a8cec-182">在"**数据连接器"页面** 的 **"Bloomberg Message"** 下，单击"**查看"。**</span><span class="sxs-lookup"><span data-stu-id="a8cec-182">On the **Data connectors** page under **Bloomberg Message**, click **View**.</span></span>

3. <span data-ttu-id="a8cec-183">在 **"Bloomberg 邮件** "产品说明页面上，单击" **添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="a8cec-183">On the **Bloomberg Message** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="a8cec-184">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="a8cec-184">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="a8cec-185">在"**为 Bloomberg SFTP** 添加凭据"网站页面的"步骤 3"下，在下列框中输入所需信息，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a8cec-185">On the **Add credentials for Bloomberg SFTP site** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

      - <span data-ttu-id="a8cec-186">**公司代码：** 用作 Bloomberg SFTP 网站的用户名的组织 ID。</span><span class="sxs-lookup"><span data-stu-id="a8cec-186">**Firm code:** The ID for your organization that is used as the username for the Bloomberg SFTP site.</span></span>

      - <span data-ttu-id="a8cec-187">**密码：** 您组织的 Bloomberg SFTP 网站的密码。</span><span class="sxs-lookup"><span data-stu-id="a8cec-187">**Password:** The password for your organization's Bloomberg SFTP site.</span></span>

      - <span data-ttu-id="a8cec-188">**SFTP URL：** Bloomberg SFTP 网站的 URL (例如，sftp.bloomberg.com) 。</span><span class="sxs-lookup"><span data-stu-id="a8cec-188">**SFTP URL:** The URL for the Bloomberg SFTP site (for example, sftp.bloomberg.com).</span></span>

      - <span data-ttu-id="a8cec-189">**SFTP 端口：** Bloomberg SFTP 网站的端口号。</span><span class="sxs-lookup"><span data-stu-id="a8cec-189">**SFTP port:** The port number for the Bloomberg SFTP site.</span></span> <span data-ttu-id="a8cec-190">连接器使用此端口连接到 SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="a8cec-190">The connector uses this port to connect to the SFTP site.</span></span>

6. <span data-ttu-id="a8cec-191">在 **"用户映射"** 页上，启用自动用户映射并按需要提供自定义用户映射</span><span class="sxs-lookup"><span data-stu-id="a8cec-191">On the **User-mapping** page, enable automatic user mapping and provide custom user mapping as required</span></span>

7. <span data-ttu-id="a8cec-192">单击 **"下** 一步"，查看设置，然后单击"准备"以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="a8cec-192">Click **Next**, review your settings, and then click prepare to create the connector.</span></span>

8. <span data-ttu-id="a8cec-193">转到" **数据连接器"** 页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="a8cec-193">Go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a8cec-194">已知问题</span><span class="sxs-lookup"><span data-stu-id="a8cec-194">Known issues</span></span>

- <span data-ttu-id="a8cec-195">不支持对导入到 Microsoft 365 的 Bloomberg 邮件电子邮件进行线程处理。</span><span class="sxs-lookup"><span data-stu-id="a8cec-195">Threading of Bloomberg Message email imported to Microsoft 365 isn't supported.</span></span> <span data-ttu-id="a8cec-196">发送给某人的单个消息将被导入，但它们不会呈现在线程对话中。</span><span class="sxs-lookup"><span data-stu-id="a8cec-196">Individual messages sent to a person are imported, but they aren't presented in a threaded conversation.</span></span> <span data-ttu-id="a8cec-197">Microsoft 正在致力于在更高版本的 Bloomberg 邮件数据连接器中支持线程处理。</span><span class="sxs-lookup"><span data-stu-id="a8cec-197">Microsoft is working to support threading in later versions of the Bloomberg Message data connector.</span></span>