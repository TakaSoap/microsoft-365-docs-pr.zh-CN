---
title: 服务加密
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
ms.openlocfilehash: 4759cfda13ab5044ddf5980d7e61004e9e7626fa
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024772"
---
# <a name="service-encryption"></a><span data-ttu-id="6ff38-103">服务加密</span><span class="sxs-lookup"><span data-stu-id="6ff38-103">Service Encryption</span></span>

<span data-ttu-id="6ff38-104">除了使用卷级加密之外，Exchange Online、Skype for business、SharePoint Online 和 OneDrive for business 还使用服务加密来加密客户数据。</span><span class="sxs-lookup"><span data-stu-id="6ff38-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="6ff38-105">服务加密允许两个密钥管理选项：</span><span class="sxs-lookup"><span data-stu-id="6ff38-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="6ff38-106">Microsoft 托管密钥</span><span class="sxs-lookup"><span data-stu-id="6ff38-106">Microsoft managed keys</span></span>
<span data-ttu-id="6ff38-107">Microsoft 管理所有加密密钥，包括服务加密的根密钥。</span><span class="sxs-lookup"><span data-stu-id="6ff38-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="6ff38-108">此选项目前在 SharePoint Online 和 OneDrive for business 中可用。</span><span class="sxs-lookup"><span data-stu-id="6ff38-108">This option is currently available in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="6ff38-109">此选项当前正在为 Exchange Online 推出。</span><span class="sxs-lookup"><span data-stu-id="6ff38-109">This option is currently being rolled out for Exchange Online.</span></span> <span data-ttu-id="6ff38-110">Microsoft 托管密钥提供了默认服务加密，除非你决定使用客户密钥进行板载。</span><span class="sxs-lookup"><span data-stu-id="6ff38-110">Microsoft managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="6ff38-111">如果以后你决定停止使用客户密钥，而不考虑数据清除路径，则你的数据将使用 Microsoft 托管密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="6ff38-111">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft managed keys.</span></span> <span data-ttu-id="6ff38-112">你的数据始终至少在此默认级别进行加密。</span><span class="sxs-lookup"><span data-stu-id="6ff38-112">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="6ff38-113">客户密钥</span><span class="sxs-lookup"><span data-stu-id="6ff38-113">Customer Key</span></span>
<span data-ttu-id="6ff38-114">提供用于服务加密的根密钥，并使用 Azure Key Vault 管理这些密钥。</span><span class="sxs-lookup"><span data-stu-id="6ff38-114">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="6ff38-115">Microsoft 管理所有其他密钥。</span><span class="sxs-lookup"><span data-stu-id="6ff38-115">Microsoft manages all other keys.</span></span> <span data-ttu-id="6ff38-116">此选项称为 "客户密钥"，目前适用于 Exchange Online、SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="6ff38-116">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="6ff38-117">（以前称为使用 BYOK 的高级加密。</span><span class="sxs-lookup"><span data-stu-id="6ff38-117">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="6ff38-118">请参阅增强针对原始公告的[Office 365 客户的透明度和控制](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)。</span><span class="sxs-lookup"><span data-stu-id="6ff38-118">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="6ff38-119">服务加密提供了多项优势。</span><span class="sxs-lookup"><span data-stu-id="6ff38-119">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="6ff38-120">例如，客户密钥：</span><span class="sxs-lookup"><span data-stu-id="6ff38-120">For example, Customer Key:</span></span>

- <span data-ttu-id="6ff38-121">在强加密保护之上提供权限保护和管理功能。</span><span class="sxs-lookup"><span data-stu-id="6ff38-121">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="6ff38-122">包括一个 "客户密钥" 选项，该选项使多租户服务能够提供每租户密钥管理。</span><span class="sxs-lookup"><span data-stu-id="6ff38-122">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="6ff38-123">提供 Windows 操作系统管理员的分离，以访问由操作系统存储或处理的客户数据。</span><span class="sxs-lookup"><span data-stu-id="6ff38-123">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="6ff38-124">增强了 Microsoft 365 满足具有有关加密合规性要求的客户需求的能力。</span><span class="sxs-lookup"><span data-stu-id="6ff38-124">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="6ff38-125">使用 "客户密钥"，可以使用本地硬件服务模块（HSM）或 Azure Key Vault （AKV）生成自己的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="6ff38-125">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="6ff38-126">无论生成密钥的方式如何，都可以使用 AKV 来控制和管理 Office 365 使用的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="6ff38-126">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="6ff38-127">密钥存储在 AKV 中后，可以将其用作加密邮箱数据的 keychains 之一的根。</span><span class="sxs-lookup"><span data-stu-id="6ff38-127">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="6ff38-128">客户密钥的另一个好处是，您可以控制 Microsoft 处理数据的能力。</span><span class="sxs-lookup"><span data-stu-id="6ff38-128">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="6ff38-129">如果要从 Office 365 中删除数据（例如，如果要使用 Microsoft 终止服务或删除云中存储的部分数据），则可以执行此操作，并将客户密钥用作技术控制。</span><span class="sxs-lookup"><span data-stu-id="6ff38-129">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="6ff38-130">这可确保任何人（包括 Microsoft）都不能访问或处理数据。</span><span class="sxs-lookup"><span data-stu-id="6ff38-130">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="6ff38-131">客户密钥补充并补充了用于控制 Microsoft 人员对数据的访问权限的客户密码箱的补充。</span><span class="sxs-lookup"><span data-stu-id="6ff38-131">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="6ff38-132">若要了解如何设置用于 Exchange Online、Skype for Business、SharePoint Online （包括工作组网站和 OneDrive for business）的 Microsoft 365 客户密钥，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6ff38-132">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="6ff38-133">使用客户密钥进行服务加密</span><span class="sxs-lookup"><span data-stu-id="6ff38-133">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="6ff38-134">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="6ff38-134">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="6ff38-135">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="6ff38-135">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="6ff38-136">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="6ff38-136">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="6ff38-137">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="6ff38-137">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

