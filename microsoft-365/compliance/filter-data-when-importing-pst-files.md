---
title: 导入 PST 文件时筛选数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
ms.custom: seo-marvel-apr2020
description: 了解如何在将 PST 文件导入到 Microsoft 365 时，使用 Microsoft 365 导入服务中的智能导入功能筛选Microsoft 365。
ms.openlocfilehash: 0c321c4bcdb413c42c5a3edff1f19e2a34c093d1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200505"
---
# <a name="filter-data-when-importing-pst-files"></a>导入 PST 文件时筛选数据

使用 Microsoft 365 导入服务中的新智能导入功能筛选 PST 文件中实际导入到目标邮箱的项目。 以下是相应的工作方式：
  
- 创建并提交 PST 导入作业后，PST 文件将上载到 Microsoft 云中的 Azure 存储区域。
  
- Microsoft 365以安全的方式分析 PST 文件的数据，方法为确定邮箱项目的年龄以及 PST 文件中包含的不同邮件类型。
  
- 当分析完成并且数据已准备好导入时，您可以选择按此方式导入 PST 文件内的所有数据，或者通过设置控制导入哪些数据的筛选器来修整导入的数据。 例如，可以选择：
  
  - 仅导入特定年龄的项目。
  
  - 导入所选邮件类型。
  
  - 排除特定人员发送或接收的邮件。
  
- 配置筛选器设置后，Microsoft 365只将满足筛选条件的数据导入导入作业中指定的目标邮箱。
  
下图显示了智能导入过程，并突出显示了您执行的任务以及由 Office 365。
  
