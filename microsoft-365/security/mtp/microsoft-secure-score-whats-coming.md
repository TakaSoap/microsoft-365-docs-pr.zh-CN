---
title: 即将推出的 Microsoft 安全分数
description: 介绍 Microsoft 365 安全中心中的 Microsoft 安全分数的新更改。
keywords: microsoft 安全分数，安全分数，office 365 安全分数，microsoft 安全分数，microsoft 365 安全中心，改进操作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779244"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="a1b76-104">即将推出的 Microsoft 安全分数</span><span class="sxs-lookup"><span data-stu-id="a1b76-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a1b76-105">我们在不久的将来进行一些更改，让 [Microsoft 安全](microsoft-secure-score.md) 成为你的安全状态的更好代表并提高可用性。</span><span class="sxs-lookup"><span data-stu-id="a1b76-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="a1b76-106">你的分数和可能的最大分数可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="a1b76-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="a1b76-107">建议的更改</span><span class="sxs-lookup"><span data-stu-id="a1b76-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="a1b76-108">2020年11月</span><span class="sxs-lookup"><span data-stu-id="a1b76-108">November 2020</span></span>

<span data-ttu-id="a1b76-109">通过转到 **共享 > ServiceNow** ，删除通过安全分数创建 ServiceNow 票证的能力。</span><span class="sxs-lookup"><span data-stu-id="a1b76-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="a1b76-110">ServiceNow 连接器的预览周期即将结束。</span><span class="sxs-lookup"><span data-stu-id="a1b76-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="a1b76-111">2020的结尾将不再提供此功能。</span><span class="sxs-lookup"><span data-stu-id="a1b76-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="a1b76-112">感谢你的反馈，并在我们确定后续步骤时继续提供支持。</span><span class="sxs-lookup"><span data-stu-id="a1b76-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="a1b76-113">添加与 Microsoft Defender for Endpoint (之前的 Microsoft Defender ATP) 相关的18个改进操作：</span><span class="sxs-lookup"><span data-stu-id="a1b76-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="a1b76-114">攻击面降低 (ASR) 相关建议：</span><span class="sxs-lookup"><span data-stu-id="a1b76-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="a1b76-115">阻止来自电子邮件客户端和 web 邮件的可执行内容</span><span class="sxs-lookup"><span data-stu-id="a1b76-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="a1b76-116">阻止所有 Office 应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="a1b76-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="a1b76-117">阻止 Office 应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="a1b76-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="a1b76-118">阻止 Office 应用程序将代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="a1b76-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="a1b76-119">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="a1b76-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="a1b76-120">阻止执行可能模糊的脚本</span><span class="sxs-lookup"><span data-stu-id="a1b76-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="a1b76-121">阻止来自 Office 宏的 Win32 API 调用</span><span class="sxs-lookup"><span data-stu-id="a1b76-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="a1b76-122">阻止可执行文件运行，除非它们满足流行、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="a1b76-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="a1b76-123">对勒索软件使用高级防护</span><span class="sxs-lookup"><span data-stu-id="a1b76-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="a1b76-124">阻止从 Windows 本地安全颁发机构子系统中盗取凭据 ( # A0) </span><span class="sxs-lookup"><span data-stu-id="a1b76-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="a1b76-125">阻止进程创建源自 PSExec 和 WMI 命令</span><span class="sxs-lookup"><span data-stu-id="a1b76-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="a1b76-126">阻止从 USB 运行的不受信任和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="a1b76-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="a1b76-127">阻止 Office 通信应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="a1b76-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="a1b76-128">阻止 Adobe Reader 创建子流程</span><span class="sxs-lookup"><span data-stu-id="a1b76-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="a1b76-129">通过 WMI 事件订阅阻止持久化</span><span class="sxs-lookup"><span data-stu-id="a1b76-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="a1b76-130">与服务相关的建议：</span><span class="sxs-lookup"><span data-stu-id="a1b76-130">Services related recommendations:</span></span>
- <span data-ttu-id="a1b76-131">修复 Windows 服务的无引号服务路径</span><span class="sxs-lookup"><span data-stu-id="a1b76-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="a1b76-132">将服务可执行路径更改为常见的受保护位置</span><span class="sxs-lookup"><span data-stu-id="a1b76-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="a1b76-133">更改服务帐户以避免 windows 注册表中的缓存密码</span><span class="sxs-lookup"><span data-stu-id="a1b76-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="a1b76-134">相关资源</span><span class="sxs-lookup"><span data-stu-id="a1b76-134">Related resources</span></span>

- [<span data-ttu-id="a1b76-135">Microsoft 安全评分概述</span><span class="sxs-lookup"><span data-stu-id="a1b76-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="a1b76-136">评估你的安全状况</span><span class="sxs-lookup"><span data-stu-id="a1b76-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="a1b76-137">跟踪你的 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="a1b76-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="a1b76-138">新增功能</span><span class="sxs-lookup"><span data-stu-id="a1b76-138">What's new</span></span>](microsoft-secure-score-whats-new.md)
