---
title: 安装并使用 Microsoft 垃圾邮件报告外接程序Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: 了解如何安装和使用 Microsoft 垃圾邮件报告外接程序向 Microsoft 报告垃圾邮件、非垃圾邮件和网络钓鱼邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e120ceec355ffc135e00e13a89a0f29085946a3b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203265"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>安装并使用 Microsoft 垃圾邮件报告外接程序Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 如果您当前没有使用垃圾邮件报告外接程序，我们建议改为使用报告邮件外接程序或报告网络钓鱼[外接程序](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md) 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

Microsoft Outlook 垃圾邮件报告外接程序允许用户向 Microsoft 提交误报 (标记为垃圾邮件) 、漏报 (错误电子邮件) 以及网络钓鱼邮件。 如果您的组织不使用 Exchange Online Protection (，例如本地 Exchange 或除 Exchange Online) 外的电子邮件服务，则垃圾邮件报告提交不会影响垃圾邮件筛选。

本主题介绍如何安装和使用垃圾邮件报告外接程序。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要安装垃圾邮件报告外接程序，请参阅本文稍后介绍的安装 [垃圾](#install-the-junk-email-reporting-add-in) 电子邮件报告外接程序一节。

- 垃圾邮件报告外接程序适用于以下版本的Outlook：

  - Outlook 2013 或更高版本
  - Outlook包含在Microsoft 365 企业应用版

- 有关向 Microsoft 报告邮件的信息，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>使用垃圾邮件报告外接程序报告垃圾邮件和网络钓鱼邮件

1. 对于收件箱或其他任何电子邮件文件夹中的邮件（垃圾邮件除外），请使用以下任一方法报告垃圾邮件和网络钓鱼邮件：

   - 选择邮件或打开邮件。 在功能 **区的"****主页"** 或"邮件"选项卡中，单击"垃圾邮件"，然后选择"**报告为垃圾邮件**"或"**报告为网络钓鱼"。**

     ![从功能区报告垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-ribbon.png)

   - 右键单击邮件，选择 **"垃圾邮件**"，然后选择"**报告为垃圾邮件**"或"**报告为网络钓鱼"。**

     ![右键单击报告垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-right-click.png)

   - 选择多个邮件，右键单击，然后选择报告 **为垃圾邮件** 或 **报告为网络钓鱼**。

     ![右键单击报告多个垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

2. 在出现的对话框中，阅读信息并单击"报告 **"。** 如果改变主意，请单击"**不报告"。**

   ![报告为垃圾邮件对话框](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![报告为网络钓鱼对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 选定的邮件将发送给 Microsoft 进行分析，并：

   - 如果报告为垃圾邮件，则移动到"垃圾邮件"文件夹。
   - 如果报告为网络钓鱼，则将其删除。

   若要确认已提交的邮件，请打开您的“已发送邮件”文件夹查看已提交的邮件。

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>使用垃圾邮件报告外接程序从"垃圾邮件"文件夹报告非垃圾邮件和网络钓鱼邮件

1. 在"垃圾邮件"文件夹中，使用以下任一方法报告垃圾邮件误报或网络钓鱼邮件：

   - 选择邮件或打开邮件。 在功能 **区的"****主页"** 或"邮件"选项卡中，单击"非垃圾邮件"，然后选择"报告 **为非** 垃圾邮件"或"**报告为网络钓鱼"。**

     ![从"垃圾邮件"文件夹的功能区报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - 右键单击邮件，**单击"垃圾邮件**"，然后选择"**报告为非** 垃圾邮件"或"**报告为网络钓鱼"。**

     ![从"垃圾邮件"文件夹中右键单击报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

   - 选择多个邮件，右键单击，然后选择报告 **为非** 垃圾邮件或 **报告为网络钓鱼**。

     ![从"垃圾邮件"文件夹中右键单击报告多个非垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. 在出现的对话框中，阅读信息并单击"报告 **"。** 如果改变主意，请单击"**不报告"。**

   ![报告为非垃圾邮件对话框](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![报告为网络钓鱼对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 选定的邮件将发送给 Microsoft 进行分析，并：

   - 如果报告为垃圾邮件，则移动到"垃圾邮件"文件夹。
   - 如果报告为网络钓鱼，则将其删除。

   若要确认已提交的邮件，请打开您的“已发送邮件”文件夹查看已提交的邮件。

## <a name="install-the-junk-email-reporting-add-in"></a>安装垃圾邮件报告外接程序

- 您需要在要安装外接程序的计算机上拥有管理员权限。

- 转到 <https://www.microsoft.com/download/details.aspx?id=18275> 并下载适用于.msi版本Office文件下载到易于查找的位置：

  - **32 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- 对于 Outlook 2013 或更高版本，唯一的先决条件是 Microsoft .NET Framework 2.0。 在Windows 10中，你无法从.NET Framework安装 2.0。

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>使用安装向导安装垃圾电子邮件报告外接程序

1. 在您的计算机上关闭 Outlook。

2. In Windows 10， verify the .NET Framework 2.0 is enabled. 有关说明，请参阅[在控制面板.NET Framework启用 3.5。](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)

3. 找到.msi下载的文件，然后双击它。

4. 在“欢迎使用 Microsoft 垃圾电子邮件报告外接程序安装程序”页面上，单击“下一步”。

5. 查看许可协议，如果同意许可协议中的条款，请单击"我接受许可协议中的条款"，然后单击"下一步 **"。**

6. 向导完成后，单击“完成”。 

启动 Outlook。

在"垃圾邮件 **"** 功能区上Outlook按钮。 现在，可以通过在收件箱中选择垃圾电子邮件并单击“报告垃圾邮件”按钮，向 Microsoft 报告垃圾电子邮件。

如果想要向 Microsoft 报告仿冒垃圾电子邮件，请选择“垃圾邮件”旁边的向下箭头查看更多选项，如“报告为仿冒邮件”。如果一封电子邮件被错误识别为垃圾邮件，则在垃圾邮件文件夹中，您还可以选择“报告不是垃圾邮件”。

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>使用静默模式安装垃圾电子邮件报告外接程序

1. 在您的计算机上关闭 Outlook。

2. 在Windows 10中，运行以下.NET Framework安装 2.0：

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. 若要在没有任何用户交互的情况下安装外接程序，请打开命令提示符并使用以下语法：

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` 指定你可以为单个提交选择的最大邮件数。 有效值为 1 到 50。 默认值为 15。

   - `BccEmailAddress` 指定将接收所有用户提交副本的其他 Bcc 收件人。 如果没有其他"Bcc" (，则默认值为空) 。

   此示例使用默认设置从指定路径安装 64 位版本的外接程序。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   此示例使用下列其他设置从指定路径安装 32 位版本的外接程序：

   - 一次提交中最多只能选择 20 条消息。
   - junkreports@contoso.com 和 hollyd@treyresearch.net 接收所有提交的 Bcc 副本。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>如何知道操作成功？

若要验证您是否已成功安装垃圾邮件报告外接程序，请执行以下任一Outlook：

- 选择邮件或打开邮件。 在功能 **区的"****主页"** 或"邮件"选项卡中，单击"**垃圾邮件**"，并验证以下选项是否可用：

  - **报告为垃圾邮件**
  - **报告为网络钓鱼**
  - **垃圾邮件报告选项**
  - **报告垃圾邮件联机帮助**

  ![从功能区报告垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-ribbon.png)

- 右键单击邮件， **选择"垃圾邮件**"，并验证以下选项是否可用：

  - **报告为垃圾邮件**
  - **报告为网络钓鱼**
  - **垃圾邮件报告选项**
  - **报告垃圾邮件联机帮助**

  ![右键单击报告垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-right-click.png)

- 选择多条消息，右键单击并验证以下选项是否可用：

  - **报告为垃圾邮件**
  - **报告为网络钓鱼**

  ![右键单击报告多个垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

- 在"垃圾邮件"文件夹中执行 **之前的操作，** 并验证以前的 **"** 垃圾邮件"报告选项现在为 **"非垃圾邮件"。**

  ![从"垃圾邮件"文件夹的功能区报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![从"垃圾邮件"文件夹中右键单击报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![从"垃圾邮件"文件夹中右键单击报告多个非垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>卸载垃圾电子邮件报告外接程序

关闭Outlook后，请使用以下任一过程卸载垃圾电子邮件报告外接程序：

- **控制面板：** 按Windows键 + R。在打开 **的"运行**"对话框中，输入 `control appwiz.cpl` ，然后单击"确定 **"。**

  在列表中查找并选择 **"Microsoft 垃圾邮件报告** 外接程序"，然后单击"卸载 **"。**

- **Windows安装程序程序包**：查找或下载.msi文件，然后双击它。

  - **32 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  在出现的对话框中，选择"删除 Microsoft 垃圾邮件报告外接程序 **"Outlook** 然后单击"下一步 **"。**

- **静默** 模式：查找或下载相应的.msi文件。 在命令提示符窗口中，将 替换为 .msi \<PathToFile\> 文件的位置，然后运行以下命令之一：

  - **32 位**：

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 位**：

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

在卸载Outlook打开邮件时，垃圾邮件（非垃圾邮件）和网络钓鱼报告选项应该会消失。

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>垃圾邮件报告外接程序疑难解答

有时，在添加垃圾邮件报告Outlook后，您可能遇到与垃圾邮件报告外接程序有关的问题。 本节介绍您可能遇到的问题，以及解决这些问题的提示。

### <a name="troubleshooting-for-users"></a>用户疑难解答

您遇到以下一个或多个问题：

- Nothing happens when you click **Report Junk**
- 当您选择一封电子邮件之后，Outlook 停止响应
- 由于收到"未送达"回复，报告的垃圾邮件无法传递

若要解决此问题，请执行以下步骤：

1. 关闭并重新启动Outlook。
2. 创建并发送测试邮件，并验证收件人是否收到该邮件。
3. 如果问题仍然存在，请与管理员联系。

有关可用于向 Microsoft 提交邮件的其他方法，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。

### <a name="troubleshooting-for-admins"></a>管理员疑难解答

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>问题：不断出现一条错误消息，要求用户联系系统管理员

1. 验证注册表 `LoggingLevel` 项或将注册表项设置为值"Verbose"：

   - **32 位Outlook 32 位** Windows：

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 位Outlook 32 位** Windows：

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 位Outlook：**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. 重新启动Outlook，并要求用户在看到错误消息时返回报告。

3. 收集在以下位置找到的日志信息：

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. 联系 Exchange Online Protection 技术支持并向他们提供日志信息。

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>问题：用户在报告邮件时选择不接收确认提示，但现在希望返回提示

1. 创建 `ConfirmReportJunk` 值为"True"的注册表项：

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. 重新启动 Outlook。