---
title: 双字节字符集的 Microsoft 365 合规性支持发行说明（预览版）
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 双字节字符集支持的发行说明。
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681498"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="9406e-103">双字节字符集支持发行说明（预览版）</span><span class="sxs-lookup"><span data-stu-id="9406e-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="9406e-104">Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持（预览）：</span><span class="sxs-lookup"><span data-stu-id="9406e-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="9406e-105">简体中文</span><span class="sxs-lookup"><span data-stu-id="9406e-105">Chinese (simplified)</span></span>
- <span data-ttu-id="9406e-106">繁体中文</span><span class="sxs-lookup"><span data-stu-id="9406e-106">Chinese (traditional)</span></span>
- <span data-ttu-id="9406e-107">韩语</span><span class="sxs-lookup"><span data-stu-id="9406e-107">Korean</span></span>
- <span data-ttu-id="9406e-108">日语</span><span class="sxs-lookup"><span data-stu-id="9406e-108">Japanese</span></span>

<span data-ttu-id="9406e-109">此支持适用于敏感信息类型和关键字字典，并且将在数据丢失防护、通信合规性、Exchange Online、SharePoint Online、OneDrive for Business 和 Teams 解决方案中有所体现。</span><span class="sxs-lookup"><span data-stu-id="9406e-109">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="9406e-110">已知问题</span><span class="sxs-lookup"><span data-stu-id="9406e-110">Known issues</span></span>

- <span data-ttu-id="9406e-111">当附加到电子邮件的文本文件采用不带字节顺序标记 (BOM) 的 UTF-8 格式时，通信合规性策略不会检测到该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9406e-111">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="9406e-112">如果针对策略条件“邮件包含其中任意字词”输入了一句话，则通信合规性策略无法检测到值。</span><span class="sxs-lookup"><span data-stu-id="9406e-112">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="9406e-113">如果将该策略中指定的文本写为一个词，则可以检测到；但是，如果将其写在句子中间，则不会检测到。</span><span class="sxs-lookup"><span data-stu-id="9406e-113">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="9406e-114">将字典指定为类型信息的通信合规性策略不会检测 Teams 私人聊天和频道聊天。</span><span class="sxs-lookup"><span data-stu-id="9406e-114">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="9406e-115">目前阶段不支持采用以下条件来确保通信合规性（我们计划以后修复这些问题）：</span><span class="sxs-lookup"><span data-stu-id="9406e-115">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="9406e-116">“邮件包含其中任意字词”</span><span class="sxs-lookup"><span data-stu-id="9406e-116">“Message contains any of these words”</span></span>
  - <span data-ttu-id="9406e-117">“邮件不包含其中任意字词”</span><span class="sxs-lookup"><span data-stu-id="9406e-117">“Message contains none of these words”</span></span>
  - <span data-ttu-id="9406e-118">“附件包含其中任意字词”</span><span class="sxs-lookup"><span data-stu-id="9406e-118">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="9406e-119">“附件包含其中任意字词”</span><span class="sxs-lookup"><span data-stu-id="9406e-119">“Attachment contains any of these words”</span></span>

<span data-ttu-id="9406e-120">相反，建议使用可检测邮件和附件中的模式的关键字字典创建自定义敏感信息类型 (SIT)，并将此自定义 SIT 作为通信合规性策略条件。</span><span class="sxs-lookup"><span data-stu-id="9406e-120">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
