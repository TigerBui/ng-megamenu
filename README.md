# @tigerbui/ng-megamenu

ng-megamenu là directive dành cho Angular@1.x với tính năng cơ bản của một dropdown menu.
# Cài đặt (installation)
```sh
$ npm install @tigerbui/ng-megamenu
```
Cài đặt trên project của bạn theo các bước sau:
```html
1> Bước 1 (step 1)
<script src="./node_module/@tigerbui/ng-megamenu/immenu.directive.min.js"></script>
Hoặc
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
<body>
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
</body>
</html>
```

### Tùy biến ng-megamenu (Option)
- Thay đổi `font-family` 
```html 
<div mega-menu-drt i-mm-font="Arial, 'sans-serif'"></div>
``` 
- Thay đổi hiển thị dropdown menu
```html
<div mega-menu-drt i-mm-config="{screen: 'full'}"></div>
```
- `i-mm-config` hiện tại chỉ có tùy chọn với `{screen: ''}` => sau sẽ mở rộng thêm.
- `{screen: ''}` có 2 giá trị `full` và `df`
### CSS
Css mặc định `.i-submm-dropdown` được responsive theo màn hình window như sau:

| Kích thước màn hình | Số cột hiển thị `.i-mm-col-item` |
|---------------------|----------------------------------|
| `>= 1200px` | 4 cột |
| `769px < 1200px` | 3 cột |
| `<=768px` | 1 cột |

### Công nghệ (Tech)

@tigerbui/ng-megamenu sử dụng công nghệ

* [AngularJS](https://angularjs.org/) - HTML is great for declaring static documents, but it falters...
* [Javascript](https://javascript.info/) - How it's done now. From the basics to advanced topics with simple,...

License
----
This project is [MIT](/ng-megamenu/LICENSE.md) licensed.
