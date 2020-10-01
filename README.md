# ci4-study

## Cài đặt môi trường local

1. Kiểm tra version php của xampp, nếu php version < 7.4 thì hãy cài đặt lại bản xampp khác trên windows

Download: https://www.apachefriends.org/jp/download.html

XAMPP Version: 7.4.10 / PHP 7.4.10

2. Sau khi cài đặt cần kiểm tra php.ini đã được mở extension intl hay chưa ?

Bỏ dấu comment để sử dụng extension này

;extension=intl -> extension=intl

Nếu không mở có thể sẽ gặp lỗi như sau

PHP Fatal error:  Uncaught Error: Call to undefined function CodeIgniter\locale_set_default() in C:\xampp_php74\htdocs\ci4-study\system\CodeIgniter.php:184

3. Chuyển tên file env thành ".env"

Thay đổi 1 số thông số như dưới đây

CI_ENVIRONMENT = development

app.baseURL = 'http://localhost/ci4-study/public'

\project_folder\app\config\App.php
Before
public $baseURL = 'http://localhost:8080/';

After change
public $baseURL = 'http://localhost/';

## Khởi động project

1. Khởi động xampp theo đường dẫn

http://localhost/ci4-study/public/

2. Thêm phần config dưới đây vào file vshosts của apache để rút gọn domain

C:\xampp_php74\apache\conf\extra\httpd-vhosts.conf

<VirtualHost *:80>

DocumentRoot "C:/xampp_php74/htdocs/ci4-study/public"

ServerName localhost

</VirtualHost>

<Directory "C:/xampp_php74/htdocs/ci4-study/public/">

Options Indexes FollowSymLinks MultiViews

AllowOverride all

Order Deny,Allow

Allow from all

Require all granted

</Directory>


3. Khởi động lại xampp và truy câp đường dẫn

http://localhost

Lúc này hiện trạng hoàn toàn giống với khi ta truy cập đường dẫn ở bước số 1
