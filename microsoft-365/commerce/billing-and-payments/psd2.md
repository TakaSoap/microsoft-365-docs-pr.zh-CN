---
title: 面向商业客户的付款服务指令2和强客户身份验证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 从2019年9月14日开始，需要在欧洲经济区域的31个国家/地区内的银行验证在付款可以处理之前进行在线购买的人员的身份。
keywords: 付款服务指令2，强大的客户身份验证，多重身份验证
ms.openlocfilehash: f59808d3735f10b57ed5c0cd279b6703b24a44a4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594703"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="f4c3d-104">面向商业客户的付款服务指令2和强客户身份验证</span><span class="sxs-lookup"><span data-stu-id="f4c3d-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="f4c3d-105">从2019年9月14日开始，需要在欧洲经济区域的31个国家/地区内的银行验证在付款可以处理之前进行在线购买的人员的身份。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-105">Starting on September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="f4c3d-106">此验证要求进行多重身份验证，以帮助确保你的在线购买安全且受到保护。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="f4c3d-107">对于某些国家/地区，此验证要求的日期将延迟。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-107">The date for this verification requirement will be delayed for some countries.</span></span> 

<span data-ttu-id="f4c3d-108">有关详细信息，请参阅[MICROSOFT 常见问题解答关于付款服务指令2和加强客户身份验证](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="f4c3d-109">何时需要多重身份验证？</span><span class="sxs-lookup"><span data-stu-id="f4c3d-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="f4c3d-110">目前，使用多重身份验证的此指令的验证要求仅适用于使用来自欧洲经济区域的31个国家/地区的银行信用卡的客户。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="f4c3d-111">有时，客户会因其现有订阅或服务的事件而提示他们采取的措施，有时会提示他们。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="f4c3d-112">客户操作</span><span class="sxs-lookup"><span data-stu-id="f4c3d-112">Customer Actions</span></span>

<span data-ttu-id="f4c3d-113">您的银行可能需要通过多重身份验证进行验证。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="f4c3d-114">一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="f4c3d-114">Some examples include:</span></span>
- <span data-ttu-id="f4c3d-115">注册新订阅</span><span class="sxs-lookup"><span data-stu-id="f4c3d-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="f4c3d-116">向订阅添加许可证</span><span class="sxs-lookup"><span data-stu-id="f4c3d-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="f4c3d-117">添加或替换用于支付订阅或服务的信用卡</span><span class="sxs-lookup"><span data-stu-id="f4c3d-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="f4c3d-118">在帐单配置文件上添加或替换信用卡</span><span class="sxs-lookup"><span data-stu-id="f4c3d-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="f4c3d-119">购买应用程序</span><span class="sxs-lookup"><span data-stu-id="f4c3d-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="f4c3d-120">订阅生命周期事件</span><span class="sxs-lookup"><span data-stu-id="f4c3d-120">Subscription lifecycle events</span></span>

<span data-ttu-id="f4c3d-121">定期付款的费用可能会失败。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="f4c3d-122">如果是这样，你将收到一封电子邮件，其中包含相关说明。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="f4c3d-123">系统将提示您响应验证请求，并提出您的当前付款。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="f4c3d-124">需要更多帮助吗？</span><span class="sxs-lookup"><span data-stu-id="f4c3d-124">Need more help?</span></span>

<span data-ttu-id="f4c3d-125">在以下情况下，您的金融机构是最佳联系：</span><span class="sxs-lookup"><span data-stu-id="f4c3d-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="f4c3d-126">您没有收到验证代码。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="f4c3d-127">提交验证代码后，验证过程不起作用。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="f4c3d-128">你不确定信用卡的联系信息是否正确。</span><span class="sxs-lookup"><span data-stu-id="f4c3d-128">You're not sure if the contact info for your credit card is correct.</span></span>