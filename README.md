# Mean
Ngăn xếp dành cho nhà phát triển Mean: Mean Stack là sự kết hợp giữa của MongoDB, ExpressJS, AngularJS, NodeJS và khiến cho việc xây dựng những ứng dụng web trở nên mạnh mẽ và đơn giản hơn bao giờ hết.

<img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-03%2017-01-26-743.jpg?raw=true">

# Các bước thực hiện
  ## Tiến hành Create Instance trong Lightsail AWS
  • Chọn Stack Mean và đặt tên instance lại nếu cần. Sau đó chọn Create Instance. Đợi 1 vài phút để AWS có thể tạo và running.
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2010-25-33-075.jpg?raw=true" >
  
  ## Lấy Password Mean
  • Mở connect bitnami trong Stack Mean vừa tạo, gõ lệnh ls để xem các thành phần, sẽ có mục bitnami_application_password để chúng ta lấy password. Để lấy password của Mean, gõ lệnh `cat bitnami_application_password` 
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2010-29-38-872.jpg?raw=true">
  
  ## Clone các project github
  • Clone 2 project từ github về gồm Front-End và Back-End để thực hiện cài đặt app React. Sau khi clone xong, sử dụng lệnh `ls` để xem đã có mục phần đó hay chưa.
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2010-42-52-360.jpg?raw=true">
  
  ## Tạo Database Mongodb
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
  
  ## Chỉnh sửa cấu hình Folder customerManagement_MERN
  
  • Truy cập Folder customerManagement_MERN và mở file index.js để chỉnh sửa bằng lệnh:
  
  `cd customerManagement_MERN`
  
  `vim index.js`
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2011-06-00-597.jpg?raw=true">
  
  • Thực hiện chỉnh sửa file index.js theo như trong hình.
  
  <img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-13%2011-06-00-597.jpg?raw=true">
  
  Sau đó
  
  DATABASE_PATH=mongodb://mean:admin@172.0.0.1:27017/GROUP22
  
  SECRET_KEY=thisissecret
  
  npm install -g forever
  
  forever start index.js
  
  forever start -c "npm start:production" ./
  
  npm install o MEAN
  
  172.26.15.127
