---
title: 管理计费对象信息
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 了解计费配置文件如何支持发票。
keywords: 计费配置文件、发票、费用、管理费用
ms.openlocfilehash: de6d6cd65d9e83e7211bcdc33f1774aaec3d1729
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638443"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="12bbe-104">管理计费对象信息</span><span class="sxs-lookup"><span data-stu-id="12bbe-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="12bbe-105">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="12bbe-105">The admin center is changing.</span></span> <span data-ttu-id="12bbe-106">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="12bbe-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="12bbe-107">对于从 Microsoft 购买产品和服务的商业客户，计费配置文件允许您自定义发票中包含的项目以及支付发票的方式。</span><span class="sxs-lookup"><span data-stu-id="12bbe-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="12bbe-108">计费配置文件包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="12bbe-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="12bbe-109">**帐单帐户** &ndash; 与配置文件相关的帐单帐户的名称</span><span class="sxs-lookup"><span data-stu-id="12bbe-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="12bbe-110">**付款方式** &ndash; 信用卡或借记卡、银行帐户、支票或电汇转帐</span><span class="sxs-lookup"><span data-stu-id="12bbe-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="12bbe-111">**联系人信息** &ndash; 帐单地址和联系人姓名</span><span class="sxs-lookup"><span data-stu-id="12bbe-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="12bbe-112">**发票设置** &ndash; 基于计费帐户所在国家/地区的货币、可选的 PO 号以及将发票作为电子邮件附件接收的选项</span><span class="sxs-lookup"><span data-stu-id="12bbe-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="12bbe-113">**权限** &ndash; 允许您更改帐单配置文件、支付帐单或使用记帐配置文件上的付款方式进行购买的权限</span><span class="sxs-lookup"><span data-stu-id="12bbe-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="12bbe-114">使用计费配置文件控制购买和自定义发票。</span><span class="sxs-lookup"><span data-stu-id="12bbe-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="12bbe-115">为使用记帐配置文件购买的产品生成月度发票。</span><span class="sxs-lookup"><span data-stu-id="12bbe-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="12bbe-116">您可以自定义发票，例如更新采购订单编号和电子邮件发票首选项。</span><span class="sxs-lookup"><span data-stu-id="12bbe-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="12bbe-117">在您首次购买过程中，会自动为您的帐单帐户创建一个记帐配置文件。</span><span class="sxs-lookup"><span data-stu-id="12bbe-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="12bbe-118">您可以在 " <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">计费配置文件</a> " 页上创建帐单配置文件以设置更多发票。</span><span class="sxs-lookup"><span data-stu-id="12bbe-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="12bbe-119">例如，在对组织中的每个部门进行购买时，您可以使用不同的记帐配置文件。</span><span class="sxs-lookup"><span data-stu-id="12bbe-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="12bbe-120">在下一个帐单日期，您将收到每个记帐配置文件的发票。</span><span class="sxs-lookup"><span data-stu-id="12bbe-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="12bbe-121">计费配置文件角色</span><span class="sxs-lookup"><span data-stu-id="12bbe-121">Billing profile roles</span></span>

<span data-ttu-id="12bbe-122">计费配置文件上的角色具有控制采购的权限，并查看和管理发票。</span><span class="sxs-lookup"><span data-stu-id="12bbe-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="12bbe-123">将这些角色分配给跟踪、组织和支付发票的用户，如组织中的采购团队的成员。</span><span class="sxs-lookup"><span data-stu-id="12bbe-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="12bbe-124">Role</span><span class="sxs-lookup"><span data-stu-id="12bbe-124">Role</span></span>                          | <span data-ttu-id="12bbe-125">说明</span><span class="sxs-lookup"><span data-stu-id="12bbe-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="12bbe-126">计费配置文件所有者</span><span class="sxs-lookup"><span data-stu-id="12bbe-126">Billing profile owner</span></span>         | <span data-ttu-id="12bbe-127">管理计费配置文件的所有内容</span><span class="sxs-lookup"><span data-stu-id="12bbe-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="12bbe-128">帐单档案文件参与者</span><span class="sxs-lookup"><span data-stu-id="12bbe-128">Billing profile contributor</span></span>   | <span data-ttu-id="12bbe-129">管理帐单配置文件中除权限之外的所有内容</span><span class="sxs-lookup"><span data-stu-id="12bbe-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="12bbe-130">计费配置文件读者</span><span class="sxs-lookup"><span data-stu-id="12bbe-130">Billing profile reader</span></span>        | <span data-ttu-id="12bbe-131">记帐配置文件中所有内容的只读视图</span><span class="sxs-lookup"><span data-stu-id="12bbe-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="12bbe-132">发票管理器</span><span class="sxs-lookup"><span data-stu-id="12bbe-132">Invoice manager</span></span>               | <span data-ttu-id="12bbe-133">查看和支付帐单，并在计费配置文件中提供所有内容的只读视图</span><span class="sxs-lookup"><span data-stu-id="12bbe-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="12bbe-134">查看帐单配置文件</span><span class="sxs-lookup"><span data-stu-id="12bbe-134">View billing profiles</span></span>

1. <span data-ttu-id="12bbe-135">在管理中心，转到“**账单**”\> “<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">账单和付款</a>”页。</span><span class="sxs-lookup"><span data-stu-id="12bbe-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="12bbe-136">选择 " **帐单配置文件**"，然后从列表中选择帐单配置文件。</span><span class="sxs-lookup"><span data-stu-id="12bbe-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="12bbe-137">在 " **概述** " 选项卡上，您可以编辑帐单档案文件详细信息，打开或关闭 "通过电子邮件发送发票"。</span><span class="sxs-lookup"><span data-stu-id="12bbe-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="12bbe-138">在 " **权限** " 选项卡上，您可以向用户分配用于支付发票的角色。</span><span class="sxs-lookup"><span data-stu-id="12bbe-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="12bbe-139">在 " **azure 信用额度余额** " 选项卡上，azure 客户可以查看该记帐配置文件使用的 Azure 信用的交易余额历史记录。</span><span class="sxs-lookup"><span data-stu-id="12bbe-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="12bbe-140">在 " **Azure 积分** " 选项卡上，azure 客户可以查看与该计费配置文件关联的 azure 信用列表及其到期日期。</span><span class="sxs-lookup"><span data-stu-id="12bbe-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="12bbe-141">如果你没有任何 Azure 信用，你将看不到 **azure 信用余额** 或 **azure 积分** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="12bbe-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="12bbe-142">需要帮助?</span><span class="sxs-lookup"><span data-stu-id="12bbe-142">Need help?</span></span> <span data-ttu-id="12bbe-143">请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="12bbe-143">Contact support.</span></span>

<span data-ttu-id="12bbe-144">如果你在 Azure 费用方面遇到疑问或需要帮助，请 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">使用 azure 支持创建支持请求</a>。</span><span class="sxs-lookup"><span data-stu-id="12bbe-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="12bbe-145">如果您在 Microsoft 365 管理中心中有关于付费配置文件的问题或需要帮助，请 [联系业务产品支持人员](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="12bbe-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
