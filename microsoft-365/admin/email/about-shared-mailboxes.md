---
title: 关于共享邮箱
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 当多个用户需要访问同一个邮箱时，使用共享邮箱。 在创建共享邮箱之前，了解您需要了解的内容。
ms.openlocfilehash: f5d46af5abdd528ce3db817dbabce015ed5abade
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094717"
---
# <a name="about-shared-mailboxes"></a><span data-ttu-id="cf883-104">关于共享邮箱</span><span class="sxs-lookup"><span data-stu-id="cf883-104">About shared mailboxes</span></span>

<span data-ttu-id="cf883-105">当多个用户需要访问同一邮箱（例如公司信息或支持电子邮件地址、接待台或其他可能由多个用户共享的其他功能）时，将使用共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="cf883-105">Shared mailboxes are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="cf883-106">如果管理员已授予用户执行该操作的权限，具有组邮箱权限的用户可以作为或代表邮箱电子邮件地址发送。</span><span class="sxs-lookup"><span data-stu-id="cf883-106">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="cf883-107">这对帮助和支持邮箱尤其有用，因为用户可从 "Contoso 支持" 或 "构建 A 接待台" 发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cf883-107">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="cf883-108">创建 [共享邮箱之前](create-a-shared-mailbox.md)，应了解以下一些信息：</span><span class="sxs-lookup"><span data-stu-id="cf883-108">Before you [create a shared mailbox](create-a-shared-mailbox.md), here are some things you should know:</span></span>

- <span data-ttu-id="cf883-109">**许可证：** 共享邮箱可以存储多达 50GB 的数据，而无需为其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="cf883-109">**Licenses:** Your shared mailbox can store up to 50GB of data without you assigning a license to it.</span></span> <span data-ttu-id="cf883-110">在此之后，需要向邮箱分配许可证才能存储更多的数据。</span><span class="sxs-lookup"><span data-stu-id="cf883-110">After that, you need to assign a license to the mailbox to store more data.</span></span> <span data-ttu-id="cf883-111">有关共享邮箱许可的更多详细信息，请参阅 Exchange [Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)。</span><span class="sxs-lookup"><span data-stu-id="cf883-111">For more details on shared mailbox licensing, please see [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits).</span></span> <span data-ttu-id="cf883-112">共享邮箱达到存储空间时，短时间内还可以收到电子邮件，但不能发送新的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cf883-112">When a shared mailbox reaches the storage limit, you'll be able to receive email for a while, but you won't be able to send new email.</span></span> <span data-ttu-id="cf883-113">然后，它会停止接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cf883-113">Then, after that, it will stop receiving email.</span></span> <span data-ttu-id="cf883-114">邮箱的发件人将收到未送达回执。</span><span class="sxs-lookup"><span data-stu-id="cf883-114">Senders to the mailbox will get a non-delivery receipt.</span></span>

- <span data-ttu-id="cf883-115">**用户权限：** 您需要向用户授予使用 (邮箱) 权限。</span><span class="sxs-lookup"><span data-stu-id="cf883-115">**User permissions:** You need to give users permissions (membership) to use the shared mailbox.</span></span> <span data-ttu-id="cf883-116">只有组织内部人员才能使用共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="cf883-116">Only people inside your organization can use a shared mailbox.</span></span>

- <span data-ttu-id="cf883-117">**外部用户：** 你无法向企业外部人员授予 (，例如具有 Gmail 帐户) 访问共享邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="cf883-117">**External users:** You can't give people outside your business (such as people with a Gmail account) access to your shared mailbox.</span></span> <span data-ttu-id="cf883-118">如果你希望这么做，请考虑改为创建 Outlook 组。</span><span class="sxs-lookup"><span data-stu-id="cf883-118">If you want to do this, consider creating a group for Outlook instead.</span></span> <span data-ttu-id="cf883-119">若要了解更多信息，请参阅在管理中心创建 [Microsoft 365 组](../create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="cf883-119">To learn more, see [Create a Microsoft 365 group in the admin center](../create-groups/create-groups.md).</span></span>

