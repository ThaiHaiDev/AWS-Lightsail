# Mean
Ngăn xếp dành cho nhà phát triển Mean: Mean Stack là sự kết hợp giữa của MongoDB, ExpressJS, AngularJS, NodeJS và khiến cho việc xây dựng những ứng dụng web trở nên mạnh mẽ và đơn giản hơn bao giờ hết.

<img src="https://github.com/ThaiHaiDev/Mean/blob/main/Images/bandicam%202021-12-03%2017-01-26-743.jpg?raw=true">

# Các bước thực hiện
  • Tiến hành Create Instance trong Lightsail AWS. 
  
  db = db.getSiblingDB('GROUP22')
  
  db.createUser( { user : "mean", pwd : "admin", roles : [ "readWrite", "dbAdmin" ]} )
  
  DATABASE_PATH=mongodb://mean:admin@172.0.0.1:27017/GROUP22
  
  SECRET_KEY=thisissecret
  
  npm install -g forever
  
  forever start index.js
  
  forever start -c "npm start:production" ./
  
  npm install o MEAN
  
  172.26.15.127
