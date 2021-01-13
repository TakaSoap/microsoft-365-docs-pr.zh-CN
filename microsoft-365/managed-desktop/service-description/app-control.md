---
title: 应用程序控制
description: 如何使用应用程序控制和信任应用程序
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841299"
---
# <a name="app-control"></a><span data-ttu-id="518c3-104">应用程序控制</span><span class="sxs-lookup"><span data-stu-id="518c3-104">App control</span></span>

<span data-ttu-id="518c3-105">应用控制是 Microsoft 托管桌面中的可选安全做法，可限制在客户端设备上执行代码。</span><span class="sxs-lookup"><span data-stu-id="518c3-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="518c3-106">此控制通过要求只有经客户批准的发布者列表签名的代码才能运行，从而降低恶意软件或恶意脚本的风险。</span><span class="sxs-lookup"><span data-stu-id="518c3-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="518c3-107">此控件有许多安全优势，但它主要用于保护数据和标识免受基于客户端的漏洞攻击。</span><span class="sxs-lookup"><span data-stu-id="518c3-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="518c3-108">Microsoft 托管桌面通过创建支持核心生产力方案的基本策略来简化应用控制策略的管理。</span><span class="sxs-lookup"><span data-stu-id="518c3-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="518c3-109">你可以将信任扩展到特定于环境中应用和脚本的其他签名者。</span><span class="sxs-lookup"><span data-stu-id="518c3-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="518c3-110">任何安全技术都需要在用户体验、安全性和成本之间取得平衡。</span><span class="sxs-lookup"><span data-stu-id="518c3-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="518c3-111">应用控制可降低环境中恶意软件的威胁，但会给用户带来后果，并针对 IT 管理员执行进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="518c3-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="518c3-112">**其他安全性：**</span><span class="sxs-lookup"><span data-stu-id="518c3-112">**Additional security:**</span></span>

<span data-ttu-id="518c3-113">应用控制策略不受信任的应用或脚本被阻止在设备上运行。</span><span class="sxs-lookup"><span data-stu-id="518c3-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="518c3-114">**其他责任：**</span><span class="sxs-lookup"><span data-stu-id="518c3-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="518c3-115">你负责测试你的应用，以确定应用程序控制策略是否会阻止它们。</span><span class="sxs-lookup"><span data-stu-id="518c3-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="518c3-116">如果应用 (或将被) 阻止，你负责通过管理门户确定所需的签名者详细信息并请求更改。</span><span class="sxs-lookup"><span data-stu-id="518c3-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="518c3-117">**Microsoft 托管桌面职责：**</span><span class="sxs-lookup"><span data-stu-id="518c3-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="518c3-118">Microsoft 托管桌面维护支持核心 Microsoft 产品（如 M365 应用、Windows、Teams、OneDrive 等）的基本策略。</span><span class="sxs-lookup"><span data-stu-id="518c3-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="518c3-119">Microsoft 托管桌面插入受信任的签名者，并将更新的策略部署到设备。</span><span class="sxs-lookup"><span data-stu-id="518c3-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="518c3-120">管理应用程序中的信任</span><span class="sxs-lookup"><span data-stu-id="518c3-120">Managing trust in applications</span></span>

<span data-ttu-id="518c3-121">Microsoft 托管桌面可制定信任 Microsoft 技术核心组件的基本策略。</span><span class="sxs-lookup"><span data-stu-id="518c3-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="518c3-122">然后 *，通过* 通知 Microsoft 托管桌面已信任哪些应用程序和脚本，为它们添加信任。</span><span class="sxs-lookup"><span data-stu-id="518c3-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="518c3-123">基本策略</span><span class="sxs-lookup"><span data-stu-id="518c3-123">Base policy</span></span>

