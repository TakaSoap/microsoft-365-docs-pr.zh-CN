---
title: 敏感度标签概述
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 01/06/2020
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 使用敏感度标签，可以对敏感内容进行分类和保护，同时确保组织内人员的工作效率和协作能力不受阻碍。敏感度标签可用于对已标记内容应用包括加密或水印在内的保护设置。
ms.openlocfilehash: 91481bb1c1267b40ccd2596c06faf5005372ac39
ms.sourcegitcommit: 3063e351e21614c236167e9cde40994d8b532bd6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989497"
---
# <a name="overview-of-sensitivity-labels"></a>敏感度标签概述

组织内人员需要与组织内外的其他人员协作，才能完成工作。也就是说，内容不再一直停留在防火墙后面 — 而是可跨设备、应用和服务到处漫游。你希望内容的漫游方式不仅安全、受保护，还符合组织的业务和合规性策略。

使用敏感度标签，可以对敏感内容进行分类和保护，而组织内人员的工作效率和协作能力丝毫不受影响。

敏感度标签示例：

![Excel 功能区和状态栏上的敏感度标签](media/Sensitivity-label-in-Excel.png)

仅全局（公共）云中的租户支持敏感度标签。 目前，其他云（如[国家云](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)）中的租户不支持敏感度标签。

若要应用敏感度标签，用户必须使用其工作或学校帐户登录到 Office。

借助敏感度标签，你可以：
  
- **强制执行保护设置，如对已标记内容设置加密或水印。** 例如，用户可以向文档或电子邮件应用“机密”标签，然后此标签便能加密相应内容，并应用“机密”水印。

- **跨不同平台和设备保护 Office 应用中的内容。** 有关受支持的应用的列表，请参阅[在 Office 应用中的敏感度标签](sensitivity-labels-office-apps.md)。

- **利用 Microsoft Intune 终结点保护，防止在 Windows 设备上驻留的敏感内容从组织中泄露。** 当 Windows 设备上驻留的内容已应用有敏感度标签后，终结点保护可以阻止此类内容被复制到第三方应用（如 Twitter 或 Gmail），也可以阻止此类内容被复制到可移动存储（如 U 盘）。

- 利用 Microsoft Cloud App Security **保护第三方应用和服务中的内容**。 借助 Cloud App Security，可检测、分类、标记和保护第三方服务和应用（如 SalesForce、Box 或 Dropbox）中的内容，即使第三方应用或服务无法读取或不支持敏感度标签也不例外。

- **将敏感度标签扩展到第三方应用和服务。** 借助 Microsoft 信息保护 SDK，[这些平台](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)上的第三方应用可读取敏感度标签并应用保护设置。

- **对内容进行分类，无需使用任何保护设置。** 也可以只对内容进行分类（如不干胶标签），只要有人使用和共享内容，此分类就会随内容一起暂留和漫游。 使用此分类，可生成使用情况报告，并查看敏感内容的活动数据。 根据此类信息，稍后随时可以选择应用保护设置。

在所有这些情况下，Office 365 中的敏感度标签都可帮助你针对各个内容采取恰当的操作。 通过敏感度标签，可对整个组织中的数据分类进行分类，并根据该分类强制执行保护设置。
  
可在 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心的“**分类**” > “**敏感度标签**”下创建敏感度标签。 这些敏感度标签可供 Azure 信息保护、Office 应用和 Office 365 服务使用。

对于 Azure 信息保护客户，可以在其他管理中心内使用 Azure 信息保护标签。如果你选择执行其他配置或高级配置，这些标签便会与 Azure 门户同步。 Azure 信息保护标签和 Office 365 敏感度标签彼此相互兼容。也就是说，例如，如果内容已有 Azure 信息保护标签，无需重新对此内容进行分类或标记。

## <a name="what-a-sensitivity-label-is"></a>什么是敏感度标签

为文档或电子邮件分配敏感度标签时，它就像是应用于以下内容的标记：

- **可自定义**：可以为组织中不同级别的敏感内容创建类别，如“个人”、“公开”、“常规”、“机密”和“高度机密”。