![Office 365 中的智能导入过程。](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a>创建 PST 导入作业

- 本主题中的步骤假定你已使用网络上载或驱动器寄送在 Office 365 导入服务中创建 PST 导入作业。 有关分步说明，请参阅下列主题之一：
    
  - [使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)
    
  - [使用驱动器传送将 PST 文件导入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- 使用网络上载创建导入作业后，安全 & 合规中心的"导入"页上的导入作业的状态将设置为"正在分析"，这意味着 Microsoft 365正在分析您上载的 PST 文件的数据。 单击 **"刷新** ![ 刷新"。](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 更新导入作业的状态。 
    
- 对于驱动器寄送导入作业，Microsoft 数据中心工作人员Microsoft 365硬盘驱动器，将 PST 文件上载到组织的 Azure 存储区域后，系统将会分析数据。
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>筛选导入到邮箱的数据

创建 PST 导入作业后，请按照以下步骤筛选数据，然后再将数据导入Office 365。
  
1. 转到 <https://compliance.microsoft.com>，然后使用你组织中的管理员帐户凭据登录。
    
2. 在 Microsoft 365 合规中心的侧左窗格中，单击“**信息治理**”\>“**导入**”。
    
    组织的导入作业列在"导入"**选项卡** 上。The **Analysis completed** value in the **Status** column indicates the import jobs that have been analysis by Microsoft 365 and are ready for you to import.
    
    ![分析完成状态Microsoft 365 PST 文件中已分析数据。](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. 选择要完成的导入作业，然后单击"导入 **以Office 365"。**
  
    系统将显示一个浮出页面，其中包含有关 PST 文件的信息和有关导入作业的其他信息。

4. 单击 **导入以Office 365。**
    
    系统将显示“**筛选数据**”页面。 它包含有关导入作业的 PST 文件中数据的数据见解，包括有关数据年龄的信息。 
    
    !["筛选数据"页显示导入作业的 PST 文件的数据见解。](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. 根据是否要剪裁导入到数据Microsoft 365，在"是否要筛选数据 **？"** 下，执行下列操作之一：
  
    a. 单击 **"是，我希望在导入** 之前进行筛选以修整导入的数据"，然后单击"下一步 **"。**
  
    "**将数据导入Office 365"** 页将显示，并包含来自所执行分析的详细Microsoft 365见解。 
  
    ![Microsoft 365 PST 文件分析中显示详细的数据见解。](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    此页面上的图形显示将导入的数据量。 有关在 PST 文件中找到的每封邮件类型的信息将显示在图中。 您可以将光标悬停在每个栏上，以显示有关该消息类型的特定信息。 根据 PST 文件分析，还有一个包含不同年龄值的下拉列表。 当你在下拉列表中选择一个年龄时，图形将更新以显示所选年龄将导入多少数据。 
  
    b. 若要配置添加筛选器以减少导入的数据量，请单击"更多筛选 **选项"。**
  
    ![配置"更多选项"页上的筛选器以修整导入的数据。](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    可以配置以下筛选器：
  
      - **Age** - 选择一个年数，以便仅导入比指定年龄更新的项目。 请参阅 [详细信息部分](#more-information)，了解有关如何确定Microsoft 365年龄筛选器的年龄 **存储桶的说明**。 
  
      - **类型** - 此部分显示在导入作业的 PST 文件中找到的所有邮件类型。 可以取消选中要排除的邮件类型旁边的框。 不能排除其他邮件类型。 有关 [其他类别](#more-information) 中包含的邮箱项目列表，请参阅详细信息部分。
  
      - **用户** - 可以排除特定人员发送或接收的邮件。 若要排除出现在"发件人："字段、"收件人："字段或邮件的"抄送："字段中的用户，请单击该 **收件人类型** 旁边的"排除用户"。 键入用户 (SMTP 地址) ，单击"**添加新** ![ 图标"。](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 以将其添加到该收件人类型的已排除用户列表中，然后单击"保存"以保存已排除用户的列表。 
  
        > [!NOTE]
        > Microsoft 365显示通过设置人员筛选器获得 **的数据** 见解。 但是，如果设置此筛选器以排除特定人员发送或接收的邮件，则在实际导入过程中将排除这些邮件。 
  
    c. 单击 **"** 更多筛选 **选项** "飞出页面中的"应用"以保存筛选器设置。 
  
    "将数据导入到Office 365"页上的数据见解将基于筛选器设置进行更新，包括将基于筛选器设置导入的数据总量。 还会显示筛选器设置的摘要。 可以单击 **筛选器** 旁边的"编辑"以在必要时更改设置。 
  
    ![数据见解将基于筛选器设置进行更新。](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. 单击“下一步”。
  
    将显示一个状态页，其中显示筛选器设置。 同样，您可以编辑任何筛选器设置。
  
    e. 单击 **"导入数据** "开始导入。 将显示将导入的数据总量。 
  
    或
  
    a. 单击 **"否，我希望导入所有内容** 以将 PST 文件内的所有数据导入Office 365，然后单击"下一步 **"。**
  
    b. 在"**将数据导入Office 365** 页上，单击 **"导入数据**"以开始导入。 将显示将导入的数据总量。 
  
6. 在"导入 **"选项卡** 上，单击" **刷新刷新** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) "。。 导入作业的状态显示在"状态 **"** 列中。
  
7. 单击导入作业可显示更详细的信息，例如每个 PST 文件的状态和配置的筛选器设置。

## <a name="more-information"></a>更多信息

- 如何Microsoft 365年龄筛选器的增量？ 当Microsoft 365 PST 文件时，它会查看每个项目的已发送或已接收时间戳 (如果某个项目同时具有已发送和已接收时间戳，则选择) 。 然后Microsoft 365该时间戳的年值，并将其与当前日期进行比较以确定项目的年龄。 然后，这些年龄用作"年龄"筛选器的下拉列表 **中的** 值。 例如，如果 PST 文件包含来自 2016、2015 和 2014 的邮件，则 **Age** 筛选器中的值为 **1 年****、2** 年和 **3 年**。
  
- 下表列出了"更多选项"飞出页面 (请参阅上一过程中的步骤5b中"类型"筛选器中的"其他"类别中包含) 。  目前，在将 PST 导入到其他类别时，不能排除"其他"Office 365。 
  
    |**邮件类标识符**|**使用此邮件类的邮箱项目**|
    |:-----|:-----|
    |IPM。活动  <br/> |“日记”条目  <br/> |
    |IPM。文档  <br/> |未附加到 (电子邮件的文档和)   <br/> |
    |IPM。文件  <br/> | (IPM 相同。文档)   <br/> |
    |IPM。Note.IMC.Notification  <br/> |由 Internet 邮件连接发送的报告，Exchange Server Internet 的网关  <br/> |
    |IPM。Note.Microsoft.Fax  <br/> |传真邮件  <br/> |
    |IPM。Note.Rules.Oof.Template.Microsoft  <br/> |外出自动修复邮件  <br/> |
    |IPM。Note.Rules.ReplyTemplate.Microsoft  <br/> |收件箱规则发送的答复  <br/> |
    |IPM。OLE。类  <br/> |定期系列的例外  <br/> |
    |IPM。Recall.Report  <br/> |邮件撤回报告  <br/> |
    |IPM。远程  <br/> |远程邮件  <br/> |
    |IPM。报告  <br/> |项目状态报告  <br/> |