<span data-ttu-id="518c3-124">Microsoft 托管桌面与 Microsoft 网络安全专家协作，创建和维护一个标准策略，该策略支持通过 Microsoft Intune 部署大多数应用，同时阻止危险活动，如代码编译或执行不受信任的文件。</span><span class="sxs-lookup"><span data-stu-id="518c3-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="518c3-125">基本策略采用以下方法限制软件执行：</span><span class="sxs-lookup"><span data-stu-id="518c3-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="518c3-126">将允许由管理员运行的文件运行。</span><span class="sxs-lookup"><span data-stu-id="518c3-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="518c3-127">将允许不在用户可写目录中的位置中的文件运行。</span><span class="sxs-lookup"><span data-stu-id="518c3-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="518c3-128">文件由受信任的 [签名者签名](#signer-requests)。</span><span class="sxs-lookup"><span data-stu-id="518c3-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="518c3-129">大多数由 Microsoft 签名的文件都将运行，但会阻止某些文件，以防止执行代码编译等高风险操作。</span><span class="sxs-lookup"><span data-stu-id="518c3-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="518c3-130">如果管理员外的用户可能已经将应用或脚本添加到设备 (即，它位于用户可写目录) 中，则除非管理员明确允许它，否则我们不会允许它执行。</span><span class="sxs-lookup"><span data-stu-id="518c3-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="518c3-131">如果用户被诱使尝试安装恶意软件，如果用户运行的应用中的漏洞尝试安装恶意软件，或者用户有意尝试运行未经授权的应用或脚本，我们的策略将停止执行。</span><span class="sxs-lookup"><span data-stu-id="518c3-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="518c3-132">签名者请求</span><span class="sxs-lookup"><span data-stu-id="518c3-132">Signer requests</span></span>

<span data-ttu-id="518c3-133">通过提交签名者请求，你可以通知我们哪些应用由你信任的软件 *发布者提供*。</span><span class="sxs-lookup"><span data-stu-id="518c3-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="518c3-134">这样，我们会将此信任信息添加到基线应用程序控制策略中，并允许使用该发布者证书签名的任何软件在设备上运行。</span><span class="sxs-lookup"><span data-stu-id="518c3-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="518c3-135">审核和强制执行的策略</span><span class="sxs-lookup"><span data-stu-id="518c3-135">Audit and Enforced policies</span></span>

<span data-ttu-id="518c3-136">Microsoft 托管桌面使用两个 Microsoft Intune 策略提供应用控制：</span><span class="sxs-lookup"><span data-stu-id="518c3-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="518c3-137">审核策略</span><span class="sxs-lookup"><span data-stu-id="518c3-137">Audit policy</span></span>
<span data-ttu-id="518c3-138">此策略创建日志以记录应用或脚本是否将被强制策略阻止。</span><span class="sxs-lookup"><span data-stu-id="518c3-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="518c3-139">审核策略不强制执行应用控制规则，旨在用于测试目的，以确定应用程序是否需要发布者豁免。</span><span class="sxs-lookup"><span data-stu-id="518c3-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="518c3-140">它会在事件 (中记录 8003 或 8006) 警告，而不是阻止执行或安装指定的应用或脚本。</span><span class="sxs-lookup"><span data-stu-id="518c3-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="518c3-141">强制策略</span><span class="sxs-lookup"><span data-stu-id="518c3-141">Enforced policy</span></span>
<span data-ttu-id="518c3-142">此策略阻止不受信任的应用和脚本在应用或脚本被阻止时运行并创建日志。</span><span class="sxs-lookup"><span data-stu-id="518c3-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="518c3-143">强制执行的策略会阻止标准用户执行存储在用户可写目录中的应用或脚本。</span><span class="sxs-lookup"><span data-stu-id="518c3-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="518c3-144">测试组的设备应用了审核策略，以便你可以使用它们来验证任何应用程序是否会导致问题。</span><span class="sxs-lookup"><span data-stu-id="518c3-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="518c3-145">其他所有 (一、快速和广泛) 组都使用强制策略，因此这些组的用户将无法运行不受信任的应用或脚本。</span><span class="sxs-lookup"><span data-stu-id="518c3-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







