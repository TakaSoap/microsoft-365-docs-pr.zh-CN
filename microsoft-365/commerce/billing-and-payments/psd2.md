---
title: 付款服务指令 2 和针对商业客户的强客户身份验证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
search.appverid: MET150
description: 自 2019 年 9 月 14 日起，必须验证进行在线购买的人的身份，然后才能处理付款。"
keywords: 付款服务指令 2，强客户身份验证，多重身份验证
ms.date: 11/03/2020
ms.openlocfilehash: e687cac5bb1b7f1c88e9166993e29d437134e138
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280843"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="50573-104">付款服务指令 2 和针对商业客户的强客户身份验证</span><span class="sxs-lookup"><span data-stu-id="50573-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="50573-105">自 2019 年 9 月 14 日起，在可以处理付款之前，需要欧盟 31 个国家/地区的银行验证进行在线购买的人的身份。</span><span class="sxs-lookup"><span data-stu-id="50573-105">As of September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="50573-106">此验证需要多重身份验证，以帮助确保在线购买的安全和保护。</span><span class="sxs-lookup"><span data-stu-id="50573-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="50573-107">某些国家/地区将延迟此验证要求的日期。</span><span class="sxs-lookup"><span data-stu-id="50573-107">The date for this verification requirement will be delayed for some countries.</span></span>

<span data-ttu-id="50573-108">有关详细信息，请参阅 [有关付款服务指令 2 和强客户身份验证的 Microsoft 常见问题解答](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)。</span><span class="sxs-lookup"><span data-stu-id="50573-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="50573-109">何时需要多重身份验证？</span><span class="sxs-lookup"><span data-stu-id="50573-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="50573-110">目前，此指令使用多重身份验证的验证要求仅适用于使用来自欧盟 31 个国家/地区的银行信用卡的客户。</span><span class="sxs-lookup"><span data-stu-id="50573-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="50573-111">有时，由于客户所采取操作，系统将会提示客户，有时由于现有订阅或服务的事件而提示客户。</span><span class="sxs-lookup"><span data-stu-id="50573-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="50573-112">客户操作</span><span class="sxs-lookup"><span data-stu-id="50573-112">Customer Actions</span></span>

<span data-ttu-id="50573-113">你的银行可能需要通过多重身份验证进行验证。</span><span class="sxs-lookup"><span data-stu-id="50573-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="50573-114">例如:</span><span class="sxs-lookup"><span data-stu-id="50573-114">Some examples include:</span></span>

- <span data-ttu-id="50573-115">注册新订阅</span><span class="sxs-lookup"><span data-stu-id="50573-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="50573-116">向订阅添加许可证</span><span class="sxs-lookup"><span data-stu-id="50573-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="50573-117">添加或替换用于支付订阅或服务的信用卡</span><span class="sxs-lookup"><span data-stu-id="50573-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="50573-118">在计费配置文件中添加或替换信用卡</span><span class="sxs-lookup"><span data-stu-id="50573-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="50573-119">购买应用</span><span class="sxs-lookup"><span data-stu-id="50573-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="50573-120">订阅生命周期事件</span><span class="sxs-lookup"><span data-stu-id="50573-120">Subscription lifecycle events</span></span>

<span data-ttu-id="50573-121">定期付款的费用可能会失败。</span><span class="sxs-lookup"><span data-stu-id="50573-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="50573-122">如果收到，你将收到一封电子邮件，说明要遵循。</span><span class="sxs-lookup"><span data-stu-id="50573-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="50573-123">系统将提示你响应验证请求并支付当前付款。</span><span class="sxs-lookup"><span data-stu-id="50573-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="50573-124">需要更多帮助吗？</span><span class="sxs-lookup"><span data-stu-id="50573-124">Need more help?</span></span>

<span data-ttu-id="50573-125">你的金融机构是以下方案的最佳联系人：</span><span class="sxs-lookup"><span data-stu-id="50573-125">Your financial institution is the best contact for these scenarios:</span></span>

- <span data-ttu-id="50573-126">您未收到验证码。</span><span class="sxs-lookup"><span data-stu-id="50573-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="50573-127">提交验证码后，验证过程不起作用。</span><span class="sxs-lookup"><span data-stu-id="50573-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="50573-128">不确定信用卡的联系人信息是否正确。</span><span class="sxs-lookup"><span data-stu-id="50573-128">You're not sure if the contact info for your credit card is correct.</span></span>
