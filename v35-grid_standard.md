## grid 加载数据

### 引用包
``` html
<!-- 引用 datatables控件的 css -->
<asp:Content ID="Content1" ContentPlaceHolderID="HeadHolder" runat="server">
    <%=RequireCss(ControlType.KoDatatables)%>
</asp:Content>
<!-- 引用 datatables控件的 js -->
<asp:Content ID="Content3" ContentPlaceHolderID="ScriptHolder" runat="server">
    <%=RequireJs(ControlType.App, ControlType.KoDatatables) %>
</asp:Content>
```

### 表格html代码配置
``` html
<table data-bind="dataTable: { 
    # 数据源api地址
    dataSource: mainDatas, 
    # 数据源api参数
    ajaxParams: mainAjaxParams, 
    # 绑定数据时触发的事件
    onSuccess: mainDataComplete, 
    # grid数据区模板
    rowTemplate: 'mainRowTemplate', 
    # 字段（需要与模板中的data属性值对上，不需要与数据库中的字段对上，数据库中的数据只要顺序正确即可）
    columns: ['store_code', 'store_name'] }"
    class="table table-striped table-bordered table-hover" id="mainGrid">
    <thead>
        <tr role="row" class="heading">
            <th data-bind="text: $.lang.i18n('main.StoreCode')"><%--店铺号--%></th>
            <th data-bind="text: $.lang.i18n('main.StoreName')"><%--店铺名--%></th>
        </tr>
    </thead>
    <tbody>
    </tbody>
</table>
<script id="mainRowTemplate" type="text/html">
    <td data-bind="attr: { 'data-title': $.lang.i18n('main.StoreCode') }, template: { name: 'label', data: store_code_fortemp }"></td>
    <td data-bind="attr: { 'data-title': $.lang.i18n('main.StoreName') }, template: { name: 'label', data: store_name_fortemp }"></td>
</script>
```

### js方法
``` js
var self = this;

    ////初始化
    //this.init = function () {

    //}

    this.mainDatas = baseUrl + '/QueryGridData';
    //查询参数
    this.mainAjaxParams = {
        
    };

    //刷新表
    this.mainRefreshAjax = function () {
        var table = ko.bindingHandlers.dataTable.getDataTableInstance($("#" + mainGridId + ""));
        table.fnDraw();
    };

    //查询【刷新】
    this.refresh = function () {
        
        self.mainRefreshAjax();
    };

    //页面查询按钮事件
    this.query = function () {
        self.refresh();
    };

    //Grid绑定事件, 主要处理grid里的额外控件的数据绑定。
    this.mainDataComplete = function (allData) {
        $.each(allData.aaData, function () {
            var that = this;
        });

    };
```