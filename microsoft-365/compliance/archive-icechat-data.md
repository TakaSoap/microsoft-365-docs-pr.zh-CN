---
title: 设置连接器以存档 ICE Chat 数据
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
description: 管理员可以设置连接器，以将数据从 ICE 聊天工具导入和存档到Microsoft 365。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 958a6dde0a4f23933ef6328719fbf43265420c7c
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077297"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a><span data-ttu-id="3280a-104">设置连接器以存档 ICE Chat 数据</span><span class="sxs-lookup"><span data-stu-id="3280a-104">Set up a connector to archive ICE Chat data</span></span>

<span data-ttu-id="3280a-105">使用合规性中心中的本机连接器Microsoft 365 ICE 聊天协作工具导入和存档金融服务聊天数据。</span><span class="sxs-lookup"><span data-stu-id="3280a-105">Use a native connector in the Microsoft 365 compliance center to import and archive financial services chat data from the ICE Chat collaboration tool.</span></span> <span data-ttu-id="3280a-106">设置和配置连接器后，它每天连接到组织的 ICE Chat 安全 FTP (SFTP) 站点一次，将聊天消息的内容转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3280a-106">After you set up and configure a connector, it connects to your organization's ICE Chat secure FTP (SFTP) site once every day, converts the content of chat messages to an email message format, and then import those items to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="3280a-107">ICE 聊天数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、电子数据展示、存档、审核、通信合规性和 Microsoft 365 保留策略）应用到 ICE 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="3280a-107">After ICE chat data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as litigation hold, eDiscovery, archiving, auditing, communication compliance, and Microsoft 365 retention policies to ICE Chat data.</span></span> <span data-ttu-id="3280a-108">例如，您可以使用内容搜索来搜索 ICE Chat 消息，或将包含 ICE Chat 数据的邮箱与案例的保管人Advanced eDiscovery关联。</span><span class="sxs-lookup"><span data-stu-id="3280a-108">For example, you can search ICE Chat messages using content search or associate the mailbox that contains the ICE Chat data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="3280a-109">使用 ICE 聊天连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="3280a-109">Using an ICE Chat connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ice-chat-data"></a><span data-ttu-id="3280a-110">存档 ICE 聊天数据概述</span><span class="sxs-lookup"><span data-stu-id="3280a-110">Overview of archiving ICE Chat data</span></span>

<span data-ttu-id="3280a-111">以下概述介绍使用连接器在聊天室中存档 ICE 聊天数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3280a-111">The following overview explains the process of using a connector to archive ICE chat data in Microsoft 365.</span></span>

![ICE 聊天存档工作流](../media/ICEChatConnectorWorkflow.png)

1. <span data-ttu-id="3280a-113">你的组织与 ICE 聊天一起设置 ICE 聊天 SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="3280a-113">Your organization works with ICE Chat to set up an ICE Chat SFTP site.</span></span> <span data-ttu-id="3280a-114">你还将使用 ICE Chat 配置 ICE Chat 以将聊天消息复制到 ICE Chat SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="3280a-114">You'll also work with ICE Chat to configure ICE Chat to copy chat messages to your ICE Chat SFTP site.</span></span>

2. <span data-ttu-id="3280a-115">每 24 小时一次，ICE 聊天中的聊天消息将复制到 ICE 聊天 SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="3280a-115">Once every 24 hours, chat messages from ICE Chat are copied to your ICE Chat SFTP site.</span></span>

3. <span data-ttu-id="3280a-116">在 Microsoft 365 合规中心创建的 ICE 聊天连接器每天连接到 ICE 聊天 SFTP 网站，将聊天消息从过去 24 小时转移到 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="3280a-116">The ICE Chat connector that you create in the Microsoft 365 compliance center connects to the ICE Chat SFTP site every day and transfers the chat messages from the previous 24 hours to a secure Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="3280a-117">连接器还会将聊天聊天者的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="3280a-117">The connector also converts the content of a chat massage to an email message format.</span></span>

