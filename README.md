# @tigerbui/ng-megamenu

ng-megamenu là directive dành cho [Angular@1.x](https://angularjs.org/) với tính năng cơ bản của một dropdown menu.
# Cài đặt (installation)
```sh
$ npm install @tigerbui/ng-megamenu
```
#### Bạn có thể xem [Demo Megamenu](https://jsfiddle.net/tigerbui/9s3nf57b/30/)
`Hoặc (or)`
#### Cài đặt trên project của bạn theo các bước sau:
```html
1> Bước 1 (step 1)
<script src="./node_module/@tigerbui/ng-megamenu/immenu.directive.min.js"></script>
Hoặc (or)
<script src="https://io.inet.vn/assets/js/immenu/immenu.directive.min.js"></script>

2> Bước 2 (step 2)
Khai báo App directive immenuDirectiveApp vào app module của bạn
<script>
    angular.module('yourApp', ['immenuDirectiveApp']);
</script>

3> Bước 3 (step 3)
Thêm mega-menu-drt trong cấu trúc HTML, ví dụ như dưới đây:

<!DOCTYPE html>
<html ng-app="yourApp">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Hello World!</title>
    <script src="./node_modules/angular/angular.js"></script>
    <script src="./node_modules/@tigerbui/ng-megamenu/immenu.directive.js"></script>
</head>
<body ng-controller="yourController">
    <div class="container">
        <nav class="navbar-wrap" mega-menu-drt>
            <ul class="navbar">
                <li class="i-mm-dropdown">
                    <a href="#">
                        Demo - Mega menu
                    </a>
                    <div class="i-submm-dropdown" style="display:none;">
                        <div class="i-mm-col-item">
                            <div class="i-mm-group">
                                <p class="i-mm-gr-title">Group 1</p>
                                <ul class="i-mm-gr-list">
                                    <li class="i-mm-gr-item">
                                        <a class="i-mm-link" href="#">Sản phẩm 1</a>
                                        <p class="i-mm-des">Mô tả sản phẩm 1</p>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </li>
            </ul>
        </nav>
    </div>
    <script>
        var app = angular.module('yourApp', ['immenuDirectiveApp']);
        app.controller("yourController", yourController);
        
        yourController.$inject = ['$scope'];
        
        function yourController($scope) {
            $scope.mmDtmock = [
                {
                    title: "Menu item"
                }
            ];
            for(var i=0; i < 6; i++) {
                $scope.mmDtmock.push({title: 'Menu item ' + i, dropdown: false});
            }
            $scope.mmDtmock.forEach(function (item, id, nArr) {
                if(id%2 == 0) {
                    item.dropdown = true;
                }
            })
        }
    </script>
</body>
</html>
```

### Tùy biến ng-megamenu (Option)
- Thay đổi `font-family` 
```html 
<div mega-menu-drt i-mm-font="Arial, 'sans-serif'"></div>
``` 
Mặc định (Default) `font-family: 'Open Sans', sans-serif;`
- Thay đổi hiển thị dropdown menu
```html
<div mega-menu-drt i-mm-config="{screen: 'full'}"></div>
```
- `i-mm-config` hiện tại chỉ có tùy chọn với `{screen: ''}` => sau sẽ mở rộng thêm.
- `{screen: ''}` có 2 giá trị `full` và `df`
### CSS
```html
<link rel="stylesheet" type="text/css" href="https://io.inet.vn/assets/js/immenu/style.css"/>
Hoặc (or)
<link rel="stylesheet" type="text/css" href="./node_modules/@tigerbui/ng-megamenu/style.css"/>
```
Responsive

| Kích thước màn hình (@media screen) | Số cột hiển thị (column view) |
|------------------------------------|----------------------------------|
| `>= 1200px` | 4 cột (4 col) |
| `769px < 1200px` | 3 cột (3 col) |
| `<=768px` | 1 cột (1 col) |

### Công nghệ (Tech)

@tigerbui/ng-megamenu sử dụng công nghệ

* [AngularJS](https://angularjs.org/)
* [Javascript](https://javascript.info/)

License
----
This project is [MIT](https://github.com/TigerBui/ng-megamenu/blob/master/LICENSE) licensed.