- <span data-ttu-id="cf883-120">**与 Outlook 一同使用：** 除了从浏览器使用 Outlook 网页版访问共享邮箱外，您还可以使用 Outlook for iOS 应用或 Outlook for Android 应用。</span><span class="sxs-lookup"><span data-stu-id="cf883-120">**Use with Outlook:** In addition to using Outlook on the web from your browser to access shared mailboxes, you can also use the Outlook for iOS app or the Outlook for Android app.</span></span> <span data-ttu-id="cf883-121">若要了解更多信息，请参阅["将共享邮箱添加到 Outlook Mobile"。](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f)</span><span class="sxs-lookup"><span data-stu-id="cf883-121">To learn more, see [Add a shared mailbox to Outlook mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f).</span></span> <span data-ttu-id="cf883-122">另一个选项是创建共享邮箱的组。</span><span class="sxs-lookup"><span data-stu-id="cf883-122">Another option is to create a group for your shared mailbox.</span></span> <span data-ttu-id="cf883-123">若要了解详细信息，请参阅[比较组](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="cf883-123">To learn more, see [Compare Groups](../create-groups/compare-groups.md).</span></span>

- <span data-ttu-id="cf883-124">**加密：** 无法加密从共享邮箱发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cf883-124">**Encryption:** You can't encrypt email sent from a shared mailbox.</span></span> <span data-ttu-id="cf883-125">这是因为共享邮箱没有其自己的安全上下文 (用户名/密码) 因此无法为其分配密钥。</span><span class="sxs-lookup"><span data-stu-id="cf883-125">This is because a shared mailbox does not have its own security context (username/password) so it cannot be assigned a key.</span></span> <span data-ttu-id="cf883-126">如果多个用户是成员，并且他们发送/接收使用自己的密钥加密的电子邮件，则其他成员可能无法阅读电子邮件，其他人可能无法阅读，具体取决于使用哪个公钥加密了电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cf883-126">If more than one person is a member, and they send/receive emails they encrypted with their own keys, other members might be able to read the email and others might not, depending which public key the email was encrypted with.</span></span>

- <span data-ttu-id="cf883-127">**邮箱转换：** 可以将用户邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="cf883-127">**Mailbox conversion:** You can convert user mailboxes to shared mailboxes.</span></span> <span data-ttu-id="cf883-128">请参阅[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="cf883-128">See [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span>

- <span data-ttu-id="cf883-129">**管理员角色：** 具有全局管理员或 Exchange 管理员角色的用户可以创建共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="cf883-129">**Admin roles:** Users with global admin or Exchange admin roles can create shared mailboxes.</span></span>

- <span data-ttu-id="cf883-130">**订阅要求：** 若要创建共享邮箱，需要订阅 Microsoft 365 商业版计划，该计划包括 Exchange Online (电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="cf883-130">**Subscription requirements:** To create a shared mailbox, you need to subscribe to a Microsoft 365 for business plan that includes email (the Exchange Online service).</span></span> <span data-ttu-id="cf883-131">Microsoft 365 商业应用版订阅不包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cf883-131">The Microsoft 365 Apps for business subscription doesn't include email.</span></span> <span data-ttu-id="cf883-132">Microsoft 365 商业标准版包含电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cf883-132">Microsoft 365 Business Standard does include email.</span></span>

- <span data-ttu-id="cf883-133">**登录：** 共享邮箱不用于通过关联的用户帐户直接登录。</span><span class="sxs-lookup"><span data-stu-id="cf883-133">**Signing in:** A shared mailbox is not intended for direct sign-in by its associated user account.</span></span> <span data-ttu-id="cf883-134">应始终阻止共享邮箱帐户的登录，并阻止登录。</span><span class="sxs-lookup"><span data-stu-id="cf883-134">You should always block sign-in for the shared mailbox account and keep it blocked.</span></span>

- <span data-ttu-id="cf883-135">**用户过多：** 当同时访问共享邮箱的指定用户过多时，他们可能间歇性地无法连接到此邮箱。</span><span class="sxs-lookup"><span data-stu-id="cf883-135">**Too many users:** When there are too many designated users concurrently accessing a shared mailbox, they may intermittently fail to connect to this mailbox.</span></span> <span data-ttu-id="cf883-136">在这种情况下，你可以考虑减少用户数或使用不同的工作负载，如 Microsoft 365 组或公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="cf883-136">In this case, you can consider reducing the number of the users or using a different workload, such a Microsoft 365 group or Public folder.</span></span>

- <span data-ttu-id="cf883-137">**邮件删除：** 遗憾的是，无法阻止用户删除共享邮箱中的邮件。</span><span class="sxs-lookup"><span data-stu-id="cf883-137">**Message deletion:** Unfortunately, you can't prevent people from deleting messages in a shared mailbox.</span></span> <span data-ttu-id="cf883-138">唯一的方法就是创建 Microsoft 365 组，而不是共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="cf883-138">The only way around this is to create a Microsoft 365 group instead of a shared mailbox.</span></span> <span data-ttu-id="cf883-139">Outlook 中的组与共享邮箱类似。</span><span class="sxs-lookup"><span data-stu-id="cf883-139">A group in Outlook is like a shared mailbox.</span></span> <span data-ttu-id="cf883-140">有关这两个组的比较，请参阅["比较组"。](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="cf883-140">For a comparison of the two, see [Compare groups](../create-groups/compare-groups.md).</span></span> <span data-ttu-id="cf883-141">若要详细了解组，请参阅" [了解有关组"更多信息](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。</span><span class="sxs-lookup"><span data-stu-id="cf883-141">To learn more about groups, see [Learn more about groups](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>


> [!NOTE]
> <span data-ttu-id="cf883-142">若要访问共享邮箱，用户必须具有 Exchange Online 许可证，但共享邮箱不需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="cf883-142">To access a shared mailbox, a user must have an Exchange Online license, but the shared mailbox doesn't require a separate license.</span></span> <span data-ttu-id="cf883-143">每个共享邮箱都有相应的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cf883-143">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="cf883-144">注意到你在创建共享邮箱时未被要求提供密码？</span><span class="sxs-lookup"><span data-stu-id="cf883-144">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="cf883-145">该帐户有一个密码，但密码是系统生成的（未知）。</span><span class="sxs-lookup"><span data-stu-id="cf883-145">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="cf883-146">不应使用该帐户登录共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="cf883-146">You shouldn't use the account to log in to the shared mailbox.</span></span> <span data-ttu-id="cf883-147">如果没有许可证，共享邮箱限制为 50 GB。</span><span class="sxs-lookup"><span data-stu-id="cf883-147">Without a license, shared mailboxes are limited to 50 GB.</span></span> <span data-ttu-id="cf883-148">若要将大小限制提高至 100 GB，必须为共享邮箱分配 Exchange Online 计划 2 许可证或具有 Exchange Online Archiving 附加许可证的 Exchange Online 计划 1 许可证。</span><span class="sxs-lookup"><span data-stu-id="cf883-148">To increase the size limit to 100 GB, the shared mailbox must be assigned an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving add-on license.</span></span> <span data-ttu-id="cf883-149">这还使您能够为无限量的存档存储容量启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="cf883-149">This will also let you enable auto-expanding archiving for an unlimited amount of archive storage capacity.</span></span> <span data-ttu-id="cf883-150">同样，如果要将共享邮箱置于诉讼保留状态，共享邮箱必须具有 Exchange Online 计划 2 许可证或 Exchange Online 计划 1 许可证以及Exchange Online Archiving许可证。</span><span class="sxs-lookup"><span data-stu-id="cf883-150">Similarly, if you want to place a shared mailbox on litigation hold, the shared mailbox must have an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving add-on license.</span></span> <span data-ttu-id="cf883-151">如果要应用 Microsoft Defender for Office 365、高级电子数据展示或自动保留策略等高级功能，共享邮箱必须获得这些功能的许可。</span><span class="sxs-lookup"><span data-stu-id="cf883-151">If you want to apply advanced features such as Microsoft Defender for Office 365, Advanced eDiscovery, or automatic retention policies, the shared mailbox must be licensed for those features.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cf883-152">相关文章</span><span class="sxs-lookup"><span data-stu-id="cf883-152">Related articles</span></span>

[<span data-ttu-id="cf883-153">创建共享邮箱</span><span class="sxs-lookup"><span data-stu-id="cf883-153">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="cf883-154">配置共享邮箱</span><span class="sxs-lookup"><span data-stu-id="cf883-154">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="cf883-155">将用户邮箱转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="cf883-155">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="cf883-156">从共享邮箱删除许可证</span><span class="sxs-lookup"><span data-stu-id="cf883-156">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="cf883-157">解决共享邮箱问题</span><span class="sxs-lookup"><span data-stu-id="cf883-157">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
