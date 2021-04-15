---
title: 在 Microsoft Viva 主题的主题中心管理主题
description: 如何在主题中心管理主题。
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: e2cbf62339e2ade240474fed9db86e68dc0b3bb4
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760118"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a>在 Microsoft Viva 主题的主题中心管理主题

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


在 Viva 主题中心，知识管理员可以查看"管理主题"页，以查看在知识管理员指定的 SharePoint 源位置中标识的主题。  

   ![主题中心](../media/knowledge-management/topic-center.png) </br> 



知识管理器可帮助指导发现的主题完成主题生命周期，主题包括：

- **建议：** 主题已由 AI 标识，并且具有足够的支持资源、连接和属性。
- **已** 确认：已验证 AI 建议的主题。 验证通过知识管理器确认完成。 此外，如果至少有两个用户通过主题卡片上的反馈问题提供正面反馈，可以确认主题。
- **已发布**：经确认的主题已计划：已进行手动编辑以提高其质量。
- **已删除**：主题被知识管理员拒绝，并且不再对查看者可见。 如果主题在建议、确认或发布后被删除 (，该主题可能) 。 删除已发布的主题后，需要通过主题中心的"页面库"手动删除包含特用详细信息的页面。

   ![主题生命周期图表](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> 在"管理主题"页上，每个知识管理员只能查看他们有权访问主题的文件和页面的主题。 这将反映在"建议"、已确认、已删除和"已发布"选项卡 **下列出的主题** 中。  但是，主题计数会显示组织中的总计数。

## <a name="requirements"></a>要求

若要在主题中心管理主题，需要：
- 拥有 Viva 主题许可证。

- 具有" [**谁可以管理主题"**](./topic-experiences-user-permissions.md) 权限。 知识管理员可以在 Viva 主题权限设置中为用户提供此权限。 

除非您具有"谁可以管理主题"权限，否则将无法在主题中心查看"管理主题 **"** 页。

在主题中心中，知识经理可以审阅在指定的 SharePoint 源位置中标识的主题，并可以确认或拒绝这些主题。 如果主题发现中未找到新主题页，知识管理员还可以创建和发布新主题页，或者编辑现有主题页（如果需要更新）。


## <a name="review-suggested-topics"></a>查看建议的主题

在主题中心"管理主题"页上，在指定的 SharePoint 源位置中发现的主题将在"建议"选项卡 **中** 列出。如果需要，知识经理可以审阅未确认的主题，并选择确认或拒绝它们。

   ![建议的主题](../media/knowledge-management/quality-score.png) </br> 

查看建议的主题：

1. 在" **管理主题"** 页上，选择" **建议"选项卡** ，选择主题以打开主题页面。</br>

2. 在主题页面上，查看主题页面，如果需要对页面做出任何更改，请选择"编辑"。 发布任何编辑将本主题移至"已发布 **"** 选项卡。

3. 查看主题后，返回到"管理主题"页。 对于所选主题，您可以：

   - 选择选中标记以确认主题。
    
   - 如果要 **拒绝该** 主题，请选择 x。

    已确认的主题将从"建议 **"** 列表中删除，现在显示在"已确认 **"** 列表中。

    拒绝的主题将从"建议"列表中 **删除，** 现在显示在"已删除 **"选项卡** 中。

   </br> 

### <a name="quality-score"></a>质量分数

显示在"建议的主题"页上的每个主题都有分配给它的质量分数。 质量分数反映了普通用户将看到有关该主题的信息的信息量，同时请记住，每个用户可能会看到更多或更少的信息，因为他们可能拥有或可能不会查看主题中信息的权限。 

质量分数可帮助深入了解包含最多信息的主题，并且可用于查找可能需要手动编辑的主题。 例如，质量分数较低的主题可能是某些用户对 AI 在主题中包含的相关文件或网站没有 SharePoint 权限的结果。 参与者随后可以编辑主题，以在适当 (包含) ，然后所有可查看该主题的用户都可以查看这些信息。

质量分数的范围为 1 到 100。 新发现的主题的质量分数将为 0，直到两个或多个用户查看它。 每个用户的质量分数由许多因素决定，例如为特定用户显示的内容量，这将控制用户的权限，因为每个主题页面都有针对 AI 生成的内容的安全修整。 "建议的主题"选项卡 **上显示** 的质量分数是每个用户的单个分数的平均值。

### <a name="impressions"></a>展示次数

" **印象** "列显示向最终用户显示主题次数。 这包括通过搜索中的主题卡片、主题突出显示和主题中心视图查看。 它并不反映这些主题的点击率，但已显示该主题。 The **Impressions** column will show for topics in the **Suggested**， **Confirmed，** **Published，** and **Removed** tabs on the Manage Topics page.

## <a name="confirmed-topics"></a>已确认的主题

在"管理主题"页上，在指定的 SharePoint 源位置中发现并且已由知识经理确认的主题，或者由两个或多个人员通过卡片反馈机制确认的"众包"主题将在"已确认"选项卡中 **列出。** 如果需要，具有管理主题权限的用户可以审阅已确认的主题，并选择拒绝它们。

查看已确认的主题：

1. 在" **已确认** "选项卡上，选择主题以打开主题页面。</br>

2. 在主题页面上，查看主题页面，如果需要对页面做出任何更改，请选择"编辑"。

请注意，您仍可以选择拒绝已确认的主题。 为此，请转到"已确认"选项卡上的所选主题，如果要拒绝该主题，请选择 **"x"。**

## <a name="published-topics"></a>已发布的主题
已发布的主题已经过编辑，以便始终向遇到页面的任何人显示特定信息。 此处也列出了手动创建的主题。

   ![管理主题](../media/knowledge-management/manage-topics-new.png) </br>