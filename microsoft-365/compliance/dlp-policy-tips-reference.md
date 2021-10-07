---
title: 数据丢失防护策略提示参考
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: 了解如何将策略提示添加到 DLP 策略 (数据丢失) 通知用户他们处理的内容与 DLP 策略冲突。
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 2537b653b435240e052374e3328e2b94504a8d74
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195637"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>数据丢失防护策略提示参考

对于适用于 DLP 策略中 Outlook 工作负荷的所有条件、例外和操作，Exchange支持 Outlook Web Access 中的 DLP 策略提示，以下条件除外：

**条件：**

- 发件人是
- 发件人域为
- 收件人所在组为
- 标头包含单词或短语
- 标题与模式匹配
- 文档大小等于或大于
- 邮件类型为
- 邮件重要性为
- 内容字符集包含单词
- 主题或正文包含字词或短语
- 主题或正文与模式匹配
- 内容字符集包含单词
- 内容接收自
- 使发件人覆盖策略提示
- 邮件大小等于或大于
- Sender AD 属性包含字词或短语
- Sender AD 属性与模式匹配
- 文档内容包含字词或短语
- 文档内容与模式匹配

**操作：**

- 将邮件转发给发件人的经理进行审批
- 将邮件转发给特定审批者进行审批
- 将邮件重定向到特定用户
- 将收件人添加到"收件人"框
- 将收件人添加到抄送框
- 将收件人添加到"Bcc"框
- 将发件人的经理添加为收件人
- 添加 HTML 免责声明
- 预悬电子邮件主题
- 删除 O365 邮件加密和权限保护

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 及更高版本仅支持显示某些条件和例外的策略提示

目前，Outlook 2013 及更高版本支持显示策略提示，这些策略不包含以下提及的条件和相应例外之外的任何条件或例外：

- 内容 (仅适用于敏感信息类型。 不支持敏感度标签) 
- 共享内容

请注意，所有条件都适用于在客户端Outlook创作的电子邮件，这些条件将匹配内容，并强制对内容执行保护性操作。 但是，对于除上述条件之外使用的任何条件，都不支持向用户显示策略提示。

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 及更高版本Office桌面应用支持仅显示某些敏感信息类型的策略提示

