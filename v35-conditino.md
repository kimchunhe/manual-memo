### 页面控件
form控件加载方式

``` javascript
//查询条件数据源
    this.sources = {
        storeStatus: ko.observableArray([{ text: "开店", value: "OPEN" }, { text: "关店", value: "CLOSE" }]),
        businessType: ko.observableArray()
    }
    //查询条件默认值
    this.condition = {
        storeCode: ko.observable(''),
        businessType: ko.observable(''),
        storeStatus: ko.observable('')
    }
    //查询条件控件
    this.searchInputs = [
        {
            id: 'main.StoreCode',
            size: [3, 4],
            value: self.condition.storeCode
        }, {
            id: 'brand.BusinessType',
            size: [3, 4],
            type: 'dropdown',
            blankText: '',
            source: self.sources.businessType,
            value: self.condition.businessType
        }, {
            id: 'brand.StoreStatus',
            size: [3, 4],
            type: 'dropdown',
            blankText: '',
            source: self.sources.storeStatus,
            value: self.condition.storeStatus
            //required: true,
            //enable: self.enable
        }
    ];
    this.init = function () {
        //
        var conditionFactory = new $.fom.inputsFactory();
        conditionFactory.updateHtml($('#' + conditionAreaId), self.searchInputs, self);
        //get方式调用api
        conditionFactory.updateSelect(apiUrl, inputId, selectValue);
    }
```

### form控件配置参数

|field|desc|default value|
|---|---|---|
|id|''||
|name|''||
|label|''|左边显示的|
|size|3||
|type|'text'|'date'|'dropdown'|
|source|[]|需要用数据源的控件用来存储数据源|
|value|''|关联的值|
|img|''|上传控件图片img   |
|filename|''|上传控件filename|
|imgwidth|''|上传控件imgwidth |
|imgheight|''|上传控件imgheight|
|tagvalue|''|上传控件tagvalue|
|tagstyle|''|上传控件tagstyle|
|acceptFileTypes|'*'|上传控件acceptFileTypes|
|acceptFiles|''|上传控件acceptFiles|
|imgdel|''|上传控件imgdel|
|delclick|''|上传控件delclick|
|blankText|null|空值时的提示|
|enable|ko.observable(true)|能否输入|
|visible|true|是否可见|
|showLabel|true|是否显示label|
|otherAttrs|{}|其他属性如{maxLength:2}|
|style|''||
|fontcolor|''| |
|helpText|''|显示在控件下面的提示信息|
|isCheckValid|false|是否需要检查值|
|isRequired|false||
|multiple|false|上传控件用来判断是否可以上传多个|
|css|''||
|rows|10||
|enddate|''||
|step|''||
|showSeconds|false||
|switchchecked|false|radiolist选中项|
|dataDateFormat|'yyyy-mm-dd'||
|typeahead|ko.observable('')||
|search|false|下拉框设置为true时,可以搜索下拉选项内容|
|tobitable|false|设置为true时,会强制转为保留两位带千位符显示|
|todigitable|false|设置为true时,会强制转为整数带千位符显示|
|popovercontent|''|提示内容html格式|
|popovertitle|''|提示标题,默认值为提示|
|popoverposition|''|规定如何定位弹出框（即 top,bottom,left,right）|
|popovertrigger|''|定义如何触发弹出框： click, hover, focus,您可以传递多个触发器，每个触发器之间用空格分隔。|

