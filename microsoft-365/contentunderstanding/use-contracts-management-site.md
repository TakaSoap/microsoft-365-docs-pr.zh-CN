---
title: 使用 Microsoft 合同管理网站模板SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: kkameth
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: 了解如何在 Microsoft SharePoint Syntex 中设置、使用和自定义合同管理网站SharePoint Syntex。
ms.openlocfilehash: e5629dd370899d504e9b64ef577a06ebf1bd3777
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320461"
---
# <a name="use-the-contracts-management-site-template-for-microsoft-sharepoint-syntex"></a>使用 Microsoft 合同管理网站模板SharePoint Syntex

合同管理网站是一个随时可供部署且可自定义SharePoint网站模板，可帮助您的组织最大程度地提高 SharePoint Syntex。 该网站旨在让您创建一个专业网站来管理、处理和跟踪组织中合同的状态。

## <a name="features-of-the-site"></a>网站的功能

![合同管理网站模板主页的屏幕截图。](../media/content-understanding/contracts-management-site-home-page.png)

合同管理网站包括预填充的页面、Web 部件和网站导航。 可以自定义网站以合并组织自己的品牌、员工信息、策略和规划信息、工作流、联系人和资源。

该网站使用在文档库上运行SharePoint Syntex模型SharePoint文档和提取元数据。 该网站提供预生成的文档库，可快速入门，但您也可以根据需要创建自己的文档库。 该网站包括以下特色库：

- **区域** – 按地理区域、国家/地区或区域对合同文档进行分类。

- **模板** – 为合同类型选择适当的合同模板，例如保密协议、服务协议和工作声明。

- **合同请求** – 直接向你的合同团队启动合同请求。

- **客户端** – 在一个方便的位置查找客户端信息。

- **模型** – 使用此库中的模型对文档进行分类并提取元数据。 用户可以创建自己的模型以满足其需求，并将其添加到此库。

- **示例合同库** – 查找已分类且已使用模型提取元数据SharePoint Syntex文件。 

库中有一个单独的视图，您可以在其中跟踪其他元数据（如状态）并使用文档库格式以更直观的方式显示它。

## <a name="provision-the-site"></a>设置网站

