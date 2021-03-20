---
title: 了解计费配置文件
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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- Commerce
search.appverid:
- MET150
description: 了解计费配置文件如何支持发票。
ms.openlocfilehash: 2f56b9a3edbbbe14927df64bed8b699a68826c9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911862"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="1de01-103">了解计费配置文件</span><span class="sxs-lookup"><span data-stu-id="1de01-103">Understand billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1de01-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="1de01-104">The admin center is changing.</span></span> <span data-ttu-id="1de01-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="1de01-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="1de01-106">对于从 Microsoft 购买产品和服务的商业客户，帐单配置文件允许您自定义发票中包含的项目以及如何支付发票费用。</span><span class="sxs-lookup"><span data-stu-id="1de01-106">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="1de01-107">计费配置文件包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="1de01-107">Billing profiles include the following information:</span></span>

- <span data-ttu-id="1de01-108">**计费帐户** &ndash; 配置文件相关的计费帐户的名称</span><span class="sxs-lookup"><span data-stu-id="1de01-108">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="1de01-109">**付款方式** &ndash; 信用卡或借记卡、银行帐户、支票或数据传输</span><span class="sxs-lookup"><span data-stu-id="1de01-109">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="1de01-110">**联系人信息** &ndash; 帐单邮寄地址和联系人姓名</span><span class="sxs-lookup"><span data-stu-id="1de01-110">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="1de01-111">**发票设置** &ndash; 基于计费帐户的国家/地区、可选 PO 编号以及接收作为电子邮件附件的发票的选项的货币</span><span class="sxs-lookup"><span data-stu-id="1de01-111">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="1de01-112">**权限** &ndash; 允许您更改计费配置文件、支付帐单或使用帐单配置文件上的付款方式进行购买的权限</span><span class="sxs-lookup"><span data-stu-id="1de01-112">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="1de01-113">使用计费配置文件来控制你的购买并自定义你的发票。</span><span class="sxs-lookup"><span data-stu-id="1de01-113">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="1de01-114">为使用计费配置文件购买的产品生成每月发票。</span><span class="sxs-lookup"><span data-stu-id="1de01-114">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="1de01-115">你可以自定义发票，例如更新采购订单编号和电子邮件发票首选项。</span><span class="sxs-lookup"><span data-stu-id="1de01-115">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="1de01-116">首次购买时，系统会自动为帐单帐户创建计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="1de01-116">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="1de01-117">可以在"计费配置文件"页上创建计费 <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">配置文件</a> 以设置更多发票。</span><span class="sxs-lookup"><span data-stu-id="1de01-117">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="1de01-118">例如，为组织的每个部门进行购买时，可以使用不同的计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="1de01-118">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="1de01-119">下一个计费日期，你将收到每个计费配置文件的发票。</span><span class="sxs-lookup"><span data-stu-id="1de01-119">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="1de01-120">计费配置文件角色</span><span class="sxs-lookup"><span data-stu-id="1de01-120">Billing profile roles</span></span>

<span data-ttu-id="1de01-121">帐单配置文件上的角色具有控制购买以及查看和管理发票的权限。</span><span class="sxs-lookup"><span data-stu-id="1de01-121">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="1de01-122">向跟踪、组织和支付发票的用户分配这些角色，例如组织中采购团队成员。</span><span class="sxs-lookup"><span data-stu-id="1de01-122">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="1de01-123">Role</span><span class="sxs-lookup"><span data-stu-id="1de01-123">Role</span></span>                          | <span data-ttu-id="1de01-124">说明</span><span class="sxs-lookup"><span data-stu-id="1de01-124">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="1de01-125">计费配置文件所有者</span><span class="sxs-lookup"><span data-stu-id="1de01-125">Billing profile owner</span></span>         | <span data-ttu-id="1de01-126">管理计费配置文件的所有内容</span><span class="sxs-lookup"><span data-stu-id="1de01-126">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="1de01-127">计费配置文件参与者</span><span class="sxs-lookup"><span data-stu-id="1de01-127">Billing profile contributor</span></span>   | <span data-ttu-id="1de01-128">管理计费配置文件中的权限之外的所有内容</span><span class="sxs-lookup"><span data-stu-id="1de01-128">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="1de01-129">计费配置文件读取器</span><span class="sxs-lookup"><span data-stu-id="1de01-129">Billing profile reader</span></span>        | <span data-ttu-id="1de01-130">帐单配置文件中所有项的只读视图</span><span class="sxs-lookup"><span data-stu-id="1de01-130">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="1de01-131">发票管理器</span><span class="sxs-lookup"><span data-stu-id="1de01-131">Invoice manager</span></span>               | <span data-ttu-id="1de01-132">查看和支付帐单，并且对帐单配置文件中所有内容具有只读视图</span><span class="sxs-lookup"><span data-stu-id="1de01-132">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="1de01-133">查看计费配置文件</span><span class="sxs-lookup"><span data-stu-id="1de01-133">View billing profiles</span></span>

1. <span data-ttu-id="1de01-134">在管理中心，转到“**账单**”\> “<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">账单和付款</a>”页。</span><span class="sxs-lookup"><span data-stu-id="1de01-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="1de01-135">选择 **"计费配置文件**"，然后从列表中选择计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="1de01-135">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="1de01-136">在" **概述** "选项卡上，可以编辑计费配置文件详细信息，并通过电子邮件打开或关闭发送发票。</span><span class="sxs-lookup"><span data-stu-id="1de01-136">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="1de01-137">在 **"权限"** 选项卡上，可以将角色分配给用户以支付发票。</span><span class="sxs-lookup"><span data-stu-id="1de01-137">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="1de01-138">在 **"Azure 信用余额** "选项卡上，Azure 客户可以看到该计费配置文件使用的 Azure 信用的交易余额历史记录。</span><span class="sxs-lookup"><span data-stu-id="1de01-138">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="1de01-139">在 **"Azure 信用额度** "选项卡上，Azure 客户可以看到与该计费配置文件关联的 Azure 信用列表及其到期日期。</span><span class="sxs-lookup"><span data-stu-id="1de01-139">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1de01-140">如果你没有任何 Azure 信用额度，你将看不到 **Azure** 信用余额或 **Azure 信用** 表。</span><span class="sxs-lookup"><span data-stu-id="1de01-140">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="1de01-141">需要帮助？</span><span class="sxs-lookup"><span data-stu-id="1de01-141">Need help?</span></span> <span data-ttu-id="1de01-142">请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="1de01-142">Contact support.</span></span>

<span data-ttu-id="1de01-143">如果对 Azure 费用有疑问或需要帮助，请通过 Azure 支持 创建 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">支持请求</a>。</span><span class="sxs-lookup"><span data-stu-id="1de01-143">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="1de01-144">如果对 Microsoft 365 管理中心中的帐单配置文件有疑问或需要帮助，请联系 [商业版产品支持人员](/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="1de01-144">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](/office365/admin/contact-support-for-business-products).</span></span>