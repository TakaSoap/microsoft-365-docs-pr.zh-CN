---
title: 设置连接器以存档 LinkedIn 数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器以将数据从 LinkedIn 公司页面导入到 Microsoft 365。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据的合规性。
ms.openlocfilehash: b42584efb0c99b97c14059ed7d860013f085262c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079623"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a><span data-ttu-id="39a30-104">设置连接器以存档 LinkedIn 数据</span><span class="sxs-lookup"><span data-stu-id="39a30-104">Set up a connector to archive LinkedIn data</span></span>

<span data-ttu-id="39a30-105">使用 Microsoft 365 合规性中心中的连接器从 LinkedIn 公司页面导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="39a30-105">Use a connector in the Microsoft 365 compliance center to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="39a30-106">在设置和配置连接器后，它会每24小时连接到特定 "LinkedIn 公司" 页面的帐户。</span><span class="sxs-lookup"><span data-stu-id="39a30-106">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="39a30-107">连接器将发布到公司页面的邮件转换为电子邮件，然后将这些项目导入到 Microsoft 365 中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="39a30-107">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="39a30-108">在将 LinkedIn 公司页面数据存储在邮箱中之后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核和 Microsoft 365 保留策略）应用于 LinkedIn 数据。</span><span class="sxs-lookup"><span data-stu-id="39a30-108">After the LinkedIn Company page data is stored in a mailbox, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="39a30-109">例如，可以使用内容搜索来搜索这些项目，或将存储邮箱与高级电子数据展示事例中的管理员相关联。</span><span class="sxs-lookup"><span data-stu-id="39a30-109">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="39a30-110">创建连接器以在 Microsoft 365 中导入和存档 LinkedIn 数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="39a30-110">Creating a connector to import and archive LinkedIn data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you--begin"></a><span data-ttu-id="39a30-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="39a30-111">Before you  begin</span></span>

- <span data-ttu-id="39a30-112">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="39a30-112">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="39a30-113">若要同意此请求，请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Microsoft 365 全局管理员的凭据登录，然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="39a30-113">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Microsoft 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="39a30-114">必须在 Exchange Online 中为创建 LinkedIn 公司页面连接器的用户分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="39a30-114">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="39a30-115">这是在 Microsoft 365 合规性中心的 "**数据连接器**" 页中添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="39a30-115">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="39a30-116">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="39a30-116">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="39a30-117">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="39a30-117">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="39a30-118">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="39a30-118">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="39a30-119">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。</span><span class="sxs-lookup"><span data-stu-id="39a30-119">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="39a30-120">您必须具有作为您要存档的 "LinkedIn 公司" 页面的管理员的 LinkedIn 用户帐户的登录凭据（电子邮件地址或电话号码和密码）。</span><span class="sxs-lookup"><span data-stu-id="39a30-120">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="39a30-121">设置连接器时，可以使用这些凭据登录到 LinkedIn。</span><span class="sxs-lookup"><span data-stu-id="39a30-121">You use these credentials to sign in to LinkedIn when setting up the connector.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="39a30-122">创建 LinkedIn 连接器</span><span class="sxs-lookup"><span data-stu-id="39a30-122">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="39a30-123">转到<https://compliance.microsoft.com> ，然后单击 "**数据连接器** > **LinkedIn 公司" 页面**。</span><span class="sxs-lookup"><span data-stu-id="39a30-123">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **LinkedIn Company pages**.</span></span>

2. <span data-ttu-id="39a30-124">在 " **LinkedIn 公司页面**产品" 页上，单击 "**添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="39a30-124">On the **LinkedIn company pages** product page, click **Add connector**.</span></span>

3. <span data-ttu-id="39a30-125">在 "**服务条款**" 页上，选择 "**接受**"。</span><span class="sxs-lookup"><span data-stu-id="39a30-125">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="39a30-126">在 "**使用 Linkedin 登录**" 页面上，单击 "**使用 linkedin 登录**"。</span><span class="sxs-lookup"><span data-stu-id="39a30-126">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="39a30-127">将显示 "LinkedIn 登录" 页面。</span><span class="sxs-lookup"><span data-stu-id="39a30-127">The LinkedIn sign in page is displayed.</span></span>

   ![LinkedIn 登录页](../media/LinkedInSigninPage.png)

