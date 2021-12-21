# Group22_Lightsail
Project Final Cloud Class 06 (AWS)

+ Trần Lưu Thế Anh - 19110324

+ Nguyễn Thái Hải - 19110356

+ Nguyễn Hữu Hiếu - 19110364

Giảng viên hướng dẫn: TS. Huỳnh Xuân Phụng

Mã môn học: CLCO332779

# I. Cấu hình WordPress với Amazon Lightsail

- Amazon Web Services là nền tảng dịch vụ điện toán đám mây an toàn, mang đến khả năng tính toán, lưu trữ cơ sở dữ liệu, phân phối nội dung và các chức năng khác nhằm giúp các doanh nghiệp mở rộng và phát triển.

- Vậy Amazon Lightsail là gì? Amazon Lightsail là một dịch vụ đám mây của Amazon, không chỉ là môi trường điện toán (Computing environment), nó còn có thể lưu trữ dữ liệu (Storage - Amazon S3 ), khả năng khôi phục dữ liệu (Snapshots - Amazon RDS). Ngoài ra, nó cung cấp các dịch vụ khác như cân bằng tải (Elastic Load Balancing), tưởng lửa (Firewall), DNS (Route 53) kèm theo một số chức năng có sẵn khác.

- Đầu tiên giới thiệu về cách cài đặt và cấu hình WordPress trên Amazon Lightsail

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/logo.jpg)

# Các bước thực hiện

## 1. Cài đặt WordPress với Lightsail

- Truy cập vào tab Lightsail chọn **Create instance**.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/1Create_instance.PNG)

- Chọn vị trí AWS

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/2Singapore.PNG)

- Chọn hệ điều hành sẽ sử dụng.

- Linux/Unix.

- WordPress.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/3hdh.PNG)

- Chọn gói dịch vụ Amazon Lightsail chọn gói dịch vụ phù hợp với trang web của bạn ở đây thì mình sẽ chọn gói ít tiền nhất 3.5$

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/4price_per_month.PNG)

- Cuối cùng thì nhập tên ứng dụng và khởi tạo.

- Với Amazon Lightsail cài đặt rất dễ dàng, chỉ cần vài cú click chuột, thì chúng ta đã có một server hoàn chỉnh.

## 2. Kết nối với máy tính thông qua SSH và lấy mật khẩu WordPress website

### Lấy mật khẩu để đăng nhập vào màn hình quản trị của WordPress

- Trên tab Lightsail click vào icon SSH

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/5ssh.PNG)

- Sau đó dùng lệnh

`cat $HOME/bitnami_application_password` để lấy mật khẩu mặc định

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/6password.PNG)

## 3. Đăng nhập vào trang quản trị WordPress

- Sau khi đăng nhập chúng ta có thể thay đổi mật khẩu cài đặt plugin và tùy biến giao diện cũng như các chức năng trên website của mình

- truy cập http://52.76.18.66/wp-login.php

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/7ip.PNG)

- Đăng nhập và cấu hình, plugin

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/8wordpress.PNG)

## 4. Tạo địa chỉ IP

- Truy cấp vào ứng dụng bạn vừa tạo và chọn tab Networking, sau đó tạo địa chỉ IP.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/9createIp.PNG)

- Sau khi đặt tên cho StaticIP nhấn Create.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/91Staticip.PNG)

## 5. Kết nối trang wordpress với cơ sở dữ liệu quản lý bằng mysql
- Đầu tiên, tạo database trên lightsail.
- Chọn tag **Databases**, chọn **Create database**.
![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/createdb.jpg)

- Chọn vị trí cho database, ở đây ta chọn Singapore.
![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/regiondb.jpg)

- Chọn MySql, chọn version cho MySql.
![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/vsmysql.jpg)

- Chọn gói phù hợp với dung lượng dữ liệu cần thiết, ở đây ta chọn gói 15$.
![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/pricedb.jpg)

- Đặt tên cho database và nhấn **Create database** để tạo database.
![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/dbname.jpg)

- Sau khi tạo xong, database sẽ bị ẩn đi bởi vì phía server đang tạo database, ta chờ khoảng 15p database sẽ hoàn tất.
- Chọn vào database để xem thông tin.
![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/waitdb.jpg)

