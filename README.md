#ngCityPicker

类似电商网站的城市选择器，基于AngularJS框架构建。

## 说明：
1. 本插件受https://github.com/cipchk/angular-city-select 启发，本着学习AngularJS而写；
2. ng-model和q的设计比较混乱，如果有大牛能指点一下那就感激不尽；
3. http://www.jq22.com/jquery-info632 ，找到的另外一个类似插件供参考选择；

## Demo:

## 许可证:
Apache License 2.0

## 依赖库:
只有Angularjs！(开发时使用1.2.16版本，没有做兼容性测试，其他版本应该没问题)

## 安装:
引入ngCityPicker的css和js文件：

**JS:**
```html
<script src="../dist/angular.js"></script>
<script src="../dist/ngCityPicker.min.js"></script>
```
**CSS:**
```css
<link rel="stylesheet" href="../lib/ngCityPicker.min.css">
```

## 使用:
1、 引入ngCityPicker模块：
```javascript
angular.module('myApp', ['ngCityPicker'])
```

2、 使用mk-city-picker指令：
```html
<mk-city-picker open="params.open" placeholder="请选择城市" format="$0-$1-$2" ng-model="params.outputModel" q="params.inputModel">
</mk-city-picker>
```

3、 Controller代码:
```javascript
angular.module('myApp', ['ngCityPicker'])
.controller('myController', ['$scope', function($scope){
    $scope.params = {
        outputModel:null,
        open:false,
        // inputModel:"440106",
        inputModel:['广东','广州','天河']
    }
}]);
```

## 参数：
### [可选][类型:boolean] open:
#### 说明：控制ngCityPicker下拉框的打开或关闭；
#### 默认值：false
<br/>

### [可选][类型:string] placeholder:
#### 说明：默认显示的提示信息；
#### 默认值：请选择城市
<br/>

### [可选][类型:string] format:
####说明：格式化选中的城市，$0是省份，$1是城市，$2是县区；
#### 默认值：$0-$1-$2
#### 示例：
```html
<mk-city-picker format='$0省-$1市-$2县'></mk-city-picker>
```
<br/>

### [可选][类型:**array of string** | **string**] q:
#### 说明：传入要选择的城市数据；
#### 默认值：null
#### 默认格式：array of string
传入数据格式示例（支持数组和字符串）：
**array**:['广东','广州','天河']——按[省份名称,城市名称,县区名称]的格式传入；
**string**:"44"，或"4401"，或"440106"——可传入省份、城市或县区对应的代码；
<br/>

### [必须][类型:object] ng-model:
####说明：返回选择的城市；
返回数据格式示例：
```json
{
    "province":["44","粤","广东"],
    "city":["4401","广州"],
    "district":["440106","天河"]
}
```