---
title: 将 PST 文件导入到 Office 365 的常见问题解答
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '有关使用 Office 365 导入服务将组织的 PST 文件导入到 Office 365 邮箱的管理员的常见问题。 '
ms.openlocfilehash: 31df33ffe2c69478f0304bd27b49254995d8b89c
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170482"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>将 PST 文件导入到 Office 365 的常见问题解答

**本文适用于管理员。是否要将 PST 文件导入到自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
下面是一些有关使用 Office 365 导入服务批量导入 PST 文件到 Office 365 邮箱的常见问题。 有关如何导入 PST 文件的详细信息，请参阅[将 pst 文件导入到 Office 365 概述](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)。
  
## <a name="using-network-upload-to-import-pst-files"></a>使用网络上传导入 PST 文件

有关分步说明，请参阅[使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)。
  
 **在 Office 365 导入服务中创建导入作业需要哪些权限？**
  
必须分配有 Exchange Online 中的邮箱导入导出角色，才能将 PST 文件导入到 Office 365 邮箱。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以向“组织管理”角色组添加“邮箱导入导出”角色。 或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。 有关详细信息，请参阅[管理 Exchange Online 中的角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的“向角色组添加角色”或“创建角色组”部分。
  
此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：
  
- 必须分配有 Exchange Onlin 中的“邮件收件人”角色。 默认情况下，此角色分配给“组织管理和收件人管理”角色组。
    
    或
    
- 必须是你的 Office365 组织中的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 中创建新角色组，此角色组专门用于将 PST 文件导入 Office 365。 若要获取导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。 
  
 **网络上传在哪些地区提供？**
  
目前，这些地区提供了网络上传：美国、加拿大、巴西、英国、法国、欧洲、印度、东亚、东南亚、日本、韩国和澳大利亚。 Network upload will be available in more regions soon.

> [!NOTE]
> 目前，PST 文件的网络上载在德国和瑞士不可用。 当这些国家/地区提供网络上载时，将更新此 FAQ。
  
 **使用网络上传导入 PST 文件的定价如何？**
  
Using network upload to import PST files is free.
  
这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在 Microsoft 365 管理中心已完成导入作业的文件列表中。 虽然导入作业可能仍然列在“**将数据导入到 Office 365**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。 
  
 **哪个版本的 PST 文件格式支持导入到 Office 365？**
  
可选两个版本的 PST 文件格式：ANSI 和 Unicode。 建议导入使用 Unicode PST 文件格式的文件。 但是，采用 ANSI PST 文件格式的文件也可以导入到 Office 365，如语言采用双字节字符集 (DBCS) 的文件。 有关导入 ANSI PST 文件的详细信息，请参阅 "[使用网络上载将组织的 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)" 中的步骤4。
  
此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Office 365。
  
 **将 PST 文件上传到 Azure 存储区域后，这些文件在删除前可在 Azure 中保留多长时间？**
  
使用网络上传的方法导入 PST 文件时，需要将它们上传到名为 **ingestiondata** 的 Azure Blob 容器。 如果安全与合规中心中的“**导入 PST 页面**”页面上没有正在进行的导入作业，则 Azure 中 **ingestiondata** 容器内的所有 PST 文件都会在安全与合规中心中创建最新导入作业 30 天后被删除。 这也意味着须在将 PST 文件上传到 Azure 后的 30 天内在安全与合规中心中创建新的导入作业（如网络上传说明的步骤 5 中所述）。 
  
这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。 虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。 
  
 **将 PST 文件导入到邮箱需要多长时间？**
  
这取决于你的网络容量，但每 TB 数据通常需要几个小时才能上传到组织的 Azure 存储区域。 PST 文件复制到 Azure 存储区域后，PST 文件将以每天至少 24 GB 的速度导入到 Office 365 邮箱。 如果此速度不满足你的需求，可能需要考虑采用其他方法将电子邮件数据迁移到 Office 365。 有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
如果不同的 PST 文件导入到不同的目标邮箱中，则导入过程将以并行方式进行；也就是说，每个 PST/邮箱对是同时导入的。 同样，如果多个 PST 文件导入到同一个邮箱中，也将同时导入这些文件。
  
 **导入 PST 文件时是否有邮件大小限制？**
  
是。 如果 PST 文件包含大于 150 MB 的邮件项，则将在导入过程中跳过此项。
  
 **PST 文件导入到 Office365 邮箱时，是否会保留邮件发送时间或接收时间、收件人和其他属性等邮件属性？**
  
是。 导入过程中不会更改任何原始邮件元数据。
  
 **我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**
  
是的。不能导入包含 300 个或更多级别的嵌套文件夹的 PST 文件。
  
 **是否可以使用网络上传将 PST 文件导入到 Office 365 中的非活动邮箱？**
  
是的，这一功能现已推出。
  
 **是否可以使用网络上传将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**
  
是的，这一功能现已推出。 
  
 **是否可以使用网络上传将 PST 文件导入 Exchange Online 中的公用文件夹？**
  
否，无法将 PST 文件导入公用文件夹。
  
## <a name="using-drive-shipping-to-import-pst-files"></a>使用驱动器寄送导入 PST 文件

有关分步说明，请参阅[使用驱动器发货将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。
  
 **在 Office 365 导入服务中创建导入作业需要哪些权限？**
  
必须分配有邮箱导入导出角色，才能将 PST 文件导入到 Office 365 邮箱。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以向“组织管理”角色组添加“邮箱导入导出”角色。 或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。 有关详细信息，请参阅[管理 Exchange Online 中的角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的“向角色组添加角色”或“创建角色组”部分。
  
此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：
  
- 必须分配有 Exchange Onlin 中的“邮件收件人”角色。 默认情况下，此角色分配给“组织管理和收件人管理”角色组。
    
    或
    
- 必须是你的 Office365 组织中的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 中创建新角色组，此角色组专门用于将 PST 文件导入 Office 365。 若要获取导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。 
  
 **哪些地区提供驱动器寄送服务？**
  
当前，美国、加拿大、巴西、英国、欧洲、印度、东亚地址、东南亚、日本、韩国和澳大利亚已推出驱动器传送。 不久之后，还会有更多地区推出驱动器传送。

> [!NOTE]
> 目前，用于导入 PST 文件的驱动器运送在德国和瑞士不可用。 在这些国家/地区提供驱动器发货时，将更新此 FAQ。
  
 **哪些商业许可协议支持驱动器发运？**
  
驱动器寄送可通过 Microsoft 企业协议 (EA) 将 PST 文件导入到 Office 365。 驱动器寄送不可通过 Microsoft 产品和服务协议 (MPSA) 实现。
  
 **使用驱动器发运将 PST 文件导入到 Office_365 的定价如何？**
  
使用驱动器发运将 PST 文件导入到 Office 365 邮箱的费用为每 GB 数据 2 美元。 例如，如果发运的硬盘包含 1,000 GB (1 TB) 的 PST 文件，则费用为 2,000 美元。 您可以与合作伙伴共同协作来支付导入费用。 有关查找合作伙伴的信息，请参阅[查找 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
  
 **哪类硬盘支持驱动器发运？**
  
仅支持将 2.5 英寸固态硬盘 (SSD) 或 2.5 或 3.5 英寸 SATA II/III 内部硬盘与 Office 365 导入服务结合使用。 可使用最多 10 TB 的硬盘。 对于导入作业，仅将处理硬盘上的第一个数据卷。 必须使用 NTFS 格式化数据卷。 将数据复制到硬盘时，可使用 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III 连接器直接连接，或可使用外部 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III USB 适配器在外部将其连接。
  
> [!IMPORTANT]
> Office 365 导入服务中不支持内置 USB 适配器随附的外部硬盘。 此外，无法使用外部硬盘盒内的磁盘。 请不要发运外部硬盘。 
  
 **单个导入作业可以发运多少个硬盘？**
  
单个导入作业最多可以发运 10 个硬盘。
  
 **发运硬盘后，需要多长时间才能转到 Microsoft 数据中心？**
  
这取决于几点，例如你与 Microsoft 数据中心之间的距离、使用哪种类型的送货选项来配送硬盘（如隔天送达、两天送达或地面配送）。对于大多数运货商，可使用跟踪编号跟踪配送状态。
  
 **硬盘驱动器到达 Microsoft 数据中心后，需要多久才能将 PST文件上传到 Azure？**
  
在 Microsoft 数据中心收到硬盘驱动器后，需要7到10个工作日才能将 PST 文件上传到组织的 Azure 存储区。 PST 文件将被上传到名为**ingestiondata**的 Azure blob 容器中。 
  
 **将 PST 文件导入到邮箱需要多长时间？**
  
将 PST 文件上传到 Azure 存储区域后，Office 365 采用安全的方式分析 PST 文件中的数据，确定 PST 文件中所含项目的存在时长以及各种邮件类型。 分析完成后，可以选择将所有数据导入 PST 文件，或设置筛选器控制导入的数据。 开始导入作业后，PST 文件将以每天至少 24 GB 的速度导入到 Office 365 邮箱。 如果此速度不满足你的需求，可能需要考虑采用其他方法将电子邮件数据导入 Office 365。 有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
如果不同的 PST 文件导入到不同的目标邮箱中，则导入过程将以并行方式进行；也就是说，每个 PST/邮箱对是同时导入的。 同样，如果多个 PST 文件导入到同一个邮箱中，也将同时导入这些文件。
  
 **Microsoft 将 PST 文件上传到 Azure 后，这些文件在删除前可在 Azure 中保留多长时间？**
  
在安全 & 合规中心的 "**导入 PST 文件**" 页上创建最近的导入作业之后30天内，将删除您的组织的 Azure 存储位置中的所有 PST 文件（在 blob 容器中名为**ingestiondata**）。 
  
这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。 虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。 
  
 **哪个版本的 PST 文件格式支持导入到 Office 365？**
  
可选两个版本的 PST 文件格式：ANSI 和 Unicode。 建议导入使用 Unicode PST 文件格式的文件。 但是，采用 ANSI PST 文件格式的文件也可以导入到 Office 365，如语言采用双字节字符集 (DBCS) 的文件。 有关导入 ANSI PST 文件的详细信息，请参阅 "[使用驱动器传送将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)" 中的步骤3。
  
此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Office 365。
  
 **导入 PST 文件时是否有邮件大小限制？**
  
是。 如果 PST 文件包含大于 150 MB 的邮件项，则将在导入过程中跳过此项。
  
 **PST 文件导入到 Office365 邮箱时，是否会保留邮件发送时间或接收时间、收件人和其他属性等邮件属性？**
  
是。 导入过程中不会更改原始邮件的元数据
  
 **我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**
  
是的。不能导入包含 300 个或更多级别的嵌套文件夹的 PST 文件。
  
 **是否可以使用驱动器发运将 PST 文件导入到 Office 365 中的非活动邮箱？**
  
Yes, this capability is now available.
  
 **是否可以使用驱动器发运将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**
  
是的，这一功能现已推出。
  
 **是否可以使用驱动器发运将 PST 文件导入 Exchange Online 中的公用文件夹？**
  
否，无法将 PST 文件导入公用文件夹。
  
 **Microsoft 将硬盘运回给我之前，是否会进行擦除？**
  
不会，Microsoft 将硬盘运回给客户前不会进行擦除。硬盘将以 Microsoft 接收到的状态返回给你。
  
 **Microsoft 是否会销毁我的硬盘，而不是寄回给我？**
  
不会，Microsoft 不会销毁硬盘。硬盘将以 Microsoft 接收到的状态返回给你。
  
 **寄回时支持哪些快递服务？**
  
对于美国或欧洲客户，Microsoft 使用 FedEx 运回硬盘。对于所有其他区域的客户，Microsoft 将使用 DHL。
  
 **寄回的运费是多少？**
  
运回的运费有所不同，具体取决于你与硬盘运达的 Microsoft 数据中心之间的距离。Microsoft 将向你收取通过 FedEx 或 DHL 运回硬盘的费用。返回运费需由你支付。
  
 **是否可以使用 FedEx Custom Shipping 等自定义快递运输服将我的硬盘寄送至 Microsoft？**
  
是。
  
 **如果我必须将我的硬盘发运到其他国家/地区，是否有任何需要执行的操作？**
  
你发运到 Microsoft 的硬盘可能会跨越国际边界。如果是这种情况，你有责任确保硬盘及其所含数据是根据适用法律导入和/或导出的。发运硬盘前，请与顾问联系，确保驱动器和数据可以合法地发送到指定的 Microsoft 数据中心。这有助于确保它及时送达 Microsoft。
