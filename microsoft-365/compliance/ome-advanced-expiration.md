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
description: 使用 Office 365 高级邮件加密自定义品牌模板设置电子邮件的到期日期，以扩展电子邮件安全性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927782"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="00410-103">为使用 Office 365 高级邮件加密进行加密的电子邮件设置到期日期</span><span class="sxs-lookup"><span data-stu-id="00410-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="00410-104">Office 365 高级邮件加密[包含在 Microsoft 365 企业版 E5、Office 365 E5、Microsoft 365 E5 (](https://www.microsoft.com/microsoft-365/enterprise/home)非营利组织员工定价) 、Office 365 企业版 E5 (非营利组织员工定价) 和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="00410-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="00410-105">如果你的组织订阅不包含 Office 365 高级邮件加密，可以使用 Microsoft 365 E3 的 Microsoft 365 E5 合规 SKU 加载项、Microsoft 365 E3 (非营利组织员工定价) 或 Microsoft 365 E3、Microsoft 365 E3 (非营利组织员工定价) 或 Office 365 SKU 的 Office 365 高级合规版 SKU 加载项购买它。</span><span class="sxs-lookup"><span data-stu-id="00410-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="00410-106">可以在用户发送给使用 OME 门户访问加密电子邮件的外部收件人的电子邮件上使用邮件过期。</span><span class="sxs-lookup"><span data-stu-id="00410-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="00410-107">您强制收件人使用 OME 门户查看和回复由组织发送的加密电子邮件，具体使用自定义品牌模板指定 Windows PowerShell 中的到期日期。</span><span class="sxs-lookup"><span data-stu-id="00410-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="00410-108">作为Office 365管理员，当你应用公司品牌自定义组织电子邮件的外观时，还可以指定这些电子邮件的过期时间。</span><span class="sxs-lookup"><span data-stu-id="00410-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="00410-109">使用 Office 365 高级邮件加密，你可以为来自组织的加密电子邮件创建多个模板。</span><span class="sxs-lookup"><span data-stu-id="00410-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="00410-110">使用模板，您可以控制收件人有权访问用户发送的邮件的多久。</span><span class="sxs-lookup"><span data-stu-id="00410-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="00410-111">当最终用户收到设置了过期日期的邮件时，用户将看到包装电子邮件中的到期日期。</span><span class="sxs-lookup"><span data-stu-id="00410-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="00410-112">如果用户尝试打开过期的邮件，OME 门户中将显示错误。</span><span class="sxs-lookup"><span data-stu-id="00410-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="00410-113">只能为发送给外部收件人的电子邮件设置到期日期。</span><span class="sxs-lookup"><span data-stu-id="00410-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="00410-114">使用 Office 365 高级邮件加密，每当应用自定义品牌时，Office 365将包装应用于符合您应用模板的邮件流规则的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="00410-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="00410-115">此外，只有当使用自定义品牌时，才能使用过期。</span><span class="sxs-lookup"><span data-stu-id="00410-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="00410-116">使用 PowerShell 创建自定义品牌模板以强制邮件过期</span><span class="sxs-lookup"><span data-stu-id="00410-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="00410-117">连接Exchange Online组织中具有全局管理员权限的帐户来使用[PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="00410-117">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="00410-118">运行 New-OMEConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00410-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="00410-119">其中：</span><span class="sxs-lookup"><span data-stu-id="00410-119">Where:</span></span>

- <span data-ttu-id="00410-120">`Identity` 是自定义模板的名称。</span><span class="sxs-lookup"><span data-stu-id="00410-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="00410-121">`ExternalMailExpiryInDays` 标识收件人在邮件过期之前可以保留邮件的天数。</span><span class="sxs-lookup"><span data-stu-id="00410-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="00410-122">可以使用 1 到 730 天之间的任意值。</span><span class="sxs-lookup"><span data-stu-id="00410-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="00410-123">有关 Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="00410-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="00410-124">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="00410-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="00410-125">撤销使用 Office 365 高级邮件加密进行加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="00410-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="00410-126">邮件策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="00410-126">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)