可以从"合同管理"服务预配SharePoint[网站](https://lookbook.microsoft.com/)。

!["合同管理"网站模板设置页面的屏幕截图。](../media/content-understanding/contracts-management-site-provisioning-page.png)

> [!NOTE]
> 您必须是全局管理员或SharePoint管理员Microsoft 365网站。 还必须拥有一个SharePoint Syntex许可证才能将此网站模板添加到您的组织。

1. 从"查看设计"[SharePoint](https://lookbook.microsoft.com/) > 主页上的"查看设计"菜单上，选择"SharePoint Syntex **SharePoint Syntex合同管理"**。

2. 在" **合同管理"** 页上，选择 **"添加到租户"**。

    !["合同管理"网站模板设置页上的"添加到租户"按钮的屏幕截图。](../media/content-understanding/contracts-management-site-add-to-your-tenant.png)

3. 输入您的电子邮件地址 (，以通知网站何时准备好使用) 、想要使用的网站 URL 以及要用于网站的标题。 

    !["合同管理"网站模板设置页上的电子邮件和网站 URL 字段的屏幕截图。](../media/content-understanding/contracts-management-email-and-site-url.png)

4. 选择“**预配**”，很快你的网站就可供使用了。 You'll get an email (sent to the email address you provided) indicating the Contracts Management site template is completed.

5. 选择 **"打开** 网站"，你将看到合同管理网站。 在这里，您可以浏览网站并自定义页面和内容。 

有关从书SharePoint设置详细信息，请参阅预配[新的学习路径解决方案](/office365/customlearning/custom_provision)。

## <a name="customize-the-site"></a>自定义网站

在与其他用户共享合同管理网站之前，您需要自定义该网站以满足您的要求。 

### <a name="customize-the-look-and-feel-of-your-site"></a>自定义网站的外观和感觉

自定义网站的以下元素以适应组织的需要：

- 更新 [合同管理](https://support.microsoft.com/office/customize-your-sharepoint-site-320b43e5-b047-4fda-8381-f61e8ac7f59b) 网站上的品牌，以与组织保持一致。
- 自定义 [“英雄”Web 部件](https://support.microsoft.com/office/use-the-hero-web-part-d57f449b-19a0-4b0d-8ce3-be5866430645)，以在可能的情况下包含组织真实站点的图像。
- 自定义 [人员 Web 部件](https://support.microsoft.com/office/show-people-profiles-on-your-page-with-the-people-web-part-7e52c5f6-2d72-48fa-a9d3-d2750765fa05) 以包括合同经理或其他联系人的联系信息。
- 自定义 [文本 Web 部件](https://support.microsoft.com/office/add-text-and-tables-to-your-page-with-the-text-web-part-729c0aa1-bc0d-41e3-9cde-c60533f2c801) ，向样式、项目符号、缩进、突出显示和链接等选项添加段落和设置格式。
- 自定义 [图像 Web 部件](https://support.microsoft.com/office/use-the-image-web-part-a63b335b-ad0a-4954-a65d-33c6af68beb2) 以将图像添加到页面。
- 自定义 [快速链接 Web 部件](https://support.microsoft.com/office/use-the-quick-links-web-part-e1df7561-209d-4362-96d4-469f85ab2a82) 以组织和显示指向其他资源的链接。
- 根据需要 [将其他 Web](https://support.microsoft.com/office/using-web-parts-on-sharepoint-pages-336e8e92-3e2d-4298-ae01-d404bbe751e0) 部件添加到网站。
- 根据需要自定义[页面布局](https://support.microsoft.com/office/add-sections-and-columns-on-a-sharepoint-modern-page-fc491eb4-f733-4825-8fe2-e1ed80bd0899)。
- 添加新 [页面](https://support.microsoft.com/office/create-and-use-modern-pages-on-a-sharepoint-site-b3d46deb-27a6-4b1e-87b8-df851e503dec) 以添加其他支持或信息性资源。

### <a name="customize-the-site-navigation"></a>自定义网站导航

您可以控制合同管理网站的网站导航。 使用以下资源帮助你进行与组织一致的更改：

- 自定义[网站导航](https://support.microsoft.com/office/customize-the-navigation-on-your-sharepoint-site-3cd61ae7-a9ed-4e1e-bf6d-4655f0bf25ca)。
- [将此网站与中心相关联](https://support.microsoft.com/office/associate-a-sharepoint-site-with-a-hub-site-ae0009fd-af04-4d3d-917d-88edb43efc05)。
- 使用[受众目标](https://support.microsoft.com/office/target-navigation-news-and-files-to-specific-audiences-33d84cb6-14ed-4e53-a426-74c38ea32293)将特定导航链接指向特定用户。 
- 如果需要，[可删除不需要的页面](https://support.microsoft.com/office/delete-a-page-from-a-sharepoint-site-1d4197b8-31b6-460d-906b-3fb492a51db1)。


### <a name="add-other-workflows"></a>添加其他工作流

合同管理网站包含您需要开始的组件，但您也可以包括其他组件，例如：

- 当 [Power Automate](/power-automate/getting-started)合同请求库时，使用工作流流 **触发工作流。**
- 生成其他[SharePoint Syntex模型](/microsoft-365/contentunderstanding/#models)。
- 使用 [模板库](content-assembly.md) 上 **的内容程序集** 功能。
- 将[合同管理解决方案与](solution-manage-contracts-in-microsoft-365.md)项目SharePoint Syntex组件一Microsoft 365。

## <a name="share-the-site-with-others"></a>与他人共享网站

[与他人共享网站](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658)。 与组织中的其他人合作，以确保合同管理网站已广为人知并且已被采用。

管理合同管理网站的关键成功因素：

- 庆祝合同管理网站的启动。
- 创建并发布宣布新资源的新闻。
- 确保用户有提出问题和反馈的渠道。
- 为了清楚起见， [使用](https://support.microsoft.com/office/view-usage-data-for-your-sharepoint-site-2fa8ddc2-c4b3-4268-8d26-a772dc55779e) 网站分析中的见解来推广主页上的内容、更新导航或重写内容。
- 根据需要查看合同管理网站，以确保内容是新鲜且仍然相关的。

