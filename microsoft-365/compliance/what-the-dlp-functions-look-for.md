---
title: " (DLP) 函数查找的数据丢失防护功能"
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解 (DLP) 函数查找的数据丢失防护。
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841443"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 函数查找的内容

数据丢失防护 (DLP) 策略可以使用敏感信息类型标识敏感项目。 信用卡号和欧盟借记卡号是敏感信息类型的示例。 敏感信息类型查找特定模式。 敏感信息类型通过查看数据的格式、校验和，并查找相关的关键字或其他信息来验证数据。 其中一些功能是由内部函数执行的。 例如，信用卡号敏感信息类型使用函数查找格式类似于到期日期的日期。 这有助于 corroborate 号码是信用卡号。
  
本文介绍了这些函数查找的内容，以帮助您了解预定义的敏感信息类型的工作原理。 有关详细信息，请参阅 [敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>函数表

|函数名称  |函数操作  |是一个验证程序|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|检测和验证阿根廷唯一税密钥|否|
|Func_aba_routing|检测 ABA 传送号码| 是|
|Func_alabama_drivers_license_number|检测 Alabama driver 的许可证编号|否|
|Func_alaska_delaware_oregon_drivers_license_number|检测阿拉斯加、特拉华州和俄勒冈州的驾驶执照号码|否|
|Func_alaska_drivers_license_number|检测阿拉斯加驾驶执照号码|否|
|Func_alberta_drivers_license_number|检测 Alberta driver 的许可证编号|否|
|Func_Argentina_Unique_Tax_Key|检测阿根廷唯一税密钥|否|
|Func_arizona_drivers_license_number|检测亚利桑那州驾照号码|否|
|Func_arkansas_drivers_license_number|检测 Arkansas driver 的许可证编号|否|
|Func_australian_business_number|检测澳大利亚商业版号码|否|
|Func_Australian_Company_Number|检测澳大利亚公司编号|否|
|Func_australian_medical_account_number|检测澳大利亚医疗帐户号码|否|
|Func_australian_tax_file_number|检测澳大利亚税文件编号|是|
|Func_austria_eu_ssn_or_equivalent|检测奥地利社会安全号码|否|
|Func_austria_eu_tax_file_number|检测奥地利税文件号|否|
|Func_Austria_Value_Added_Tax|检测奥地利的增值税|否|
|Func_belgium_national_number|检测比利时国家/地区号码|否|
|Func_belgium_value_added_tax_number|检测比利时增值税号|否|
|Func_brazil_cnpj|检测 CNPJ)  (的巴西法人编号|是|
|Func_brazil_cpf|检测巴西 CPF|是|
|Func_brazil_rg|检测巴西 RG|否|
|Func_british_columbia_drivers_license_number|检测英属哥伦比亚驾驶执照号码|否|
|Func_bulgaria_eu_national_id_card|检测保加利亚统一的民事号码|否|
|Func_california_drivers_license_number|检测加利福尼亚州的驾照号码|否|
|Func_canadian_sin|检测加拿大 sin|是|
|Func_chile_id_card|检测智利 ID 卡|否|
|Func_china_resident_id|检测中国居民 ID|否|
|Func_colorado_drivers_license_number|检测科罗拉多驾驾的许可证编号|否|
|Func_connecticut_drivers_license_number|检测 Connecticut driver 的许可证编号|否|
|Func_credit_card|检测信用卡|是|否|
|Func_croatia_id_card|检测克罗地亚 ID 卡|否|
|Func_croatia_oib_number|检测克罗地亚 OIB 号码|否|
|Func_cyprus_eu_tax_file_number|检测塞浦路斯税文件编号|否|
|Func_czech_id_card|检测捷克 ID 卡|否|
|Func_czech_id_card_new_format|以新格式检测捷克语 ID 卡|否|
|Func_dea_number|检测 DEA 号码|是|
|Func_denmark_eu_tax_file_number|检测丹麦个人身份号码|否|
|Func_district_of_columbia_drivers_license_number|检测哥伦比亚地区的许可证号码|否|
|Func_estonia_eu_national_id_card|检测爱沙尼亚个人标识代码|否|
|Func_eu_debit_card|检测欧盟借记卡|否|
|Func_finnish_national_id|检测芬兰国 ID|否|
|Func_florida_drivers_license_number|检测佛罗里达州的驾照号码|否|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|检测佛罗里达州、马里兰、密歇根州和 Minnesota 驾驶执照号码|否|
|Func_formatted_itin|检测已格式化的美国 ITIN|是|
|Func_fr_insee|检测法国 INSEE|否|
|Func_fr_passport|检测法国护照|否|
|Func_france_eu_tax_file_number|检测法国税文件编号|否|
|Func_france_value_added_tax_number|检测法国增值税号|否|
|Func_french_drivers_license|检测法语驱动程序的许可证|否|
|Func_french_insee|检测法语 INSEE|否|
|Func_georgia_drivers_license_number|检测格鲁吉亚驱动程序的许可证编号|否|
|Func_german_drivers_license|检测德国司机的许可证|否|
|Func_german_passport|检测德国护照|否|
|Func_german_passport_data|检测德国护照|否|
|Func_germany_eu_tax_file_number|检测德国税文件编号|否|
|Func_germany_value_added_tax_number|检测德国增值税号|否|
|Func_greece_eu_ssn|检测 AMKA) 的希腊 sin (|否|
|Func_hawaii_drivers_license_number|检测夏威夷驾驾号码|否|
|Func_hong_kong_id_card |检测中国香港 ID 卡|否|
|Func_hungarian_value_added_tax_number|检测匈牙利增值税号|否|
|Func_hungary_eu_national_id_card|检测匈牙利个人标识号|否|
|Func_hungary_eu_ssn_or_equivalent|检测匈牙利社会安全号码|否|
|Func_hungary_eu_tax_file_number|检测匈牙利税文件编号|否|
|Func_iban|检测 IBAN|是|
|Func_idaho_drivers_license_number|检测爱达荷州 driver 的许可证编号|否|
|Func_illinois_drivers_license_number|检测伊利诺斯州 driver 的许可证编号|否|
|Func_india_aadhaar|检测印度 aadhaar|是|
|Func_indiana_drivers_license_number|检测印地安那件驾驶执照号码|否|
|Func_iowa_drivers_license_number|检测艾奥瓦 driver 的许可证编号|否|
|Func_ireland_pps|检测爱尔兰 PPS|否|
|Func_israeli_national_id_number|检测以色列国家/地区 ID 号|否|
|Func_italy_eu_national_id_card |检测意大利会计代码|否|
|Func_italy_value_added_tax_number|检测意大利增值税增值税号|否|
|Func_japanese_my_number_corporate|检测日本我的号码公司|是|
|Func_japanese_my_number_personal|检测日本我的号码-个人|是|
|Func_jp_bank_account|检测日本银行帐户|否|
|Func_jp_bank_account_branch_code|检测日本银行帐户分支代码|否|
|Func_jp_drivers_license_number|检测日本驾驶执照号码|否|
|Func_jp_passport|检测日本护照|否|
|Func_jp_resident_registration_number|检测日本居民注册号码|否|
|Func_jp_sin|检测日本 SIN|否|
|Func_jp_sin_pre_1997|检测日本 sin pre 1997|否|
|Func_kansas_drivers_license_number|检测堪萨斯州 driver 的许可证编号|否|
|Func_kentucky_drivers_license_number|检测 Kentucky driver 的许可证编号|否|
|Func_kentucky_massachusetts_virginia_drivers_license_number|检测 Kentucky、马萨诸塞州和弗吉尼亚州的许可证编号|否|
|Func_latvia_eu_national_id_card|检测拉脱维亚个人代码|否|
|Func_lithuania_eu_tax_file_number|检测立陶宛个人代码|否|
|Func_louisiana_drivers_license_number|检测 Louisiana driver 的许可证编号|否|
|Func_luxemburg_eu_tax_file_number|检测 (自然个人的 Luxemburg 国家标识号码) |否|
|Func_luxemburg_eu_tax_file_number_non_natural|检测非自然个人 (的 Luxemburg 国家标识号) |否|
|Func_maine_drivers_license_number|检测 Maine driver 的许可证编号|否|
|Func_manitoba_drivers_license_number|检测 Manitoba driver 的许可证编号|否|
|Func_maryland_drivers_license_number|检测马里兰 driver 的许可证编号|否|
|Func_massachusetts_drivers_license_number|检测马萨诸塞州驱动程序的许可证编号|否|
|Func_mexico_population_registry_code|检测墨西哥填充注册表代码|否|
|Func_michigan_minnesota_drivers_license_number|检测密歇根州的密歇根州 Minnesota 驾驶执照号码|否|
|Func_minnesota_drivers_license_number|检测 Minnesota driver 的许可证编号|否|
|Func_mississippi_oklahoma_drivers_license_number|检测 Mississippi、俄克拉荷马 driver 的许可证编号|否|
|Func_missouri_drivers_license_number|检测 Missouri driver 的许可证编号|否|
|Func_montana_drivers_license_number|检测 Montana driver 的许可证编号|否|
|Func_nebraska_drivers_license_number|检测 Nebraska driver 的许可证编号|否|
|Func_netherlands_bsn|检测荷兰 BSN|否|
|Func_netherlands_eu_tax_file_number|检测荷兰税文件编号|否|
|Func_netherlands_value_added_tax_number|检测荷兰增值税号|否|
|Func_nevada_drivers_license_number|检测内华达 driver 的许可证编号|否|
|Func_new_brunswick_drivers_license_number|检测新不伦瑞克 driver 的许可证编号|否|
|Func_new_hampshire_drivers_license_number|检测新新罕布什尔 driver 的许可证编号|否|
|Func_new_jersey_drivers_license_number |检测新 Jersey driver 的许可证编号|否|
|Func_new_mexico_drivers_license_number |检测新的墨西哥驾驾驶号码|否|
|Func_new_york_drivers_license_number   |检测纽约驾驶执照号码|否|
|Func_new_zealand_bank_account_number   |检测新西兰银行帐户号|否|
|Func_new_zealand_inland_revenue_number |检测新西兰 inland 收入编号|否|
|Func_new_zealand_ministry_of_health_number|检测新新西兰的运行状况号码|否|
|Func_newfoundland_labrador_drivers_license_number|检测纽芬兰拉布拉多 driver 的许可证编号|否|
|Func_newzealand_driver_license_number  |检测新西兰驱动程序许可证编号|否|
|Func_newzealand_social_welfare_number  |检测新西兰社会 welfare 号码|否|
|Func_north_carolina_drivers_license_number|检测北卡罗莱纳州司机的许可证编号|否|
|Func_north_dakota_drivers_license_number|检测北美州 driver 的许可证编号|否|
|Func_norway_id_number  |检测挪威 ID 号|否|
|Func_nova_scotia_drivers_license_number|检测新斯科舍 driver 的许可证编号|否|
|Func_ohio_drivers_license_number   |检测 Ohio driver 的许可证编号|否|
|Func_ontario_drivers_license_number    |检测安大略司机的许可证编号|否|
|Func_pennsylvania_drivers_license_number|检测宾夕法尼亚州驱动程序的许可证编号|否|
|Func_pesel_identification_number   |检测波兰国家 ID (PESEL) |否|
|Func_poland_eu_tax_file_number |检测波兰税文件号|否|
|Func_polish_national_id    |检测波兰身份卡片|否|
|Func_polish_passport_number    |检测波兰语护照号码|否|
|Func_polish_regon_number   |检测波兰语 REGON 号码|否|
|Func_portugal_eu_tax_file_number|检测葡萄牙纳税标识号|否|
|Func_prince_edward_island_drivers_license_number|检测爱德华王子孤岛驱动程序的许可证编号|否|
|Func_quebec_drivers_license_number |检测魁北克驾驶的许可证号码|否|
|Func_randomized_formatted_ssn  |检测随机格式化的美国 SSN|是|
|Func_randomized_unformatted_ssn|检测随机的无格式的 US SSN|是|
|Func_rhode_island_drivers_license_number|检测 Rhode 岛驱动程序的许可证编号|否|
|Func_romania_eu_national_id_card   |检测 CNP) 的罗马尼亚个人数字代码 (|否|
|Func_saskatchewan_drivers_license_number|检测萨斯驾驶执照号码|否|
|Func_slovakia_eu_national_id_card  |检测斯洛伐克个人号码|否|
|Func_slovenia_eu_national_id_card  |检测斯洛文尼亚唯一主公民号码|否|
|Func_slovenia_eu_tax_file_number   |检测斯洛文尼亚税文件号|否|
|Func_south_africa_identification_number|检测南非身份证号码|是|
|Func_south_carolina_drivers_license_number|检测南卡罗莱纳州驾驶执照号码|否|
|Func_south_dakota_drivers_license_number|检测南州 driver 的许可证编号|否|
|Func_south_korea_resident_number   |检测韩国居民号码|否|
|Func_spain_eu_DL_and_NI_number_citizen |检测西班牙 DL 和 NI 号码公民|否|
|Func_spain_eu_DL_and_NI_number_foreigner|检测西班牙 DL 和 NI 号码 foreigner|否|
|Func_spain_eu_driver "s_license_number  |检测西班牙驾驶执照号码|否|
|Func_spain_eu_tax_file_number  |检测西班牙税文件号|否|
|Func_spanish_social_security_number|检测西班牙语社会安全号码|否|
|Func_ssn   |用于检测非随机格式化的 US SSN 的函数|是|
|Func_sweden_eu_tax_file_number|检测瑞典税文件号|否|
|Func_swedish_national_identifier|检测瑞典语国家标识符|是|
|Func_swiss_social_security_number_ahv|检测瑞士社会安全号码 AHV|否|
|Func_taiwanese_national_id |检测中国国家/地区 ID|否|
|Func_tennessee_drivers_license_number|检测田纳西州 driver 的许可证编号|否|
|Func_texas_drivers_license_number  |检测德克萨斯州的驾照号码|否|
|Func_Thai_Citizen_Id   |检测泰语公民 ID|否|
|Func_Turkish_National_Id|检测土耳其国家 ID|是|
|Func_uk_drivers_license|检测英国驱动程序的许可证|否|
|Func_uk_eu_tax_file_number|检测英国唯一纳税人号|否|
|Func_uk_nhs_number |检测英国 NHS 号码|是|
|Func_uk_nino   |检测英国 NINO|否|
|Func_unformatted_canadian_sin|检测未格式化的加拿大 SIN|否|
|Func_unformatted_itin  |检测未格式化的美国 ITIN|是|
|Func_unformatted_ssn   |检测非随机的无格式美国 SSN|是|
|Func_usa_uk_passport   |检测美国和英国护照|是|
|Func_utah_drivers_license_number|检测犹他州驱动程序的许可证编号|否|
|Func_vermont_drivers_license_number|检测 Vermont driver 的许可证编号|否|
|Func_virginia_drivers_license_number|检测弗吉尼亚州驾照号码|否|
|Func_washington_drivers_license_number|检测华盛顿州驾驶执照号码|否|
|Func_west_virginia_drivers_license_number|检测西弗吉尼亚州驾照号码|否|
|Func_wisconsin_drivers_license_number  |检测 Wisconsin driver 的许可证编号|否|
|Func_wyoming_drivers_license_number    |检测 Wyoming driver 的许可证编号|否|


## <a name="func_us_date"></a>Func_us_date

Func_us_date 查找采用美国通用格式的日期。 常见的格式为 "月/日/年"、"月-日-年" 和 "月年"。 月份的名称或缩写不区分大小写。 
  
示例：
  
- 2016年12月2日
    
- 2016年12月2日
    
- dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
接受的月份名称：
  
- 英语
    
  - 一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月
    
  - 2003年4月4日. 5 月4月6月11月11月11月4日。
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates 查找常见欧盟中的日期 将 (和大多数位置的格式设置在美国 ) 之外，例如 "日/月/年"、"日-月-年" 和 "月年"。 月份的名称或缩写不区分大小写。
  
示例：
  
- 2 Dec 2016
    
- 02年12月2016
    
- 2 Dec 16
    
- 2/12/2016
    
- 02/12/16
    
- 2016年12月2日
    
- 2-12-16
    
接受的月份名称：
  
- 英语
    
  - 一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月
    
  - 2003年4月4日. 5 月4月6月11月11月11月4日。
    
- 荷兰语
    
  - januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月
    
  - 2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月
    
- 法语
    
  - janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre
    
  - janv. févr. 火星 avril mai juin juil。 août 9 月。 2008. 年11月. déc.
    
- 德语
    
  - jänuar、februar、märz、四月、mai、juni juli、八月、九月、oktober、十一月、dezember
    
  - Jan./Jän。 2003年 März 年4月 Juni Juli，Okt。 Dez 年11月。
    
- 意大利语
    
  - gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre
    
  - genn. febbr. mar. 四月. magg. giugno luglio ag。 设置. ott. 年11月. home.dic.
    
- 葡萄牙语
    
  - 里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev mar abr mai 06 年6月前设置11月 dez
    
- 西班牙语
    
  - enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre
    
  - enero 2003 年2月。 marzo abr。 mayo 06。 年7月. agosto/set。 2008. 年11月. home.dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (已弃用) 

> [!NOTE]
> 此函数已被弃用，因为它仅支持包含在上述函数中的葡萄牙月名称  `Func_eu_date` 。 
  
此函数使用葡萄牙语中常用的格式查找日期。 此函数的格式与  `Func_eu_date` 使用的语言不同。
  
示例：
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
接受的月份名称：
  
- 葡萄牙语
    
  - 里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev mar abr mai 06 年6月前设置11月 dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (已弃用) 

> [!NOTE]
> 此函数已被弃用，因为它仅支持荷兰月份名称，这些名称现在包含在  `Func_eu_date` 上述函数中。 
  
此函数查找在荷兰语中常用的格式的日期。 此函数的格式与  `Func_eu_date` 使用的语言不同。
  
示例：
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
接受的月份名称：
  
- 荷兰语
    
  - januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月
    
  - 2004年1月1月 maart 日 mei 日09月8日，okt 年11月9日
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date 查找使用信用卡和借记卡常用的格式的日期。 此函数将以 "月/年"、"月-年"、"[月 name] year" 和 "[月缩写] 年" 的格式匹配日期。 月份的名称或缩写不区分大小写。
  
示例：
  
- MM/YY--例如，01/11 或1/11
    
- MM/YYYY--例如，01/2011 或1/2011
    
- MM-YY--例如，01-22 或1-11
    
- MM--例如，01-2000 或1-2000
    
以下格式支持 YY 或 YYYY：
  
- 年月日--例如 Jan-2010 或一月-2010 或 Jan-10 或一月-10
    
- 年月日-例如，"一月 2010" 或 "Jan 2010" 或 "Jan 10" 或 "Jan 10"
    
- MonthYYYY-例如，"january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"
    
- Month/YYYY-例如，"一月/2010" 或 "Jan/2010" 或 "一月/10" 或 "Jan/10"
    
接受的月份名称：
  
- 英语
    
  - 一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月
    
  - 2004年2月3月4月5月8日12月8月8日
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address 查找美国省/市/自治区名称或邮政缩写，后跟有效的邮政编码。 邮政编码必须是与美国省/市/自治区名称或缩写相关联的正确邮政编码之一。 美国省/市/自治区名称和邮政编码不能由标点符号或字母分隔。
  
示例：
  
- 华盛顿98052
    
- 华盛顿98052-9998
    
- WA 98052
    
- WA 98052-9998
