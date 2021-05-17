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
description: 在设置内容格式时，使用通信编辑器更改文本和合并字段变量。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769157"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="f3eac-103">使用通信编辑器</span><span class="sxs-lookup"><span data-stu-id="f3eac-103">Use the communications editor</span></span>

<span data-ttu-id="f3eac-104">定义门户内容、合法保留通知和相关提醒/升级的内容时，可以使用通信编辑器设置内容的格式并动态自定义内容。</span><span class="sxs-lookup"><span data-stu-id="f3eac-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="f3eac-105">格式文本编辑器</span><span class="sxs-lookup"><span data-stu-id="f3eac-105">Rich text editor</span></span>

<span data-ttu-id="f3eac-106">通信编辑器允许用户使用编辑器选项自定义文本。</span><span class="sxs-lookup"><span data-stu-id="f3eac-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="f3eac-107">例如，用户可以更改字体类型、创建项目符号列表、突出显示内容等。</span><span class="sxs-lookup"><span data-stu-id="f3eac-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="f3eac-108">合并域变量</span><span class="sxs-lookup"><span data-stu-id="f3eac-108">Merge field variables</span></span>

<span data-ttu-id="f3eac-109">您可以使用通信编辑器中的电子邮件合并变量将自定义保管人属性嵌入通信的正文文本中。</span><span class="sxs-lookup"><span data-stu-id="f3eac-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="f3eac-110">发送到保管人时，合并域将填充相应的字段。</span><span class="sxs-lookup"><span data-stu-id="f3eac-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="f3eac-111">例如，当发送到保管人 John Smith 时，合并域 [Custodian Name] 将用相应的名称进行转换。</span><span class="sxs-lookup"><span data-stu-id="f3eac-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="f3eac-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span><span class="sxs-lookup"><span data-stu-id="f3eac-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="f3eac-113">占位符将基于用户光标的位置添加。</span><span class="sxs-lookup"><span data-stu-id="f3eac-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="f3eac-114">合并域变量列表</span><span class="sxs-lookup"><span data-stu-id="f3eac-114">List of merge field variables</span></span>

| <span data-ttu-id="f3eac-115">字段名</span><span class="sxs-lookup"><span data-stu-id="f3eac-115">Field name</span></span>                  | <span data-ttu-id="f3eac-116">字段详细信息</span><span class="sxs-lookup"><span data-stu-id="f3eac-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="f3eac-117">显示名称</span><span class="sxs-lookup"><span data-stu-id="f3eac-117">Display Name</span></span>  | <span data-ttu-id="f3eac-118">保管人的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="f3eac-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="f3eac-119">Acknowledgment 链接</span><span class="sxs-lookup"><span data-stu-id="f3eac-119">Acknowledgment Link</span></span> | <span data-ttu-id="f3eac-120">用于记录每个保管人确认的自定义链接。</span><span class="sxs-lookup"><span data-stu-id="f3eac-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="f3eac-121">门户链接</span><span class="sxs-lookup"><span data-stu-id="f3eac-121">Portal Link</span></span>     | <span data-ttu-id="f3eac-122">保管人合规性门户的自定义链接。</span><span class="sxs-lookup"><span data-stu-id="f3eac-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="f3eac-123">颁发官</span><span class="sxs-lookup"><span data-stu-id="f3eac-123">Issuing Officer</span></span>                   | <span data-ttu-id="f3eac-124">指定颁发机构主管的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f3eac-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="f3eac-125">颁发日期</span><span class="sxs-lookup"><span data-stu-id="f3eac-125">Issuing Date</span></span>                   | <span data-ttu-id="f3eac-126">通知的发布日期为 UTC () 。</span><span class="sxs-lookup"><span data-stu-id="f3eac-126">The date that the notice was issued (UTC).</span></span>              |
|||