- **明文。** 由于该标签以明文的方式存储在内容的元数据中，因此第三方应用和服务可以读取它，然后根据需要应用其自己的保护操作。

- **永久。** 将敏感度标签应用于内容后，该标签将保留在该电子邮件或文档的元数据中。 这意味着标签将随内容（包括保护设置）一起漫游，并且此数据将成为应用和强制实施策略的基础。

在 Office 应用中，敏感度标签就像是电子邮件或文档上向用户显示的标记。

每个内容项都可以应用有一个敏感度标签。一个内容项可以同时应用有一个敏感度标签和一个[保留标签](labels.md)。

![应用于电子邮件的敏感度标签](media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>敏感度标签有何用途

除了电子邮件和文档以外，多个公共预览版本也提供了敏感度标签。 有关如何将敏感度标签用于文件、团队、组和网站的详细信息，请参阅以下文章：

- [启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)

- [将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用](sensitivity-labels-teams-groups-sites.md)

当电子邮件或文档应用敏感度标签后，系统便会对内容强制执行相应标签的任何已配置保护设置。 敏感度标签可用于：

- 仅**加密**加密电子邮件，或者同时加密电子邮件和文档。 可选择哪些用户或组有权执行哪些操作多长时间。 例如，可选择允许组织之外特定域中的用户有权查看内容且查看期限为对该内容标上标签后 7 天内。 或者，与其自行分配权限，可允许用户在应用标签时分配对内容的权限。 有关详细信息，请参阅[使用敏感度标签中的加密限制对内容的访问](encryption-sensitivity-labels.md)。

- **内容标记**：方法是向已应用标签的电子邮件或文档添加自定义水印、页眉或页脚。 水印只能应用于文档，不得应用于电子邮件，并且长度限制为 255 个字符。 此外，页眉和页脚长度限制为 1024 个字符（在 Excel 中除外，其中的页眉和页脚长度限制为 255 个字符或更少，具体取决于文档是否包含其他页眉或页脚和其他因素。）

    ![应用于文档的水印和页眉](media/Sensitivity-label-watermark-header.png)

- **防止数据丢失**：方法是在 Intune 中开启终结点保护。 如果下载了敏感内容，则有助于防止 Windows 设备中的数据丢失。 例如，不能将带有标签的内容复制到 Dropbox、Gmail 或 U 盘中。 在敏感度标签可以使用 Windows 信息保护 (WIP) 之前，先需要在 Azure 门户中创建应用保护策略。 有关详细信息，请参阅 [Windows 信息保护如何使用敏感度标签保护文件](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。

- **将标签应用到包含敏感信息的内容。** 你可以选择要标记的敏感信息类型，标签可以自动应用，也可以提示用户应用你推荐的标签。如果你推荐标签，则提示会显示你选择的任何文本。有关详细信息，请参阅[自动将敏感标签应用于内容](apply-sensitivity-label-automatically.md)。

    ![提示分配所需的标签](media/Sensitivity-label-Prompt-for-required-label.png)

创建敏感度标签时即会提供以下所有选项：

![创建敏感度标签时可使用的选项](media/Sensitivity-label-create-options.png)

### <a name="label-priority-order-matters"></a>标签优先级（顺序非常重要）

在管理中心创建敏感度标签时，这些标签会显示在“**标签**”页的“**敏感度**”选项卡的列表中。 此列表中的标签顺序至关重要，因为它反映了标签的优先级。 限制性最高的敏感度标签（如“高度机密”）需显示在此列表的**底部**，限制性最低的敏感度标签（如“公开”）需显示在**顶部**。

一个文档或电子邮件仅可应用一个敏感度标签。 如果要求用户提供将标签更改为较低分类的理由，理由可以是此列表的排序，因为它会标识较低分类。

标签优先级也适用于子标签。

![子标签创建选项](media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>子标签（对标签进行分组）

使用子标签，你可以将一个或多个标签分组到用户在 Office 应用程序中看到的父标签下方。 例如，在“机密”下，你的组织可能会为该分类的特定类型使用多个不同的标签。 在此示例中，父标签“机密”仅仅是没有保护设置的文本标签，并且因为它具有子标签，所以它不能应用于内容。 相反，用户必须选择“机密”才能查看子标签，然后他们可以选择要应用于内容的子标签。

子标签只是向逻辑组中的用户显示标签的一种方式。 子标签不会从其父标签继承任何设置。 为用户发布子标签后，该用户可以将该子标签应用于内容，但不能仅应用父标签。

请勿选择父标签作为默认标签或将父标签配置为自动应用或推荐使用，因为父标签不会应用于使用 Azure 信息保护统一标签客户端的 Office 应用中的内容。

面向用户的子标签显示方式示例：

![功能区上的已分组子标签](media/Sensitivity-label-grouped-labels.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>编辑或删除敏感度标签

如果删除敏感度标签，不会从内容中删除标签，并且会对内容继续强制执行所有保护设置。

如果编辑敏感度标签，应用于内容的标签版本就是对相应内容强制执行的标签。

## <a name="what-label-policies-can-do"></a>标签策略有何用途

创建敏感度标签后，需要发布它们，以便组织内人员能够将标签应用于内容。与发布到所有 Exchange 邮箱等位置的保留标签不同，敏感度标签是发布到用户或组。然后，敏感度标签便会显示在这些用户或组的 Office 应用中。

借助标签策略，你可以：

- **选择向哪些用户和组显示标签。** 可以将标签发布到任意启用电子邮件的安全组、通讯组、Office 365 组或动态通讯组。

- **将默认标签应用于**标签策略包含的用户和组新建的所有文档和电子邮件。此默认标签可设置要对所有内容应用的保护设置的基本级别。

- **要求提供更改标签的理由。** 如果内容标记为“机密”，并且用户希望删除该标签或将其替换为较低分类，例如名为“公共”的标签，则可以要求用户在执行此操作时提供理由。 目前，未将理由原因发送到[标签分析](label-analytics.md)供管理员查看。 但是，[Azure 信息保护统一标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)将此信息发送到 [Azure 信息保护分析](https://docs.microsoft.com/azure/information-protection/reports-aip)。

    ![提示用户输入理由的页面](media/Sensitivity-label-justification-required.png)

- **要求用户将标签应用于他们的电子邮件和文档。** 如果你希望标记用户的所有内容，则可以要求必须将标签应用于所有已保存的文档和已发送的电子邮件。标签可以由用户手动分配、按条件自动分配或者进行默认分配（上述默认标签选项）。以下是当要求用户分配标签时 Outlook 中显示的提示。

    > [!NOTE]
    > 强制性标记要求具备 Azure 信息保护订阅。 要使用此功能，必须下载并安装 [Azure 信息保护客户端](https://www.microsoft.com/download/details.aspx?id=53018)或更高版本的 [Azure 信息保护统一标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。 此外，客户端仅在 Windows 上运行，因此 Mac、iOS 和 Android 上尚不支持此功能。

    ![在 Outlook 中要求用户应用所需标签的提示](media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)

- **为自定义帮助页面提供帮助链接。** 如果用户不确定敏感度标签的含义或应如何使用标签，你可以提供在 Office 应用中“**敏感度标签**”菜单底部显示的“了解更多”URL。

    ![功能区上“敏感度”按钮中的“了解更多”链接](media/Sensitivity-label-learn-more.png)

在你创建标签策略并将敏感度标签分配给用户和组后，这些人员会在不超过一小时的时间内在 Office 应用中看到这些标签。

可创建和发布的敏感度标签的数量没有限制，但有一种例外：如果标签应用了加密，则最多可以有 500 个标签。 但是，最佳做法是减少管理开销并降低用户复杂程度，尽量将标签的数量保持在最低限度。 事实证明，当用户拥有五个以上的主标签或者每个主标签拥有五个以上的子标签时，实际部署的效率就会显著降低。

### <a name="label-policy-priority-order-matters"></a>标签策略优先级（顺序非常重要）

你可以通过在敏感度标签策略中发布敏感度标签来向用户提供敏感度标签，该策略显示在“**标签策略**”页的“**敏感度策略**”选项卡的列表中。 正如敏感度标签（参见[标签优先级（顺序非常重要）](#label-priority-order-matters)）一样，敏感度标签策略的顺序很重要，因为它反映了它们的优先级。 优先级最低的标签策略显示在**顶部**，优先级最高的标签策略显示在**底部**。

标签策略包括：

- 一组标签。
- 标签策略的范围，表示策略中包含的用户和组。
- 上述标签策略的设置（默认标签、对齐方式、强制标签和帮助链接）。

可以在多个标签策略中包含某个用户，该用户将看到这些策略中的所有敏感度标签。 但是，用户只能从具有最高优先级的标签策略中看到策略设置。

如果组织中的用户或组在标签策略中没有看到你想要的选项（例如默认标签或强制标签），请检查敏感度标签策略的顺序。 若要重新排序标签策略，请选择某个敏感度标签策略 > 选择右侧的省略号 >“**下移**”或“**上移**”。

![敏感度标签策略页上的移动选项](media/sensitivity-label-policy-priority.png)

虽然敏感度标签策略的优先级很重要，但保留标签策略的优先级并**不**重要。 如[保留原则或优先原则？](labels.md#the-principles-of-retention-or-what-takes-precedence)中所述，内容可能受多个保留策略的约束。

## <a name="how-to-get-started-with-sensitivity-labels"></a>如何开始使用敏感度标签

敏感度标签可快速上手：

1. **定义标签。** 首先，需要建立分类法，以定义具有不同敏感度级别的内容。 使用对用户有意义的常用名称或术语。 例如，可以先使用“个人”、“公开”、“常规”、“机密”和“高度机密”等标签。 可以使用子标签按类别对类似标签进行分组。 此外，创建标签时，还需要一个工具提示，当用户将鼠标悬停在功能区上的标签选项上时，该提示将显示在 Office 应用中。

2. **定义每个标签的用途。** 然后，配置要与每个标签关联的保护设置。 例如，较低敏感度内容（如“常规”标签）可以只应用有页眉或页脚，而较高敏感度内容（如“机密”标签）则可以应用有水印、加密和 WIP，这样有助于确保只有特权用户才能访问它。

3. **定义谁能获取标签。** 定义组织的标签后，通过标签策略发布它们。标签策略控制了哪些用户和组能看到这些标签。一个标签是可重用的。也就是说，定义标签一次后，可将它添加到分配给不同用户的多个标签策略。不过，必须先发布相应标签，使其显示在 Office 应用或其他服务中，然后才能将标签分配给内容。刚开始的时候，可尝试仅将敏感度标签分配给少数几个人员。

下面的基本流展示了管理员、用户和 Office 应用为了让敏感度标签起作用所要执行的操作。

![敏感度标签工作流关系图](media/Sensitivity-label-flow.png)

## <a name="where-sensitivity-labels-can-appear"></a>敏感度标签可以显示在哪里

敏感度标签显示在 Office 应用的 UI 中。 要查看特定应用和平台的内置标签的当前可用性，请使用下表：

- [Word、Excel 和 PowerPoint 中的敏感度标签功能支持](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-word-excel-and-powerpoint)

- [Outlook 中的敏感度标签功能支持](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-outlook)

如果对 Windows 计算机使用了 Azure 信息保护统一标签客户端，则其他功能可用于敏感性标签。 有关详细信息，请参阅[比较 Windows 计算机的标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

### <a name="office-apps-on-windows"></a>Windows 上的 Office 应用

在 Windows 设备上的 Office 应用中，敏感度标签显示在功能区上“**开始**”选项卡的“**敏感度**”按钮中。 

使用内置标签时，已应用的标签还显示在窗口底部的状态栏中：

![Windows 上 Excel 功能区中的“敏感度”按钮](media/Sensitivity-label-Sensitivity-button.png)

### <a name="office-apps-on-the-web"></a>Web 上的 Office 应用

有关 Web 上的 Office 应用中使用敏感度标签的信息，请参阅[将敏感度标签应用于 Office Web 文档和电子邮件](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。

### <a name="office-apps-on-mac"></a>Mac 上的 Office 应用

在 Mac 设备上的 Office 应用中，敏感度标签显示在功能区上“**开始**”选项卡的“**敏感度**”按钮中。 已应用的标签还显示在窗口底部的状态栏中：

![Mac 上 Office 功能区中的“敏感度”按钮](media/Sensitivity-label-on-Mac.png)

### <a name="office-apps-on-ios"></a>iOS 上的 Office 应用

在 iOS 设备上的 Office 应用中，敏感度标签显示在功能区上“**开始**”选项卡的“**敏感度**”按钮中。 已应用的标签还显示在窗口底部的状态栏中：

![iOS 上 Office 功能区中的“敏感度”按钮](media/Sensitivity-label-on-iOS.png)

### <a name="office-apps-on-android"></a>Android 上的 Office 应用

在 Android 设备上的 Office 应用中，敏感度标签显示在功能区上“**开始**”选项卡的“**敏感度**”按钮中。 已应用的标签还显示在窗口底部的状态栏中：

![Android 上 Office 功能区中的“敏感度”按钮](media/Sensitivity-label-on-Android.png)

### <a name="more-information-on-sensitivity-labels-in-office-apps"></a>详细了解 Office 应用中的敏感度标签

- [将敏感度标签应用于 Office 文档和电子邮件](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [将敏感度标签应用于 Office 文件时的已知问题](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
- [在 Office 应用中的敏感度标签](sensitivity-labels-office-apps.md)

## <a name="how-sensitivity-labels-work-with-existing-azure-information-protection-labels"></a>如何结合使用敏感度标签与现有 Azure 信息保护标签

Azure 信息保护用户可以使用 Azure 信息保护统一标签客户端在 Windows 上对内容进行分类和标记。 现有的 Azure 信息保护标签可与新的敏感度标签（也称为统一标签）无缝协作。 这意味着你可以：

- 保留文档和电子邮件中的现有 Azure 信息保护标签。
- 保留现有 Azure 信息保护标签配置。

如果你使用的是 Azure 信息保护标签（因为你的租户尚未在[统一标签平台](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)上），我们建议你在激活统一标签之前避免在其他管理中心中创建新标签。 有关此过程的详细信息，请参阅[如何将 Azure 信息保护标签迁移到统一敏感度标签](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)。

## <a name="sensitivity-labels-and-the-azure-information-protection-client"></a>敏感度标签和 Azure 信息保护客户端

如果安装了 Azure 信息保护客户端，Office 365 专业增强版应用会自动关闭 Office Windows 应用中敏感度标签的内置标签。
要更改此默认行为以便可以使用内置标签，请参阅[关于 Office 内置标签客户端](sensitivity-labels-office-apps.md#about-the-office-built-in-labeling-client)。

## <a name="protect-content-on-windows-devices-by-using-endpoint-protection-in-microsoft-intune"></a>使用 Microsoft Intune 终结点保护来保护 Windows 设备上的内容

创建敏感度标签时，可以选择告诉 Windows，当此内容存储在 Windows 设备上时，需要对具有此标签的文件进行保护，防止数据泄露。 此选项有助于确保具有此标签的内容只能共享或复制到已批准的位置，即使其存储在终结点上也是如此。 实际上，为敏感度标签启用此选项将告诉 Windows 这是额外的关键数据，需要额外的使用限制。

当你启用此选项后，Windows 便能读取、理解和处理文档中的敏感度标签，并自动对内容应用 Windows 信息保护 (WIP)，无论内容是以何种方式到达 Windows 托管设备的。这样有助于防止已标记文件发生意外数据泄露，无论是否应用加密。

例如，Windows 可知道驻留在用户计算机上的 Word 文档已应用有“机密”标签，WIP 可应用应用保护策略，以防相应设备中的数据被复制或共享到任何非工作位置（如个人 OneDrive、个人电子邮件帐户、社交媒体或 U 盘）。

如果用户试图将已标记内容上传到个人 Gmail 帐户，便会看到以下消息。

![提示无法将已标记内容复制到 Gmail 的消息](media/Sensitivity-label-WIP-Gmail.png)

此外，如果用户试图将已标记内容保存到 U 盘，还会看到以下消息：

![提示无法将已标记内容保存到 U 盘的消息](media/Sensitivity-label-WIP-USB-drive.png)

### <a name="important-prerequisites-for-using-wip"></a>使用 WIP 的重要先决条件

必须先满足 [Windows 信息保护如何保护具有敏感度标签的文件](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)中提及的先决条件，然后敏感度标签才能使用 WIP。这篇主题提及以下先决条件：

- 确保运行的是 Windows 10 版本 1809 或更高版本。
- [设置 Microsoft Defender 高级威胁防护 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)，它会扫描标签内容并应用相应的 WIP 保护。 ATP 会独立于 WIP 执行一些操作，例如报告异常情况。
- 创建适用于终结点设备的 Windows 信息保护 (WIP) 策略。可以在下列两个位置之一执行此操作：

  - [使用适用于 Microsoft Intune 的 Azure 门户通过 MDM 创建 Windows 信息保护 (WIP) 策略](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)
  - [使用 System Center Configuration Manager 创建并部署 Windows 信息保护 (WIP) 策略](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)

## <a name="protect-content-in-third-party-apps-and-services-by-using-microsoft-cloud-app-security"></a>利用 Microsoft Cloud App Security 保护第三方应用和服务中的内容

利用 Cloud App Security (CAS) 保护第三方应用和服务中的内容。 借助 CAS，可检测、分类、标记和保护第三方服务和应用（如 SalesForce、Box 或 Dropbox）中的内容。 例如，Dropbox 可能无法理解敏感度标签，但 CAS 可访问并保护该位置中带标签的内容。

有关详细信息，请参阅[自动应用 Azure 信息保护分类标签](https://docs.microsoft.com/cloud-app-security/use-case-information-protection)。

### <a name="important-prerequisites-for-using-cas"></a>使用 CAS 的重要先决条件

必须先满足[自动应用 Azure 信息保护分类标签](https://docs.microsoft.com/cloud-app-security/use-case-information-protection)中提及的先决条件，这样敏感度标签才能使用 CAS。 本主题介绍了以下先决条件：

- 为租户[启用 Cloud App Security 和 Azure 信息保护](https://docs.microsoft.com/cloud-app-security/azip-integration)。
- [将应用连接到](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps) Cloud App Security。

## <a name="extend-sensitivity-labels-to-third-party-apps-and-services-by-using-the-microsoft-information-protection-sdk"></a>使用 Microsoft 信息保护 SDK 将敏感度标签扩展到第三方应用和服务

由于敏感度标签以明文形式暂留在文档的元数据中，因此第三方应用和服务可选择支持识别和保护包含此类标签的内容。我们会一直扩大对其他应用和服务的支持。

借助 [Microsoft 信息保护 SDK](https://docs.microsoft.com/information-protection/develop/)，第三方应用和服务可读取敏感度标签和保护并将其应用到文档。 SDK 支持[这些平台](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)上的应用。

借助此 SDK，可以标记和保护内容，且方式与其他 Microsoft 信息保护应用和服务（如 Office 应用、Office 365 服务、Azure 信息保护扫描程序、Microsoft Cloud App Security 及其他多个合作伙伴解决方案）兼容。有关示例，请详细了解 [Adobe Acrobat 中的敏感度标签支持](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738)。

若要详细了解 Microsoft 信息保护 SDK，请参阅[技术社区博客公告](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)。此外，还可以了解[与 Microsoft 信息保护集成的合作伙伴解决方案](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)。

## <a name="permissions-required-to-create-sensitivity-labels"></a>创建敏感度标签所需的权限

将要创建敏感度标签的合规团队成员需要 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心的访问权限。 默认情况下，你的租户管理员有权访问这些管理中心，并且可以向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。要获得委派的受限管理员访问权限，请转到其中一个管理中心的“**权限**”页面，然后将成员添加到**合规性管理员**或**安全管理员**角色组。

有关详细信息，请参阅[授予用户访问 Office 365 安全与合规中心的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

只有在创建和应用标签和标签策略时，才必须拥有这些权限。强制执行策略并不需要访问内容。