4. <span data-ttu-id="3280a-118">连接器将聊天消息项目导入特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3280a-118">The connector imports chat message items to the mailboxes of specific users.</span></span> <span data-ttu-id="3280a-119">在用户邮箱中创建 **一** 个名为 ICE Chat 的新文件夹，聊天消息项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="3280a-119">A new folder named **ICE Chat** is created in the user mailboxes and the chat message items are imported to that folder.</span></span> <span data-ttu-id="3280a-120">连接器使用 *SenderEmail* 和 *RecipientEmail 属性的值* 实现。</span><span class="sxs-lookup"><span data-stu-id="3280a-120">The connector does by using the value of the *SenderEmail* and *RecipientEmail* properties.</span></span> <span data-ttu-id="3280a-121">每个聊天消息都包含这些属性，这些属性填充了聊天消息的发件人和每个收件人/参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3280a-121">Every chat message contains these properties, which are populated with email address of the sender and every recipient/participant of the chat message.</span></span>

   <span data-ttu-id="3280a-122">除了使用 *SenderEmail* 和 *RecipientEmail* 属性的值的自动用户映射 (这意味着连接器将聊天消息导入到发件人的邮箱和每个收件人) 的邮箱之外，您还可以通过上载 CSV 映射文件来定义自定义用户映射。</span><span class="sxs-lookup"><span data-stu-id="3280a-122">In addition to automatic user mapping that uses the values of the *SenderEmail* and *RecipientEmail* property (which means that the connector imports a chat message to the sender's mailbox and the mailboxes of every recipient), you can also define custom user mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="3280a-123">此映射文件包含 ICE Chat *ImId* 以及Microsoft 365每个用户的相应邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="3280a-123">This mapping file contains the ICE Chat *ImId* and the corresponding Microsoft 365 mailbox address for every user in your organization.</span></span> <span data-ttu-id="3280a-124">如果启用自动用户映射并提供自定义映射文件，连接器将首先查看自定义映射文件，以查找每个聊天项。</span><span class="sxs-lookup"><span data-stu-id="3280a-124">If you enable automatic user mapping and provide a custom-mapping file, for every chat item the connector will first look at the custom-mapping file.</span></span> <span data-ttu-id="3280a-125">如果找不到与用户的 ICE Chat ImId 对应的有效 Microsoft 365 用户帐户，连接器将使用聊天项目的 *SenderEmail* 和 *RecipientEmail* 属性将项目导入聊天参与者的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3280a-125">If it doesn't find a valid Microsoft 365 user account that corresponds to a user's ICE Chat ImId, the connector will use the *SenderEmail* and *RecipientEmail* properties of the chat item to import the item to the mailboxes of the chat participants.</span></span> <span data-ttu-id="3280a-126">如果连接器在自定义映射文件或 *SenderEmail* Microsoft 365 *RecipientEmail* 属性中找不到有效的邮件用户，则不导入该项目。</span><span class="sxs-lookup"><span data-stu-id="3280a-126">If the connector doesn't find a valid Microsoft 365 user in either the custom-mapping file or the *SenderEmail* and *RecipientEmail* properties, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="3280a-127">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="3280a-127">Before you set up a connector</span></span>

<span data-ttu-id="3280a-128">存档 ICE Chat 数据所需的一些实现步骤位于 Microsoft 365且必须先完成，然后才能在合规性中心创建连接器。</span><span class="sxs-lookup"><span data-stu-id="3280a-128">Some of the implementation steps required to archive ICE Chat data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="3280a-129">ICE 聊天会向客户收取外部合规性的费用。</span><span class="sxs-lookup"><span data-stu-id="3280a-129">ICE Chat charges their customers a fee for external compliance.</span></span> <span data-ttu-id="3280a-130">贵组织应联系 ICE Chat 销售组，以讨论和签署 ICE Chat 数据服务协议（可在 上获取 [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) ）。</span><span class="sxs-lookup"><span data-stu-id="3280a-130">Your organization should contact the ICE Chat sales group to discuss, and to sign the ICE Chat data services agreement, which you can obtain at [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf).</span></span> <span data-ttu-id="3280a-131">本协议在 ICE Chat 和您的组织之间签署，不涉及 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="3280a-131">This agreement is between ICE Chat and your organization and does not involve Microsoft.</span></span> <span data-ttu-id="3280a-132">在步骤 2 中设置 ICE 聊天 SFTP 站点后，ICE Chat 直接向您的组织提供 FTP 凭据。</span><span class="sxs-lookup"><span data-stu-id="3280a-132">After you set up an ICE Chat SFTP site in Step 2, ICE Chat provides the FTP credentials directly to your organization.</span></span> <span data-ttu-id="3280a-133">然后，你在步骤 3 中设置连接器时会向 Microsoft 提供这些凭据。</span><span class="sxs-lookup"><span data-stu-id="3280a-133">Then you who would provide those credentials to Microsoft when setting up the connector in Step 3.</span></span>

- <span data-ttu-id="3280a-134">在步骤 3 中创建连接器之前，必须设置 ICE 聊天 SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="3280a-134">You must set up an ICE Chat SFTP site before creating the connector in Step 3.</span></span> <span data-ttu-id="3280a-135">使用 ICE 聊天设置 SFTP 站点后，ICE 聊天的数据将每天上载到 SFTP 网站。</span><span class="sxs-lookup"><span data-stu-id="3280a-135">After working with ICE Chat to set up the SFTP site, data from ICE Chat is uploaded to the SFTP site every day.</span></span> <span data-ttu-id="3280a-136">在步骤 3 创建的连接器连接到此 SFTP 站点，将聊天数据Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="3280a-136">The connector you create in Step 3 connects to this SFTP site and transfers the chat data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="3280a-137">SFTP 还加密传输过程中发送到邮箱的 ICE 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="3280a-137">SFTP also encrypts the ICE Chat data that's sent to mailboxes during the transfer process.</span></span>

- <span data-ttu-id="3280a-138">若要设置 ICE 聊天连接器，您必须使用密钥和密钥密码实现良好隐私 (PGP) 和 SSH (安全) 。</span><span class="sxs-lookup"><span data-stu-id="3280a-138">To set up an ICE Chat connector, you have to use keys and key passphrases for Pretty Good Privacy (PGP) and Secure Shell (SSH).</span></span> <span data-ttu-id="3280a-139">这些密钥用于配置 ICE Chat SFTP 站点，连接器使用这些密钥连接到 ICE Chat SFTP 站点以将数据导入Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3280a-139">These keys are used to configure the ICE Chat SFTP site and used by the connector to connect to the ICE Chat SFTP site to import data to Microsoft 365.</span></span> <span data-ttu-id="3280a-140">PGP 密钥用于配置从 ICE 聊天 SFTP 站点传输到数据组的数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3280a-140">The PGP key is used to configure the encryption of data that's transferred from the ICE Chat SFTP site to Microsoft 365.</span></span> <span data-ttu-id="3280a-141">SSH 密钥用于配置安全命令行管理程序，以在连接器连接到 ICE Chat SFTP 站点时启用安全远程登录。</span><span class="sxs-lookup"><span data-stu-id="3280a-141">The SSH key is used to configure secure shell to enable a secure remote login when the connector connects to the ICE Chat SFTP site.</span></span>

  <span data-ttu-id="3280a-142">设置连接器时，可以选择使用 Microsoft 提供的公钥和密钥密码，或者可以使用自己的私钥和密码。</span><span class="sxs-lookup"><span data-stu-id="3280a-142">When setting up a connector, you have the option to use public keys and key passphrases provided by Microsoft or you can use your own private keys and passphrases.</span></span> <span data-ttu-id="3280a-143">建议使用 Microsoft 提供的公钥。</span><span class="sxs-lookup"><span data-stu-id="3280a-143">We recommend that you use the public keys provided by Microsoft.</span></span> <span data-ttu-id="3280a-144">但是，如果你的组织已使用私钥配置 ICE 聊天 SFTP 站点，那么你可以使用相同的私钥创建连接器。</span><span class="sxs-lookup"><span data-stu-id="3280a-144">However, if your organization has already configured an ICE Chat SFTP site using private keys, then you can create a connector using these same private keys.</span></span>

- <span data-ttu-id="3280a-145">ICE 聊天连接器在一天中总共可以导入 200，000 个项目。</span><span class="sxs-lookup"><span data-stu-id="3280a-145">The ICE Chat connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="3280a-146">如果 SFTP 网站上有 200，000 多个项目，则这些项均不会导入Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3280a-146">If there are more than 200,000 items on the SFTP site, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="3280a-147">必须在步骤 3 (中为在步骤 3 中创建 ICE 聊天连接器且在步骤 1) 中下载公钥和 IP 地址的管理员分配邮箱导入导出Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="3280a-147">The admin who creates the ICE Chat connector in Step 3 (and who downloads the public keys and IP address in Step 1) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="3280a-148">若要在合规性中心的"数据连接器"页上添加 **连接器，Microsoft 365** 此角色。</span><span class="sxs-lookup"><span data-stu-id="3280a-148">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3280a-149">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="3280a-149">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="3280a-150">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="3280a-150">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3280a-151">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="3280a-151">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="3280a-152">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="3280a-152">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="set-up-a-connector-using-public-keys"></a><span data-ttu-id="3280a-153">使用公钥设置连接器</span><span class="sxs-lookup"><span data-stu-id="3280a-153">Set up a connector using public keys</span></span>

<span data-ttu-id="3280a-154">本节中的步骤将展示如何使用 SSH 中"良好隐私" (PGP) 和安全外壳 (公钥设置 ICE 聊天) 。</span><span class="sxs-lookup"><span data-stu-id="3280a-154">The steps in this section show you how to set up an ICE Chat connector using the public keys for Pretty Good Privacy (PGP) and Secure Shell (SSH).</span></span>

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a><span data-ttu-id="3280a-155">步骤 1：获取 PGP 和 SSH 公钥</span><span class="sxs-lookup"><span data-stu-id="3280a-155">Step 1: Obtain PGP and SSH public keys</span></span>

<span data-ttu-id="3280a-156">第一步是获取 SSH 中"良好隐私" (安全) 安全 (密钥) 。</span><span class="sxs-lookup"><span data-stu-id="3280a-156">The first step is to obtain a copy of the public keys for Pretty Good Privacy (PGP) and Secure Shell (SSH).</span></span> <span data-ttu-id="3280a-157">可以使用步骤 2 中的这些键配置 ICE Chat SFTP 站点，以允许步骤 3) 创建的连接器 (连接到 SFTP 站点，将 ICE 聊天数据传输给 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="3280a-157">You use these keys in Step 2 to configure the ICE Chat SFTP site to allow the connector (that you create in Step 3) to connect to the SFTP site and transfer the ICE Chat data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="3280a-158">在此步骤中，您还将获得一个 IP 地址，该地址在配置 ICE Chat SFTP 站点时使用。</span><span class="sxs-lookup"><span data-stu-id="3280a-158">You will also obtain an IP address in this step, which you use when configuring the ICE Chat SFTP site.</span></span>

1. <span data-ttu-id="3280a-159">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="3280a-159">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3280a-160">在"**数据连接器"页上** 的 **"ICE 聊天"** 下，单击"查看 **"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-160">On the **Data connectors** page under **ICE Chat**, click **View**.</span></span>

3. <span data-ttu-id="3280a-161">在 **"ICE 聊天"** 页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-161">On the **ICE Chat** page, click **Add connector**.</span></span>

4. <span data-ttu-id="3280a-162">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-162">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="3280a-163">在"**添加内容源的** 凭据"页上，单击"我想要使用 Microsoft 提供的 PGP 和 **SSH 公钥"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-163">On the **Add credentials for content source** page, click **I want to use PGP and SSH public keys provided by Microsoft**.</span></span>

   ![选择使用公钥的选项](../media/ICEChatPublicKeysOption.png)

6. <span data-ttu-id="3280a-165">在步骤 1 下，单击"下载 **SSH 密钥**、 **下载 PGP** 密钥"和" **下载 IP** 地址"链接，将每个文件的副本保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="3280a-165">Under step 1, click the **Download SSH key**, **Download PGP key**, and **Download IP address** links to save a copy of each file to your local computer.</span></span>

   ![用于下载公钥和 IP 地址的链接](../media/ICEChatPublicKeyDownloadLinks.png)

   <span data-ttu-id="3280a-167">这些文件包含用于配置步骤 2 中的 ICE 聊天 SFTP 站点的以下项目：</span><span class="sxs-lookup"><span data-stu-id="3280a-167">These files contain the following items that are used to configure the ICE Chat SFTP site in Step 2:</span></span>

   - <span data-ttu-id="3280a-168">PGP 公钥：此密钥用于配置从 ICE 聊天 SFTP 站点传输到数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3280a-168">PGP public key: This key is used to configure the encryption of data that's transferred from the ICE Chat SFTP site to Microsoft 365.</span></span>

   - <span data-ttu-id="3280a-169">SSH 公钥：此密钥用于配置安全 SSH，以在连接器连接到 ICE 聊天 SFTP 站点时启用安全远程登录。</span><span class="sxs-lookup"><span data-stu-id="3280a-169">SSH public key: This key is used to configure Secure SSH to enable a secure remote login when the connector connects to the ICE Chat SFTP site.</span></span>

   - <span data-ttu-id="3280a-170">IP 地址：ICE 聊天 SFTP 站点配置为仅接受来自此 IP 地址的连接请求，由你在步骤 3 创建的 ICE 聊天连接器使用。</span><span class="sxs-lookup"><span data-stu-id="3280a-170">IP address: The ICE Chat SFTP site is configured to accept a connection request only from this IP address, which is used by the ICE Chat connector that you create in Step 3.</span></span>

7. <span data-ttu-id="3280a-171">单击 **"** 取消"关闭向导。</span><span class="sxs-lookup"><span data-stu-id="3280a-171">Click **Cancel** to close the wizard.</span></span> <span data-ttu-id="3280a-172">在步骤 3 中返回到此向导以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="3280a-172">You come back to this wizard in Step 3 to create the connector.</span></span>

### <a name="step-2-configure-the-ice-chat-sftp-site"></a><span data-ttu-id="3280a-173">步骤 2：配置 ICE 聊天 SFTP 站点</span><span class="sxs-lookup"><span data-stu-id="3280a-173">Step 2: Configure the ICE Chat SFTP site</span></span>

<span data-ttu-id="3280a-174">下一步是使用在步骤 1 中获得的 PGP 和 SSH 公钥和 IP 地址为 ICE Chat SFTP 网站配置 PGP 加密和 SSH 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3280a-174">The next step is to use the PGP and SSH public keys and the IP address that you obtained in Step 1 to configure PGP encryption and SSH authentication for the ICE Chat SFTP site.</span></span> <span data-ttu-id="3280a-175">这样，你在步骤 3 创建的 ICE 聊天连接器可以连接到 ICE 聊天 SFTP 站点，将 ICE 聊天数据传输Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3280a-175">This lets the ICE Chat connector that you create in Step 3 connect to the ICE Chat SFTP site and transfer ICE Chat data to Microsoft 365.</span></span> <span data-ttu-id="3280a-176">你需要与 ICE Chat 客户支持一起设置 ICE 聊天 SFTP 网站。</span><span class="sxs-lookup"><span data-stu-id="3280a-176">You need to work with ICE Chat customer support to set up your ICE Chat SFTP site.</span></span>

### <a name="step-3-create-an-ice-chat-connector"></a><span data-ttu-id="3280a-177">步骤 3：创建 ICE 聊天连接器</span><span class="sxs-lookup"><span data-stu-id="3280a-177">Step 3: Create an ICE Chat connector</span></span>

<span data-ttu-id="3280a-178">最后一步是在合规性中心内Microsoft 365 ICE 聊天连接器。</span><span class="sxs-lookup"><span data-stu-id="3280a-178">The last step is to create an ICE Chat connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3280a-179">连接器使用您提供的信息连接到 ICE Chat SFTP 网站，将聊天消息传输至 MICROSOFT 365 中的相应用户邮箱框。</span><span class="sxs-lookup"><span data-stu-id="3280a-179">The connector uses the information you provide to connect to the ICE Chat SFTP site and transfer chat messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="3280a-180">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="3280a-180">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3280a-181">在"**数据连接器"页上** 的 **"ICE 聊天"** 下，单击"查看 **"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-181">On the **Data connectors** page under **ICE Chat**, click **View**.</span></span>

3. <span data-ttu-id="3280a-182">在 **"ICE 聊天"** 页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-182">On the **ICE Chat** page, click **Add connector**.</span></span>

4. <span data-ttu-id="3280a-183">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-183">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="3280a-184">在"**添加内容源的** 凭据"页上，单击 **"我想要使用 PGP 和 SSH 公钥"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-184">On the **Add credentials for content source** page, click **I want to use PGP and SSH public keys**.</span></span>

6. <span data-ttu-id="3280a-185">在"步骤 3"下，在下列框中输入所需信息，然后单击"验证 **连接"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-185">Under Step 3, enter the required information in the following boxes and then click **Validate connection**.</span></span>

   - <span data-ttu-id="3280a-186">**公司代码：** 组织的 ID，用作 ICE 聊天 SFTP 网站的用户名。</span><span class="sxs-lookup"><span data-stu-id="3280a-186">**Firm code:** The ID for your organization, which is used as the username for the ICE Chat SFTP site.</span></span>

   - <span data-ttu-id="3280a-187">**密码：** ICE 聊天 SFTP 站点的密码。</span><span class="sxs-lookup"><span data-stu-id="3280a-187">**Password:** The password for your ICE Chat SFTP site.</span></span>

   - <span data-ttu-id="3280a-188">**SFTP URL：** ICE Chat SFTP 网站的 URL (例如 `sftp.theice.com` ，) 。</span><span class="sxs-lookup"><span data-stu-id="3280a-188">**SFTP URL:** The URL for the ICE Chat SFTP site (for example, `sftp.theice.com`).</span></span> <span data-ttu-id="3280a-189">您还可以将 IP 地址用于此值。</span><span class="sxs-lookup"><span data-stu-id="3280a-189">You can also use an IP address for this value.</span></span>

   - <span data-ttu-id="3280a-190">**SFTP 端口：** ICE 聊天 SFTP 站点的端口号。</span><span class="sxs-lookup"><span data-stu-id="3280a-190">**SFTP port:** The port number for the ICE Chat SFTP site.</span></span> <span data-ttu-id="3280a-191">连接器使用此端口连接到 SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="3280a-191">The connector uses this port to connect to the SFTP site.</span></span>

7. <span data-ttu-id="3280a-192">成功验证连接后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-192">After the connection is successfully validated, click **Next**.</span></span>

8. <span data-ttu-id="3280a-193">在"**将外部用户映射到 Microsoft 365"** 页上，启用自动用户映射并按需要提供自定义用户映射。</span><span class="sxs-lookup"><span data-stu-id="3280a-193">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping and provide custom user mapping as required.</span></span> <span data-ttu-id="3280a-194">可以在此页面上下载用户映射 CSV 文件的副本。</span><span class="sxs-lookup"><span data-stu-id="3280a-194">You can download a copy of the user-mapping CSV file on this page.</span></span> <span data-ttu-id="3280a-195">您可以将用户映射添加到文件，然后上载它。</span><span class="sxs-lookup"><span data-stu-id="3280a-195">You can add the user mappings to the file and then upload it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3280a-196">如前所述，自定义映射文件 CSV 文件包含 ICE Chat imid 和Microsoft 365每个用户的邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="3280a-196">As previously explained, custom mapping file CSV file contains the ICE Chat imid and corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="3280a-197">如果启用自动用户映射并提供自定义映射，连接器将首先查看每个聊天项的自定义映射文件。</span><span class="sxs-lookup"><span data-stu-id="3280a-197">If you enable automatic user mapping and provide a custom mapping, for every chat item, the connector will first look at custom mapping file.</span></span> <span data-ttu-id="3280a-198">如果找不到与用户的 ICE Chat imid 对应的有效 Microsoft 365 用户，连接器将为聊天项目的 *SenderEmail* 和 *RecipientEmail* 属性中指定的用户将项目导入邮箱。</span><span class="sxs-lookup"><span data-stu-id="3280a-198">If it doesn't find a valid Microsoft 365 user that corresponds to a user's ICE Chat imid, the connector will import the item to the mailboxes for the users specified in the *SenderEmail* and *RecipientEmail* properties of the chat item.</span></span> <span data-ttu-id="3280a-199">如果连接器通过自动或自定义用户映射Microsoft 365有效的用户映射，则不导入该项目。</span><span class="sxs-lookup"><span data-stu-id="3280a-199">If the connector doesn't find a valid Microsoft 365 user by either automatic or custom user mapping, the item won't be imported.</span></span>

9. <span data-ttu-id="3280a-200">单击 **"下** 一步"，查看设置，然后单击" **完成** "以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="3280a-200">Click **Next**, review your settings, and then click **Finish** to create the connector.</span></span>

10. <span data-ttu-id="3280a-201">转到" **数据连接器"** 页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="3280a-201">Go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="set-up-a-connector-using-private-keys"></a><span data-ttu-id="3280a-202">使用私钥设置连接器</span><span class="sxs-lookup"><span data-stu-id="3280a-202">Set up a connector using private keys</span></span>

<span data-ttu-id="3280a-203">本部分中的步骤将展示如何使用 PGP 和 SSH 私钥设置 ICE 聊天连接器。</span><span class="sxs-lookup"><span data-stu-id="3280a-203">The steps in this section show you how to set up an ICE Chat connector using PGP and SSH private keys.</span></span> <span data-ttu-id="3280a-204">此连接器设置选项适用于已使用私钥配置 ICE 聊天 SFTP 站点的组织。</span><span class="sxs-lookup"><span data-stu-id="3280a-204">This connector setup option is intended for organizations that have already configured an ICE Chat SFTP site using private keys.</span></span>

### <a name="step-1-obtain-an-ip-address-to-configure-the-ice-chat-sftp-site"></a><span data-ttu-id="3280a-205">步骤 1：获取 IP 地址以配置 ICE Chat SFTP 站点</span><span class="sxs-lookup"><span data-stu-id="3280a-205">Step 1: Obtain an IP address to configure the ICE Chat SFTP site</span></span>

<span data-ttu-id="3280a-206">如果你的组织已使用 PGP 和 SSH 私钥来设置 ICE Chat SFTP 站点，则你必须获取 IP 地址，并为 ICE Chat 客户支持提供该地址。</span><span class="sxs-lookup"><span data-stu-id="3280a-206">If your organization has used PGP and SSH private keys to set up an ICE Chat SFTP site, then you have to obtain an IP address and provide it to ICE Chat customer support.</span></span> <span data-ttu-id="3280a-207">ICE 聊天 SFTP 站点必须配置为接受来自此 IP 地址的连接请求。</span><span class="sxs-lookup"><span data-stu-id="3280a-207">The ICE Chat SFTP site must be configured to accept  connection requests from this IP address.</span></span> <span data-ttu-id="3280a-208">ICE 聊天连接器使用同一 IP 地址连接到 SFTP 站点，将 ICE 聊天数据传输Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3280a-208">The same IP address is used by the ICE Chat connector to connect to the SFTP site and transfer ICE Chat data to Microsoft 365.</span></span>

<span data-ttu-id="3280a-209">若要获取 IP 地址：：</span><span class="sxs-lookup"><span data-stu-id="3280a-209">To obtain the IP address:</span></span>

1. <span data-ttu-id="3280a-210">转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="3280a-210">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3280a-211">在"**数据连接器"页上** 的 **"ICE 聊天"** 下，单击"查看 **"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-211">On the **Data connectors** page under **ICE Chat**, click **View**.</span></span>

3. <span data-ttu-id="3280a-212">在 **ICE 聊天产品** 说明页上，单击" **添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="3280a-212">On the **ICE Chat** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="3280a-213">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-213">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="3280a-214">在"**添加内容源的** 凭据"页上，单击 **"我想要使用 PGP 和 SSH 私钥"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-214">On the **Add credentials for content source** page, click **I want to use PGP and SSH private keys**.</span></span>

   ![选择使用私钥的选项](../media/ICEChatPrivateKeysOption.png)

6. <span data-ttu-id="3280a-216">在步骤 1 下， **单击"下载 IP** 地址"以将 IP 地址文件的副本保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="3280a-216">Under step 1, click **Download IP address** to save a copy of the IP address file to your local computer.</span></span>

   ![下载 IP 地址](../media/ICEChatConnectorIPAddress.png)

7. <span data-ttu-id="3280a-218">单击 **"** 取消"关闭向导。</span><span class="sxs-lookup"><span data-stu-id="3280a-218">Click **Cancel** to close the wizard.</span></span> <span data-ttu-id="3280a-219">您将在步骤 2 中返回到此向导以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="3280a-219">You come back to this wizard in Step 2 to create the connector.</span></span>

<span data-ttu-id="3280a-220">你需要与 ICE Chat 客户支持合作，将 ICE 聊天 SFTP 站点配置为接受来自此 IP 地址的连接请求。</span><span class="sxs-lookup"><span data-stu-id="3280a-220">You need to work with ICE Chat customer support to configure your ICE Chat SFTP site to accept connection requests from this IP address.</span></span>

### <a name="step-2-create-an-ice-chat-connector"></a><span data-ttu-id="3280a-221">步骤 2：创建 ICE 聊天连接器</span><span class="sxs-lookup"><span data-stu-id="3280a-221">Step 2: Create an ICE Chat connector</span></span>

<span data-ttu-id="3280a-222">配置 ICE 聊天 SFTP 站点后，下一步是在合规性中心内Microsoft 365 ICE 聊天连接器。</span><span class="sxs-lookup"><span data-stu-id="3280a-222">After your ICE Chat SFTP site is configured, the next step is to create an ICE Chat connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3280a-223">连接器使用您提供的信息连接到 ICE Chat SFTP 站点，将电子邮件传输至 MICROSOFT 365 中的相应用户邮箱框。</span><span class="sxs-lookup"><span data-stu-id="3280a-223">The connector uses the information you provide to connect to the ICE Chat SFTP site and transfer email messages to the corresponding user mailbox boxes in Microsoft 365.</span></span> <span data-ttu-id="3280a-224">若要完成此步骤，请确保具有用于设置 ICE 聊天 SFTP 网站的相同私钥和密钥密码的副本。</span><span class="sxs-lookup"><span data-stu-id="3280a-224">To complete this step, be sure to have copies of the same private keys and key passphrases that you used to set up your ICE Chat SFTP site.</span></span>

1. <span data-ttu-id="3280a-225">转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="3280a-225">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3280a-226">在"**数据连接器"页上** 的 **"ICE 聊天"** 下，单击"查看 **"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-226">On the **Data connectors** page under **ICE Chat**, click **View**.</span></span>

3. <span data-ttu-id="3280a-227">在 **ICE 聊天产品** 说明页上，单击" **添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="3280a-227">On the **ICE Chat** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="3280a-228">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-228">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="3280a-229">在"**添加内容源的** 凭据"页上，单击 **"我想要使用 PGP 和 SSH 私钥"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-229">On the **Add credentials for content source** page, click **I want to use PGP and SSH private keys**.</span></span>

6. <span data-ttu-id="3280a-230">在"步骤 3"下，在下列框中输入所需信息，然后单击"验证 **连接"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-230">Under Step 3, enter the required information in the following boxes and then click **Validate connection**.</span></span>

      - <span data-ttu-id="3280a-231">**名称：** 连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="3280a-231">**Name:** The name for the connector.</span></span> <span data-ttu-id="3280a-232">它必须在组织中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3280a-232">It must be unique in your organization.</span></span>

      - <span data-ttu-id="3280a-233">**公司代码：** 用作 ICE 聊天 SFTP 网站的用户名的组织 ID。</span><span class="sxs-lookup"><span data-stu-id="3280a-233">**Firm code:** The ID for your organization that is used as the username for the ICE Chat SFTP site.</span></span>

      - <span data-ttu-id="3280a-234">**密码：** 组织的 ICE 聊天 SFTP 站点的密码。</span><span class="sxs-lookup"><span data-stu-id="3280a-234">**Password:** The password for your organization's ICE Chat SFTP site.</span></span>

      - <span data-ttu-id="3280a-235">**SFTP URL：** ICE Chat SFTP 网站的 URL (例如 `sftp.theice.com` ，) 。</span><span class="sxs-lookup"><span data-stu-id="3280a-235">**SFTP URL:** The URL for the ICE Chat SFTP site (for example, `sftp.theice.com`).</span></span> <span data-ttu-id="3280a-236">您还可以将 IP 地址用于此值。</span><span class="sxs-lookup"><span data-stu-id="3280a-236">You can also use an IP address for this value.</span></span>

      - <span data-ttu-id="3280a-237">**SFTP 端口：** ICE 聊天 SFTP 站点的端口号。</span><span class="sxs-lookup"><span data-stu-id="3280a-237">**SFTP port:** The port number for the ICE Chat SFTP site.</span></span> <span data-ttu-id="3280a-238">连接器使用此端口连接到 SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="3280a-238">The connector uses this port to connect to the SFTP site.</span></span>

      - <span data-ttu-id="3280a-239">**PGP 私钥：** ICE 聊天 SFTP 站点的 PGP 私钥。</span><span class="sxs-lookup"><span data-stu-id="3280a-239">**PGP private key:** The PGP private key for the ICE Chat SFTP site.</span></span> <span data-ttu-id="3280a-240">请务必包括整个私钥值，包括键块的开头和结尾行。</span><span class="sxs-lookup"><span data-stu-id="3280a-240">Be sure to include the entire private key value, including the beginning and ending lines of the key block.</span></span>

      - <span data-ttu-id="3280a-241">**PGP 键密码：** PGP 私钥的通行短语。</span><span class="sxs-lookup"><span data-stu-id="3280a-241">**PGP key passphrase:** The passphrase for the PGP private key.</span></span>

      - <span data-ttu-id="3280a-242">**SSH 私钥：** ICE 聊天 SFTP 站点的 SSH 私钥。</span><span class="sxs-lookup"><span data-stu-id="3280a-242">**SSH private key:** The SSH private key for the ICE Chat SFTP site.</span></span> <span data-ttu-id="3280a-243">请务必包括整个私钥值，包括键块的开头和结尾行。</span><span class="sxs-lookup"><span data-stu-id="3280a-243">Be sure to include the entire private key value, including the beginning and ending lines of the key block.</span></span>

      - <span data-ttu-id="3280a-244">**SSH 密钥密码：** SSH 私钥的通行短语。</span><span class="sxs-lookup"><span data-stu-id="3280a-244">**SSH key passphrase:** The passphrase for the SSH private key.</span></span>

7. <span data-ttu-id="3280a-245">成功验证连接后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="3280a-245">After the connection is successfully validated, click **Next**.</span></span>

8. <span data-ttu-id="3280a-246">在"**将 ICE 聊天用户映射到Microsoft 365"页上**，启用自动用户映射并按需要提供自定义用户映射。</span><span class="sxs-lookup"><span data-stu-id="3280a-246">On the **Map ICE Chat users to Microsoft 365 users** page, enable automatic user mapping and provide custom user mapping as required.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3280a-247">如前所述，自定义映射文件 CSV 文件包含 ICE Chat imid 和Microsoft 365每个用户的邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="3280a-247">As previously explained, custom mapping file CSV file contains the ICE Chat imid and corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="3280a-248">如果启用自动用户映射并提供自定义映射，连接器将首先查看每个聊天项的自定义映射文件。</span><span class="sxs-lookup"><span data-stu-id="3280a-248">If you enable automatic user mapping and provide a custom mapping, for every chat item, the connector will first look at custom mapping file.</span></span> <span data-ttu-id="3280a-249">如果找不到与用户的 ICE Chat imid 对应的有效 Microsoft 365 用户，连接器将为聊天项目的 *SenderEmail* 和 *RecipientEmail* 属性中指定的用户将项目导入邮箱。</span><span class="sxs-lookup"><span data-stu-id="3280a-249">If it doesn't find a valid Microsoft 365 user that corresponds to a user's ICE Chat imid, the connector will import the item to the mailboxes for the users specified in the *SenderEmail* and *RecipientEmail* properties of the chat item.</span></span> <span data-ttu-id="3280a-250">如果连接器通过自动或自定义用户映射Microsoft 365有效的用户映射，则不导入该项目。</span><span class="sxs-lookup"><span data-stu-id="3280a-250">If the connector doesn't find a valid Microsoft 365 user by either automatic or custom user mapping, the item won't be imported.</span></span>

9. <span data-ttu-id="3280a-251">单击 **"下** 一步"，查看设置，然后单击" **完成** "以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="3280a-251">Click **Next**, review your settings, and then click **Finish** to create the connector.</span></span>

10. <span data-ttu-id="3280a-252">转到" **数据连接器"** 页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="3280a-252">Go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span> <span data-ttu-id="3280a-253">单击连接器可显示包含连接器相关信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="3280a-253">Click the connector to display the flyout page, which contains information about the connector.</span></span>
