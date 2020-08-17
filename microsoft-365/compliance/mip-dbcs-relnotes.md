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
ms.openlocfilehash: 13bac873f2ba18bc166451ea73ec0d569fb30f68
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695233"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="71a44-103">双字节字符集支持发行说明（预览版）</span><span class="sxs-lookup"><span data-stu-id="71a44-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="71a44-104">Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持（预览）：</span><span class="sxs-lookup"><span data-stu-id="71a44-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="71a44-105">简体中文</span><span class="sxs-lookup"><span data-stu-id="71a44-105">Chinese (simplified)</span></span>
- <span data-ttu-id="71a44-106">繁体中文</span><span class="sxs-lookup"><span data-stu-id="71a44-106">Chinese (traditional)</span></span>
- <span data-ttu-id="71a44-107">韩语</span><span class="sxs-lookup"><span data-stu-id="71a44-107">Korean</span></span>
- <span data-ttu-id="71a44-108">日语</span><span class="sxs-lookup"><span data-stu-id="71a44-108">Japanese</span></span>

<span data-ttu-id="71a44-109">此功能预览仅在商业云中提供，并且仅在以下地区推出：</span><span class="sxs-lookup"><span data-stu-id="71a44-109">This preview is only in the commercial cloud and the rollout is limited to:</span></span>

- <span data-ttu-id="71a44-110">日本</span><span class="sxs-lookup"><span data-stu-id="71a44-110">Japan</span></span>
- <span data-ttu-id="71a44-111">韩国</span><span class="sxs-lookup"><span data-stu-id="71a44-111">Korea</span></span>
- <span data-ttu-id="71a44-112">中国大陆</span><span class="sxs-lookup"><span data-stu-id="71a44-112">China</span></span>
- <span data-ttu-id="71a44-113">香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="71a44-113">Hong Kong</span></span>
- <span data-ttu-id="71a44-114">澳门特别行政区</span><span class="sxs-lookup"><span data-stu-id="71a44-114">Macau</span></span>
- <span data-ttu-id="71a44-115">中国台湾</span><span class="sxs-lookup"><span data-stu-id="71a44-115">Taiwan</span></span>

<span data-ttu-id="71a44-116">此支持适用于敏感信息类型和关键字字典，并且将在数据丢失防护、通信合规性、Exchange Online、SharePoint Online、OneDrive for Business 和 Teams 解决方案中有所体现。</span><span class="sxs-lookup"><span data-stu-id="71a44-116">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="71a44-117">已知问题</span><span class="sxs-lookup"><span data-stu-id="71a44-117">Known issues</span></span>

- <span data-ttu-id="71a44-118">当附加到电子邮件的文本文件采用不带字节顺序标记 (BOM) 的 UTF-8 格式时，通信合规性策略不会检测到该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71a44-118">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="71a44-119">如果针对策略条件“邮件包含其中任意字词”输入了一句话，则通信合规性策略无法检测到值。</span><span class="sxs-lookup"><span data-stu-id="71a44-119">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="71a44-120">如果将该策略中指定的文本写为一个词，则可以检测到；但是，如果将其写在句子中间，则不会检测到。</span><span class="sxs-lookup"><span data-stu-id="71a44-120">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="71a44-121">将字典指定为类型信息的通信合规性策略不会检测 Teams 私人聊天和频道聊天。</span><span class="sxs-lookup"><span data-stu-id="71a44-121">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="71a44-122">目前阶段不支持采用以下条件来确保通信合规性（我们计划以后修复这些问题）：</span><span class="sxs-lookup"><span data-stu-id="71a44-122">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="71a44-123">“邮件包含其中任意字词”</span><span class="sxs-lookup"><span data-stu-id="71a44-123">“Message contains any of these words”</span></span>
  - <span data-ttu-id="71a44-124">“邮件不包含其中任意字词”</span><span class="sxs-lookup"><span data-stu-id="71a44-124">“Message contains none of these words”</span></span>
  - <span data-ttu-id="71a44-125">“附件包含其中任意字词”</span><span class="sxs-lookup"><span data-stu-id="71a44-125">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="71a44-126">“附件包含其中任意字词”</span><span class="sxs-lookup"><span data-stu-id="71a44-126">“Attachment contains any of these words”</span></span>

<span data-ttu-id="71a44-127">相反，建议使用可检测邮件和附件中的模式的关键字字典创建自定义敏感信息类型 (SIT)，并将此自定义 SIT 作为通信合规性策略条件。</span><span class="sxs-lookup"><span data-stu-id="71a44-127">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
