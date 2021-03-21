---
title: 高级邮件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 高级邮件加密使管理员能够使用受保护的邮件执行更多操作，帮助组织履行合规性义务。
ms.openlocfilehash: 8c650c47c1853102e4e2d142040e49724ef707e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923952"
---
# <a name="advanced-message-encryption"></a><span data-ttu-id="f3656-103">高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="f3656-103">Advanced Message Encryption</span></span>

<span data-ttu-id="f3656-104">Office 365 高级邮件加密包含在 [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/home)企业版 E5、Office 365 E5、Microsoft 365 E5 (非营利组织员工定价) 、Office 365 企业版 E5 (非营利组织版员工定价) 和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="f3656-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="f3656-105">如果你的组织订阅不包含 Office 365 高级邮件加密，可以使用 Microsoft 365 E365 E3 的 Microsoft 365 E5 合规性 SKU 加载项购买。 Microsoft 365 E3 (非营利组织员工定价) 或适用于 Microsoft 365 E3 的 Office 365 高级合规性 SKU 加载项、Microsoft 365 E3 (非营利组织员工定价) 、Office 365 SKU 或 Microsoft 365 E5/A5 信息保护和管理 SKU 附加项。</span><span class="sxs-lookup"><span data-stu-id="f3656-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), Office 365 SKUs, or the Microsoft 365 E5/A5 Information Protection and Governance SKU add-on for Microsoft 365 A3/E3.</span></span>

<span data-ttu-id="f3656-106">高级邮件加密可帮助客户履行合规性义务，这些义务要求对外部收件人及其对加密电子邮件的访问进行更灵活的控制。</span><span class="sxs-lookup"><span data-stu-id="f3656-106">Advanced Message Encryption helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="f3656-107">使用 Office 365 中的高级邮件加密，可以使用自动策略控制在组织外部共享的敏感电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f3656-107">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="f3656-108">您可以配置这些策略以标识敏感信息类型，如 PII、财务或运行状况标识，或者您可以使用关键字来增强保护。</span><span class="sxs-lookup"><span data-stu-id="f3656-108">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="f3656-109">配置策略后，将策略与自定义品牌电子邮件模板配对，然后添加过期日期，以对符合策略的电子邮件进行额外控制。</span><span class="sxs-lookup"><span data-stu-id="f3656-109">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="f3656-110">此外，管理员还可以随时撤销对邮件的访问，以进一步控制通过安全 Web 门户从外部访问的加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f3656-110">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="f3656-111">只能撤消和设置发送给外部收件人的电子邮件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="f3656-111">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="f3656-112">Office 365 高级邮件加密入门</span><span class="sxs-lookup"><span data-stu-id="f3656-112">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="f3656-113">以下文章介绍如何设置和使用高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="f3656-113">The following articles describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="f3656-114">您的组织必须具有包含 Office 365 高级邮件加密的订阅。</span><span class="sxs-lookup"><span data-stu-id="f3656-114">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="f3656-115">有关受支持的订阅的详细信息，请参阅邮件 [策略和合规性服务说明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="f3656-115">For detailed information about supported subscriptions, see the [Message policy and compliance service description](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="f3656-116">如果尚未设置 Office 365 邮件加密，请参阅设置 [新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="f3656-116">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="f3656-117">使用高级邮件加密，不限于单个品牌模板。</span><span class="sxs-lookup"><span data-stu-id="f3656-117">With Advanced Message Encryption you're not limited to a single branding template.</span></span> <span data-ttu-id="f3656-118">相反，你可以创建和使用多个品牌模板。</span><span class="sxs-lookup"><span data-stu-id="f3656-118">Instead, you can create and use multiple branding templates.</span></span> <span data-ttu-id="f3656-119">有关信息，[请参阅将组织的品牌添加到加密邮件。](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="f3656-119">For information, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>

<span data-ttu-id="f3656-120">[设置由 Office 365 高级邮件加密加密的电子邮件的到期日期](ome-advanced-expiration.md)。</span><span class="sxs-lookup"><span data-stu-id="f3656-120">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="f3656-121">使用自动策略控制在组织外部共享的敏感电子邮件，这些策略通过通过安全 Web 门户过期对加密电子邮件的访问来增强保护。</span><span class="sxs-lookup"><span data-stu-id="f3656-121">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="f3656-122">[撤销由 Office 365 高级邮件加密加密的电子邮件](revoke-ome-encrypted-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="f3656-122">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="f3656-123">控制在组织外部共享的敏感电子邮件，并通过撤销通过安全 Web 门户对加密电子邮件的访问来增强保护。</span><span class="sxs-lookup"><span data-stu-id="f3656-123">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  

<span data-ttu-id="f3656-124">借助 Office 365 高级邮件加密，每当应用自定义品牌模板时，Microsoft 都向符合模板所应用的邮件流规则的电子邮件应用包装器。</span><span class="sxs-lookup"><span data-stu-id="f3656-124">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Microsoft applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="f3656-125">只能撤销邮件，并应用过期日期至用户通过门户接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3656-125">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="f3656-126">换句话说，应用了自定义品牌模板的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f3656-126">In other words, email that has a custom branding template applied.</span></span> <span data-ttu-id="f3656-127">有关详细信息和示例，请参阅 Ensure [all external recipients use the OME Portal to read encrypted mail 中的指南](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)。</span><span class="sxs-lookup"><span data-stu-id="f3656-127">For more information and an example, see the guidance in [Ensure all external recipients use the OME Portal to read encrypted mail](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).</span></span>