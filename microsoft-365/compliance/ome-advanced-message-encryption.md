---
title: Office 365 高级邮件加密
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/8/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 中的高级邮件加密帮助组织通过 Office 365 web 门户向加密电子邮件过期并撤销访问权限，从而帮助组织满足其合规性义务。
ms.openlocfilehash: eb6e95b1cbf24ab19df6a595c34721c84c831211
ms.sourcegitcommit: 27a7a373ca77375fdab0690a899135fad16c3cf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435506"
---
# <a name="office-365-advanced-message-encryption"></a><span data-ttu-id="1fc9a-103">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="1fc9a-103">Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="1fc9a-104">Office 365 高级邮件加密包含在[Microsoft 365 企业版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 e5 （非盈利员工定价）、Office 365 企业版 E5 （非盈利员工定价）和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="1fc9a-105">如果您的组织有一个不包含 Office 365 高级邮件加密的订阅，则可以使用 microsoft 365 E5 兼容性 SKU 附加项购买 Microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Office 365 高级适用于 Microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Office 365 Sku 的合规性 SKU 外接程序。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="1fc9a-106">Office 365 中的高级邮件加密帮助客户满足法规遵从性义务，这些要求对外部收件人和其加密电子邮件的访问权限要求更灵活的控制。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-106">Advanced Message Encryption in Office 365 helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="1fc9a-107">使用 Office 365 中的高级邮件加密，可以控制使用自动策略在组织外共享的敏感电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-107">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="1fc9a-108">您可以配置这些策略以标识敏感信息类型（如 PII、财务或运行状况 Id），也可以使用关键字来增强保护。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-108">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="1fc9a-109">配置策略后，您可以使用自定义品牌的电子邮件模板对策略进行配对，然后添加一个到期日期，以对符合该策略的电子邮件进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-109">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="1fc9a-110">此外，管理员可以随时撤销对邮件的访问权限，从而进一步控制在外部通过安全 web 门户访问的加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-110">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="1fc9a-111">您只能撤销和设置发送给外部收件人的电子邮件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-111">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

<span data-ttu-id="1fc9a-112">使用 Office 365 高级邮件加密时，无论您何时应用自定义品牌打造模板，Office 365 都会对适合您应用该模板的邮件流规则的电子邮件应用包装。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-112">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Office 365 applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="1fc9a-113">您只能撤消邮件并将到期日期应用到用户通过门户接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-113">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="1fc9a-114">也就是说，应用了自定义品牌打造模板的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-114">In other words, email that has a custom branding template applied.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="1fc9a-115">开始使用 Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="1fc9a-115">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="1fc9a-116">下列主题介绍了如何设置和使用高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-116">The following topics describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="1fc9a-117">您的组织必须具有包含 Office 365 高级邮件加密的订阅。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-117">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="1fc9a-118">有关受支持订阅的详细信息，请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-118">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="1fc9a-119">如果尚未设置 Office 365 邮件加密，请参阅[设置新的 office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-119">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="1fc9a-120">[为通过 Office 365 高级邮件加密加密的电子邮件设置到期日期](ome-advanced-expiration.md)。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-120">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="1fc9a-121">使用自动策略控制在组织外部共享的敏感电子邮件，从而通过将安全 web 门户转到加密电子邮件来实现访问权限，从而增强保护。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-121">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="1fc9a-122">[撤消由 Office 365 高级邮件加密加密的电子邮件](revoke-ome-encrypted-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-122">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="1fc9a-123">控制在组织外共享的敏感电子邮件，并通过将访问安全的 web 门户转到加密电子邮件来增强保护。</span><span class="sxs-lookup"><span data-stu-id="1fc9a-123">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  
