---
title: 管理计费配置文件
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 了解计费配置文件如何支持发票。
keywords: 计费配置文件、发票、费用、管理费用
ms.openlocfilehash: bd963ff993a064615f0f7ad06c8f2cc5c3401ad2
ms.sourcegitcommit: 1e3916bbe94d4fbb858566e7db5018e1e46bcd0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2019
ms.locfileid: "37646413"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="ce3ea-104">管理计费配置文件</span><span class="sxs-lookup"><span data-stu-id="ce3ea-104">Manage billing profiles</span></span>
<span data-ttu-id="ce3ea-105">对于从 Microsoft 购买产品和服务的商业客户，计费配置文件允许您自定义发票中包含的项目以及支付发票的方式。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-105">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="ce3ea-106">计费配置文件包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="ce3ea-106">Billing profiles include the following information:</span></span>

- <span data-ttu-id="ce3ea-107">与配置文件相关**的帐单帐户名称** &mdash;</span><span class="sxs-lookup"><span data-stu-id="ce3ea-107">**Billing account** &mdash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="ce3ea-108">**支付方式** &mdash;信用卡或借记卡、银行帐户、支票或电汇转帐</span><span class="sxs-lookup"><span data-stu-id="ce3ea-108">**Payment methods** &mdash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="ce3ea-109">**联系人信息** &mdash;帐单地址和联系人姓名</span><span class="sxs-lookup"><span data-stu-id="ce3ea-109">**Contact information** &mdash; Billing address and a contact name</span></span>
- <span data-ttu-id="ce3ea-110">**发票设置** &mdash;货币根据计费帐户所在的国家/地区、可选的 PO 号以及将发票作为电子邮件附件接收的选项。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-110">**Invoice settings** &mdash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="ce3ea-111">允许您更改帐单配置文件、支付帐单或使用付费配置文件上的付款方式进行购买的**权限** &mdash;权限</span><span class="sxs-lookup"><span data-stu-id="ce3ea-111">**Permissions** &mdash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="ce3ea-112">使用计费配置文件控制购买和自定义发票。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-112">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="ce3ea-113">为使用记帐配置文件购买的产品生成月度发票。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-113">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="ce3ea-114">您可以自定义发票，例如更新采购订单编号和电子邮件发票首选项。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-114">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="ce3ea-115">在您首次购买过程中，会自动为您的帐单帐户创建一个记帐配置文件。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-115">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="ce3ea-116">您可以在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">计费配置文件</a>" 页上创建帐单配置文件以设置更多发票。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-116">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="ce3ea-117">例如，在对组织中的每个部门进行购买时，您可以使用不同的记帐配置文件。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-117">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="ce3ea-118">在下一个帐单日期，您将收到每个记帐配置文件的发票。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-118">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="ce3ea-119">计费配置文件角色</span><span class="sxs-lookup"><span data-stu-id="ce3ea-119">Billing profile roles</span></span>

<span data-ttu-id="ce3ea-120">计费配置文件上的角色具有控制采购的权限，并查看和管理发票。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-120">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="ce3ea-121">将这些角色分配给跟踪、组织和支付发票的用户，如组织中的采购团队的成员。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-121">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="ce3ea-122">角色</span><span class="sxs-lookup"><span data-stu-id="ce3ea-122">Role</span></span>                          | <span data-ttu-id="ce3ea-123">说明</span><span class="sxs-lookup"><span data-stu-id="ce3ea-123">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="ce3ea-124">计费配置文件所有者</span><span class="sxs-lookup"><span data-stu-id="ce3ea-124">Billing profile owner</span></span>         | <span data-ttu-id="ce3ea-125">管理计费配置文件的所有内容</span><span class="sxs-lookup"><span data-stu-id="ce3ea-125">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="ce3ea-126">帐单档案文件参与者</span><span class="sxs-lookup"><span data-stu-id="ce3ea-126">Billing profile contributor</span></span>   | <span data-ttu-id="ce3ea-127">管理帐单配置文件中除权限之外的所有内容</span><span class="sxs-lookup"><span data-stu-id="ce3ea-127">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="ce3ea-128">计费配置文件读者</span><span class="sxs-lookup"><span data-stu-id="ce3ea-128">Billing profile reader</span></span>        | <span data-ttu-id="ce3ea-129">记帐配置文件中所有内容的只读视图</span><span class="sxs-lookup"><span data-stu-id="ce3ea-129">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="ce3ea-130">发票管理器</span><span class="sxs-lookup"><span data-stu-id="ce3ea-130">Invoice manager</span></span>               | <span data-ttu-id="ce3ea-131">查看和支付帐单，并在计费配置文件中提供所有内容的只读视图</span><span class="sxs-lookup"><span data-stu-id="ce3ea-131">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="ce3ea-132">查看帐单配置文件</span><span class="sxs-lookup"><span data-stu-id="ce3ea-132">View billing profiles</span></span>

1. <span data-ttu-id="ce3ea-133">在 "管理中心" 中，转到 "**计费** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">帐单 & 付款</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="ce3ea-134">选择 "**帐单配置文件**"，然后从列表中选择帐单配置文件。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-134">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="ce3ea-135">在 "**概述**" 选项卡上，您可以编辑帐单档案文件详细信息，打开或关闭 "通过电子邮件发送发票"。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-135">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="ce3ea-136">在 "**权限**" 选项卡上，您可以向用户分配用于支付发票的角色。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-136">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="ce3ea-137">在 " **azure 信用额度余额**" 选项卡上，azure 客户可以查看该记帐配置文件使用的 Azure 信用的交易余额历史记录。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-137">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="ce3ea-138">在 " **Azure 积分**" 选项卡上，azure 客户可以查看与该计费配置文件关联的 azure 信用列表及其到期日期。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-138">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce3ea-139">如果你没有任何 Azure 信用，你将看不到**azure 信用余额**或**azure 积分**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-139">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="ce3ea-140">是否需要帮助？</span><span class="sxs-lookup"><span data-stu-id="ce3ea-140">Need help?</span></span> <span data-ttu-id="ce3ea-141">请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-141">Contact support.</span></span>

<span data-ttu-id="ce3ea-142">如果你在 Azure 费用方面遇到疑问或需要帮助，请<a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">使用 azure 支持创建支持请求</a>。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-142">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="ce3ea-143">如果您在 Microsoft 365 管理中心中有关于付费配置文件的问题或需要帮助，请[联系业务产品支持人员](https://docs.microsoft.com/en-us/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="ce3ea-143">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/en-us/office365/admin/contact-support-for-business-products).</span></span>