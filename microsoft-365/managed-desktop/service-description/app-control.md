---
title: 应用程序控制
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 32ed3f95ebb4299796c5ad3eb71802c949701b65
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289123"
---
# <a name="app-control"></a><span data-ttu-id="98056-103">应用程序控制</span><span class="sxs-lookup"><span data-stu-id="98056-103">App control</span></span>

<span data-ttu-id="98056-104">应用程序控制是 Microsoft 托管桌面中的一种可选安全实践，用于限制客户端设备上的代码的执行。</span><span class="sxs-lookup"><span data-stu-id="98056-104">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="98056-105">此控件通过要求只有经客户核准的发布者签名的代码才能运行，从而缓解恶意软件或恶意脚本的风险。</span><span class="sxs-lookup"><span data-stu-id="98056-105">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="98056-106">此控制提供了很多安全优势，但它主要旨在保护基于客户端的攻击的数据和身份。</span><span class="sxs-lookup"><span data-stu-id="98056-106">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="98056-107">Microsoft 托管桌面通过创建启用核心生产力方案的基本策略简化了应用程序控制策略的管理。</span><span class="sxs-lookup"><span data-stu-id="98056-107">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="98056-108">您可以将信任扩展到特定于环境中的应用程序和脚本的其他签名人。</span><span class="sxs-lookup"><span data-stu-id="98056-108">You can extend trust to additional signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="98056-109">任何安全技术都需要在用户体验、安全性和成本之间实现平衡。</span><span class="sxs-lookup"><span data-stu-id="98056-109">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="98056-110">应用程序控制可降低环境中恶意软件的威胁，但对用户和 IT 管理员的其他操作会产生后果。</span><span class="sxs-lookup"><span data-stu-id="98056-110">App control reduces the threat of malicious software in your environment, but there are consequences to the user and additional actions for your IT administrator.</span></span>

<span data-ttu-id="98056-111">**其他安全性：**</span><span class="sxs-lookup"><span data-stu-id="98056-111">**Additional security:**</span></span>

<span data-ttu-id="98056-112">阻止应用程序控制策略所信任的应用程序或脚本无法在设备上运行。</span><span class="sxs-lookup"><span data-stu-id="98056-112">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="98056-113">**您的额外职责：**</span><span class="sxs-lookup"><span data-stu-id="98056-113">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="98056-114">您负责测试您的应用程序，以确定应用程序控件策略是否会阻止这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="98056-114">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="98056-115">如果某个应用程序 (或将被) 阻止，您将负责标识所需的签名者详细信息，并通过管理门户请求更改。</span><span class="sxs-lookup"><span data-stu-id="98056-115">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="98056-116">**Microsoft 托管桌面职责：**</span><span class="sxs-lookup"><span data-stu-id="98056-116">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="98056-117">Microsoft 托管桌面维护允许核心 Microsoft 产品（如 M365 应用程序、Windows、团队、OneDrive 等）的基本策略。</span><span class="sxs-lookup"><span data-stu-id="98056-117">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="98056-118">Microsoft 托管桌面插入你的受信任签署人，并将更新的策略部署到你的设备。</span><span class="sxs-lookup"><span data-stu-id="98056-118">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="98056-119">在应用程序中管理信任</span><span class="sxs-lookup"><span data-stu-id="98056-119">Managing trust in applications</span></span>

<span data-ttu-id="98056-120">Microsoft 托管桌面 curates 信任 Microsoft 技术的核心组件的基本策略。</span><span class="sxs-lookup"><span data-stu-id="98056-120">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="98056-121">然后，通过通知 Microsoft 托管桌面的已信任您自己的应用程序和脚本来 *添加* 信任。</span><span class="sxs-lookup"><span data-stu-id="98056-121">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="98056-122">基本策略</span><span class="sxs-lookup"><span data-stu-id="98056-122">Base policy</span></span>

