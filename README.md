﻿# hotel-backend
 
 
## Installation
- Clone or download then extract, open the project on your code editor. Open the terminal in your code editor and type npm install then   enter. Here I use the Visual Code Editor 
- For database settings, type http://localhost/phpmyadmin/ in your browser. create the db_si_hotel database and import the database in     the project folder. I use Mysql
- The final step is to type npm start in your project terminal.

## Built With

- [Express JS](https://expressjs.com) - Back-end
- [MySQL](https://www.mysql.com) - Database
- [istanbul nyc](https://www.istanbul.js.org) - Code coverage
 
##Endpoint
 
 ### `Get all Room Types`
Method GET<br /> 
http://localhost:7000/api/v1/room_categories

 ### `Get Room Info`
Method GET<br /> 
http://localhost:7000/api/v1/rooms

 ### `Get Room Info By ID Room`
Method GET<br /> 
http://localhost:7000/api/v1/room/:id
example : http://localhost:7000/api/v1/room/1

 ### `Get User By ID User`
Method GET<br /> 
http://localhost:7000/api/v1/user/:id
example : http://localhost:7000/api/v1/user/1

### `Get Reservation data By ID User`
Method GET<br /> 
http://localhost:7000/api/v1/order/:id/user
example : http://localhost:7000/api/v1/order/1/user

### `Post payment for hotels that have been booked by the user`
Method POST<br /> 
http://localhost:7000/api/v1/order/payment
example for request body :
{
  "order_id":"1",
	"id_customer":"1",
	"jml_bayar":"500000",
	"nm_bank":"Mandiri",
	"no_rek":"121212121",
	"attachment":"bukti_pembayaran.png"
}
example for output response body : 
{
    "success": true,
    "data": {
        "order_id": "1",
        "id_customer": "1",
        "jml_bayar": "500000",
        "nm_bank": "Mandiri",
        "no_rek": "121212121",
        "attachment": "bukti_pembayaran.png"
    }
}

### `Create hotel booking data from user`
Method POST<br /> 
http://localhost:7000/api/v1/orders
example for request body :
{
	"order_date":"2020-02-12 14:00:00",
	"payment_deadline":"2020-02-12 14:30:00",
	"room_id":"2",
	"jml_order_room":"1",
	"id_customer":"1",
	"check_in":"2020-02-12 14:00:00",
	"check_out":"2020-02-13 14:00:00",
	"total_bayar":"1000000"
}
example for output response body :
{
    "success": true,
    "data": {
        "order_date": "2020-02-12 14:00:00",
        "payment_deadline": "2020-02-12 14:30:00",
        "room_id": "2",
        "jml_order_room": "1",
        "id_customer": "1",
        "check_in": "2020-02-12 14:00:00",
        "check_out": "2020-02-13 14:00:00",
        "total_bayar": "1000000"
    }
}

### `Payment confirmation status update`
Method PUT<br /> 
http://localhost:7000/api/v1/order/:id
example : http://localhost:7000/api/v1/order/2

### `Get financial statements`
Method GET<br /> 
http://localhost:7000/api/v1/report
