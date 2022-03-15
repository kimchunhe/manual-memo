### 结构

#### 栅格化
##### 页面垂直分割为12等分
``` html
<!-- 行 -->
<div class="row">
    <!-- 末尾的数字表示该div占用的列数，如12表示占整列 -->
    <div class = "col-md-12">
        
    </div>
</div>
```
<table>
    <tr>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
        <td>col-md-1</td>
    </tr>
    <tr>
        <td colspan="2">col-md-2</td>
        <td colspan="2">col-md-2</td>
        <td colspan="2">col-md-2</td>
        <td colspan="2">col-md-2</td>
        <td colspan="2">col-md-2</td>
        <td colspan="2">col-md-2</td>
    </tr>
</table>