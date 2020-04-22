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
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632237"
---
# <a name="service-encryption"></a><span data-ttu-id="5d471-103">服务加密</span><span class="sxs-lookup"><span data-stu-id="5d471-103">Service Encryption</span></span>

<span data-ttu-id="5d471-104">除了使用卷级加密之外，Exchange Online、Skype for business、SharePoint Online 和 OneDrive for business 还使用服务加密来加密客户数据。</span><span class="sxs-lookup"><span data-stu-id="5d471-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="5d471-105">服务加密允许两个密钥管理选项：</span><span class="sxs-lookup"><span data-stu-id="5d471-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="5d471-106">Microsoft 管理所有加密密钥。</span><span class="sxs-lookup"><span data-stu-id="5d471-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="5d471-107">（此选项目前在 SharePoint Online、OneDrive for business 和 Skype for Business 中可用。）</span><span class="sxs-lookup"><span data-stu-id="5d471-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="5d471-108">您的组织提供根键。</span><span class="sxs-lookup"><span data-stu-id="5d471-108">Your organization supplies the root keys.</span></span> <span data-ttu-id="5d471-109">您可以使用 Azure Key Vault 管理这些密钥。</span><span class="sxs-lookup"><span data-stu-id="5d471-109">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="5d471-110">此选项称为 "客户密钥"。</span><span class="sxs-lookup"><span data-stu-id="5d471-110">This option is called Customer Key.</span></span> <span data-ttu-id="5d471-111">目前，客户密钥可用于 Exchange Online、SharePoint Online、OneDrive for business、Skype for business 和团队文件。</span><span class="sxs-lookup"><span data-stu-id="5d471-111">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="5d471-112">如果使用客户密钥，这些密钥将替换 Microsoft 管理的密钥以加密数据。</span><span class="sxs-lookup"><span data-stu-id="5d471-112">If you use Customer Key, these keys replace Microsoft-managed keys to encrypt your data.</span></span>

<span data-ttu-id="5d471-113">服务加密提供了多项优势。</span><span class="sxs-lookup"><span data-stu-id="5d471-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="5d471-114">例如，客户密钥：</span><span class="sxs-lookup"><span data-stu-id="5d471-114">For example, Customer Key:</span></span>

- <span data-ttu-id="5d471-115">在强加密保护之上提供权限保护和管理功能。</span><span class="sxs-lookup"><span data-stu-id="5d471-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="5d471-116">包括一个 "客户密钥" 选项，该选项使多租户服务能够提供每租户密钥管理。</span><span class="sxs-lookup"><span data-stu-id="5d471-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="5d471-117">提供 Windows 操作系统管理员的分离，以访问由操作系统存储或处理的客户数据。</span><span class="sxs-lookup"><span data-stu-id="5d471-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="5d471-118">增强了 Microsoft 365 满足具有有关加密合规性要求的客户需求的能力。</span><span class="sxs-lookup"><span data-stu-id="5d471-118">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="5d471-119">客户密钥</span><span class="sxs-lookup"><span data-stu-id="5d471-119">Customer Key</span></span>

<span data-ttu-id="5d471-120">使用 "客户密钥"，可以使用本地硬件服务模块（HSM）或 Azure Key Vault （AKV）生成自己的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="5d471-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="5d471-121">无论生成密钥的方式如何，都可以使用 AKV 来控制和管理 Office 365 使用的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="5d471-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="5d471-122">密钥存储在 AKV 中后，可以将其用作加密邮箱数据的 keychains 之一的根。</span><span class="sxs-lookup"><span data-stu-id="5d471-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="5d471-123">客户密钥的另一个好处是，您可以控制 Microsoft 处理数据的能力。</span><span class="sxs-lookup"><span data-stu-id="5d471-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="5d471-124">如果要从 Office 365 中删除数据（例如，如果要使用 Microsoft 终止服务或删除云中存储的部分数据），则可以执行此操作，并将客户密钥用作技术控制。</span><span class="sxs-lookup"><span data-stu-id="5d471-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="5d471-125">这可确保任何人（包括 Microsoft）都不能访问或处理数据。</span><span class="sxs-lookup"><span data-stu-id="5d471-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="5d471-126">客户密钥补充并补充了用于控制 Microsoft 人员对数据的访问权限的客户密码箱的补充。</span><span class="sxs-lookup"><span data-stu-id="5d471-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="5d471-127">若要了解如何设置用于 Exchange Online、Skype for Business、SharePoint Online （包括工作组网站和 OneDrive for business）的 Microsoft 365 客户密钥，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="5d471-127">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="5d471-128">使用客户密钥进行服务加密</span><span class="sxs-lookup"><span data-stu-id="5d471-128">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="5d471-129">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="5d471-129">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="5d471-130">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="5d471-130">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="5d471-131">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="5d471-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="5d471-132">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="5d471-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
