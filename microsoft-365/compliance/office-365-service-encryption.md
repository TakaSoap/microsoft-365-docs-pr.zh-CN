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
ms.openlocfilehash: fbd2672986046a4f6d25c47b011eaef0a87d90e1
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777046"
---
# <a name="service-encryption"></a><span data-ttu-id="8a170-103">服务加密</span><span class="sxs-lookup"><span data-stu-id="8a170-103">Service Encryption</span></span>

<span data-ttu-id="8a170-104">除了使用卷级加密之外，Exchange Online、Skype for Business、SharePoint Online 和 OneDrive for Business 还使用服务加密来加密客户数据。</span><span class="sxs-lookup"><span data-stu-id="8a170-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="8a170-105">服务加密允许两种密钥管理选项：</span><span class="sxs-lookup"><span data-stu-id="8a170-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="8a170-106">Microsoft 管理的密钥</span><span class="sxs-lookup"><span data-stu-id="8a170-106">Microsoft-managed keys</span></span>
<span data-ttu-id="8a170-107">Microsoft 管理所有加密密钥，包括用于服务加密的根密钥。</span><span class="sxs-lookup"><span data-stu-id="8a170-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="8a170-108">此选项当前默认为 Exchange Online、SharePoint Online、OneDrive for Business 启用。</span><span class="sxs-lookup"><span data-stu-id="8a170-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="8a170-109">除非决定使用客户密钥载入，否则 Microsoft 托管密钥提供默认服务加密。</span><span class="sxs-lookup"><span data-stu-id="8a170-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="8a170-110">如果以后决定在未遵循数据清除路径的情况下停止使用客户密钥，那么数据会使用 Microsoft 管理的密钥保持加密状态。</span><span class="sxs-lookup"><span data-stu-id="8a170-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="8a170-111">你的数据始终至少在此默认级别加密。</span><span class="sxs-lookup"><span data-stu-id="8a170-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="8a170-112">客户密钥</span><span class="sxs-lookup"><span data-stu-id="8a170-112">Customer Key</span></span>
<span data-ttu-id="8a170-113">你提供用于服务加密的根密钥，并且使用 Azure 密钥保管库管理这些密钥。</span><span class="sxs-lookup"><span data-stu-id="8a170-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="8a170-114">Microsoft 管理所有其他密钥。</span><span class="sxs-lookup"><span data-stu-id="8a170-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="8a170-115">此选项称为"客户密钥"，当前可用于 Exchange Online、SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="8a170-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="8a170-116"> (BYOK 高级加密。</span><span class="sxs-lookup"><span data-stu-id="8a170-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="8a170-117">请参阅 [增强 Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) 客户对原始公告的透明度和控制。) </span><span class="sxs-lookup"><span data-stu-id="8a170-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="8a170-118">服务加密具有多种优势：</span><span class="sxs-lookup"><span data-stu-id="8a170-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="8a170-119">在 BitLocker 顶部提供一层额外的保护。</span><span class="sxs-lookup"><span data-stu-id="8a170-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="8a170-120">使 Windows 操作系统管理员无法访问操作系统存储或处理的应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="8a170-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="8a170-121">包括一个客户密钥选项，该选项允许多租户服务提供每个租户密钥管理。</span><span class="sxs-lookup"><span data-stu-id="8a170-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="8a170-122">增强 Microsoft 365 满足对加密有特定合规性要求的客户的需求的能力。</span><span class="sxs-lookup"><span data-stu-id="8a170-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="8a170-123">使用客户密钥，可以使用本地硬件服务模块 (HSM) 或 Azure Key Vault (AKV) 。</span><span class="sxs-lookup"><span data-stu-id="8a170-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="8a170-124">无论您如何生成密钥，都可以使用 AKV 来控制和管理 Office 365 使用的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="8a170-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="8a170-125">密钥存储在 AKV 中后，可以用作加密邮箱数据或文件的其中一个密钥链的根。</span><span class="sxs-lookup"><span data-stu-id="8a170-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="8a170-126">客户密钥的另一个好处是，你可以控制 Microsoft 处理数据的能力。</span><span class="sxs-lookup"><span data-stu-id="8a170-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="8a170-127">如果要从 Office 365 中删除数据，例如想要终止 Microsoft 服务或删除云中存储的部分数据，可以这样做，并使用客户密钥作为技术控制。</span><span class="sxs-lookup"><span data-stu-id="8a170-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="8a170-128">删除数据可确保包括 Microsoft 在内的任何人无法访问或处理数据。</span><span class="sxs-lookup"><span data-stu-id="8a170-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="8a170-129">客户密钥是对用于控制 Microsoft 人员访问数据的客户密码箱的补充。</span><span class="sxs-lookup"><span data-stu-id="8a170-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="8a170-130">若要了解如何为 Microsoft 365 for Exchange Online、Skype for Business、SharePoint Online（包括团队网站和 OneDrive for Business）设置客户密钥，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8a170-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="8a170-131">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="8a170-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="8a170-132">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="8a170-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="8a170-133">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="8a170-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="8a170-134">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="8a170-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="8a170-135">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="8a170-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