- Để bất kỳ ai có thông tin của database đều có thể lấy dữ liệu xuống MySql Local, ta chọn tag **Networking** trong database, Bật **Public mode**.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/publicdb.jpg)

- Sau đó ta mở ssh của trang WordPress, nhập dòng lệnh bên dưới để chuyển cơ sở dữ liệu WordPress sang cơ sở dữ liệu MySql.

`sudo mysqldump -u root --databases bitnami_wordpress --single-transaction --compress --order-by-primary -p$(cat /home/bitnami/bitnami_application_password) | sudo mysql -u dbmasteruser --host ls-be2c25772e3015d19df6c655cd60ca1578467739.cmqnhyzvdn9v.ap-southeast-1.rds.amazonaws.com --password`

- Nhập mật khẩu của Database, mật khẩu sẽ không hiển thị khi nhập.

- Nếu phản hồi xuất hiện như hình bên dưới thì dữ liệu được chuyển thành công.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/passSuccess.jpg)

- Phòng trường hợp xảy ra sự cố, ta sẽ tạo bản sao lưu của `config.php` bằng lệnh:

`cp stack/wordpress/wp-config.php stack/wordpress/wp-config.php-backup`

- Tiếp đó, ta mở tệp `wp-config.php` bằng :

`nano stack/wordpress/wp-config.php`

- Tìm và chỉnh sửa ba giá trị của `DB_USER`, `DB_PASSWORD` và `DB_HOST` bằng User name, Password, Endpoint:3306 của database.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/config.jpg)

- Cuối cùng, nhập lệnh `sudo stack/ctlscript.sh restart` để khởi động lại các dịch vụ web trên phiên bản.

## 6. Trỏ tên miền cho ứng dụng

- Tạo tên miền ở Freenom

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/92domain1.PNG)

- Quay lại Networking thì ta chọn Create DNS zone.

- Sau đó nhập tên miền và click Create DNS zone.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/9createIp.PNG)

- Nhập tên miền vào DNS records.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/92domain.PNG)

- Sao chép các Name servers từ DNS.

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/93domain_add_recore.PNG)

- Lưu vào bên Freenom

