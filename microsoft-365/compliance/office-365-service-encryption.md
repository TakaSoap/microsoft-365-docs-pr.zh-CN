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
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：了解 Microsoft Office 365 中服务层的数据加密。
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193458"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="f157e-103">Office 365 服务加密</span><span class="sxs-lookup"><span data-stu-id="f157e-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="f157e-104">除了将 BitLocker 用于卷级加密之外，Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队也使用服务加密来加密客户数据。</span><span class="sxs-lookup"><span data-stu-id="f157e-104">In addition to using BitLocker for volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="f157e-105">服务加密允许两个密钥管理选项：</span><span class="sxs-lookup"><span data-stu-id="f157e-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="f157e-106">Microsoft 管理所有加密密钥。</span><span class="sxs-lookup"><span data-stu-id="f157e-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="f157e-107">此选项目前在 SharePoint Online、OneDrive for business、Skype for business 和团队聊天版中可用。</span><span class="sxs-lookup"><span data-stu-id="f157e-107">This option is currently available in SharePoint Online, OneDrive for Business, Skype for Business, and Teams chats.</span></span> <span data-ttu-id="f157e-108">默认情况下，使用 Microsoft 托管密钥对数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="f157e-108">Your data is encrypted by default with Microsoft managed keys.</span></span>

- <span data-ttu-id="f157e-109">您的组织提供根键。</span><span class="sxs-lookup"><span data-stu-id="f157e-109">Your organization supplies the root keys.</span></span> <span data-ttu-id="f157e-110">您可以使用 Azure Key Vault 管理这些密钥。</span><span class="sxs-lookup"><span data-stu-id="f157e-110">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="f157e-111">此选项称为 "客户密钥"。</span><span class="sxs-lookup"><span data-stu-id="f157e-111">This option is called Customer Key.</span></span> <span data-ttu-id="f157e-112">目前，客户密钥可用于 Exchange Online、SharePoint Online、OneDrive for business、Skype for business 和团队文件。</span><span class="sxs-lookup"><span data-stu-id="f157e-112">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="f157e-113">如果使用客户密钥，这些密钥将替换 Microsoft 托管密钥以加密数据。</span><span class="sxs-lookup"><span data-stu-id="f157e-113">If you use Customer Key, these keys replace Microsoft managed keys to encrypt your data.</span></span>

<span data-ttu-id="f157e-114">无论选择哪个选项，服务加密都会提供多种好处：</span><span class="sxs-lookup"><span data-stu-id="f157e-114">Regardless of the option you choose, service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="f157e-115">强制执行用户身份验证以检索和解密授权用户请求的数据。</span><span class="sxs-lookup"><span data-stu-id="f157e-115">Enforces user authentication to retrieve and decrypt data requested by an authorized user.</span></span>

- <span data-ttu-id="f157e-116">提供 Windows 操作系统管理员的分离，以访问由操作系统存储或处理的客户数据。</span><span class="sxs-lookup"><span data-stu-id="f157e-116">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="f157e-117">增强了 Office 365 满足有关加密合规性要求的客户需求的能力。</span><span class="sxs-lookup"><span data-stu-id="f157e-117">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="f157e-118">若要了解如何为 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队文件设置适用于 Office 365 的客户密钥，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="f157e-118">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files, see these articles:</span></span>

- [<span data-ttu-id="f157e-119">Office 365 中的客户密钥的服务加密</span><span class="sxs-lookup"><span data-stu-id="f157e-119">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="f157e-120">设置适用于 Office 的客户密钥365</span><span class="sxs-lookup"><span data-stu-id="f157e-120">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="f157e-121">管理 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="f157e-121">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="f157e-122">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="f157e-122">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="f157e-123">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="f157e-123">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
