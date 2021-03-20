---
title: 设置连接器以存档 LinkedIn 数据
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 了解管理员如何设置&使用本机连接器将数据从 LinkedIn 公司页面导入到 Microsoft 365。
ms.openlocfilehash: 40e51424d086b0eee42d1f15ea577b7e8f1648c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906142"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a><span data-ttu-id="49a22-103">设置连接器以存档 LinkedIn 数据</span><span class="sxs-lookup"><span data-stu-id="49a22-103">Set up a connector to archive LinkedIn data</span></span>

<span data-ttu-id="49a22-104">使用 Microsoft 365 合规中心中的连接器从 LinkedIn 公司页面导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="49a22-104">Use a connector in the Microsoft 365 compliance center to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="49a22-105">设置和配置连接器后，它每 24 小时连接到特定 LinkedIn 公司页面的帐户一次。</span><span class="sxs-lookup"><span data-stu-id="49a22-105">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="49a22-106">连接器会将发送到"公司"页面的邮件转换为电子邮件，然后将这些项目导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="49a22-106">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="49a22-107">将 LinkedIn 公司页面数据存储在邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核和 Microsoft 365 保留策略）应用于 LinkedIn 数据。</span><span class="sxs-lookup"><span data-stu-id="49a22-107">After the LinkedIn Company page data is stored in a mailbox, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="49a22-108">例如，您可以使用内容搜索搜索这些项目，或将存储邮箱与高级电子数据展示案例中的保管人关联。</span><span class="sxs-lookup"><span data-stu-id="49a22-108">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="49a22-109">创建连接器以在 Microsoft 365 中导入和存档 LinkedIn 数据可帮助你的组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="49a22-109">Creating a connector to import and archive LinkedIn data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="49a22-110">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="49a22-110">Before you set up a connector</span></span>

- <span data-ttu-id="49a22-111">必须在 Exchange Online 中为创建 LinkedIn 公司页面连接器的用户分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="49a22-111">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="49a22-112">这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。</span><span class="sxs-lookup"><span data-stu-id="49a22-112">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="49a22-113">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="49a22-113">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="49a22-114">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="49a22-114">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="49a22-115">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="49a22-115">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="49a22-116">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="49a22-116">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="49a22-117">你必须拥有作为要存档 (LinkedIn 公司页面管理员的 LinkedIn 用户帐户) 电子邮件地址或电话号码和密码的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="49a22-117">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="49a22-118">设置连接器时，使用这些凭据登录 LinkedIn。</span><span class="sxs-lookup"><span data-stu-id="49a22-118">You use these credentials to sign into LinkedIn when setting up the connector.</span></span>

- <span data-ttu-id="49a22-119">LinkedIn 连接器在一天中总共可以导入 200，000 个项目。</span><span class="sxs-lookup"><span data-stu-id="49a22-119">The LinkedIn connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="49a22-120">如果一天中 LinkedIn 项目超过 200，000 个，则这些项目均不会导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="49a22-120">If there are more than 200,000 LinkedIn items in a day, none of those items will be imported to Microsoft 365.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="49a22-121">创建 LinkedIn 连接器</span><span class="sxs-lookup"><span data-stu-id="49a22-121">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="49a22-122">转到 ， <https://compliance.microsoft.com> 然后单击数据 **连接器**  >  **LinkedIn 公司页面**。</span><span class="sxs-lookup"><span data-stu-id="49a22-122">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **LinkedIn Company pages**.</span></span>

2. <span data-ttu-id="49a22-123">在 **LinkedIn 公司页面** 产品页面上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="49a22-123">On the **LinkedIn company pages** product page, click **Add connector**.</span></span>

3. <span data-ttu-id="49a22-124">在"**服务条款"页上**，选择"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="49a22-124">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="49a22-125">在"**使用 LinkedIn 登录"** 页上，单击 **"使用 LinkedIn 登录"。**</span><span class="sxs-lookup"><span data-stu-id="49a22-125">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="49a22-126">将显示 LinkedIn 登录页。</span><span class="sxs-lookup"><span data-stu-id="49a22-126">The LinkedIn sign-in page is displayed.</span></span>

   ![LinkedIn 登录页](../media/LinkedInSigninPage.png)

