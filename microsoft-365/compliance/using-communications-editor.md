---
title: 使用通信编辑器
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在设置内容格式时使用通信编辑器更改文本和合并字段变量。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0cb415da9aa09452176bd8aa9be4575cfc827582
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034474"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="360a5-103">使用通信编辑器</span><span class="sxs-lookup"><span data-stu-id="360a5-103">Use the communications editor</span></span>

<span data-ttu-id="360a5-104">在定义门户内容、法律保留通知和相关提醒/上报的内容时，可以利用通信编辑器格式化和动态自定义内容。</span><span class="sxs-lookup"><span data-stu-id="360a5-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="360a5-105">富文本编辑器</span><span class="sxs-lookup"><span data-stu-id="360a5-105">Rich text editor</span></span> 

<span data-ttu-id="360a5-106">通过通信编辑器，用户可以使用编辑器选项自定义文本。</span><span class="sxs-lookup"><span data-stu-id="360a5-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="360a5-107">例如，用户可以更改字体类型、创建项目符号列表、突出显示内容等。</span><span class="sxs-lookup"><span data-stu-id="360a5-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="360a5-108">合并字段变量</span><span class="sxs-lookup"><span data-stu-id="360a5-108">Merge field variables</span></span>

<span data-ttu-id="360a5-109">您可以利用通信编辑器中的电子邮件合并变量将自定义的保管人属性嵌入到通信的正文文本中。</span><span class="sxs-lookup"><span data-stu-id="360a5-109">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="360a5-110">当发送给管理员时，将使用对应的字段填充合并域。</span><span class="sxs-lookup"><span data-stu-id="360a5-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="360a5-111">例如，当发送给保管人 John Smith 时，合并域 [保管人 Name] 将转换为相应的名称。</span><span class="sxs-lookup"><span data-stu-id="360a5-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="360a5-112">您可以通过选择 "rtf" 文本编辑器控件顶部的 "**合并域**" 图标来使用电子邮件合并域。</span><span class="sxs-lookup"><span data-stu-id="360a5-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="360a5-113">将根据用户光标的位置添加占位符。</span><span class="sxs-lookup"><span data-stu-id="360a5-113">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="360a5-114">合并域变量的列表</span><span class="sxs-lookup"><span data-stu-id="360a5-114">List of merge field variables</span></span>

| <span data-ttu-id="360a5-115">字段名</span><span class="sxs-lookup"><span data-stu-id="360a5-115">Field name</span></span>                  | <span data-ttu-id="360a5-116">字段详细信息</span><span class="sxs-lookup"><span data-stu-id="360a5-116">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="360a5-117">显示名称</span><span class="sxs-lookup"><span data-stu-id="360a5-117">Display Name</span></span>  | <span data-ttu-id="360a5-118">保管人的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="360a5-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="360a5-119">确认链接</span><span class="sxs-lookup"><span data-stu-id="360a5-119">Acknowledgement Link</span></span> | <span data-ttu-id="360a5-120">记录每个保管人的确认的自定义链接。</span><span class="sxs-lookup"><span data-stu-id="360a5-120">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="360a5-121">门户链接</span><span class="sxs-lookup"><span data-stu-id="360a5-121">Portal Link</span></span>     | <span data-ttu-id="360a5-122">用于保管人合规性门户的自定义链接。</span><span class="sxs-lookup"><span data-stu-id="360a5-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="360a5-123">签发专员</span><span class="sxs-lookup"><span data-stu-id="360a5-123">Issuing Officer</span></span>                   | <span data-ttu-id="360a5-124">指定的颁发专员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="360a5-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="360a5-125">签发日期</span><span class="sxs-lookup"><span data-stu-id="360a5-125">Issuing Date</span></span>                   | <span data-ttu-id="360a5-126">通知发布的日期（UTC）。</span><span class="sxs-lookup"><span data-stu-id="360a5-126">The date that the notice was issued (UTC).</span></span>              |
