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
description: 高级邮件加密通过使管理员能够更好地使用受保护的邮件来帮助组织满足其合规性义务。
ms.openlocfilehash: 0e28bd283b6a7d1666d5db9b71040d2f377adffe
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626890"
---
# <a name="advanced-message-encryption"></a><span data-ttu-id="c8dd3-103">高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="c8dd3-103">Advanced Message Encryption</span></span>

<span data-ttu-id="c8dd3-104">Office 365 高级邮件加密包含在[Microsoft 365 企业版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 e5 （非盈利员工定价）、Office 365 企业版 E5 （非盈利员工定价）和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="c8dd3-105">如果您的组织有一个不包含 Office 365 高级邮件加密的订阅，则可以使用 microsoft 365 E5 合规性 SKU 加载项购买 Microsoft 365 E3 的订阅。 microsoft 365 E3 （非盈利员工定价）或 Office 365 高级合规性 SKU 外接程序 for Microsoft 365 E3、Microsoft 365 E3 （非盈利性员工定价）、Office 365 Sku 或 microsoft 365 E5/A5 信息保护和调控 SKU 附加 Microsoft 365 A3/E3。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), Office 365 SKUs, or the Microsoft 365 E5/A5 Information Protection and Governance SKU add-on for Microsoft 365 A3/E3.</span></span>

<span data-ttu-id="c8dd3-106">高级邮件加密帮助客户满足法规遵从性义务，这些要求对外部收件人和对加密电子邮件的访问权限要求更灵活的控制。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-106">Advanced Message Encryption helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="c8dd3-107">使用 Office 365 中的高级邮件加密，可以控制使用自动策略在组织外共享的敏感电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-107">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="c8dd3-108">您可以配置这些策略以标识敏感信息类型（如 PII、财务或运行状况 Id），也可以使用关键字来增强保护。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-108">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="c8dd3-109">配置策略后，您可以使用自定义品牌的电子邮件模板对策略进行配对，然后添加一个到期日期，以对符合该策略的电子邮件进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-109">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="c8dd3-110">此外，管理员可以随时撤销对邮件的访问权限，从而进一步控制在外部通过安全 web 门户访问的加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-110">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="c8dd3-111">您只能撤销和设置发送给外部收件人的电子邮件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-111">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="c8dd3-112">开始使用 Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="c8dd3-112">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="c8dd3-113">以下文章介绍了如何设置和使用高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-113">The following articles describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="c8dd3-114">您的组织必须具有包含 Office 365 高级邮件加密的订阅。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-114">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="c8dd3-115">有关受支持订阅的详细信息，请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-115">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="c8dd3-116">如果尚未设置 Office 365 邮件加密，请参阅[设置新的 office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-116">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="c8dd3-117">使用高级邮件加密时，您并不局限于单个品牌模板。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-117">With Advanced Message Encryption you're not limited to a single branding template.</span></span> <span data-ttu-id="c8dd3-118">相反，您可以创建和使用多个品牌打造模板。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-118">Instead, you can create and use multiple branding templates.</span></span> <span data-ttu-id="c8dd3-119">有关信息，请参阅[将组织的品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-119">For information, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>

<span data-ttu-id="c8dd3-120">[为通过 Office 365 高级邮件加密加密的电子邮件设置到期日期](ome-advanced-expiration.md)。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-120">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="c8dd3-121">使用自动策略控制在组织外部共享的敏感电子邮件，从而通过将安全 web 门户转到加密电子邮件来实现访问权限，从而增强保护。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-121">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="c8dd3-122">[撤消由 Office 365 高级邮件加密加密的电子邮件](revoke-ome-encrypted-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-122">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="c8dd3-123">控制在组织外共享的敏感电子邮件，并通过将访问安全的 web 门户转到加密电子邮件来增强保护。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-123">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  

<span data-ttu-id="c8dd3-124">使用 Office 365 高级邮件加密，无论您何时应用自定义品牌打造模板，Microsoft 都会将包装应用于与应用该模板的邮件流规则相适应的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-124">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Microsoft applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="c8dd3-125">您只能撤消邮件并将到期日期应用到用户通过门户接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-125">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="c8dd3-126">也就是说，应用了自定义品牌打造模板的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-126">In other words, email that has a custom branding template applied.</span></span> <span data-ttu-id="c8dd3-127">有关详细信息和示例，请参阅[确保所有外部收件人使用 OME 门户阅读加密邮件](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)中的指南。</span><span class="sxs-lookup"><span data-stu-id="c8dd3-127">For more information and an example, see the guidance in [Ensure all external recipients use the OME Portal to read encrypted mail](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).</span></span>
