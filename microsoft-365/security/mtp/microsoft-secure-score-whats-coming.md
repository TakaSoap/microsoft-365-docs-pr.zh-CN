---
title: Microsoft 安全分数中的情况如何？
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员可预期的内容。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
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
ms.openlocfilehash: 48ff6d6f5cac0991895c40cae90ca31657cfedff
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844878"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="41698-104">Microsoft 安全分数中的情况如何？</span><span class="sxs-lookup"><span data-stu-id="41698-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="41698-105">为了使[Microsoft 安全得分](microsoft-secure-score.md)更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。</span><span class="sxs-lookup"><span data-stu-id="41698-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="41698-106">你的分数和可能的最大分数都将发生变化。</span><span class="sxs-lookup"><span data-stu-id="41698-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="41698-107">但是，这并不意味着您的安全状况发生了变化。</span><span class="sxs-lookup"><span data-stu-id="41698-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="41698-108">若要了解最近所做的更改，请参阅[Microsoft 安全分数中的新增功能？](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="41698-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="june-2020"></a><span data-ttu-id="41698-109">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="41698-109">June 2020</span></span>

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="41698-110">删除 Microsoft Defender 高级威胁防护的提高操作</span><span class="sxs-lookup"><span data-stu-id="41698-110">Remove improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="41698-111">打开攻击面降低规则</span><span class="sxs-lookup"><span data-stu-id="41698-111">Turn on Attack Surface Reduction rules</span></span>

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="41698-112">为 Microsoft Defender 高级威胁防护添加改进操作</span><span class="sxs-lookup"><span data-stu-id="41698-112">Add improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="41698-113">阻止 Adobe Reader 创建子流程</span><span class="sxs-lookup"><span data-stu-id="41698-113">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="41698-114">对勒索软件使用高级防护</span><span class="sxs-lookup"><span data-stu-id="41698-114">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="41698-115">阻止所有 Office 应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="41698-115">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="41698-116">阻止 Office 应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="41698-116">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="41698-117">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="41698-117">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="41698-118">阻止执行可能模糊的脚本</span><span class="sxs-lookup"><span data-stu-id="41698-118">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="41698-119">阻止来自电子邮件客户端和 web 邮件的可执行内容</span><span class="sxs-lookup"><span data-stu-id="41698-119">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="41698-120">阻止 Office 通信应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="41698-120">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="41698-121">阻止从 USB 运行的不受信任和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="41698-121">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="41698-122">通过 WMI 事件订阅阻止持久化</span><span class="sxs-lookup"><span data-stu-id="41698-122">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="41698-123">阻止 Office 应用程序将代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="41698-123">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="41698-124">阻止可执行文件运行，除非它们满足流行、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="41698-124">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="41698-125">阻止进程创建源自 PSExec 和 WMI 命令</span><span class="sxs-lookup"><span data-stu-id="41698-125">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="41698-126">阻止从 Windows 本地安全颁发机构子系统盗取凭据（lsass.exe）</span><span class="sxs-lookup"><span data-stu-id="41698-126">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="41698-127">阻止来自 Office 宏的 Win32 API 调用</span><span class="sxs-lookup"><span data-stu-id="41698-127">Block Win32 API calls from Office macros</span></span>