![myimage-alt-tag](https://github.com/theanh176/Group22_Lightsail/blob/main/image/93domain_add_recore2.PNG)


# II. Mean
Ngăn xếp dành cho nhà phát triển Mean: Mean Stack là sự kết hợp giữa của MongoDB, ExpressJS, AngularJS, NodeJS và khiến cho việc xây dựng những ứng dụng web trở nên mạnh mẽ và đơn giản hơn bao giờ hết.

<img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-03%2017-01-26-743.jpg?raw=true">

# Các bước thực hiện
  ## 1. Tiến hành Create Instance trong Lightsail AWS
  • Chọn Stack Mean và đặt tên instance lại nếu cần. Sau đó chọn Create Instance. Đợi 1 vài phút để AWS có thể tạo và running.
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2010-25-33-075.jpg?raw=true" >
  
  ## 2. Lấy Password Mean
  • Mở connect bitnami trong Stack Mean vừa tạo, gõ lệnh ls để xem các thành phần, sẽ có mục bitnami_application_password để chúng ta lấy password. Để lấy password của Mean, gõ lệnh `cat bitnami_application_password` 
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2010-29-38-872.jpg?raw=true">
  
  ## 3. Clone các project github
  • Clone 2 project từ github về gồm Front-End và Back-End để thực hiện cài đặt app React. Sau khi clone xong, sử dụng lệnh `ls` để xem đã có mục phần đó hay chưa. Link 2 project: 
  
  https://github.com/ThaiHaiDev/customerManagement_MERN
  
  https://github.com/ThaiHaiDev/cm_frontend
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2010-42-52-360.jpg?raw=true">
  
  ## 4. Tạo Database Mongodb
  • Thực hiện tạo Database với Mongodb với các lệnh:
  
  `mongo admin --username root --password + Password Mean ở trên vừa lấy`
  
  Sau khi kết nối với Mongodb sẽ có dạng như sau:
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2010-50-16-927.jpg?raw=true">
  
  • Tiến hành tạo Database 
  
  `db = db.getSiblingDB('GROUP22')`
  
  • Thêm User vào Database
  
  `db.createUser( { user : "mean", pwd : "admin", roles : [ "readWrite", "dbAdmin" ]} )`
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2011-00-59-303.jpg?raw=true">
  
  Sau khi thêm thành công sẽ có hiện Successfull.
  
  ## 5. Chỉnh sửa cấu hình Folder customerManagement_MERN
  
  • Truy cập Folder customerManagement_MERN và mở file index.js để chỉnh sửa bằng lệnh:
  
  `cd customerManagement_MERN`
  
  `vim index.js`
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2011-06-00-597.jpg?raw=true">
  
  • Thực hiện chỉnh sửa file index.js theo như trong hình bằng cách nhấn phím `s` rồi thực hiện.
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2020-29-38-346.jpg?raw=true">
  
  Sau đó lưu lại bằng cách nhấn tổ hợp phím `Ctrl + C` và gõ lệnh `wq!` để lưu.
  
  • Lấy địa chỉ localhost bằng cách cd .. ra mục ban đầu và gõ lệnh `sudo ifconfig` để lấy địa chỉ localhost.
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2020-43-57-476.jpg?raw=true">
  
  • Mở .env để chỉnh sửa đường dẫn Path Database đã được tạo ở trên bằng các lệnh:
  
  `touch .env`
  
  `vim .env`
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2011-57-39-851.jpg?raw=true">
  
  Sau đó cũng nhấn phím `s để bắt đầu chỉnh sửa và gõ 2 lệnh ở dưới vào:
  
  `DATABASE_PATH=mongodb://mean:admin@172.26.8.161/GROUP22`
  
  `SECRET_KEY=thisissecret`
  
  Với mean là tên User, admin là Password, GROUP22 là tên Database, 172.26.8.161 là địa chỉ localhost.
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2020-43-06-800.jpg?raw=true">
  
  • Truy cập Folder cm_frontend và kiểm tra yêu cầu:
  
  Trong cm_frontend có src, chúng ta sẽ xem code bằng lệnh `cat src/index.js` và `cat src/backend` sẽ thấy yêu cầu đường dẫn REACT_APP_BACKEND. Sẽ thêm vào ở .env như ở trên.
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2012-00-36-211.jpg?raw=true">
  
  Thêm dòng code vào .env ở cm_frontend
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2021-06-04-795.jpg?raw=true">
  
  • Với địa chỉ ip được lấy ở Network ở AWS Lightsail của Stack Mean. Và đồng thời add rule ở Netword 2 Port 3000 và 8000
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2021-09-15-801.jpg?raw=true">
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2021-07-13-707.jpg?raw=true">
  
  • Quay về vị trí ban đầu, cài đặt forever: `npm install -g forever` 
  
  Chạy `forever start index.js`
  
  • Truy cập lại customerManagement_MERN và cài npm `npm install`
  
  Sau khi cài xong npm, chạy `npm start` kiểm tra xem đã kết nối Database hay chưa. Nếu kết nối thành công sẽ hiện DB is Connected.
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2021-48-01-367.jpg?raw=true">
  
  • Truy cập cm_frontend và cài npm `npm install`. Sau đó chạy lệnh `forever start "npm start" ./` và chạy `npm install`. App React đã được Starting với Server.
  
  • Chạy trên trình duyện địa chỉ: `54.251.142.63:3000` . Bây giờ đã start App thành công với giao diện:
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2021-23-18-528.jpg?raw=true">
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2021-23-34-427.jpg?raw=true">
  
# Container
Lightsail Container là gì Amazon Lightsail Containers cung cấp cho bạn khả năng chạy ứng dụng trên container với trải nghiệm cực kì đơn giản. Với Lightsail Containers, giờ đây bạn có thể triển khai các ứng dụng được container hóa lên đám mây bằng cách sử dụng các Docker image trực tiếp từ máy tính của bạn hoặc từ các ứng dụng trong hệ thống đăng ký công khai như DockerHub - chỉ với một vài cú nhấp chuột, thông qua một giao diện dễ sử dụng. Lightsail xử lý tất cả các vấn đề phức tạp về quản lý cơ sở hạ tầng và cho phép bạn tập trung vào mã ứng dụng của mình.

# Các bước thực hiện
## Chuẩn bị
  • Thực hiện tạo 1 máy ảo trên EC2, tương tự như đã được học trên lớp. Chúng ta tạo 1 máy ảo Ubuntu. (Đã được thầy hướng dẫn, tiến hành thực nghiệm nhanh)
  
  + Step 1: Tìm kiếm Cloud9Ubuntu
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/step1.jpg?raw=true">
  
  + Step 2: Chọn máy ảo t3.large
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/step2.jpg?raw=true">

  + Step 3: Set mặc định theo hình

  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/step3.jpg?raw=true">
  
  + Step 4: Set size là 64 GB

  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/step4.jpg?raw=true">
  
  + Step 5: Mặc định
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/step5.jpg?raw=true">

  + Step 6: Set mặc định theo hình

  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/step6.jpg?raw=true">

  + Step 7: Set mặc định theo hình, nhấn Lauch Instance

  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/step7.jpg?raw=true">

  • Tiến hình download key về để dùng Connect SSH.
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/key.jpg?raw=true">
  
  • Tạo 1 Create Repository trên Docker Hub, có thể đặt tên tùy ý. Trong demo này, đặt tên là lightsail. Repository trong bài: `hai19110356/lightsail`
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/dockerhub.jpg?raw=true">
  
## Push image lên Docker Hub

  • Truy cập vào Folder chứa key và tiến hành Connect trên CMD.
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/ssh.jpg?raw=true">
  
  • Tiến hành tạo ra Folder lightsail, truy cập đến Folder và dùng lệnh `vi index.html` để xem và edit file html.
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/mkdir.jpg?raw=true">
  
  • Nhấn phím `s` để thực hiện edit file, sau khi copy đoạn code html vào index.html. Nhấn tổ hợp phím `Ctrl + c` và gõ `:wq!` để lưu thay đổi.
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/html.jpg?raw=true">
  
  • Edit file Dockerfile bằng lệnh `vi Dockerfile` và chỉnh sửa file bằng cách tương tự như index. Edit theo như hình và `wq!` để lưu lại.
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/dockerfile.jpg?raw=true">
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/editdockerfile.jpg?raw=true">
  
  • Build docker 
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/build.jpg?raw=true">
  
  • Đặt tag và Login vào tài khoản Docker Hub để tiến hành push image
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/tag_login.jpg?raw=true">
  
  • Login thành công và push image bằng lệnh `docker push hai19110356/lightsail`
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/push.jpg?raw=true">
  
 Sau khi push image lên Docker Hub thành công, tiến hành kiểm tra Repository đã được đẩy lên hay chưa.
 
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/dockerhub.jpg?raw=true">
 
 ## Tạo Container Service
  • Quay trở lại giao diện Lightsail console. Click vào tab Container. Click Create container service.
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/createcontainer.jpg?raw=true">
  
  • Chọn một vị trí cho dịch vụ container của bạn bằng cách chọn một AWS Region gần bạn hoặc gần khách hàng của bạn. Đối với lab này, chúng ta sẽ sử dụng Region Singapore. Kéo màn hình xuống dưới, đặt tên cho dịch vụ container của bạn là lightsail sau đó click Create container service.
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/name.jpg?raw=true">
  
Sẽ mất vài phút để quá trình tạo dịch vụ container hoàn tất và trạng thái chuyển sang Ready. Bước tiếp theo chúng ta sẽ thực hiện triển khai một deployment từ 1 container image lấy từ public repo ( kho lưu trữ công cộng).

## Deploy
  • Click vào tab Deployments và chọn Create your first deployment.
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/deploy.jpg?raw=true">
  
  • Đặt các thông số Container theo mẫu dưới.
  
  <img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/thongso1.jpg?raw=true">
  
Sau khi deploy, cần đợi vài phút để xử lí.

<img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/after.jpg?raw=true">

Đợi vài phút ...

<img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/deploying.jpg?raw=true">

Sau khi đã xong, chúng ta có thể truy cập Public domain để đến trang web của ta đã deploy.

<img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/running.jpg?raw=true">

Trang web Pulic Domain sau khi đã Deploy Image hoàn thành.

<img src="https://github.com/ThaiHaiDev/AWS-Lightsail/blob/main/Images/demo.jpg?raw=true">


  
# Tài liệu tham khảo

https://aws.amazon.com

