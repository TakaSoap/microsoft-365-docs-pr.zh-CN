---
title: 有关导入组织的 PST 文件的概述
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用安全与合规中心的导入服务将电子邮件数据（PST 文件）批量导入到用户邮箱中。
ms.openlocfilehash: f1b695ecd156fd8a26ee7a5ca04bb0e76c77f4b8
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464041"
---
# <a name="overview-of-importing-your-organizations-pst-files"></a>有关导入组织的 PST 文件的概述

> [!NOTE]
> 本文适用于管理员。 你正在尝试将 PST 文件导入到自己的邮箱吗？ 请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)。

可以使用安全与合规中心的导入服务将 PST 文件快速批量导入到组织中的 Exchange Online 邮箱中。可以通过两种方式将 PST 文件导入到 Office 365：

- **网络上传** ![云上传](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - 通过网络将 PST 文件上传到 Microsoft 云中的临时 Azure 存储位置。 然后，使用 Office 365 导入服务将 PST 数据导入到组织的邮箱中。

- **驱动器寄送** ![硬盘](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - 将 PST 文件复制到 BitLocker 加密的硬盘中，然后将驱动器实际寄到 Microsoft。 Microsoft 收到硬盘后，数据中心工作人员会将数据上传到 Microsoft 云中的临时 Azure 存储位置。 然后，使用 Office 365 导入服务将数据导入到组织的邮箱中。

## <a name="step-by-step-instructions"></a>分步说明

请参阅以下主题，获取有关将组织的 PST 文件导入到 Office 365 的详细分步说明。

- [使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)

- [使用驱动器传送导入 PST 文件](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>导入 PST 文件的工作原理

以下是完整 PST 流程的图示和说明。 该图示显示了主要工作流程并突出显示了网络上传和驱动器寄送方法之间的差别。

![PST 导入流程的工作流](../media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)

1. **将 PST 导入工具和密钥下载到专用 Azure 存储位置** - 第一步是下载用于上传 PST 文件或将其复制到硬盘的工具和访问密钥。 需要从安全与合规中心的“导入”页获取工具和密钥。 密钥为你（如果是驱动器寄送，则是 Microsoft 数据中心人员）提供所需的权限用于将 PST 文件上传到安全的专用 Azure 存储位置。 此访问密钥对组织是唯一的，有助于防止在 PST 文件上传至 Microsoft 云之后对其进行未经授权的访问。 将 PST 文件导入到 Microsoft 365 不需要你的组织拥有单独的 Azure 订阅。

2. **上传或复制 PST 文件** - 下一步取决于你是使用网络上传或驱动器寄送来导入 PST 文件。 在两种情况下，你均使用在上一步中获得的工具和安全存储密钥。

    - **网络上传：** AzCopy.exe 工具（在步骤 1 中下载）用于将 PST 文件上传并存储于 Microsoft 云中的 Azure 存储位置。 将 PST 文件上传至的 Azure 存储位置和组织所在区域 Microsoft 数据中心处于同一位置。

      若要上传，要导入的 PST 文件必须位于组织的文件共享或文件服务器上。

    - **驱动器寄送：** WAImportExport.exe 工具（在步骤 1 中下载）用于将 PST 文件复制到硬盘。 该工具使用 BitLocker 加密硬盘，然后将 PST 复制到硬盘。 与网络上传方法类似，想要复制到硬盘的 PST 文件必须位于组织的文件共享或文件服务器上。

3. **创建 PST 导入映射文件** - 将 PST 文件上传至 Azure 存储位置或复制到硬盘之后，下一步是创建逗号分隔值 (CSV) 文件，用于指定 PST 文件将要导入到的用户邮箱（并且 PST 文件可导入到用户的主邮箱或其存档邮箱）。 Office 365 导入服务将使用此信息来导入 PST 文件。

4. **创建 PST 导入作业** - 下一步是在安全与合规中心的“**导入 PST 文件**”页上创建 PST 导入作业并提交在上一步骤创建的 PST 导入映射文件。 对于网络上传（因为 PST 文件已上传至 Azure），Microsoft 365 将分析 PST 文件中的数据，然后为你提供设置筛选器的机会，以便控制哪些数据被实际导入到 PST 导入映射文件中指定的邮箱。

    对于驱动器寄送，在此过程中的这个环节会发生一些其他事情。

    - 将硬盘实际寄到 Microsoft 数据中心（创建导入作业时，将会显示 Microsoft 数据中心的寄送地址）。

    - Microsoft 收到硬盘后，数据中心工作人员会将硬盘上的 PST 文件上传到组织的 Azure 存储位置。 如前所述，PST 文件上传到位于组织所在相同区域 Microsoft 数据中心的 Azure 存储位置。

      > [!NOTE]
      > 硬盘驱动器上的 PST 文件将在 Microsoft 收到硬盘驱动器之后 7-10 个工作日之内上传至 Azure。

      与网络上传流程类似，Microsoft 365 随后将分析 PST 文件中的数据，并为你提供设置筛选器的机会，以便控制哪些数据被实际导入到 PST 导入映射文件中指定的邮箱。

    - Microsoft 将硬盘寄回给你。

5. **筛选将要导入到邮箱的 PST 数据** - 创建导入作业之后（并在驱动器传送操作中的 PST 文件上传至 Azure 存储位置后），Microsoft 365 将安全地分析 PST 文件中的数据，方法是标识项目期限以及 PST 文件中所含的不同邮件类型。 分析完成且数据准备就绪可供导入后，你可以选择导入 PST 文件中包含的所有数据，或者通过设置用于控制可导入哪些数据的筛选器来减少导入的数据。

6. **启动 PST 导入作业** - 启动导入作业后，Microsoft 365 使用 PST 导入映射文件中的信息将 PST 文件从 Azure 存储位置导入到用户邮箱。 与导入作业相关的状态信息（包括与每个导入的 PST 文件相关的信息）将显示在安全与合规中心的“**导入 PST 文件**”页。 导入作业完成后，作业的状态将设置为“**完成**”。

## <a name="why-import-email-data-to-microsoft-365"></a>为什么要将电子邮件数据导入到 Microsoft 365？

- 这是将组织的存档邮件数据导入到 Microsoft 365 的好方法。

- 可以使用“[智能导入](filter-data-when-importing-pst-files.md)”功能来筛选 PST 文件中实际导入到目标邮箱的项。 这使你能够通过设置用于控制导入的数据的筛选器来减少导入的数据。

- 通过允许你执行以下操作，将电子邮件数据导入到 Microsoft 365 有助于满足组织的合规性需求：

  - 启用[存档邮箱](enable-archive-mailboxes.md)和[无限存档](unlimited-archiving.md)，为用户提供额外的邮箱存储空间。

  - 将邮箱置于“[诉讼保留](./create-a-litigation-hold.md)”以保留内容。

  - 使用“[控制搜索工具](content-search.md)”搜索邮箱内容。

  - 使用[电子数据展示事例](./get-started-core-ediscovery.md)管理组织的法律调查

  - 使用安全与合规中心的“[保留策略](retention.md)”来控制邮箱内容的保留时长，然后在保留期限到期之后删除内容。

  - 使用“[沟通合规性策略](communication-compliance.md)”检查邮件，以确保它们符合邮件标准并添加分类类型。

- 将数据导入到 Microsoft 365 有助于防止数据丢失。 导入到 Microsoft 365 的电子邮件数据将继承 Exchange Online 的高可用性功能。

- 用户在任意设备上都可以使用电子邮件数据，因为数据存储在云中。

## <a name="importing-sharepoint-data-to-microsoft-365"></a>将 SharePoint 数据导入到 Microsoft 365

此外，还可以将文件和文档导入到组织中的 SharePoint 网站和 OneDrive 帐户。有关详细信息，请参阅下面的文章：

- [迁移到 SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)

- [SharePoint 迁移工具简介](/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [使用 PowerShell 迁移到 SharePoint Online](/sharepointmigration/overview-spmt-ps-cmdlets)

- [使用 Azure Data Box 将文件共享内容迁移到 SharePoint Online](/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)

## <a name="frequently-asked-questions-about-importing-pst-files"></a>有关导入 PST 文件的常见问题解答

以下是与使用 Office 365 导入服务将 PST 文件批量上传至 Microsoft 365 邮箱相关的常见问题。

- [使用网络上传导入 PST 文件](#using-network-upload-to-import-pst-files)

- [使用驱动器寄送导入 PST 文件](#using-drive-shipping-to-import-pst-files)

### <a name="using-network-upload-to-import-pst-files"></a>使用网络上传导入 PST 文件

 **在 Office 365 导入服务中创建导入作业需要哪些权限？**

必须分配有 Exchange Online 中的邮箱导入导出角色，才能将 PST 文件导入到 Microsoft 365 邮箱。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以向“组织管理”角色组添加“邮箱导入导出”角色。 或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。 有关详细信息，请参阅[管理 Exchange Online 中的角色组](/Exchange/permissions-exo/role-groups)中的“向角色组添加角色”或“创建角色组”部分。

此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：

- 在 Exchange Online 中必须分配有“邮件收件人”角色。默认情况下，此角色分配给“组织管理和收件人管理”角色组。

    或

- 必须是你组织中的全局管理员。

> [!TIP]
> 请考虑在 Exchange Online 中创建专门用于将 PST 文件导入到 Office 365 的新角色组。要获得导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。

 **网络上传在哪些地区提供？**

目前，在以下区域提供网络上传功能：美国、加拿大、巴西、英国、法国、德国、瑞士、挪威、欧洲、印度、东亚、东南亚、日本、韩国、澳大利亚和阿拉伯联合酋长国 (UAE)。该功能将很快在更多区域中提供。

 **使用网络上传导入 PST 文件的定价如何？**

Using network upload to import PST files is free.

这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在 Microsoft 365 管理中心已完成导入作业的文件列表中。 虽然导入作业可能仍然列在“**将数据导入到 Office 365**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。

 **哪个版本的 PST 文件格式支持导入到 Office 365？**

可选两个版本的 PST 文件格式：ANSI 和 Unicode。 建议导入使用 Unicode PST 文件格式的文件。 但是，采用 ANSI PST 文件格式的文件也可以导入到 Office 365，如语言采用双字节字符集 (DBCS) 的文件。 有关导入 ANSI PST 文件的详细信息，请参阅[使用网络上传将 PST 文件导入到 Office 365](./use-network-upload-to-import-pst-files.md) 中的步骤 4。

此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Office 365。

 **将 PST 文件上传到 Azure 存储区域后，这些文件在删除前可在 Azure 中保留多长时间？**

当使用网络上传方法导入 PST 文件时，会将文件上传到已命名的 Azure Blob 容器`ingestiondata`。 如果安全与合规中心中的“**导入 PST 页面**”页面上没有正在进行的导入作业，则 Azure 中 `ingestiondata` 容器内的所有 PST 文件都会在安全与合规中心中创建最新导入作业 30 天后被删除。 这也意味着须在将 PST 文件上传到 Azure 后的 30 天内在安全与合规中心中创建新的导入作业（如网络上传说明的步骤 5 中所述）。

这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。 虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。

 **将 PST 文件导入到邮箱需要多长时间？**

这取决于你的网络容量，但每 TB 数据通常需要几个小时才能上传到组织的 Azure 存储区域。 将 PST 文件复制到 Azure 存储区域后，PST 文件将以每天大约 24 GB 的速度导入到 Microsoft 365 邮箱<sup>\*</sup>。 如果此速度不满足你的需求，可能需要考虑采用其他方法将电子邮件数据导入 Office 365。 有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](/Exchange/mailbox-migration/mailbox-migration)。

<sup>\*</sup> 不能保证此速率。 服务器工作负载和暂时性的性能问题可能会降低此速率。

如果将不同的 PST 文件导入到不同的目标邮箱，则导入过程将按顺序进行（一次一个），并进行限制。

 **PST 导入进程如何处理重复的电子邮件项？**

如果目标邮箱或目标存档的目标文件夹中存在匹配项，PST 导入进程将检查重复的项目，并且不会将邮件项从 PST 文件复制到邮箱或存档。 如果重新导入相同的 PST 文件并指定与上一个导入作业中指定的文件夹不同的目标文件夹（使用 PST 导入映射文件中的 TargetRootFolder 属性），将重新导入 PST 文件中的所有项。

 **导入 PST 文件时是否有邮件大小限制？**

是。 如果 PST 文件包含大于 150 MB 的邮箱项目，导入过程中将跳过且不导入该项目。 不导入大小超过 150 MB 的邮件，因为 Exchange Online 中的邮件大小限制为 150 MB。 有关详细信息，请参阅 [Exchange Online 中的邮件](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits)。

 **PST 文件导入到 Microsoft 365 邮箱时，是否会保留邮件发送时间或接收时间、收件人列表和其他邮件属性？**

是的。导入过程中不会更改原始邮件元数据。

 **我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**

是的。不能导入包含 300 个或更多级别的嵌套文件夹的 PST 文件。

 **是否可以使用网络上传将 PST 文件导入到 Office 365 中的非活动邮箱？**

是的，这一功能现已推出。

 **是否可以使用网络上传将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**

是的，这一功能现已推出。 

 **是否可以使用网络上传将 PST 文件导入 Exchange Online 中的公用文件夹？**

否，无法将 PST 文件导入公用文件夹。

### <a name="using-drive-shipping-to-import-pst-files"></a>使用驱动器寄送导入 PST 文件

 **在 Office 365 导入服务中创建导入作业需要哪些权限？**

必须分配有邮箱导入导出角色，才能将 PST 文件导入到 Microsoft 365 邮箱。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以向“组织管理”角色组添加“邮箱导入导出”角色。 或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。 有关详细信息，请参阅[管理 Exchange Online 中的角色组](/Exchange/permissions-exo/role-groups)中的“向角色组添加角色”或“创建角色组”部分。

此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：

- 在 Exchange Online 中必须分配有“邮件收件人”角色。默认情况下，此角色分配给“组织管理和收件人管理”角色组。

    或

- 必须是你组织中的全局管理员。

> [!TIP]
> 请考虑在 Exchange Online 中创建专门用于将 PST 文件导入到 Office 365 的新角色组。要获得导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。

 **哪些地区提供驱动器传送服务？**

当前，美国、加拿大、巴西、英国、欧洲、印度、东亚、东南亚、日本、韩国和澳大利亚已推出驱动器传送服务。不久之后，还会有更多地区提供此服务。

> [!NOTE]
> 目前，不可在德国和瑞士使用驱动器发运导入 PST 文件。 当这些国家/地区提供驱动器发运功能后，此常见问题解答将更新。

 **哪些商业许可协议支持驱动器发运？**

驱动器传送可通过 Microsoft 企业协议 (EA) 将 PST 文件导入到 Microsoft 365。驱动器传送不可通过 Microsoft 产品和服务协议 (MPSA) 实现。

 **使用驱动器传送将 PST 文件导入到 Microsoft 365 的定价如何？**

使用驱动器传送将 PST 文件导入到 Microsoft 365 邮箱的费用为每 GB 数据 2 美元。 例如，如果发运的硬盘包含 1,000 GB (1 TB) 的 PST 文件，则费用为 2,000 美元。 您可以与合作伙伴共同协作来支付导入费用。 有关查找合作伙伴的信息，请参阅[查找 Microsoft 合作伙伴或经销商](../admin/manage/find-your-partner-or-reseller.md)。

 **哪类硬盘支持驱动器发运？**

对于 Office365 导入服务，仅支持使用 2.5 英寸固态硬盘 (SSD) 或者 2.5 或 3.5 英寸 SATA II/III 内部硬盘。可以使用容量最大为 10 TB 的硬盘驱动器。对于导入作业，将仅处理硬盘驱动器上的第一个数据卷。必须使用 NTFS 格式化数据卷。将数据复制到硬盘驱动器上时，可使用 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III 连接线将其直接连接，或可使用外部 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III USB 适配器在外部连接。

> [!IMPORTANT]
> Office365 导入服务不支持附带内置 USB 适配器的外部硬盘。此外，不能使用外部硬盘驱动器外壳内的磁盘。请不要运送外部硬盘。

 **单个导入作业可以发运多少个硬盘？**

单个导入作业最多可以发运 10 个硬盘。

 **传送硬盘后，需要多长时间才能转到 Microsoft 数据中心？**

这取决于几点，例如你与 Microsoft 数据中心之间的距离、使用哪种类型的送货选项来配送硬盘（如隔天送达、两天送达或地面配送）。对于大多数运货商，可使用跟踪编号跟踪配送状态。

 **硬盘驱动器到达 Microsoft 数据中心后，需要多久才能将 PST 文件上传到 Azure？**

Microsoft 数据中心收到你的硬盘后，需花 7 到 10 个工作日将 PST 文件上传到你组织的 Azure 存储位置。 PST 文件将上传到名为 `ingestiondata` 的 Azure Blob 容器。

 **将 PST 文件导入到邮箱需要多长时间？**

将 PST 文件上传到 Azure 存储区域后，Microsoft 365 采用安全方式分析 PST 文件中的数据，确定 PST 文件中所含项目的存在时长以及各种邮件类型。 分析完成后，可以选择将所有数据导入 PST 文件，或设置筛选器控制导入的数据。 开始导入作业后，PST 文件将以每天至少 24 GB 的速度导入到 Microsoft 365 邮箱。 如果此速度不能满足你的需求，可能需要考虑采用其他方法将电子邮件数据导入 Microsoft 365。 有关详细信息，请参阅[将多个电子邮件帐户迁移到 Microsoft 365 的方法](/Exchange/mailbox-migration/mailbox-migration)。

如果不同的 PST 文件导入到不同的目标邮箱中，则导入过程将以并行方式进行；也就是说，每个 PST/邮箱对是同时导入的。 同样，如果多个 PST 文件导入到同一个邮箱中，也将同时导入这些文件。

 **Microsoft 将 PST 文件上传到 Azure 后，这些文件在删除前可在 Azure 中保留多长时间？**

在安全与合规中心的“**导入 PST 文件**”页面上创建最新导入作业的 30 天后，将删除组织的 Azure 存储位置（位于名为 `ingestiondata` 的 Blob 容器中）内的所有 PST 文件。

这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。 虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。

 **哪个版本的 PST 文件格式支持导入到 Microsoft 365？**

可选两个版本的 PST 文件格式：ANSI 和 Unicode。 建议导入使用 Unicode PST 文件格式的文件。 但是，采用 ANSI PST 文件格式的文件也可以导入到 Microsoft 365，如语言采用双字节字符集 (DBCS) 的文件。 有关导入 ANSI PST 文件的详细信息，请参阅[使用驱动器传送将组织的 PST 文件导入到 Microsoft 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file) 中的步骤 3。

此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Microsoft 365。

 **导入 PST 文件时是否有邮件大小限制？**

是。 如果 PST 文件包含大于 150 MB 的邮箱项目，导入过程中将跳过且不导入该项目。 不导入大小超过 150 MB 的邮件，因为 Exchange Online 中的邮件大小限制为 150 MB。 有关详细信息，请参阅 [Exchange Online 中的邮件](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits)。

  **PST 导入进程如何处理重复的电子邮件项？**

如果目标邮箱或目标存档的目标文件夹中存在匹配项，PST 导入进程将检查重复的项目，并且不会将邮件项从 PST 文件复制到邮箱或存档。 如果重新导入相同的 PST 文件并指定与上一个导入作业中指定的文件夹不同的目标文件夹（使用 PST 导入映射文件中的 TargetRootFolder 属性），将重新导入 PST 文件中的所有项。

 **PST 文件导入到 Microsoft 365 邮箱时，是否会保留邮件发送时间或接收时间、收件人列表和其他邮件属性？**

是的。导入过程中不会更改原始邮件的元数据

 **我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**

是的。不能导入包含 300 个或更多级别的嵌套文件夹的 PST 文件。

 **是否可以使用驱动器传送将 PST 文件导入到 Microsoft 365 中的非活动邮箱？**

是的，这一功能现已推出。

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

 **If I have to ship my hard drive to another country, is there anything I need to do?**

你发运到 Microsoft 的硬盘可能会跨越国际边界。如果是这种情况，你有责任确保硬盘及其所含数据是根据适用法律导入和/或导出的。发运硬盘前，请与顾问联系以验证驱动器和数据可以合法地发送到指定的 Microsoft 数据中心。此操作有助于确保其及时送达 Microsoft。