5. <span data-ttu-id="49a22-128">在 LinkedIn 登录页面上，输入与要存档的公司页面关联的 LinkedIn 帐户的电子邮件地址 (或电话号码) 和密码，然后单击"**登录"。**</span><span class="sxs-lookup"><span data-stu-id="49a22-128">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="49a22-129">将显示向导页面，其中列出了与登录帐户关联的所有 LinkedIn 公司页面。</span><span class="sxs-lookup"><span data-stu-id="49a22-129">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="49a22-130">连接器只能为一个公司页面进行配置。</span><span class="sxs-lookup"><span data-stu-id="49a22-130">A connector can only be configured for one company page.</span></span> <span data-ttu-id="49a22-131">如果您的组织有多个 LinkedIn 公司页面，您必须为每个页面创建一个连接器。</span><span class="sxs-lookup"><span data-stu-id="49a22-131">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![将显示包含 LinkedIn 公司页面列表的页面](../media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="49a22-133">选择要存档其项目的公司页面，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="49a22-133">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="49a22-134">在"**选择存储位置**"页上，在框中单击，选择将 LinkedIn 项目导入到的 Microsoft 365 邮箱的电子邮件地址，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="49a22-134">On the **Choose storage location** page, click in the box, select the email address of a Microsoft 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="49a22-135">项目将导入到此邮箱中的收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="49a22-135">Items are imported to the inbox folder in this mailbox.</span></span>

8. <span data-ttu-id="49a22-136">单击 **"下** 一步"查看连接器设置，然后单击" **完成** "以完成连接器设置。</span><span class="sxs-lookup"><span data-stu-id="49a22-136">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

<span data-ttu-id="49a22-137">创建连接器后，可以返回到"数据连接器"页以查看新连接器的导入过程的进度 (如有必要，选择"刷新"以更新连接器) 。 </span><span class="sxs-lookup"><span data-stu-id="49a22-137">After you create the connector, you can go back to the **Data connectors** page to see the progress of the import process for the new connector (select **Refresh** if necessary to update the list of connectors).</span></span> <span data-ttu-id="49a22-138">"状态 **"** 列中的值为 **"正在等待启动"。**</span><span class="sxs-lookup"><span data-stu-id="49a22-138">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="49a22-139">初始导入过程最多需要 24 小时才能启动。</span><span class="sxs-lookup"><span data-stu-id="49a22-139">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="49a22-140">连接器首次运行并导入 LinkedIn 项目后，连接器将每 24 小时运行一次，并导入前 24 小时内在 LinkedIn 公司页面上创建的任何新项。</span><span class="sxs-lookup"><span data-stu-id="49a22-140">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="49a22-141">若要查看更多详细信息，请在"数据连接器"页上的列表中选择 **连接器以显示该** 飞出页。</span><span class="sxs-lookup"><span data-stu-id="49a22-141">To view more details, select the connector in the list on the **Data connectors** page to display the flyout page.</span></span> <span data-ttu-id="49a22-142">在 **"** 状态"下，显示的日期范围指示创建连接器时选择的年龄筛选器。</span><span class="sxs-lookup"><span data-stu-id="49a22-142">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span>

## <a name="more-information"></a><span data-ttu-id="49a22-143">更多信息</span><span class="sxs-lookup"><span data-stu-id="49a22-143">More information</span></span>

<span data-ttu-id="49a22-144">LinkedIn 项目将导入到 Microsoft 365 中存储邮箱的收件箱中的 LinkedIn 子文件夹。</span><span class="sxs-lookup"><span data-stu-id="49a22-144">LinkedIn items are imported to the LinkedIn subfolder in the inbox of the storage mailbox in Microsoft 365.</span></span> <span data-ttu-id="49a22-145">它们显示为电子邮件。</span><span class="sxs-lookup"><span data-stu-id="49a22-145">They appear as email messages.</span></span>