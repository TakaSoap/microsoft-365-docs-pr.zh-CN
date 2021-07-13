---
title: 了解计费配置文件
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
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
- commerce_billing
- AdminTemplateSet
search.appverid: MET150
description: 了解计费配置文件如何支持发票。
ms.date: 04/02/2021
ms.openlocfilehash: ecea09a9ceea12fa92b92eac3e5a7595b2510042
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394625"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="b7ac0-103">了解计费配置文件</span><span class="sxs-lookup"><span data-stu-id="b7ac0-103">Understand billing profiles</span></span>

<span data-ttu-id="b7ac0-104">计费配置文件包含付款方式、帐单邮寄信息和其他发票设置，如采购订单编号和电子邮件发票首选项。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="b7ac0-105">使用计费配置文件支付从 Microsoft 购买的产品。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="b7ac0-106">当用户进行自助购买时，将自动创建计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="b7ac0-107">每个计费配置文件都单独开票。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="b7ac0-108">计费配置文件不适用于从 Microsoft.com 购买产品和服务的客户或客户在 Microsoft 365 管理中心。 </span><span class="sxs-lookup"><span data-stu-id="b7ac0-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="b7ac0-109">什么是计费配置文件角色？</span><span class="sxs-lookup"><span data-stu-id="b7ac0-109">What are billing profile roles?</span></span>

<span data-ttu-id="b7ac0-110">帐单配置文件上的角色具有控制购买以及查看和管理发票的权限。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="b7ac0-111">向跟踪、组织和支付发票的用户分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="b7ac0-112">例如，您组织中采购工作组的成员。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="b7ac0-113">Role</span><span class="sxs-lookup"><span data-stu-id="b7ac0-113">Role</span></span>                         | <span data-ttu-id="b7ac0-114">说明</span><span class="sxs-lookup"><span data-stu-id="b7ac0-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="b7ac0-115">计费配置文件所有者</span><span class="sxs-lookup"><span data-stu-id="b7ac0-115">Billing profile owner</span></span>        | <span data-ttu-id="b7ac0-116">管理计费配置文件的所有内容</span><span class="sxs-lookup"><span data-stu-id="b7ac0-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="b7ac0-117">计费配置文件参与者</span><span class="sxs-lookup"><span data-stu-id="b7ac0-117">Billing profile contributor</span></span>  | <span data-ttu-id="b7ac0-118">管理计费配置文件中的权限之外的所有内容</span><span class="sxs-lookup"><span data-stu-id="b7ac0-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="b7ac0-119">计费配置文件读取器</span><span class="sxs-lookup"><span data-stu-id="b7ac0-119">Billing profile reader</span></span>       | <span data-ttu-id="b7ac0-120">帐单配置文件中所有项的只读视图</span><span class="sxs-lookup"><span data-stu-id="b7ac0-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="b7ac0-121">发票管理器</span><span class="sxs-lookup"><span data-stu-id="b7ac0-121">Invoice manager</span></span>              | <span data-ttu-id="b7ac0-122">查看和支付帐单，并且对帐单配置文件中所有内容具有只读视图</span><span class="sxs-lookup"><span data-stu-id="b7ac0-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="b7ac0-123">查看我的计费配置文件</span><span class="sxs-lookup"><span data-stu-id="b7ac0-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="b7ac0-124">如果按照这些步骤操作，并且计费配置文件列表为空，则意味着你没有计费配置文件，并且无法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="b7ac0-125">在管理中心，转到“**账单**”\> “<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">账单和付款</a>”页。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="b7ac0-126">选择" **计费配置文件** "选项卡，然后从列表中选择计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="b7ac0-127">每个计费配置文件包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="b7ac0-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="b7ac0-128">**计费配置文件名称和状态** &ndash; 计费配置文件的唯一名称，以及计费配置文件是处于活动状态还是已禁用进行购买。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="b7ac0-129">**发票设置** &ndash; 基于计费帐户的国家/地区的货币、有关发票频率和日期的信息、作为电子邮件附件接收发票的选项以及可选的 PO 编号字段</span><span class="sxs-lookup"><span data-stu-id="b7ac0-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="b7ac0-130">**付款方式** &ndash; 显示配置文件的主付款方式和备份付款方式（如果有）</span><span class="sxs-lookup"><span data-stu-id="b7ac0-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="b7ac0-131">**计费帐户** &ndash; 配置文件相关的计费帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="b7ac0-132">有关计费帐户详细信息，请参阅 [了解计费帐户](../manage-billing-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="b7ac0-133">**联系人信息** &ndash; 帐单邮寄地址、联系人姓名和电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="b7ac0-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="b7ac0-134">**计费配置文件角色** &ndash; 分配了其中一个计费配置文件角色以执行该配置文件操作的用户列表。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="b7ac0-135">例如，支付帐单、添加 PO 编号或替换用于进行购买的付款方式。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="b7ac0-136">只能将计费配置文件角色分配给贵组织的用户。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="b7ac0-137">需要帮助？</span><span class="sxs-lookup"><span data-stu-id="b7ac0-137">Need help?</span></span> <span data-ttu-id="b7ac0-138">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="b7ac0-138">Contact support</span></span>

<span data-ttu-id="b7ac0-139">如果对 Azure 费用有疑问或需要帮助，请通过 Azure 支持 创建 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">支持请求</a>。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="b7ac0-140">如果你有问题或需要帮助，请联系支持人员Microsoft 365 管理中心[配置文件](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="b7ac0-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="b7ac0-141">相关内容</span><span class="sxs-lookup"><span data-stu-id="b7ac0-141">Related content</span></span>

<span data-ttu-id="b7ac0-142">[How to pay for your subscription with a billing profile (](pay-for-subscription-billing-profile.md) article) </span><span class="sxs-lookup"><span data-stu-id="b7ac0-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="b7ac0-143">[了解帐单 (](../manage-billing-accounts.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="b7ac0-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="b7ac0-144">[管理付款方式 (](manage-payment-methods.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="b7ac0-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
