---
title: Microsoft 365管理中心中的报告 - 邮箱使用情况
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: 了解如何获取邮箱使用情况报告，以了解用户邮箱用户的活动。
ms.openlocfilehash: e3c6508148db6d3a28ef8af42c223b1c75858733
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157490"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Microsoft 365管理中心中的报告 - 邮箱使用情况

邮箱 **使用情况报告** 根据电子邮件发送、阅读、创建约会、发送会议、接受会议、拒绝会议以及取消会议活动，提供有关具有用户邮箱的用户以及每个用户的活动级别的信息。 它还显示每个用户邮箱占用了多少存储空间以及其中多少用户即将达到存储配额。 
  
> [!NOTE]
> 您必须是 Microsoft 365 中的全局管理员、全局读取者或报告读者，或者 Exchange、SharePoint、Teams Service、Teams Communications 或 Skype for Business 管理员才能查看报告。 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>如何访问邮箱使用情况报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。
2. 选择 **"电子邮件活动"** 下的"**查看更多"。** 
3. 从"**电子邮件活动**"下拉列表中，选择 **"Exchange** \> **邮箱使用情况"。**

## <a name="interpret-the-mailbox-usage-report"></a>解读邮箱使用情况报告

可查看" **邮箱**"、" **存储**"和" **配额**"图表，了解组织的" **邮箱使用情况**"。
  
:::image type="content" alt-text="邮箱使用情况报告。" source="../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png" lightbox="../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png":::

|项目|说明|
|:-----|:-----|
|1.  |可查看" **邮箱使用情况**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的某一天，则该表将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。 |
|2.  |每个报告中的数据通常涵盖过去 24 至 48 小时的数据。 |
|3.  |邮箱图表显示组织中的用户邮箱总数以及在报告周期内的任意指定日期处于活动状态的用户邮箱总数。 如果用户邮箱具有发送电子邮件、阅读、创建约会、发送会议、接受会议、拒绝会议以及取消会议活动，则认为用户邮箱处于活动状态。 |
|4.  |" **存储**"图表显示组织中使用的存储量。 存储图表不包括存档邮箱。 有关自动扩展存档的信息，请参阅 overview [of auto-expanding archiving in Microsoft 365](../../compliance/autoexpanding-archiving.md)。 |
|5.  | " **配额**"图表显示每个配额类别中用户邮箱的数量。有以下 4 种配额类别：  <br/>  良好 - 其使用的存储低于问题警告配额的用户数量。  <br/>  警告 - 其使用的存储等于或高于问题警告配额但低于禁止发送配额的用户数量  <br/>  无法发送 - 其使用的存储等于或高于禁止发送配额但低于禁止发送/接收配额的用户数量  <br/>  无法发送/接收 - 其使用的存储等于或高于禁止发送/接收配额的用户数量 |
|6.  | 在" **邮箱**"图表上，Y 轴表示用户邮箱计数。  <br/>  在" **存储**"图表上，Y 轴表示组织中用户邮箱正在使用的存储量。  <br/>  在" **配额**"图表上，Y 轴表示每个存储配额中用户邮箱的数量。  <br/>  "邮箱"和"存储"图表上的 X 轴都表示此特定报表的所选日期范围。  <br/>  "配额"图表上的 X 轴表示配额类别。 |
|7.  |可以通过选择图例中的项目来筛选所见图表。 |
|8.  | 下表详细显示每个用户级别的邮箱使用情况。可向表格添加其他列。  <br/> " **用户名**"是用户的电子邮件地址。  <br/> " **显示名称**"是用户的全名。  <br/> " **已删除邮箱**"是指当前处于"已删除"状态的邮箱，但其在报告的部分报告周期内处于活动状态。  <br/> " **删除日期**"是指删除邮箱的日期。  <br/> " **创建日期**"是指创建邮箱的日期。  <br/> " **上次活动日期**"是指邮箱的电子邮件发送或阅读活动日期。  <br/> " **项计数**"是指邮箱中项的总数。  <br/> " **使用的存储(MB)**"是指使用的存储总量。  <br/> **"已删除项目计数** "是指邮箱中已删除项目的总数。 <br/> **已删除项目大小 (MB)** 是指邮箱中所有已删除项目的总大小。 <br/> " **问题警告配额(MB)**"是指即将达到存储配额时，邮箱所有者会收到警告的存储空间上限。  <br/> " **禁止发送配额(MB)**"是指邮箱无法再发送电子邮件时的存储空间上限。  <br/> " **禁止发送接收配额(MB)**"是指邮箱无法再发送或接收电子邮件时的存储空间上限。  <br/> 可恢复项目配额 **(MB)** 是指邮箱不再能够删除电子邮件 (邮箱 (已删除) 邮件的存储限制。  <br/> **Has Archive** 显示邮箱是否已启用联机存档。  <br/>  如果组织的策略阻止你查看显示了可识别用户信息的报表，可更改所有这些报表的隐私设置。 请查看活动 **报告中的"报告**"部分中的"隐藏 [用户Microsoft 365 管理中心"。](activity-reports.md) |
|9.  |选择 **"选择要在** 报表中添加或删除列的列"。  <br/> :::image type="content" alt-text="邮箱使用情况报告 - 选择列。" source="../../media/ea3d0b18-6ac6-41b0-9bb9-4844f040ea75.png":::|
|10. |您还可以通过选择"导出"链接将报告数据导出到Excel .csv文件。  |
|||
