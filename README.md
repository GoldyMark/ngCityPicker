angularCityPicker
===========================

angularCityPicker
类似电商网站的城市选择，基于angularJS框架构建。
备注：
1、本人非专业前端，尤其是对CSS感到痛苦，所以该插件可能不是很成熟；
2、本插件受https://github.com/cipchk/angular-city-select 启发，本着学习AngularJS而写的；
3、ng-model和q的设计比较混乱，如果有大牛能指点一下那就感激不尽；
4、http://www.jq22.com/jquery-info632 ，找到的另外一个类似插件供参考选择；

PS：等有空了解Markdown语法再写好这个README

TODO：
Add less

Dependencies：
Angularjs(开发时使用1.2.16版本，没有做兼容性测试，其他版本应该没问题)

Usage:

Add dependencies:
CSS:
<link rel="stylesheet" href="../lib/angularCityPicker.min.css">

JS:
<script src="../lib/angular.js"></script>
<script src="../lib/angularCityPicker.min.js"></script>

HTML:
<mk-city-picker open="data.open" ng-model="data.model" q="data.q" placeholder="请选择城市" format="$0-$1-$2">
</mk-city-picker>

Controller:
angular.module('myApp', ['angularCityPicker'])
.('myController', ['$scope', function($scope){
    $scope.data = {
        model:"sssWWW",
        open:false,
        // q:"440106",
        q:["广东","广州","天河"]
    }
}]);

Detail:
除了ng-model，其余选项均为可选；
placeholder和format是string，其余均是expression；

open:
type:boolean,
控制下拉框打开与否

ng-model:
type:object,
返回数据格式示例：
{
    "province":["44","粤","广东"],
    "city":["4401","广州"],
    "district":["440106","天河"]
}

q:
type:array or string
传入要选择的城市数据，传入的q值会影响ng-model的生成值；
传入的数据格式示例：
string:"44"，或"4401"，或"440106"——可传入省份、城市或县区对应的代码；
array:['广东','广州','天河']——按[省份名称,城市名称,县区名称]的格式传入；

placeholder:
type:string
城市没选择时显示的提示信息；

format:
城市显示格式，$0是省份，$1是城市，$2是县区
