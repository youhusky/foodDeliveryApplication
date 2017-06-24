# Food Delivery Application 

## Dependencies
	pom.xml
	
## Architecture Design
![fooddeliveryservice](https://user-images.githubusercontent.com/10191895/27505768-f13bb228-585c-11e7-9281-0a56cfa869c5.jpg)

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
## Project Structure
	Seen in Github folder
## Test Cases
	Seen in uploadTest.json
	
## Explanations
1. Start the whole server user, restaurant and post the information 
2. There are two databases order and payment
3. When customers post the order, it will store all information in the order database and it will go into the payment server. Payment server read the data from the order databases and store the payment data into the payment databases