---
title: 为使用 Office 365 高级邮件加密进行加密的电子邮件设置到期日期
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 使用 Office 365 高级邮件加密通过自定义品牌化模板设置电子邮件的过期日期来扩展电子邮件的安全性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd018e55592e5b17149edf1a4dc0907c0184417
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769162"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="71ed9-103">为使用 Office 365 高级邮件加密进行加密的电子邮件设置到期日期</span><span class="sxs-lookup"><span data-stu-id="71ed9-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="71ed9-104">Office 365 高级邮件加密包含在 [Microsoft 365 企业版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 e5 (非盈利性员工定价) 、Office 365 企业版 E5 (非盈利性员工定价) 和 Office 365 教育版 A5。</span><span class="sxs-lookup"><span data-stu-id="71ed9-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="71ed9-105">如果您的组织具有不包含 Office 365 高级邮件加密的订阅，则可以使用 microsoft 365 E5 兼容性 SKU 附加 Microsoft 365 E3、Microsoft 365 E3 (非盈利性的员工定价) 或 Office 365 高级合规性 SKU 附加 for Microsoft 365 E3、Microsoft 365 E3 (非盈利性员工定价) 或 Office 365 Sku 购买。</span><span class="sxs-lookup"><span data-stu-id="71ed9-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="71ed9-106">您可以使用您的用户发送给使用 OME 门户访问加密电子邮件的外部收件人的电子邮件的邮件过期。</span><span class="sxs-lookup"><span data-stu-id="71ed9-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="71ed9-107">您可以通过使用在 Windows PowerShell 中指定过期日期的自定义品牌模板，强制收件人使用 OME 门户查看并回复您的组织发送的加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71ed9-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="71ed9-108">作为 Office 365 全局管理员，当您应用公司品牌以自定义组织的电子邮件的外观时，您还可以为这些电子邮件指定过期时间。</span><span class="sxs-lookup"><span data-stu-id="71ed9-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="71ed9-109">使用 Office 365 高级邮件加密，可以为来自您的组织的加密电子邮件创建多个模板。</span><span class="sxs-lookup"><span data-stu-id="71ed9-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="71ed9-110">使用模板，可以控制收件人访问您的用户发送的邮件的时间长短。</span><span class="sxs-lookup"><span data-stu-id="71ed9-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="71ed9-111">当最终用户收到设置了过期日期的邮件时，用户会看到包装电子邮件中的到期日期。</span><span class="sxs-lookup"><span data-stu-id="71ed9-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="71ed9-112">如果用户尝试打开已过期的邮件，则会在 OME 门户中显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="71ed9-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="71ed9-113">您只能将电子邮件的到期日期设置为外部收件人。</span><span class="sxs-lookup"><span data-stu-id="71ed9-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="71ed9-114">使用 Office 365 高级邮件加密，无论何时应用自定义品牌打造，Office 365 都会将包装应用于与应用该模板的邮件流规则相适应的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71ed9-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="71ed9-115">此外，如果使用自定义品牌，则只能使用过期时间。</span><span class="sxs-lookup"><span data-stu-id="71ed9-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="71ed9-116">使用 PowerShell 创建自定义品牌模板以强制邮件过期</span><span class="sxs-lookup"><span data-stu-id="71ed9-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="71ed9-117">使用组织中具有全局管理员权限的帐户[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="71ed9-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="71ed9-118">运行 New-OMEConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71ed9-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="71ed9-119">其中：</span><span class="sxs-lookup"><span data-stu-id="71ed9-119">Where:</span></span>

- <span data-ttu-id="71ed9-120">`Identity` 是自定义模板的名称。</span><span class="sxs-lookup"><span data-stu-id="71ed9-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="71ed9-121">`ExternalMailExpiryInDays` 标识收件人在过期前可保留邮件的天数。</span><span class="sxs-lookup"><span data-stu-id="71ed9-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="71ed9-122">可以使用1到730天之间的任意值。</span><span class="sxs-lookup"><span data-stu-id="71ed9-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="71ed9-123">有关 Office 365 高级邮件加密的详细信息</span><span class="sxs-lookup"><span data-stu-id="71ed9-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="71ed9-124">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="71ed9-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="71ed9-125">撤销使用 Office 365 高级邮件加密进行加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="71ed9-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="71ed9-126">邮件策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="71ed9-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