5. <span data-ttu-id="39a30-129">在 "LinkedIn 登录" 页面上，输入与要存档的 "公司" 页面相关联的 LinkedIn 帐户的电子邮件地址（或电话号码）和密码，然后单击 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="39a30-129">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="39a30-130">将显示一个向导页，其中包含与您登录的帐户关联的所有 LinkedIn 公司页面的列表。</span><span class="sxs-lookup"><span data-stu-id="39a30-130">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="39a30-131">仅可为一个公司页面配置连接器。</span><span class="sxs-lookup"><span data-stu-id="39a30-131">A connector can only be configured for one company page.</span></span> <span data-ttu-id="39a30-132">如果您的组织具有多个 LinkedIn 公司页面，则必须为每个公司创建一个连接器。</span><span class="sxs-lookup"><span data-stu-id="39a30-132">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![将显示一个包含 "LinkedIn 公司" 页面列表的页面](../media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="39a30-134">选择要存档其项目的公司页面，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="39a30-134">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="39a30-135">在 "**设置筛选器**" 页上，您可以将筛选器应用于最初导入特定年龄的项目。</span><span class="sxs-lookup"><span data-stu-id="39a30-135">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="39a30-136">选择年龄，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="39a30-136">Select an age, and then click **Next**.</span></span>

8. <span data-ttu-id="39a30-137">在 "**选择存储位置**" 页上，单击 "" 框中，选择 LinkedIn 项目将导入到其中的 Microsoft 365 邮箱的电子邮件地址，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="39a30-137">On the **Choose storage location** page, click in the box, select the email address of an Microsoft 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="39a30-138">项目将导入到此邮箱的 "收件箱" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="39a30-138">Items are imported to the inbox folder in this mailbox.</span></span>

9. <span data-ttu-id="39a30-139">在 "**提供管理员同意**" 中，单击 "**提供许可**"，然后按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="39a30-139">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="39a30-140">您必须是全局管理员，才能同意 Office 365 导入服务以访问组织中的数据。</span><span class="sxs-lookup"><span data-stu-id="39a30-140">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

10. <span data-ttu-id="39a30-141">单击 "**下一步**" 查看连接器设置，然后单击 "**完成**" 以完成连接器设置。</span><span class="sxs-lookup"><span data-stu-id="39a30-141">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

<span data-ttu-id="39a30-142">创建连接器后，可以返回到 "**数据连接器**" 页，以查看新连接器的导入过程的进度（如有必要，请选择 "**刷新**" 以更新连接器列表）。</span><span class="sxs-lookup"><span data-stu-id="39a30-142">After you create the connector, you can go back to the **Data connectors** page to see the progress of the import process for the new connector (select **Refresh** if necessary to update the list of connectors).</span></span> <span data-ttu-id="39a30-143">"**状态**" 列中的值为 "**正在等待启动**"。</span><span class="sxs-lookup"><span data-stu-id="39a30-143">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="39a30-144">启动初始导入过程需要长达24小时。</span><span class="sxs-lookup"><span data-stu-id="39a30-144">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="39a30-145">在第一次运行连接器并导入 LinkedIn 项目后，连接器将每24小时运行一次，并导入 "LinkedIn 公司" 页上的 "在前24小时内创建的任何新项目"。</span><span class="sxs-lookup"><span data-stu-id="39a30-145">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="39a30-146">若要查看更多详细信息，请选择 "**数据连接器**" 页上的列表中的连接器以显示弹出页面。</span><span class="sxs-lookup"><span data-stu-id="39a30-146">To view more details, select the connector in the list on the **Data connectors** page to display the flyout page.</span></span> <span data-ttu-id="39a30-147">在 "**状态**" 下，显示的日期范围表示创建连接器时选择的年龄筛选器。</span><span class="sxs-lookup"><span data-stu-id="39a30-147">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span> 

## <a name="more-information"></a><span data-ttu-id="39a30-148">详细信息</span><span class="sxs-lookup"><span data-stu-id="39a30-148">More information</span></span>

<span data-ttu-id="39a30-149">LinkedIn 项将导入到 Microsoft 365 中存储邮箱的 "LinkedIn" 子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="39a30-149">LinkedIn items are imported to the LinkedIn subfolder in the inbox of the storage mailbox in Microsoft 365.</span></span> <span data-ttu-id="39a30-150">它们显示为电子邮件。</span><span class="sxs-lookup"><span data-stu-id="39a30-150">They appear as email messages.</span></span>
