
# Orders -  
Alla orders

`http://localhost:8080/api/orders`


### Headers
```
authorization: "eafyasd..." // Värdet ska vara den token man får när man loggar in 
```
### Returns 
* Successful Response
```
   success: true,
    message: 'Orders found.',
    status: 200,
    orders: [...]
```

## GET - 
**Endast inloggade användare kan göra detta.**

`http://localhost:8080/orders/history`


Hämtar orderhistorik för den autentiserade användaren.

### Headers
```
authorization: "eafyasd..." // Värdet ska vara den token man får när man loggar in 
```

### Returns
* Successful Response
```
    success: true,
    message: 'Orders found.',
    status: 200,
    orders: [...]
```

## GET - 

`http://localhost:8080/orders/:orderId`

/api/orders/:orderId
Hämtar specifik order

### Headers
```
authorization: "eafyasd..." // Värdet ska vara den token man får när man loggar in 
```
* Successful Response
```
    success: true,
    message: 'Order found.',
    status: 200,
    order: {...}
```

## GET - 

/api/orders/:orderId/place
Placerar ordern vars orderId stämmer överens .

>* `orderId` måste finnas som parameter.
>* `userId` behöver finnas med om det existerar och stämmer överens med det userId som finns på ordern.

### Req.headers
```
    authorization: "eafyasd..." // Värdet ska vara den token man får när man loggar in 
```

### Req.body
```
    orderId: string,
    amount?: number
```
### Returns
* Successful Response
```
    success: true,
    message: 'Product successfully removed from order.',
    status: 200,
    order: {...},
    removedProduct: {...}
```

## GET - 

`http://localhost:8080/orders/:orderId/estimatedTimeLeft`


**Man måste vara inloggad, om ordern placerades av en inloggad användare.**

Hämtar information om resterande tid av beställning.

>* `orderId` måste finnas som parameter.
>* `userId` behöver finnas med om det existerar och stämmer överens med det userId som finns på ordern.
>* `orderIsPlaced` måste vara `true` om den ska kunna dyka upp här med data.

### Req.headers
```
    authorization: "eafyasd..." // Värdet ska vara den token man får när man loggar in, om man var inloggad när man la beställningen. 
```

### Req.body
```
    orderId: string
```
### Returns
* Successful Response - Inte klar än
```
    success: true,
    message: 'Uppskattad återstående tid: ${minutes} minuter och ${seconds} sekunder',
    status: 200,
    time: {
        minutes: 10 //Antal minuter
        seconds: 5 //Antal sekunder
    }
```
* Successful Response - Efter tiden har gått ut
```
    success: true,
    message: 'Kaffet ska ha levererats nu, enligt vårt supersäkra system! Coolt va?',
    status: 200,
```

## POST - `/api/orders/:productId`

Lägger till en produkt i användarens aktiva beställning.
>* Om man inte har en `token` så behöver man fylla i `orderId`.  
>* Om du är inloggad och har en `token` så ***behövs inte*** `orderId`, utan den parametern kan vara tom. Men ha som regel att ha den ifylld om det känns mest tryggt. 
>* `orderId` får du efter första varan är lagd i kundkorgen.
>* `amount` är valfritt att ha med. 
>>* Om `amount` inte finns med som parameter:  `amount = 1`
>>* Om `amount` har ett negativt, eller 0, som värde: `amount = 1`

### Req.headers
```
authorization: "eafyasd..." // Värdet ska vara den token man får när man loggar in 
```

### Req.body
```
    orderId?: string,
    amount?: number
```
### Req.params
```
    productId: string,
```

### Returns

* Successful Response
```
    success: true,
    message: 'Product successfully added to order. Dont forget to add "orderId" inside body if this is a guest.',
    status: 200,
    order: {...},
    addedProduct: {...}
```

## POST - `/api/orders/discount/:discountId`

Lägger till ett kampanjerbjudande i användarens aktiva beställning.
>* Om man inte har en `token` så behöver man fylla i `orderId`.  
>* Om du är inloggad och har en `token` så ***behövs inte*** `orderId`, utan den parametern kan vara tom. Men ha som regel att ha den ifylld om det känns mest tryggt. 
>* `orderId` får du efter första varan är lagd i kundkorgen.

**Kom ihåg att man inte behöver göra detta. Om man placerar varor som blir ett kampanj-erbjudande så kommer det att automatiskt adderas till ordern.**

### Req.headers
```
authorization: "eafyasd..." // Värdet ska vara den token man får när man loggar in 
```

### Req.body
```
    orderId?: string,
```
### Req.params
```
    discountId: string,
```

### Returns

* Successful Response
```
    success: true,
    message: 'Discount successfully added to order. Dont forget to add "orderId" inside body if this is a guest.',
    status: 200,
    order: {...},
    addedProduct: {...}
```

## DELETE - `/api/orders/:productId`
Tar bort en produkt i användarens aktiva beställning.
>* `orderId` Måste finnas som parameter.
>* Om man inte loggat in innan, när man börjat plocka produkter, utan gör det senare och fortsätter lägga i varor i kundkorgen, så kopplas `userId` till kundkorgen hädanefter. 
>* Om ett `userId` redan finns kopplat till ordern och man loggar ut, alternativt är inloggad på någon annan, och försöker ta bort varor från korgen så kommer detta inte gå. Därefter, när ett userId är kopplat till en order så kan det inte ändras eller kommas åt av varken gäst eller annan användare.
>* `amount` är valfri att ha med. 
>>* Om `amount` inte finns med som parameter:  `amount = 1`
>>* Om `amount` har ett negativt, eller 0, som värde: `amount = 1`  

### Req.headers
```
authorization: "eafyasd..." // Värdet ska vara den token man får när man loggar in 
```

### Req.body
```
    orderId: string,
    amount?: number
```
### Returns
* Successful Response
```
    success: true,
    message: 'Product successfully removed from order.',
    status: 200,
    order: {...},
    removedProduct: {...}
```