<span data-ttu-id="98056-123">Microsoft 托管桌面，与 Microsoft cybersecurity 专家协作，创建并维护一个标准策略，该策略允许在阻止代码编译或执行不受信任文件等危险活动时，通过 Microsoft Intune 部署大多数应用。</span><span class="sxs-lookup"><span data-stu-id="98056-123">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="98056-124">基本策略采用以下方法来限制软件执行：</span><span class="sxs-lookup"><span data-stu-id="98056-124">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="98056-125">管理员运行的文件将被允许运行。</span><span class="sxs-lookup"><span data-stu-id="98056-125">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="98056-126">将允许运行 *不* 在用户可写目录中的位置中的文件。</span><span class="sxs-lookup"><span data-stu-id="98056-126">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="98056-127">文件由 [受信任的签名人](#signer-requests)签署。</span><span class="sxs-lookup"><span data-stu-id="98056-127">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="98056-128">Microsoft 签名的大多数文件都将运行，但某些文件会被阻止，以防止高风险操作（如代码编译）。</span><span class="sxs-lookup"><span data-stu-id="98056-128">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="98056-129">如果管理员之外的用户可能已将应用程序或脚本添加到设备 (也就是说，它位于用户可写入的目录) 中，我们将不允许它执行，除非管理员已明确允许它执行。</span><span class="sxs-lookup"><span data-stu-id="98056-129">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="98056-130">如果用户被欺骗尝试安装恶意软件，如果用户运行的应用程序中的某个漏洞尝试安装恶意软件，或者如果用户有意尝试运行未授权的应用程序或脚本，则策略将停止执行。</span><span class="sxs-lookup"><span data-stu-id="98056-130">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="98056-131">签名者请求</span><span class="sxs-lookup"><span data-stu-id="98056-131">Signer requests</span></span>

<span data-ttu-id="98056-132">你将告知我们通过存档 *签名者请求*而信任的软件供应商提供的应用程序。</span><span class="sxs-lookup"><span data-stu-id="98056-132">You inform us of which apps are provided by software vendors you trust by filing a *signer request*.</span></span> <span data-ttu-id="98056-133">通过执行此操作，我们将此信任信息添加到基准应用程序控制策略中，并允许使用该发布者的证书签名的任何软件在您的设备上运行。</span><span class="sxs-lookup"><span data-stu-id="98056-133">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="98056-134">审核和强制实施策略</span><span class="sxs-lookup"><span data-stu-id="98056-134">Audit and Enforced policies</span></span>

<span data-ttu-id="98056-135">Microsoft 托管桌面使用两个 Microsoft Intune 策略来提供应用程序控制：</span><span class="sxs-lookup"><span data-stu-id="98056-135">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="98056-136">审核策略</span><span class="sxs-lookup"><span data-stu-id="98056-136">Audit policy</span></span>
<span data-ttu-id="98056-137">此策略将创建日志，以记录强制策略是否会阻止应用程序或脚本。</span><span class="sxs-lookup"><span data-stu-id="98056-137">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="98056-138">审核策略不会强制实施应用程序控制规则，并用于测试目的，以确定应用程序是否需要发布服务器例外。</span><span class="sxs-lookup"><span data-stu-id="98056-138">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="98056-139">它会在事件查看器中记录警告 (8003 或8006事件) ，而不是阻止执行或安装指定的应用程序或脚本。</span><span class="sxs-lookup"><span data-stu-id="98056-139">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="98056-140">强制策略</span><span class="sxs-lookup"><span data-stu-id="98056-140">Enforced policy</span></span>
<span data-ttu-id="98056-141">此策略阻止不受信任的应用程序和脚本运行，并在应用程序或脚本被阻止时创建日志。</span><span class="sxs-lookup"><span data-stu-id="98056-141">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="98056-142">强制策略阻止标准用户执行存储在用户可写目录中的应用程序或脚本。</span><span class="sxs-lookup"><span data-stu-id="98056-142">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="98056-143">测试组中的设备已应用审核策略，以便您可以使用它们来验证是否有任何应用程序将导致问题。</span><span class="sxs-lookup"><span data-stu-id="98056-143">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="98056-144">所有其他组 (的第一个、快速和广泛的) 使用强制性策略，因此这些组中的用户将无法运行不受信任的应用程序或脚本。</span><span class="sxs-lookup"><span data-stu-id="98056-144">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







