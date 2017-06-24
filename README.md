# Food Delivery Application 

## Dependencies
	pom.xml
## REST_API Design
### Resource Restaurant

```bash
POST	/localhost/restaurants
POST all restaurant
GET 	/localhost/restaurants	
GET all restaurant
GET 	/localhost/restaurants/{restaurant}
GET a particular restaurant 
DELETE /localhost/restaurants/{restaurant}
DELETE a particular restaurant
```
### Resource Menu

```bash
POST 	/localhost/restaurants/{restaurant}/menu
POST the menu for particular restaurant
GET 	/localhost/restaurants/{restaurant}/menu
GET the full menu
Response:
{
	food,
	price
}
```

### Resource User

```bash
POST 	/localhost/users
POST users
GET 	/localhost/users/{userId}
```

### Resource Order

```bash
POST 	/localhost/users/{userId}/orders
POST a order
Require:
{
	restaurant,
	foodItem,
	quantity,
	note,
	deliveryAddress
}
GET 	/localhost/users/{userId}/orders/{orderId}
GET a order
Response:
{
	orderId,
	foodItem,
	quantity,
	price,
	orderTime,
	orderStatus,
	orderStatus	
}
POST 	/localhost/users/{userId}/orders/{orderId}/pay
POST a payment
Request:
{
	creditCardNumber,
	expireDate,
	securityCode
}
GET 	/localhost/users/{userId}/orders/{orderId}/pay/{paymentId}
Response:
{
	paymentID,
	timestamp,
	estimateTime,
	orderId,
	orderStatus,
	userId
}
```