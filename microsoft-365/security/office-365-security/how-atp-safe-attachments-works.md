---
title: ATP 安全附件的工作原理
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用适用于 Office 365 的 ATP 安全附件，让您的组织免受恶意文件的安全。
ms.openlocfilehash: f4f355d4def1f108a72854c3796e0e9373cb5ef1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819396"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="a39b8-103">ATP 安全附件的工作原理</span><span class="sxs-lookup"><span data-stu-id="a39b8-103">How ATP Safe Attachments works</span></span>

<span data-ttu-id="a39b8-104">ATP 安全附件功能检查组织中人员的电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="a39b8-104">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="a39b8-105">如果 ATP 安全附件策略已就绪，并且该策略涵盖的人在 Office 365 中查看其电子邮件，则会检查其电子邮件附件，并根据 ATP 安全附件策略采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="a39b8-105">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="a39b8-106">根据您的策略定义方式，用户可以继续工作，而无需知道他们是否发送了恶意文件。</span><span class="sxs-lookup"><span data-stu-id="a39b8-106">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="a39b8-107">以下是有关工作的 ATP 安全附件的两个示例。</span><span class="sxs-lookup"><span data-stu-id="a39b8-107">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="a39b8-108">**示例1：电子邮件附件**假设收到电子邮件，其中包含附件。</span><span class="sxs-lookup"><span data-stu-id="a39b8-108">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="a39b8-109">如果附件是安全的还是实际包含旨在窃取用户的用户凭据的恶意软件，则不会这样。</span><span class="sxs-lookup"><span data-stu-id="a39b8-109">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="a39b8-110">在先生/她的组织中，安全管理员在几天前定义了 ATP 安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="a39b8-110">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="a39b8-111">使用 ATP 安全附件功能，在获得电子邮件附件之前，将在虚拟环境中打开并测试该附件。</span><span class="sxs-lookup"><span data-stu-id="a39b8-111">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="a39b8-112">如果认为附件是恶意的，则会自动将其删除。</span><span class="sxs-lookup"><span data-stu-id="a39b8-112">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="a39b8-113">如果附件是安全的，则会在您通过单击它时按预期方式打开。</span><span class="sxs-lookup"><span data-stu-id="a39b8-113">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="a39b8-114">**示例2： SharePoint Online 中的文件**假设 Jean 收到一个文件，并将其上载到 SharePoint Online 中的库中。</span><span class="sxs-lookup"><span data-stu-id="a39b8-114">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="a39b8-115">Jean 与团队的其余部分共享指向文件的链接，而不知道该文件实际是恶意的。</span><span class="sxs-lookup"><span data-stu-id="a39b8-115">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="a39b8-116">幸运的是， [SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)会检测恶意文件并阻止它。</span><span class="sxs-lookup"><span data-stu-id="a39b8-116">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="a39b8-117">几天后，Chris 将转到 "打开" 文档。</span><span class="sxs-lookup"><span data-stu-id="a39b8-117">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="a39b8-118">尽管 Chris 可以看到该文件，Chris 也无法打开或共享该文件，这将保护 Chris 的计算机和恶意文件中的其他人。</span><span class="sxs-lookup"><span data-stu-id="a39b8-118">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="a39b8-119">ATP 安全附件策略可应用于组织中的特定用户或组，或应用于整个域。</span><span class="sxs-lookup"><span data-stu-id="a39b8-119">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="a39b8-120">此外，还可以将 ATP 安全附件策略配置为在扫描实际附件时使用占位符附件。</span><span class="sxs-lookup"><span data-stu-id="a39b8-120">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="a39b8-121">若要了解详细信息，请参阅**[在 Office 365 中设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)**。</span><span class="sxs-lookup"><span data-stu-id="a39b8-121">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="a39b8-122">ATP 安全附件扫描发生在数据所在的同一区域中。</span><span class="sxs-lookup"><span data-stu-id="a39b8-122">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="a39b8-123">有关数据中心地理位置的详细信息，请参阅[您的数据位于何处？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="a39b8-123">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

