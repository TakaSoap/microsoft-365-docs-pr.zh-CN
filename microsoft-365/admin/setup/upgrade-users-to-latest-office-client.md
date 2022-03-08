---
title: 将 Office 2010 升级到 Microsoft 365 - Microsoft 365 管理员
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: 了解如何为Microsoft Office升级到Office客户端。
ms.topic: article
ms.openlocfilehash: 7994fb10d00484f2c211f4443d2030fa71003d5f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321693"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>将Microsoft 365用户升级至最新的 Office 客户端

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 年达到支持终止

Office 2010 年 10 月 13 日终止支持。 Microsoft 将不再提供以下内容：

- 针对问题的技术支持

- 发现的问题的错误修复

- 已发现漏洞的安全修补程序

有关详细信息[，Office 2010 年 10 月](/deployoffice/endofsupport/office-2010-end-support-roadmap)停止提供支持路线图。

 **这是否适合你的主题？**
  
 如果你是组织中负责商业版订阅Microsoft 365管理员，那么这里就对了。 管理员通常负责管理用户、重置密码、管理 Office安装以及添加或删除许可证等任务。

 如果你不是管理员并且你有一个Microsoft 365 家庭版产品，请参阅[](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans)如何升级 [Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350)，了解如何升级旧版家庭版 Office。

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>准备好升级到 Microsoft 365

作为管理员，你可以控制组织中Office可以安装的版本。 强烈建议您帮助组织中运行早期版本的 Office（如 Office 2010、Office 2013 或 Office 2016）的用户升级到最新版本，以充分利用其安全性和工作效率改进。

## <a name="upgrade-steps"></a>升级步骤

以下步骤将指导你完成将用户升级到最新桌面Office的过程。 我们建议您在开始升级过程之前阅读这些步骤。
  
## <a name="step-1---check-system-requirements"></a>步骤 1 - 检查系统要求

[检查设备Office](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)要求以确保你的设备与最新版本的 Office。 例如，无法将较新版本的 Office 安装在运行 Windows XP 或 vista Windows计算机上。
  
> [!TIP]
> 如果你的组织中用户在电脑或笔记本电脑上运行早期版本Windows，我们建议升级到 Windows 10。 Windows 7 已终止支持。 有关详细信息[，请参阅Windows 7 的支持将于 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 年 1 月结束。

请查看Windows 10[系统](https://www.microsoft.com/windows/windows-10-specifications)要求，以查看您是否可以升级其操作系统。

### <a name="check-application-compatibility"></a>检查应用程序兼容性

为了确保成功升级，我们建议确定 Office 应用程序（包括 VBA 脚本、宏、第三方外接程序以及复杂的文档和电子表格）并评估其与 Office 最新版本的兼容性。
  
例如，如果当前安装的是第三方Office，请与制造商联系，以确保它们与最新版本的 Office。
  
## <a name="step-2---check-your-existing-subscription-plan"></a>步骤 2 - 检查现有订阅计划

某些Microsoft 365计划不包括完整桌面版本的 Office并且如果你的计划不包括 Office，则升级步骤Office。
  
不确定你拥有哪一个订阅计划？ 请参阅[Microsoft 365商业版订阅是什么？](../admin-overview/what-subscription-do-i-have.md)
  
如果现有计划包含Office，请继续执行步骤 [3 - 卸载Office](#step-3---uninstall-office)。
  
如果现有计划不包括Office，请从以下选项中进行选择：
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>不包括升级选项的计划的升级Office

 **选项 1：Office订阅**

切换到包含订阅的Office。 请参阅[切换到其他Microsoft 365商业计划](../../commerce/subscriptions/switch-to-a-different-plan.md)。

**选项 2：购买个人、一次购买 Office，或Office批量许可证购买产品**

 - 购买个人、一次购买Office。 请参阅[Office家庭&amp;企业或](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b)[Office Professional](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)

     或

 - 通过批量许可证购买Office副本。 请参阅比较 [通过批量许可提供的套件](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)。

## <a name="step-3---uninstall-office"></a>步骤 3 - 卸载Office

在安装最新版本的 Office，我们建议您卸载所有早期版本的 Office。 但是，如果你改变主意Office升级，请注意以下实例，在卸载Office将无法重新安装它。
  
如果你有第三方外接程序，请与制造商联系，以查看是否有将使用最新版本的 Office。

> [!TIP]
> 如果在卸载 microsoft Office时遇到问题，可以使用 Microsoft 支持和恢复助手 工具帮助您删除Office：下载[并运行 Microsoft](https://go.microsoft.com/fwlink/?LinkID=2155008) 支持和恢复助手。

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>选择要卸载Office的版本

- [从电脑](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [从 Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>尝试在卸载后重新安装旧版 Office已知问题

 **Office批量** 许可如果不再能够访问这些批量许可证版本的 Office，将无法重新安装它。

 **Office** 预安装在您的计算机上 如果您不再具有光盘或产品密钥 (如果 Office 有一个) 将无法重新安装它。

 **不支持的订阅** 如果你的 Office 副本是通过停止使用的订阅（如 Office 365 小型企业高级版 或 Office 365 中型企业版）获取的，则你将无法安装较旧版本的 Office，除非你拥有订阅提供的产品密钥。

如果你想要将较旧版本的 Office 与最新版本并排安装，你可以在同一台电脑安装和使用不同版本的 Office 中查看受支持的版本[列表](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)。 并行安装可能是正确的选择，例如，如果已安装要用于旧版 Office的第三方加载项，但还不确定它们是否与最新版本兼容。

## <a name="step-4---assign-office-licenses-to-users"></a>步骤 4 - Office许可证分配给用户

如果尚未这样做，请为组织中需要安装 Office 的任何用户分配许可证，请参阅为 Microsoft 365 [for business 中的用户分配许可证](../manage/assign-licenses-to-users.md)。
  
## <a name="step-5---install-office"></a>步骤 5 - 安装Office

在验证要升级的用户是否全部拥有许可证后，最后一步是让他们安装 Office，请参阅在电脑或 Mac 上下载并安装或重新安装 [Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。
  
> [!TIP]
> 如果你不希望用户自行安装Office，请参阅在 Office 365 [中管理软件下载Office 365](/DeployOffice/manage-software-download-settings-office-365)。 可以使用 Office [部署](/DeployOffice/overview-office-deployment-tool)工具将 Office 软件下载到本地网络，然后Office你通常使用的软件部署方法部署 Office。