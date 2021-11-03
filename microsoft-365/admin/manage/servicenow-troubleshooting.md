---
title: 有关支持Microsoft 365 ServiceNow 的疑难解答
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow 的作用域认证应用程序安装和配置指南。
ms.openlocfilehash: 24813fe0d0705d9404fa465420e3b0344f43f953
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661690"
---
# <a name="troubleshooting-microsoft-365-support-integration-with-servicenow"></a>有关支持Microsoft 365 ServiceNow 的疑难解答

| \#  | 问题  | 诊断操作     |
|-----|--------------------------------|----------------------|
| 1   | 无法查看 **"Microsoft 365支持"** 选项卡                                                                                                                                                                                    | 使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 验证当前视图和"系统日志全部"                        |
| 2   | 选择 **Microsoft 推荐的解决方案** ，但收到错误"Please contact your ServiceNow admin and ask them to complete the setup steps for the app."                                                                      | 检查表单顶部的错误消息和使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 的系统日志全部     |
| 3   | 选择 **Microsoft 推荐的解决方案** ，但收到错误"Please contact your ServiceNow admin and ask them to complete the final set up step for the app."                                                                | 检查表单顶部的错误消息和使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 的系统日志全部     |
| 4    | 在搜索框中键入问题并选择 **Microsoft 建议** 的解决方案，但收到错误"请联系你的 ServiceNow 管理员，并要求他们完成应用的设置步骤。"                                   | 检查表单顶部的错误消息和使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 的系统日志全部     |
| 5   | 在搜索框中键入问题并选择 **Microsoft 建议** 的解决方案，但收到错误"请联系你的 ServiceNow 管理员，并要求他们完成应用的最终设置步骤。"                                 | 检查表单顶部的错误消息和使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 的系统日志全部     |
| 6    | 选择 **"联系 Microsoft 支持** 人员"，但收到错误"Please contact your ServiceNow admin and ask them to complete the setup steps for the app."                                                                       | 检查表单顶部的错误消息和使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 的系统日志全部     |
| 7    | 选择 **"联系 Microsoft 支持** 人员"，但收到错误"Please contact your ServiceNow admin and ask them to complete the final set up step for the app."                                                                 | 检查表单顶部的错误消息和使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 的系统日志全部     |
| 8    | 选择 **"联系 Microsoft 支持** 人员"，但收到错误"{EmailAddress} 不是有效的Microsoft 365管理员帐户。 您需要Microsoft 365管理员权限才能打开服务请求。 在应用中，链接管理员帐户。" | 检查表单顶部的错误消息和使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 的系统日志全部     |
| 9    | 选择 **Microsoft 建议的解决方案** ，但没有任何显示                                                                                                                                                            | 检查 **系统日志 – 具有筛选器** 筛选器的出站 HTTP login.microsoftonline.com connector.rave.microsoft.com |
| 10   | 选择 **Microsoft 推荐的解决方案** ，但收到错误"请联系应用支持人员"。                                                                                                                                     | 检查表单顶部的错误消息和使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 的系统日志全部     |
| 11  | 在搜索框中键入问题，然后选择 **Microsoft 建议的解决方案** ，但不显示任何内容                                                                                                                             | 检查 **系统日志 – 具有筛选器** 筛选器的出站 HTTP login.microsoftonline.com connector.rave.microsoft.com |
| 12   | 在搜索框中键入问题，然后选择 **Microsoft 建议的解决方案** ，但收到错误"请联系应用支持人员"。                                                                                                      | 检查表单顶部的错误消息和使用筛选器 x  &gt;  \_ mioms \_ m365 \_ assit 的系统日志全部     |
| 13  | 用户选择" **联系 Microsoft 支持人员**"，但没有任何反应                                                                                                                                                            | 检查 **系统日志 – 具有筛选器** 筛选器的出站 HTTP login.microsoftonline.com connector.rave.microsoft.com |
| 14   | 重新打开事件后看不到 Microsoft 建议的解决方案                                                                                                                                                      | 使用 **筛选器** &gt;  x \_ mioms \_ m365 assit 检查"系统日志 \_ 全部"                                              |
| 15   | 重新打开已转移到 Microsoft 支持人员的事件时看不到 Microsoft 案例                                                                                                                            | 使用 **筛选器** &gt;  x \_ mioms \_ m365 assit 检查"系统日志 \_ 全部"                                              |
| 16  | 无法保存票证详细信息，收到错误"无法保存票证详细信息。 请联系应用支持人员。"                                                                                                                          | 检查表单顶部的错误消息                                                                            |