在桌面版 (2013 及更高版本的 Outlook (和) Office 应用（桌面版 (Word、Excel、PowerPoint) ）中显示 DLP 策略提示时，将检测到的现成敏感信息类型列表如下：

- ABA 银行代号
- 阿根廷国家身份证 (DNI) 号
- 澳大利亚银行帐号
- 澳大利亚医疗帐号
- 澳大利亚护照号
- 澳大利亚税号
- Azure DocumentDB 身份验证密钥  
- Azure IAAS 数据库连接字符串和 Azure SQL连接字符串  
- Azure IoT连接字符串  
- Azure 发布设置密码  
- Azure Redis 缓存连接字符串  
- Azure SAS  
- Azure 服务总线 连接字符串  
- Azure 存储帐户密钥  
- Azure 存储帐户密钥 (通用)   
- 比利时国家号码
- 巴西 CPF 号码
- 巴西法律实体编号 (CNPJ)
- 	巴西国家身份证 (RG)
- 加拿大银行帐号
- 加拿大驾驶证号码
- 加拿大卫生服务号
- 加拿大护照号码
- 加拿大个人健康标识号 (PHIN)
- 加拿大社会保险号码
- 	智利身份证号
- 	中国居民身份证号
- 信用卡号码
- 克罗地亚身份证号码  
- 克罗地亚个人标识 (OIB) 号码  
- 捷克个人标识号  
- 丹麦个人识别号
- 药品管制局 (DEA) 号码
- 欧盟借记卡号码
- 欧盟驾驶证号码  
- 欧盟国家标识号  
- 欧盟护照号码  
- 欧盟社会保险号码 (SSN) 或等效 ID  
- EU Tax Identification Number (TIN)   
- 芬兰国家/地区身份证号码
- 芬兰护照号码
- 法国驾驶证号码
- 法国国家/地区身份证 (CNI)
- 法国护照号码
- 法国社会保险号码 (INSEE)
- 德国驾驶证号码
- 德国护照号码
- 德国身份证号码
- 希腊国民身份证  
- 香港身份证 (HKID) 号
- 印度永久帐号 (PAN)
- India Unique Identification (Aadhaar) Number
- 印度尼西亚身份证 (KTP) 号
- 国际银行帐号 (IBAN)
- ICD-10-CM (国际)   
- ICD-9-CM (国际)   
- IP 地址
- 爱尔兰个人公共服务 (PPS) 号 
- 以色列银行帐号
- 以色列国家/地区 ID
- 意大利驾驶证号码
- 日本银行帐号
- 日本驾驶证号码
- 日本护照号码
- 日本居民登记号码
- 日本社会保险号码 (SIN)
- 日式居民身份证号码
- 马来西亚身份证号码
- 荷兰公民服务 (BSN) 号码  
- 新西兰卫生部号码
- 挪威标识号  
- 菲律宾统一多用途身份证号码
- 波兰身份证
- 波兰国家/地区身份证号码 (PESEL)
- 波兰护照
- 葡萄牙公民卡号
- 沙特阿拉伯国家 ID
- 新加坡国家登记身份证 (NRIC) 号
- 南非身份证号  
- 韩国居民注册号码
- 西班牙社会保险号码 (SSN)
- SQL Server连接字符串  
- 瑞典国家/地区身份证号码
- 瑞典护照号码
- SWIFT 代码
- 台湾国家/地区 ID
- 	台湾护照号码
- 台湾居民证书 (ARC/TARC) 
- 泰语总体标识代码
- 土耳其国家身份证号码
- 英国驾驶证号码
- 英国选民名册号码
- 英国国家卫生服务号码
- 英国国家保险号码 (NINO)
- 美国/英国护照号码
- 美国银行帐号
- 美国驾驶证号码
- 美国单独的纳税人标识号 (ITIN)
- 美国社会保险号 (SSN)

请注意，除了上述开箱即用敏感信息类型外，DLP 策略提示还支持自定义敏感信息类型。

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>终结点设备上数据丢失防护仅支持某些敏感信息类型的策略提示

将在驻留在终结点设备上的文档中检测到的现用敏感信息类型列表如下：

- ABA 银行代号 
- 阿根廷国家身份证 (DNI) 号 
- 澳大利亚银行帐号 
- 澳大利亚医疗帐号 
- 澳大利亚护照号 
- 澳大利亚税号 
- 澳大利亚商务号码 
- 澳大利亚公司编号 
- 奥地利驾驶证号码 
- 奥地利身份证 
- 奥地利护照号码 
- 奥地利社会保险号码 
- 奥地利税务标识号 
- 奥地利增值税 (VAT) 号码 
- Azure DocumentDB 身份验证密钥 
- Azure IAAS 数据库连接字符串和 Azure SQL连接字符串 
- Azure IoT连接字符串 
- Azure 发布设置密码 
- Azure Redis 缓存连接字符串 
- Azure SAS 
- Azure 服务总线 连接字符串 
- Azure 存储帐户密钥 
- Azure 存储帐户密钥 (通用)  
- 比利时驾驶证号码 
- 比利时国家号码 
- 比利时护照号码 
- 比利时增值税编号 
- 巴西 CPF 号码 
- 巴西法律实体编号 (CNPJ) 
- 	巴西国家身份证 (RG) 
- 保加利亚驾驶证号码 
- 保加利亚护照号码 
- 保加利亚统一编号 
- 加拿大银行帐号 
- 加拿大驾驶证号码 
- 加拿大卫生服务号 
- 加拿大护照号码 
- 加拿大个人健康标识号 (PHIN) 
- 加拿大社会保险号码 
- 	智利身份证号 
- 	中国居民身份证号 
- 信用卡号码 
- 克罗地亚驾驶证号码 
- 克罗地亚身份证号码 
- 克罗地亚国家/地区身份证号码 
- 克罗地亚护照号码 
- 克罗地亚个人标识 (OIB) 号码 
- CSCAN-AZURE0060 Azure 存储帐户共享访问签名 
- CSCAN-GENERAL0140 常规对称密钥 
- 塞浦路斯驾驶证号码 
- 塞浦路斯身份证 
- 塞浦路斯护照号码 
- 塞浦路斯税务标识号 
- 捷克驾驶证号码 
- 捷克个人标识号 
- 捷克共和国护照号码 
- 丹麦驾驶证号码 
- 丹麦护照号码 
- 丹麦个人识别号 
- 药品管制局 (DEA) 号码 
- 爱沙尼亚驾驶证号码 
- 爱沙尼亚护照号码 
- 爱沙尼亚个人标识代码 
- 欧盟借记卡号码 
- 欧盟驾驶证号码 
- 欧盟国家标识号 
- 欧盟护照号码 
- 欧盟社会保险号码 (SSN) 或等效 ID 
- EU Tax Identification Number (TIN)  
- 芬兰驾驶证号码 
- 芬兰欧洲健康保险号码 
- 芬兰国家/地区身份证号码 
- 芬兰护照号码 
- 法国驾驶证号码 
- 法国健康保险号码 
- 法国国家/地区身份证 (CNI) 
- 法国护照号码 
- 法国社会保险号码 (INSEE) 
- 法国税务标识号 (numéro SPI.)  
- 法国增值税编号 
- 德国驾驶证号码 
- 德国护照号码 
- 德国身份证号码 
- 德国税务标识号 
- 德国增值税编号 
- 希腊驾驶证号码 
- 希腊国民身份证 
- 希腊护照号码 
- 希腊社会保险号码 (AMKA)  
- 希腊语税务标识号 
- 香港身份证 (HKID) 号 
- 匈牙利社会安全号码 (TAJ)  
- 匈牙利语增值税编号 
- 匈牙利驾驶证号码 
- 匈牙利护照号码 
- 匈牙利个人标识号 
- 匈牙利税务标识号 
- 印度永久帐号 (PAN) 
- India Unique Identification (Aadhaar) Number 
- 印度尼西亚身份证 (KTP) 号 
- 国际银行帐号 (IBAN) 
- ICD-10-CM (国际)  
- ICD-9-CM (国际)  
- IP 地址 
- 爱尔兰驾驶证号码 
- 爱尔兰护照号码 
- 爱尔兰个人公共服务 (PPS) 号 
- 以色列银行帐号 
- 以色列国家/地区 ID 
- 意大利驾驶证号码 
- 意大利财政代码 
- 意大利护照号码 
- 意大利增值税编号 
- 日本银行帐号 
- 日本驾驶证号码 
- 日本护照号码 
- 日本居民登记号码 
- 日本社会保险号码 (SIN) 
- 日语 My Number Corporate 
- 日语个人编号 
- 日式居民身份证号码 
- 拉脱维亚驾驶证号码 
- 拉脱维亚护照号码 
- 拉脱维亚个人代码 
- 立陶宛驾驶证号码 
- 立陶宛护照号码 
- 立陶宛个人代码 
- 都明达驾驶证号码 
- 阿比塞明卡国家身份证 (自然人)  
- 阿比塞明 (非自然人的身份证)  
- 百分卡护照号码 
- 马来西亚身份证号码 
- 马耳他驾驶证号码 
- 马耳他身份证号码 
- 马耳他护照号码 
- 马耳他税务 ID 号 
- 荷兰公民服务 (BSN) 号码 
- 荷兰驾驶证号码 
- 荷兰护照号码 
- 荷兰税务标识号 
- 荷兰增值税编号 
- 新西兰银行帐号 
- 新西兰驾驶证号码 
- 新西兰的收入数字 
- 新西兰卫生部号码 
- 新西兰社会电话号码 
- 挪威标识号 
- 菲律宾统一多用途身份证号码 
- 波兰驾驶证号码 
- 波兰身份证 
- 波兰国家/地区身份证号码 (PESEL) 
- 波兰护照 
- 波兰税务标识号 
- 波兰语 REGON 号码 
- 葡萄牙公民卡号 
- 葡萄牙驾驶证号码 
- 葡萄牙护照号码 
- 葡萄牙税务标识号 
- 罗马尼亚驾驶证号码 
- 罗马尼亚护照号码 
- 罗马尼亚个人数字代码 (CNP)  
- 俄语护照号码 (国内)  
- 俄语护照号码 (国际)  
- 沙特阿拉伯国家 ID 
- 新加坡国家登记身份证 (NRIC) 号 
- 斯洛伐克驾驶证号码 
- 斯洛伐克护照号码 
- 斯洛伐克个人号码 
- 斯洛文尼亚驾驶证号码 
- 斯洛文尼亚护照号码 
- 斯洛文尼亚税务标识号 
- 斯洛文尼亚唯一主公民编号 
- 南非身份证号 
- 韩国居民注册号码 
- 西班牙 DNI 
- 西班牙驾驶证号码 
- 西班牙护照号码 
- 西班牙社会保险号码 (SSN) 
- 西班牙税务标识号 
- SQL Server连接字符串 
- 瑞典驾驶证号码 
- 瑞典国家/地区身份证号码 
- 瑞典护照号码 
- 瑞典税务标识号 
- SWIFT 代码 
- 瑞士社会保险号 AHV 
- 台湾国家/地区 ID 
- 	台湾护照号码 
- 台湾居民证书 (ARC/TARC)  
- 泰语总体标识代码 
- 土耳其国家身份证号码 
- 英国驾驶证号码 
- 英国选民名册号码 
- 英国国家卫生服务号码 
- 英国国家保险号码 (NINO) 
- 英国 唯一的纳税参考编号 
- 美国/英国护照号码 
- 美国银行帐号 
- 美国驾驶证号码 
- 美国单独的纳税人标识号 (ITIN) 
- 美国社会保险号 (SSN) 
- 乌克兰护照号码 (国内)  
- 乌克兰护照号码 (国际)  
 
请注意，除了上述开箱即用敏感信息类型之外，还将检测到自定义敏感信息类型

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Microsoft 应用中 DLP 策略提示的支持矩阵

|**应用和平台**|**DLP 策略提示支持**|**支持的敏感信息类型**|**支持的谓词和操作**|**Comments**|
|:--|:--|:--|:--|:--|
|**Outlook在 Web 上**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|subset||
|**OutlookWin32 (版本 2105 内部版本 14026.20000，半年频道版本 2102 版本 13801.20862)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|subset|请参阅[Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions)及更高版本仅支持显示某些条件和例外的策略提示，[以及桌面版上的 Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)及更高版本和 Office 应用支持显示仅针对某些敏感信息类型的策略提示，了解有关支持敏感信息类型和 DLP 条件以及支持在 Outlook Win32 上显示 DLP 策略提示的操作的详细信息.|
|**Outlook移动 (iOS、Android) /Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|无|无|DLP 策略提示在移动版上Outlook支持|
|**SharePoint联机/OneDrive for Business Web 客户端**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|DLP 中所有 SPO/ODB 谓词和操作||
|**SharePointWin32/ OneDrive for Business Win32 客户端**|:::image type="icon" source="../media/crsmrk.png" border="false":::|无|无|DLP 策略提示在桌面客户端SharePoint OneDrive上不受支持|
|**Word、Excel、PowerPoint Web 客户端**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|DLP 中所有 SPO/ODB 谓词和操作|如果文档托管在 SPO 或 ODB Web 应用上并且已标记 DLP 策略，则支持 DLP 策略提示。|
|**Word、Excel、PowerPoint Mobile Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|无|无|DLP 策略提示在适用于应用程序的移动应用程序中不受Office。|
|**TeamsWeb/ Teams Desktop/ Teams Mobile/ Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|DLP Teams中所有规则谓词|当邮件被标记为"此邮件已标记"时，将显示策略提示。 我该怎么办？ 单击链接时，用户可以查看检测到的敏感信息类型，并覆盖或报告问题（如果管理员允许）。请注意，不会为文件显示任何策略提示。 当收件人尝试访问文档时，如果不允许，他们可能会被拒绝访问。|
|**Win32 终结点设备**|:::image type="icon" source="../media/rightmrk.png" border="false":::|subset|DLP 策略中所有终结点 DLP 谓词和操作|请参阅 [Endpoint 上的数据丢失防护仅支持某些敏感信息类型的策略提示](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)|
|**Mac 设备**|:::image type="icon" source="../media/crsmrk.png" border="false":::|无|无|现在，Mac 设备上未实施数据丢失防护策略|
|**第三方云应用**|:::image type="icon" source="../media/crsmrk.png" border="false":::|无|无|第三方云应用不支持数据丢失防护策略提示|
|**On-prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|无|无||
|**Word、Excel、PowerPoint Win32 客户端**|:::image type="icon" source="../media/crsmrk.png" border="false":::|subset|subset|请参阅[Outlook 2013 及](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)更高版本Office桌面应用支持，其中仅显示某些敏感信息类型的策略提示，了解支持的敏感信息类型列表</br></br>WXP 客户端应用的策略提示适用于存储在 SharePoint Online 或 OneDrive for Business Sites 上的所有 DLP 策略的文档，这些策略在 DLP 策略中具有完全相同的条件或操作子集：</br> <ul><li>内容包含敏感信息类型</li><li>访问 (内容在内部/外部共享) </li><li>通知用户 (策略提示/用户) </li><li>阻止所有人</li><li>事件报告</li></ul></br> 如果存在任何其他条件或操作，该策略的 DLP 策略提示将不会显示在 Word、Excel 或 PowerPoint 桌面应用程序中。</br>有关详细信息[，请参阅 Excel、PowerPoint 和 Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word)中的策略提示|
||||||
