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
description: ''
ms.openlocfilehash: 2f445e4449fb20f0d13d857bb83d3dc85d7b7387
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069199"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="9f2b6-102">使用通信编辑器</span><span class="sxs-lookup"><span data-stu-id="9f2b6-102">Use the communications editor</span></span>

<span data-ttu-id="9f2b6-103">在定义门户内容、法律保留通知和相关提醒/上报的内容时，可以利用通信编辑器格式化和动态自定义内容。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="9f2b6-104">富文本编辑器</span><span class="sxs-lookup"><span data-stu-id="9f2b6-104">Rich text editor</span></span> 

<span data-ttu-id="9f2b6-105">通过通信编辑器，用户可以使用编辑器选项自定义文本。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-105">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="9f2b6-106">例如，用户可以更改字体类型、创建项目符号列表、突出显示内容等。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-106">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="9f2b6-107">合并字段变量</span><span class="sxs-lookup"><span data-stu-id="9f2b6-107">Merge field variables</span></span>

<span data-ttu-id="9f2b6-108">您可以利用通信编辑器中的电子邮件合并变量将自定义的保管人属性嵌入到通信的正文文本中。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-108">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="9f2b6-109">当发送给管理员时，将使用对应的字段填充合并域。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-109">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="9f2b6-110">例如，当发送给保管人 John Smith 时，合并域 [保管人 Name] 将转换为相应的名称。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-110">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="9f2b6-111">您可以通过选择 "rtf" 文本编辑器控件顶部的 "**合并域**" 图标来使用电子邮件合并域。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-111">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="9f2b6-112">将根据用户光标的位置添加占位符。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-112">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="9f2b6-113">合并域变量的列表</span><span class="sxs-lookup"><span data-stu-id="9f2b6-113">List of merge field variables</span></span>

| <span data-ttu-id="9f2b6-114">字段名</span><span class="sxs-lookup"><span data-stu-id="9f2b6-114">Field name</span></span>                  | <span data-ttu-id="9f2b6-115">字段详细信息</span><span class="sxs-lookup"><span data-stu-id="9f2b6-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="9f2b6-116">显示名称</span><span class="sxs-lookup"><span data-stu-id="9f2b6-116">Display Name</span></span>  | <span data-ttu-id="9f2b6-117">保管人的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="9f2b6-118">确认链接</span><span class="sxs-lookup"><span data-stu-id="9f2b6-118">Acknowledgement Link</span></span> | <span data-ttu-id="9f2b6-119">记录每个保管人的确认的自定义链接。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="9f2b6-120">门户链接</span><span class="sxs-lookup"><span data-stu-id="9f2b6-120">Portal Link</span></span>     | <span data-ttu-id="9f2b6-121">用于保管人合规性门户的自定义链接。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="9f2b6-122">签发专员</span><span class="sxs-lookup"><span data-stu-id="9f2b6-122">Issuing Officer</span></span>                   | <span data-ttu-id="9f2b6-123">指定的颁发专员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="9f2b6-124">签发日期</span><span class="sxs-lookup"><span data-stu-id="9f2b6-124">Issuing Date</span></span>                   | <span data-ttu-id="9f2b6-125">通知发布的日期（UTC）。</span><span class="sxs-lookup"><span data-stu-id="9f2b6-125">The date that the notice was issued (UTC).</span></span>              |
