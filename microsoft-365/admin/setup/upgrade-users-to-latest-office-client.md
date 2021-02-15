---
title: 将 Office 2010 升级到 Microsoft 365 - Microsoft 365 管理员
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
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
description: 了解如何将Microsoft Office升级到组织中用户的最新 Office 客户端。
ms.openlocfilehash: 3f8ea0d16e1c27414b5f3e11e842e336fadb3e75
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233314"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>将 Microsoft 365 商业版用户升级到最新的 Office 客户端

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 达到支持终止

Office 2010 于 2020 年 10 月 13 日终止支持。 Microsoft 将不再提供以下内容：

- 问题的技术支持

- 发现的问题的错误修复

- 发现的漏洞的安全修复

有关详细信息， [请参阅 Office 2010 停止提供支持](https://docs.microsoft.com/deployoffice/endofsupport/office-2010-end-support-roadmap) 路线图。

 **这适合你的主题吗？**
  
 如果你是组织中负责 Microsoft 365 商业版订阅的管理员，则你的位置正确。 管理员通常负责管理用户、重置密码、管理 Office 安装以及添加或删除许可证等任务。

 如果你不是管理员并且拥有 [Microsoft 365](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) 家庭版产品，请参阅如何升级 [Office，](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) 了解如何升级旧版家庭版 Office。

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>准备好升级到 Microsoft 365

作为管理员，你可以控制组织中哪些版本的 Office 人员可以安装。 强烈建议你帮助组织中运行较旧版本的 Office（如 Office 2010、Office 2013 或 Office 2016）的用户升级到最新版本，以利用其安全性和工作效率改进。

## <a name="upgrade-steps"></a>升级步骤

以下步骤将指导你完成将用户升级到最新 Office 桌面客户端的过程。 建议在开始升级过程之前通读这些步骤。
  
## <a name="step-1---check-system-requirements"></a>步骤 1 - 检查系统要求

[检查 Office 的系统](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) 要求，确保设备与最新版本的 Office 兼容。 例如，无法将较新版本的 Office 安装在运行 Windows XP 或 Windows Vista 的计算机上。
  
> [!TIP]
> 如果你的组织中用户在电脑或笔记本电脑上运行较早版本的 Windows，我们建议升级到 Windows 10。 Windows 7 已终止支持。 有关详细信息 [，请参阅对 Windows 7 的支持将于 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 年 1 月结束。

查看 [Windows 10 系统要求](https://www.microsoft.com/windows/windows-10-specifications) ，以查看能否升级其操作系统。

### <a name="check-application-compatibility"></a>检查应用程序兼容性

为了确保成功升级，我们建议确定 Office 应用程序（包括 VBA 脚本、宏、第三方外接程序以及复杂的文档和电子表格）并评估其与最新版本 Office 的兼容性。
  
例如，如果在当前 Office 安装中使用的是第三方外接程序，请与制造商联系，以确保它们与最新版本的 Office 兼容。
  
## <a name="step-2---check-your-existing-subscription-plan"></a>步骤 2 - 检查现有订阅计划

某些 Microsoft 365 计划不包括 Office 的完整桌面版本，如果计划不包含 Office，则升级步骤会有所不同。
  
不确定你拥有哪一个订阅计划？ 请参阅 [我拥有哪些 Microsoft 365 商业版订阅？](../admin-overview/what-subscription-do-i-have.md)
  
如果现有计划包含 Office，请继续步骤[3 - 卸载 Office。](#step-3---uninstall-office)
  
如果现有计划不包括 Office，请从以下选项中进行选择：
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>不包括 Office 的计划的升级选项

 **选项 1：切换 Office 订阅**

切换到包含 Office 的订阅。 请参阅 [切换到其他 Microsoft 365 商业版计划](../../commerce/subscriptions/switch-to-a-different-plan.md)。

**选项 2：购买 Office 的单个一次购买，或通过批量许可证购买 Office**

 - 购买 Office 的单个一次购买。 请参阅 [Office Home Business &amp; 或](https://products.office.com/home-and-business) [Office Professional](https://products.office.com/professional)

     或

 - 通过批量许可证购买 Office 的多个副本。 请参阅， [比较通过批量许可提供的套件](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)。

## <a name="step-3---uninstall-office"></a>步骤 3 - 卸载 Office

在安装最新版本的 Office 之前，建议卸载所有旧版本的 Office。 但是，如果你改变了升级 Office 的想法，请注意以下实例，在卸载 Office 后将无法重新安装 Office。
  
如果你拥有第三方加载项，请与制造商联系，以查看是否有将与最新版本的 Office 一起使用的更新。

> [!TIP]
> 如果在卸载 Office 时遇到问题，可以使用 Microsoft 支持和恢复助手工具帮助你删除 Office：下载并运行 [Microsoft 支持和恢复助手](https://go.microsoft.com/fwlink/?LinkID=2155008)。

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>选择要卸载的 Office 版本

- [从电脑](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [从 Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>卸载后尝试重新安装旧版 Office 的已知问题

 **通过批量许可证的 Office** 如果您不再能够访问这些 Office 批量许可版本的源文件，将无法重新安装它。

 **计算机上预安装的 Office** 如果你不再拥有光盘或产品密钥 (如果 Office 随一个) 你将无法重新安装它。

 **不支持的订阅** 如果 Office 副本是通过停用的订阅（如 Office 365 小型企业高级版或 Office 365 中型企业版）获取的，则将无法安装较旧版本的 Office，除非你具有订阅提供的产品密钥。

如果你希望将较旧版本的 Office 与最新版本并排安装，你可以看到支持此功能的版本列表，在同一台电脑上安装和使用不同版本的[Office。](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf) 并行安装可能是正确的选择，例如，如果已安装用于旧版 Office 的第三方加载项，但还不确定它们是否与最新版本兼容。

## <a name="step-4---assign-office-licenses-to-users"></a>步骤 4 - 向用户分配 Office 许可证

如果尚未安装，请为组织中需要安装 Office 的任何用户分配许可证，请参阅"为 [Microsoft 365](../manage/assign-licenses-to-users.md)商业版中的用户分配许可证"。
  
## <a name="step-5---install-office"></a>步骤 5 - 安装 Office

在验证要升级的用户是否均拥有许可证后，最后一步是让他们安装 Office，请参阅在电脑或 Mac 上下载并安装或重新安装[Office。](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)
  
> [!TIP]
> 如果不希望用户自行安装 Office，请参阅 ["在 Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)中管理软件下载设置"。 可以使用 Office [部署工具](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) 将 Office 软件下载到本地网络，然后使用通常使用的软件部署方法部署 Office。
