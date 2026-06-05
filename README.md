## ONMP
===
Lệnh cài đặt ONMP một chạm, dành cho các thiết bị đã cài đặt môi trường Entware.
Hiện tại đã thử nghiệm thành công trên các firmware: Padavan, LEDE (OpenWrt), Merlin.

Nếu `php-fpm` và `mysqld` khởi động thất bại, bạn có thể bật bộ nhớ ảo (SWAP) bằng cách:

```
$ onmp open 
# Chọn phím số 7
```

## Giới thiệu
ONMP là viết tắt của: Opkg + Nginx + MySQL + PHP

Đây là một script được viết bằng Linux Shell, giúp nhanh chóng xây dựng môi trường Nginx/MySQL/PHP cho các router sử dụng trình quản lý gói opkg. Ngoài ra, script còn tích hợp sẵn tính năng cài đặt nhanh không cần cấu hình cho một số ứng dụng web rất hữu ích.

```
ONMP tích hợp sẵn tính năng cài đặt nhanh các chương trình sau:
(1) phpMyAdmin (Công cụ quản lý cơ sở dữ liệu)
(2) WordPress (Mã nguồn CMS phổ biến nhất thế giới)
(3) Owncloud (Nền tảng đám mây cá nhân kinh điển)
(4) Nextcloud (Sản phẩm mới từ đội ngũ Owncloud, đám mây cá nhân đẹp và mạnh mẽ)
(5) h5ai (Trình quản lý và hiển thị thư mục tệp tin tuyệt vời)
(6) Lychee (Kho ảnh Web đẹp mắt, dễ sử dụng)
(7) Kodexplorer (Trình quản lý tài liệu trực tuyến mã nguồn mở - hay còn gọi là Mango Cloud)
(8) Typecho (Nền tảng blog mã nguồn mở siêu nhẹ và mượt mà)
(9) Z-Blog (Mã nguồn blog PHP nhỏ gọn, tốc độ cao)
(10) DzzOffice (Nền tảng văn phòng mã nguồn mở)
```

Tất cả các gói phần mềm đều được cài đặt thông qua opkg. Mọi cấu hình đều được hiển thị minh bạch trong script, bạn hoàn toàn có thể yên tâm sử dụng.
## Hướng dẫn sử dụng chi tiết

[wiki](https://github.com/xzhih/ONMP/wiki)

[Blog tác giả](https://zhih.me)


## Hướng dẫn cài đặt

### 1. Cài đặt Entware

Entware là một kho lưu trữ gói phần mềm dành cho các hệ thống nhúng, sử dụng hệ thống quản lý gói opkg. Hiện tại trên nguồn chính thức đã có hơn 2000 gói phần mềm, có thể nói là rất phong phú.

Mỗi loại firmware sẽ có cách cài đặt Entware khác nhau, vui lòng xác định đúng loại firmware thiết bị của bạn để cài đặt chính xác:

[Cài đặt Entware trên LEDE / OpenWrt](https://github.com/xzhih/ONMP/wiki/在-LEDE-上安装-Entware)

[Cài đặt Entware trên Asuswrt-Merlin](https://github.com/xzhih/ONMP/wiki/在梅林上安装-Entware)

[Cài đặt Entware trên Padavan](https://github.com/xzhih/ONMP/wiki/在-Padavan-上安装-Entware)

### 2. Cài đặt ONMP

Sử dụng lệnh một chạm: Sao chép -> Dán vào Terminal -> Nhấn Enter.

```
 $ sh -c "$(curl -kfsSl https://raw.githubusercontent.com/xzhih/ONMP/master/oneclick.sh)"
```

Nếu việc sao chép chuỗi lệnh dài trên bị lỗi, bạn có thể tiến hành cài đặt từng bước theo các lệnh dưới đây:

```
# Di chuyển vào thư mục gắn kết của entware và cài đặt wget, unzip
cd /opt && opkg install wget unzip 

# Tải gói phần mềm ONMP
wget --no-check-certificate -O /opt/onmp.zip https://github.com/xzhih/ONMP/archive/master.zip 

# Giải nén
unzip /opt/onmp.zip 
cd /opt/ONMP-master 

# Cấp quyền thực thi
chmod +x ./onmp.sh 

# Khởi chạy script
./onmp.sh
```

Nếu script chạy bình thường, giao diện menu sẽ xuất hiện. Bạn chỉ cần chọn số 1 để tiến hành cài đặt.

![Cài đặt](https://i.loli.net/2018/03/03/5a99ac096c6a1.png)

Nếu script chạy bình thường, giao diện menu sẽ xuất hiện. Bạn chỉ cần chọn số 1 để tiến hành cài đặt.

Nếu xảy ra lỗi trong quá trình cài đặt thông thường, hệ thống sẽ hiển thị thông báo lỗi, hãy xử lý theo gợi ý. Phần lớn các phản hồi lỗi hiện tại đều do vấn đề mạng, vì các máy chủ nguồn của Entware nằm ở nước ngoài (và từng bị giới hạn băng thông do sự cố DDoS). Tốc độ tải xuống có thể sẽ hơi chậm, lúc này bạn có thể thư giãn xem một bộ phim, biết đâu khi quay lại thì mọi thứ đã cài đặt xong.

Sau khi cài đặt thành công, bạn sẽ nhận được thông báo hoàn tất trên màn hình. Chúc mừng bạn đã cài đặt thành công ONMP và có thể bắt đầu trải nghiệm!

![Cài đặt thành công](https://i.loli.net/2018/03/03/5a99aeda756ac.png)

Nếu thiết bị của bạn trông giống như trong hình trên, thì xin chúc mừng! Bạn đã cài đặt ONMP thành công và giờ có thể thoải mái sử dụng nó.

## Cập nhật Script

Bạn chỉ cần chạy lại chính dòng lệnh cài đặt một chạm ở trên, sau đó chọn số 2 để cập nhật script lên phiên bản mới nhất.

## Các lệnh điều khiển ONMP thông dụng

**Các lệnh cơ bản:**

```
quản lý：onmp open
启动、停止、重启：onmp start|stop|restart
查看网站列表：onmp list 
```

**主要软件包的管理命令：**

```
Nginx 管理命令
onmp nginx start|restart|stop

MySQL 管理命令
onmp mysql start|restart|stop

PHP 管理命令
onmp php start|restart|stop

Redis 管理命令
onmp redis start|restart|stop
```

**设置数据库密码：**

输入 `onmp open` 后选择3，会提示 `Enter password:` ，这个时候要输入当前数据库的密码，比如我初始设置的数据库密码是123456，回车后要是密码正确，会提示输入你要设置的新密码，回车后会提示再次输入确认。也就是，一次旧密码，两次新密码。

这个位置很简单，但是很多人都说改不了密码，其实是没看提示，没输入旧密码，所以我写清楚一些。

## 其他

探针来自 https://github.com/WuSiYu/PHP-Probe
