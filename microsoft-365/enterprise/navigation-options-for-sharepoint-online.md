---
title: SharePoint Online 的导航选项
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: 本文介绍在 SharePoint Online 中启用了 SharePoint Publishing 的导航SharePoint网站。
ms.openlocfilehash: c59006db8505991bd41d29714caae144b284f07d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177131"
---
# <a name="navigation-options-for-sharepoint-online"></a>SharePoint Online 的导航选项

本文介绍在 SharePoint Online 中启用了 SharePoint Publishing 的导航SharePoint网站。 导航的选择和配置会显著影响 SharePoint Online 中的网站的性能和可伸缩性。 只有在SharePoint门户需要时，才应使用"发布网站模板"，并且发布功能应仅在特定网站上启用，并且仅在绝对需要时使用，因为它在错误使用时可能会影响性能。

>[!NOTE]
>如果你使用的是新式导航SharePoint如大型菜单、级联导航或中心导航，本文不适用于你的网站。 新式SharePoint网站体系结构利用更平和的网站层次结构和中心分支模型。 这可以实现许多不需要使用"发布"功能SharePoint方案。

## <a name="overview-of-navigation-options"></a>导航选项概述

导航提供程序配置会显著影响整个网站的性能，必须仔细考虑如何选择可有效扩展的导航提供程序和配置，从而满足网站SharePoint要求。 有两个开箱即用导航提供程序以及自定义导航实现。

