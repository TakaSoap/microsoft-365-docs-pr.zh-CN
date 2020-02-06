---
title: Office 365 服务加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：了解 Microsoft Office 365 中的数据恢复能力。
ms.openlocfilehash: 5b22584e677dd4815b991b4e95b5ad59feb2fbc2
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799542"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="a0825-103">Office 365 服务加密</span><span class="sxs-lookup"><span data-stu-id="a0825-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="a0825-104">除了使用卷级加密之外，Exchange Online、Skype for business、SharePoint Online 和 OneDrive for business 还使用服务加密来加密客户数据。</span><span class="sxs-lookup"><span data-stu-id="a0825-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="a0825-105">服务加密允许两个密钥管理选项：</span><span class="sxs-lookup"><span data-stu-id="a0825-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="a0825-106">Microsoft 管理所有加密密钥。</span><span class="sxs-lookup"><span data-stu-id="a0825-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="a0825-107">（此选项目前在 SharePoint Online、OneDrive for business 和 Skype for Business 中可用。）</span><span class="sxs-lookup"><span data-stu-id="a0825-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="a0825-108">客户提供用于服务加密的根键，并且客户使用 Azure Key Vault 管理这些密钥。</span><span class="sxs-lookup"><span data-stu-id="a0825-108">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault.</span></span> <span data-ttu-id="a0825-109">Microsoft 管理所有其他密钥。</span><span class="sxs-lookup"><span data-stu-id="a0825-109">Microsoft manages all other keys.</span></span> <span data-ttu-id="a0825-110">此选项称为 "客户密钥"，目前适用于 Exchange Online、SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="a0825-110">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="a0825-111">（以前称为使用 BYOK 的高级加密。</span><span class="sxs-lookup"><span data-stu-id="a0825-111">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="a0825-112">请参阅增强针对原始公告的[Office 365 客户的透明度和控制](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)。</span><span class="sxs-lookup"><span data-stu-id="a0825-112">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="a0825-113">服务加密提供了多项优势。</span><span class="sxs-lookup"><span data-stu-id="a0825-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="a0825-114">例如，客户密钥：</span><span class="sxs-lookup"><span data-stu-id="a0825-114">For example, Customer Key:</span></span>

- <span data-ttu-id="a0825-115">在强加密保护之上提供权限保护和管理功能。</span><span class="sxs-lookup"><span data-stu-id="a0825-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="a0825-116">包括一个 "客户密钥" 选项，该选项使多租户服务能够提供每租户密钥管理。</span><span class="sxs-lookup"><span data-stu-id="a0825-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="a0825-117">提供 Windows 操作系统管理员的分离，以访问由操作系统存储或处理的客户数据。</span><span class="sxs-lookup"><span data-stu-id="a0825-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="a0825-118">增强了 Office 365 满足有关加密合规性要求的客户需求的能力。</span><span class="sxs-lookup"><span data-stu-id="a0825-118">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="a0825-119">客户密钥</span><span class="sxs-lookup"><span data-stu-id="a0825-119">Customer Key</span></span>

<span data-ttu-id="a0825-120">使用 "客户密钥"，可以使用本地硬件服务模块（HSM）或 Azure Key Vault （AKV）生成自己的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="a0825-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="a0825-121">无论生成密钥的方式如何，都可以使用 AKV 来控制和管理 Office 365 使用的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="a0825-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="a0825-122">密钥存储在 AKV 中后，可以将其用作加密邮箱数据的 keychains 之一的根。</span><span class="sxs-lookup"><span data-stu-id="a0825-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="a0825-123">客户密钥的另一个好处是，您可以控制 Microsoft 处理数据的能力。</span><span class="sxs-lookup"><span data-stu-id="a0825-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="a0825-124">如果要从 Office 365 中删除数据（例如，如果要使用 Microsoft 终止服务或删除云中存储的部分数据），则可以执行此操作，并将客户密钥用作技术控制。</span><span class="sxs-lookup"><span data-stu-id="a0825-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="a0825-125">这可确保任何人（包括 Microsoft）都不能访问或处理数据。</span><span class="sxs-lookup"><span data-stu-id="a0825-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="a0825-126">客户密钥补充并补充了用于控制 Microsoft 人员对数据的访问权限的客户密码箱的补充。</span><span class="sxs-lookup"><span data-stu-id="a0825-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="a0825-127">若要了解如何为 Exchange Online、Skype for Business、SharePoint Online （包括工作组网站和 OneDrive for Business）设置适用于 Office 365 的客户密钥，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="a0825-127">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="a0825-128">Office 365 中的客户密钥的服务加密</span><span class="sxs-lookup"><span data-stu-id="a0825-128">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="a0825-129">设置适用于 Office 的客户密钥365</span><span class="sxs-lookup"><span data-stu-id="a0825-129">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="a0825-130">管理 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="a0825-130">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="a0825-131">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="a0825-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="a0825-132">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="a0825-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 