如果为网站启用 [](#using-structural-navigation-in-sharepoint-online)结构导航缓存，则第一个选项结构导航是 SharePoint Online 中推荐的SharePoint **选项。** 此导航提供程序显示当前网站下方的导航项目，也可以选择显示当前网站及其同级网站。 它提供其他功能，如安全修整和网站结构枚举。 如果禁用缓存，这将对性能和可伸缩性产生负面影响，并且可能会受到限制。

第二个选项 [**Managed (Metadata) 表示**](#using-managed-navigation-and-metadata-in-sharepoint-online)使用托管元数据术语集的导航项。 建议禁用安全修整，除非需要。 安全修整作为此导航提供程序的默认设置启用;但是，许多网站不需要安全修整开销，因为导航元素对于网站的所有用户通常都是一致的。 使用禁用安全修整的建议配置，此导航提供程序不需要枚举网站结构，并且可扩展性高，并且对性能产生可接受的影响。

除了开箱即用导航提供程序之外，许多客户还成功实现了替代自定义导航实现。 请参阅 [本文中的搜索驱动](#using-search-driven-client-side-scripting) 客户端脚本。
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>联机导航选项SharePoint优缺点

下表总结了每个选项的优缺点。

|结构导航  |托管导航  |搜索驱动的导航  |自定义导航提供程序  |
|---------|---------|---------|---------|
|优点：<br/><br/>易于维护<br/>经过安全修整<br/>内容更改后 24 小时内自动更新<br/>     |优点：<br/><br/>易于维护<br/>|优点：<br/><br/>经过安全修整<br/>添加网站时自动更新<br/>加载时间和本地缓存的导航结构<br/>|优点：<br/><br/>可用选项的更多选择<br/>正确使用缓存时快速加载<br/>许多选项都很好地用于响应式页面设计<br/>|
|缺点：<br/><br/>**如果禁用缓存，则影响性能**<br/>受限制<br/>|缺点：<br/><br/>不自动更新以反映网站结构<br/>**启用安全修整或** 导航结构复杂时影响性能<br/>|缺点：<br/><br/>无法轻松对网站排序<br/>需要自定义母版页 (所需的技术) <br/>|缺点：<br/><br/>需要自定义开发<br/>需要存储的外部数据源/缓存，例如 Azure<br/>|

网站最适合的选项将取决于网站要求和您的技术功能。 如果您希望一个易于配置的导航提供程序在内容更改时自动更新，则启用缓存 [的结构](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) 导航是一个不错的选择。

>[!NOTE]
>通过简化整体网站结构SharePoint简单化的非分层结构，应用与新式网站相同的原则可提高性能并简化移动到新式 SharePoint 网站。 这意味着，与单个网站集包含数百个网站 (子网站) ，更好的方法是让许多网站集具有非常少的子网站 (子) 。

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>分析 SharePoint Online 中的导航性能

适用于[SharePoint](./page-diagnostics-for-spo.md)的页面诊断工具是 Microsoft Edge 和 Chrome 浏览器的浏览器扩展，可分析 SharePoint Online 新式门户和经典发布网站页面。 此工具仅适用于 SharePoint Online，不能用于 SharePoint 系统页面。

该工具将针对每个分析的页面生成一个报告，其中显示页面如何针对预定义的规则集执行，并显示测试的结果超出基线值时的详细信息。 SharePoint联机管理员和设计人员可以使用该工具解决性能问题，以确保新页面在发布之前已经过优化。

**SPRequestDuration** 尤其需要一段时间SharePoint处理页面。 导航 (包括导航) 、复杂网站层次结构以及其他配置和拓扑选项等大量导航功能都可能会显著延长持续时间。

## <a name="using-structural-navigation-in-sharepoint-online"></a>在 SharePoint Online SharePoint导航

这是默认情况下使用的开箱即用导航，是最直接的解决方案。 它不需要任何自定义，非技术用户还可以轻松添加项目、隐藏项目以及从设置页管理导航。 我们建议 [启用缓存 ，](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)否则会进行代价高昂的性能选择。

### <a name="how-to-implement-structural-navigation-caching"></a>如何实现结构导航缓存

在 **"设置** 外观导航"下，可以验证是否选择了全局导航或当前导航  >    >  的结构导航。 选择 **"显示** 页面"将对性能产生负面影响。

![选择"显示子网站"的结构导航。](../media/SPONavOptionsStructuredShowSubsites.png)

Caching网站集级别和网站级别启用或禁用网站集，并且默认情况下启用这两者。 若要在网站集级别启用，请在"网站集管理设置导航"下选中"  >    >  启用缓存 **"框**。

![在网站级别启用缓存。](../media/structural-nav/structural-nav-caching-site-coll.png)

若要在网站级别启用，**请在"网站** 设置  >  **导航"下** 选中"**启用缓存"框**。

![在网站级别启用缓存。](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>在 SharePoint Online 中SharePoint导航和元数据

托管导航是另一个开箱即用选项，可用于重新创建与结构导航相同的大部分功能。 托管元数据可以配置为启用或禁用安全修整。 在禁用安全修整的情况下配置后，托管导航会相当高效，因为它加载具有固定数量的服务器调用的所有导航链接。 但是，启用安全修整会否定托管导航的一些性能优势。

如果您需要启用安全修整，我们建议您：

- 将所有友好 URL 链接更新为简单链接
- 将所需的安全修整节点添加为友好 URL
- 将导航项数限制为不超过 100 个且深度不超过 3 个级别

许多网站不需要安全修整，因为导航结构对于网站的所有用户来说通常是一致的。 如果禁用安全修整，并且向导航添加了一个链接，但并非所有用户都有权访问该链接，该链接仍将显示，但会导致出现拒绝访问的消息。 不存在意外访问内容的风险。

### <a name="how-to-implement-managed-navigation-and-the-results"></a>如何实现托管导航和结果

关于托管导航的详细信息，docs.microsoft.com 文章。 例如，请参阅[Overview of managed navigation in SharePoint Server](/sharepoint/administration/overview-of-managed-navigation)。

为了实现托管导航，您可以使用与网站的导航结构对应的 URL 设置术语。 在许多情况下，甚至可以手动选择托管导航来替换结构导航。 例如：

![SharePoint联机网站结构。](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>使用搜索驱动的客户端脚本

一种常见的自定义导航实现类采用客户端呈现的设计模式，该模式存储导航节点的本地缓存。

这些导航提供程序具有一些关键优势：

- 它们通常与响应式页面设计很好地工作。
- 它们非常可扩展且性能高，因为它们无需任何资源成本 (超时设置后在后台刷新) 。
- 这些导航提供程序可以使用各种策略检索导航数据，范围从简单的静态配置到各种动态数据提供程序。

数据提供程序的一个示例是使用 **搜索驱动的** 导航，该导航可灵活地枚举导航节点并高效处理安全修整。

还有其他一些常用选项可生成 **自定义导航提供程序**。 请查看[适用于 SharePoint Online](/sharepoint/dev/solution-guidance/portal-navigation)门户的导航解决方案，获取有关构建自定义导航提供程序的进一步指导。

使用搜索，可以使用连续爬网利用在后台构建的索引。 搜索结果从搜索索引中拉取，并且结果经过安全修整。 当需要安全修整时，这通常比开箱即用导航提供程序快。 使用搜索结构导航（尤其是在网站结构复杂时）将极大地加快页面加载速度。 与托管导航不同，这一点的主要优点是，您受益于安全修整。

此方法涉及创建自定义母版页，将开箱即用导航代码替换为自定义 HTML。 按照以下示例中概述的过程替换文件 中的导航代码 `seattle.html` 。 本示例中，您将打开 `seattle.html` 文件，将整个 元素 `id="DeltaTopNavigation"` 替换为自定义 HTML 代码。

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>示例：替换母版页中的开箱用导航代码

1. 导航到"网站设置页。
2. 通过单击"母版页"打开 **母版页样式库**。
3. 你可以在此处浏览库并下载文件 `seattle.master` 。
4. 使用文本编辑器编辑代码，并删除以下屏幕截图中的代码块。<br/>![删除显示的代码块。](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. 删除 和 标记 `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` 之间的代码，并将其替换为以下代码段：<br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. 将开始加载图像定位标记中的 URL 替换为指向网站集中的加载图像的链接。 进行更改后，重命名该文件，然后将它上载到母版页样式库。 这将生成一个新的 .master 文件。<br/>
7. 此 HTML 是由 JavaScript 代码返回的搜索结果填充的基本标记。 您需要编辑代码以更改 var root = "site collection URL" 的值，如以下代码片段所示：<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. 结果将分配给 self.nodes 数组，并且通过使用将输出分配给数组 self.hierarchy linq.js对象构建层次结构。 此数组是绑定到 HTML 的对象。 这是通过向 ko.applyBinding () ko.applyBinding 函数传递的 toggleView () 函数。<br/>这样，层次结构数组将绑定到以下 HTML：<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

和 的事件处理程序将添加到顶级导航以处理在 函数中完成的子网站 `mouseenter` `mouseexit` 下拉菜单 `addEventsToElements()` 。

在我们的复杂导航示例中，没有本地缓存的新页面负载显示服务器所花费的时间已从基准结构导航中缩减，以获得与托管导航方法类似的结果。

### <a name="about-the-javascript-file"></a>关于 JavaScript 文件...

>[!NOTE]
>如果使用自定义 JavaScript，请确保CDN文件位于其他CDN位置。

整个 JavaScript 文件如下所示：

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

为了汇总函数中以上所示的代码，创建了 一个 `jQuery $(document).ready` `viewModel object` ，然后 `loadNavigationNodes()` 调用该对象上的 函数。 此函数加载之前构建的导航层次结构，该层次结构存储在客户端浏览器的 HTML5 本地存储中，或者调用 函数 `queryRemoteInterface()` 。

`QueryRemoteInterface()` 使用 函数和脚本前面定义的 查询参数生成请求， `getRequest()` 然后从服务器返回数据。 此数据实质上是网站集中所有网站的数组，表示为具有各种属性的数据传输对象。

然后，此数据被解析到之前定义的对象中，这些对象用于创建可观察属性，以用于将值绑定到我们之前定义的 `SPO.Models.NavigationNode` `Knockout.js` HTML 的数据。

然后，将对象放入结果数组中。 此数组使用 Knockout 解析为 JSON，并存储在本地浏览器存储中，以在将来页面加载时提高性能。

### <a name="benefits-of-this-approach"></a>此方法的好处

此方法的主要 [好处是](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) ，通过使用 HTML5 本地存储，导航在用户下次加载页面时本地存储。 我们将搜索 API 用于结构导航，获得重大性能改进;但是，执行和自定义此功能需要一些技术功能。

在 [示例实现中](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)，网站按与开箱用结构导航相同的方式排序;字母顺序。 如果要偏离此顺序，开发和维护会更加复杂。 此外，此方法还要求您偏离受支持的母版页。 如果未维护自定义母版页，您的网站将错过 Microsoft 对母版页的更新和改进。

上述 [代码](#about-the-javascript-file) 具有以下依赖项：

- jQuery - https://jquery.com/
- KnockoutJS - https://knockoutjs.com/
- Linq.js - https://linqjs.codeplex.com/ 或 github.com/neuecc/linq.js

LinqJS 的当前版本不包含上述代码中使用的 ByHierarchy 方法，将中断导航代码。 若要解决此问题，将以下方法添加到 Linq.js 文件行之前 `Flatten: function ()` 。

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a>相关主题

[SharePoint Server 2013 中的托管导航概述](/sharepoint/administration/overview-of-managed-navigation)

[结构导航缓存和性能](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)